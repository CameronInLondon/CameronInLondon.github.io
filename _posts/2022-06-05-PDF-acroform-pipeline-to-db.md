# PDF Acroforms Extracting Data to Database using Python

## Introduction
In todays post I am going to show you how to build a datapipline that pulls data from a PDF form, reshapes that data and inserts into a database. This will be done using Python and a SQLite database. Why would you want to do this? Well there are thousands of business and governments that still rely on PDF forms as a means to collecting data. PDF forms are quick and easy to produce, without the need for a developer, and give a flexibility and agility to companies. Clearly there are a number of downside of PDF forms, for one they do not scale the way an online form does.

## PDF forms

I should at this point say there are two types of PDF form out there. XFA and Acroforms, XFA is an Adobe format which has been dropped from the PDF 2.0 specification so we will not be talking about this. We are referring to Acroforms, these can be made using a number of different PDF writers including:

- PDFelement Pro (Mac & Windows) ...
- Foxit PDF Editor (Mac & Windows) ...
- PDF Studio (Mac, Windows & Linux) ...
- Nitro PDF Pro (Windows only) ...
- Adobe Acrobat DC (Mac & Windows)
- and many more

For this demo I will be using MS Word and Acrobat Pro to make a simple form with three fields. By adding the field names with lines next to them in Word and saving to a PDF you have already done half the job. Opening the PDF in Acrobat and click the Prepare Form button. This gives you the option to automate the form field production in Acrobat, while this automation is far from perfect it does the job for basic forms. Should you want to use dropdowns fields then they will have to be added by hand. The field names are important as we will need them later.

## Importing libraries

For debugging we will use trackback and sys. For viewing the data json is helpful. Pandas will be used for viewing the table in the database. PDFminer will be used for extracting the text from the PDF. OS, pathlib and glob will all help when working with the operating system.

```python
import traceback
import sys
import json
import sqlite3
import pandas as pd
from pdfminer.pdfparser import PDFParser
from pdfminer.pdfdocument import PDFDocument
from pdfminer.pdftypes import resolve1
from pdfminer.psparser import PSLiteral, PSKeyword
from pdfminer.utils import decode_text
import os
from pathlib import Path
from glob import iglob
```

## PDFMiner

The code for using PDFMiner to extract the field text can be taken from the docs [here](https://pdfminersix.readthedocs.io/en/develop/howto/acro_forms.html). The two functions below do most of the work and return a list of dictionaries. I have added a list at the bottom for loop, this will allow multiple forms to be processed.

```python
def decode_value(value):
    # decode PSLiteral, PSKeyword
    if isinstance(value, (PSLiteral, PSKeyword)):
        value = value.name
    # decode bytes
    if isinstance(value, bytes):
        value = decode_text(value)
    return value


def extract_pdf_text(the_path):
    with open(the_path, 'rb') as fp:
        parser = PDFParser(fp)

        doc = PDFDocument(parser)
        res = resolve1(doc.catalog)

        if 'AcroForm' not in res:
            raise ValueError("No AcroForm Found")

        fields = resolve1(doc.catalog['AcroForm'])['Fields']  # may need further resolving

        # print file name
        # p = Path(the_path)
        # print(f'Form name# {p.stem}')
        data = {}
        for f in fields:
            # extract normal text
            # text = extract_text(file_path)
            # print(text)

            field = resolve1(f)
            name, values = field.get('T'), field.get('V')
            # decode name
            name = decode_text(name)
            # replace two spaces with one, then replace space with underscore
            name = name.replace("  ", " ").replace(" ", "_")
            # resolve indirect obj
            values = resolve1(values)
            # decode value(s)
            if isinstance(values, list):
                values = [decode_value(v) for v in values]
            else:
                values = decode_value(values)

            data.update({name: values})

        list_of_nested_dicts.append(data)
        return list_of_nested_dicts
```

## Differing forms

Now one problem you might have is if there are different versions of a forms which have differing fields. You can have extra fields in the database to cover a range of form senarios but when using SQLs VALUES function you will get a bindings error e.g. ```SQLite error: You did not supply a value for binding X``` if you do not push all the fields as per the SQL INSERT Query. One solution to this problem is to have multiple queries, but a more elegant solution is to handle this in Python by fill any blank fields with nulls. The below code will do this for us. I used list while iterating the dictionary to avoid the ```RuntimeError: dictionary changed size during iteration```.

```python
def standardise_details_dict():
    """standardise the the details key values to DB schema.
        If PDF forms have differing fields this prevents error when inserting into DB.
        Note this only adds missing values, it does NOT update current values.
    """
    defaults2 = {
        'Field_1': None,
        'Field_2': None,
        'Field_3': None,
    }

    # loop through list of dicts. Each dicts is a paper.
    for form in list_of_nested_dicts:
        # extract from dict key, values
        for dic_k, dic_v in list(form.items()):
            # extract key values from the default dict
            for def_k, def_v in defaults2.items():
                # add to dict if there are empty fields
                form.setdefault(def_k, defaults2[def_k])
```

## SQL query

Next up is the function that creates the database and inserts the content. For this blog I have gone with a simple one table solution but in reality you might want to have extra tables with more fields. I am making sure the rows are unique by concatenating all the fields into a new field called ```DetailKey```. If you are not familiar with SQLite you have to use the ```PRAGMA foreign_keys = 1``` when adding a foreign key constrain to the database. More information [here.](https://www.sqlite.org/foreignkeys.html)

```python
def create_and_insert_db(db_path):
    """create tables in DB
    Insert content in DB
    """

    conn = sqlite3.connect(db_path)
    conn.execute("PRAGMA foreign_keys = 0")  # only needed if you have more than one table
    conn.commit()
    cursor = conn.cursor()

    cursor.execute('''CREATE TABLE IF NOT EXISTS detail(
                    DetailID INTEGER PRIMARY KEY AUTOINCREMENT,
                    Field_1 TEXT,
                    Field_2 TEXT,
                    Field_3 TEXT,
                    DetailKey TEXT GENERATED ALWAYS AS (IFNULL(Field_1, '') || IFNULL(Field_2, '') || IFNULL(Field_3, '')),
                    unique (DetailKey)
                    )''')
    conn.commit()

    for form in list_of_nested_dicts:  # iterate one form at a time.
        try:
            cursor.execute('''INSERT INTO detail(
                                Field_1,
                                Field_2,
                                Field_3)
                            VALUES (
                                :Field_1,
                                :Field_2,
                                :Field_3
                                );''', form)
        except sqlite3.Error as er:
            error_msg(er)

    conn.commit()
```

## Loop through PDF files in folder

The final function is used to iterate through the PDF files within a folder using glob and the excellent pathlib Path class.

```python
def loop_files():
    """loop through all PDF files in the folder"""
    for i in iglob(folder_path + '\*'):
        print(i)
        if Path(i).suffix == '.pdf':
            extract_pdf_text(i)
```

## Running the code

Below is the main block which calls the functions. ```json.dumps``` is a nice way to print dictionaries which is helpful when debugging. I used pandas to query the database to make sure the data inserted correctly.

```python
if __name__ == "__main__":
    loop_files()
    standardise_details_dict()
    print(json.dumps(list_of_nested_dicts, sort_keys=True, indent=4))
    db_path = (os.path.join(os.getcwd(), r'Blog\2022-06-05-PDF-acroform-pipeline-to-db\PDF-acroform-pipeline-to-db.db'))
    print(db_path)
    print('---------------')
    create_and_insert_db(db_path)
    
    # check DB
    conn = sqlite3.connect(db_path)
    print(pd.read_sql_query("SELECT * FROM detail LIMIT 20", conn))
    print('------------------')
    conn.close()
```
You can grab the script from [here.](https://github.com/CameronInLondon/PDF_acroform_pipeline_to_DB/blob/main/2022-06-05-PDF-acroform-pipeline-to-db.py)

So that is all for today. Hope you enjoyed.