

<html>
<head><meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>visulisations_in_pandas</title><script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>



<style type="text/css">
    pre { line-height: 125%; }
td.linenos pre { color: #000000; background-color: #f0f0f0; padding-left: 5px; padding-right: 5px; }
span.linenos { color: #000000; background-color: #f0f0f0; padding-left: 5px; padding-right: 5px; }
td.linenos pre.special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
span.linenos.special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
.highlight .hll { background-color: var(--jp-cell-editor-active-background) }
.highlight { background: var(--jp-cell-editor-background); color: var(--jp-mirror-editor-variable-color) }
.highlight .c { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment */
.highlight .err { color: var(--jp-mirror-editor-error-color) } /* Error */
.highlight .k { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword */
.highlight .o { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator */
.highlight .p { color: var(--jp-mirror-editor-punctuation-color) } /* Punctuation */
.highlight .ch { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Multiline */
.highlight .cp { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Preproc */
.highlight .cpf { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Single */
.highlight .cs { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Special */
.highlight .kc { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Pseudo */
.highlight .kr { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Type */
.highlight .m { color: var(--jp-mirror-editor-number-color) } /* Literal.Number */
.highlight .s { color: var(--jp-mirror-editor-string-color) } /* Literal.String */
.highlight .ow { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator.Word */
.highlight .w { color: var(--jp-mirror-editor-variable-color) } /* Text.Whitespace */
.highlight .mb { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Bin */
.highlight .mf { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Float */
.highlight .mh { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Hex */
.highlight .mi { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer */
.highlight .mo { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Oct */
.highlight .sa { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Affix */
.highlight .sb { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Backtick */
.highlight .sc { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Char */
.highlight .dl { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Delimiter */
.highlight .sd { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Doc */
.highlight .s2 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Double */
.highlight .se { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Escape */
.highlight .sh { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Heredoc */
.highlight .si { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Interpol */
.highlight .sx { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Other */
.highlight .sr { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Regex */
.highlight .s1 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Single */
.highlight .ss { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Symbol */
.highlight .il { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer.Long */
  </style>



<style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
 * Mozilla scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */
[data-jp-theme-scrollbars='true'] {
  scrollbar-color: rgb(var(--jp-scrollbar-thumb-color))
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar. These selectors
 * will match lower in the tree, and so will override the above */
[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
}

/*
 * Webkit scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar,
[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-corner {
  background: var(--jp-scrollbar-background-color);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-thumb {
  background: rgb(var(--jp-scrollbar-thumb-color));
  border: var(--jp-scrollbar-thumb-margin) solid transparent;
  background-clip: content-box;
  border-radius: var(--jp-scrollbar-thumb-radius);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-track:horizontal {
  border-left: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
  border-right: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-track:vertical {
  border-top: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
  border-bottom: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar */

[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar::-webkit-scrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar::-webkit-scrollbar,
[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-corner,
[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-corner {
  background-color: transparent;
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-thumb,
[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-thumb {
  background: rgba(var(--jp-scrollbar-thumb-color), 0.5);
  border: var(--jp-scrollbar-thumb-margin) solid transparent;
  background-clip: content-box;
  border-radius: var(--jp-scrollbar-thumb-radius);
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-track:horizontal {
  border-left: var(--jp-scrollbar-endpad) solid transparent;
  border-right: var(--jp-scrollbar-endpad) solid transparent;
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-track:vertical {
  border-top: var(--jp-scrollbar-endpad) solid transparent;
  border-bottom: var(--jp-scrollbar-endpad) solid transparent;
}

/*
 * Phosphor
 */

.lm-ScrollBar[data-orientation='horizontal'] {
  min-height: 16px;
  max-height: 16px;
  min-width: 45px;
  border-top: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] {
  min-width: 16px;
  max-width: 16px;
  min-height: 45px;
  border-left: 1px solid #a0a0a0;
}

.lm-ScrollBar-button {
  background-color: #f0f0f0;
  background-position: center center;
  min-height: 15px;
  max-height: 15px;
  min-width: 15px;
  max-width: 15px;
}

.lm-ScrollBar-button:hover {
  background-color: #dadada;
}

.lm-ScrollBar-button.lm-mod-active {
  background-color: #cdcdcd;
}

.lm-ScrollBar-track {
  background: #f0f0f0;
}

.lm-ScrollBar-thumb {
  background: #cdcdcd;
}

.lm-ScrollBar-thumb:hover {
  background: #bababa;
}

.lm-ScrollBar-thumb.lm-mod-active {
  background: #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal'] .lm-ScrollBar-thumb {
  height: 100%;
  min-width: 15px;
  border-left: 1px solid #a0a0a0;
  border-right: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] .lm-ScrollBar-thumb {
  width: 100%;
  min-height: 15px;
  border-top: 1px solid #a0a0a0;
  border-bottom: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-left);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-right);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-up);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-down);
  background-size: 17px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-Widget, /* </DEPRECATED> */
.lm-Widget {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  cursor: default;
}


/* <DEPRECATED> */ .p-Widget.p-mod-hidden, /* </DEPRECATED> */
.lm-Widget.lm-mod-hidden {
  display: none !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-CommandPalette, /* </DEPRECATED> */
.lm-CommandPalette {
  display: flex;
  flex-direction: column;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-CommandPalette-search, /* </DEPRECATED> */
.lm-CommandPalette-search {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-content, /* </DEPRECATED> */
.lm-CommandPalette-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  min-height: 0;
  overflow: auto;
  list-style-type: none;
}


/* <DEPRECATED> */ .p-CommandPalette-header, /* </DEPRECATED> */
.lm-CommandPalette-header {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}


/* <DEPRECATED> */ .p-CommandPalette-item, /* </DEPRECATED> */
.lm-CommandPalette-item {
  display: flex;
  flex-direction: row;
}


/* <DEPRECATED> */ .p-CommandPalette-itemIcon, /* </DEPRECATED> */
.lm-CommandPalette-itemIcon {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-itemContent, /* </DEPRECATED> */
.lm-CommandPalette-itemContent {
  flex: 1 1 auto;
  overflow: hidden;
}


/* <DEPRECATED> */ .p-CommandPalette-itemShortcut, /* </DEPRECATED> */
.lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-itemLabel, /* </DEPRECATED> */
.lm-CommandPalette-itemLabel {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-DockPanel, /* </DEPRECATED> */
.lm-DockPanel {
  z-index: 0;
}


/* <DEPRECATED> */ .p-DockPanel-widget, /* </DEPRECATED> */
.lm-DockPanel-widget {
  z-index: 0;
}


/* <DEPRECATED> */ .p-DockPanel-tabBar, /* </DEPRECATED> */
.lm-DockPanel-tabBar {
  z-index: 1;
}


/* <DEPRECATED> */ .p-DockPanel-handle, /* </DEPRECATED> */
.lm-DockPanel-handle {
  z-index: 2;
}


/* <DEPRECATED> */ .p-DockPanel-handle.p-mod-hidden, /* </DEPRECATED> */
.lm-DockPanel-handle.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-DockPanel-handle:after, /* </DEPRECATED> */
.lm-DockPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='horizontal'],
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='horizontal'] {
  cursor: ew-resize;
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='vertical'],
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='vertical'] {
  cursor: ns-resize;
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='horizontal']:after,
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='horizontal']:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='vertical']:after,
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='vertical']:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}


/* <DEPRECATED> */ .p-DockPanel-overlay, /* </DEPRECATED> */
.lm-DockPanel-overlay {
  z-index: 3;
  box-sizing: border-box;
  pointer-events: none;
}


/* <DEPRECATED> */ .p-DockPanel-overlay.p-mod-hidden, /* </DEPRECATED> */
.lm-DockPanel-overlay.lm-mod-hidden {
  display: none !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-Menu, /* </DEPRECATED> */
.lm-Menu {
  z-index: 10000;
  position: absolute;
  white-space: nowrap;
  overflow-x: hidden;
  overflow-y: auto;
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-Menu-content, /* </DEPRECATED> */
.lm-Menu-content {
  margin: 0;
  padding: 0;
  display: table;
  list-style-type: none;
}


/* <DEPRECATED> */ .p-Menu-item, /* </DEPRECATED> */
.lm-Menu-item {
  display: table-row;
}


/* <DEPRECATED> */
.p-Menu-item.p-mod-hidden,
.p-Menu-item.p-mod-collapsed,
/* </DEPRECATED> */
.lm-Menu-item.lm-mod-hidden,
.lm-Menu-item.lm-mod-collapsed {
  display: none !important;
}


/* <DEPRECATED> */
.p-Menu-itemIcon,
.p-Menu-itemSubmenuIcon,
/* </DEPRECATED> */
.lm-Menu-itemIcon,
.lm-Menu-itemSubmenuIcon {
  display: table-cell;
  text-align: center;
}


/* <DEPRECATED> */ .p-Menu-itemLabel, /* </DEPRECATED> */
.lm-Menu-itemLabel {
  display: table-cell;
  text-align: left;
}


/* <DEPRECATED> */ .p-Menu-itemShortcut, /* </DEPRECATED> */
.lm-Menu-itemShortcut {
  display: table-cell;
  text-align: right;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-MenuBar, /* </DEPRECATED> */
.lm-MenuBar {
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-MenuBar-content, /* </DEPRECATED> */
.lm-MenuBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: row;
  list-style-type: none;
}


/* <DEPRECATED> */ .p--MenuBar-item, /* </DEPRECATED> */
.lm-MenuBar-item {
  box-sizing: border-box;
}


/* <DEPRECATED> */
.p-MenuBar-itemIcon,
.p-MenuBar-itemLabel,
/* </DEPRECATED> */
.lm-MenuBar-itemIcon,
.lm-MenuBar-itemLabel {
  display: inline-block;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-ScrollBar, /* </DEPRECATED> */
.lm-ScrollBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */
.p-ScrollBar[data-orientation='horizontal'],
/* </DEPRECATED> */
.lm-ScrollBar[data-orientation='horizontal'] {
  flex-direction: row;
}


/* <DEPRECATED> */
.p-ScrollBar[data-orientation='vertical'],
/* </DEPRECATED> */
.lm-ScrollBar[data-orientation='vertical'] {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-ScrollBar-button, /* </DEPRECATED> */
.lm-ScrollBar-button {
  box-sizing: border-box;
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-ScrollBar-track, /* </DEPRECATED> */
.lm-ScrollBar-track {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  flex: 1 1 auto;
}


/* <DEPRECATED> */ .p-ScrollBar-thumb, /* </DEPRECATED> */
.lm-ScrollBar-thumb {
  box-sizing: border-box;
  position: absolute;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-SplitPanel-child, /* </DEPRECATED> */
.lm-SplitPanel-child {
  z-index: 0;
}


/* <DEPRECATED> */ .p-SplitPanel-handle, /* </DEPRECATED> */
.lm-SplitPanel-handle {
  z-index: 1;
}


/* <DEPRECATED> */ .p-SplitPanel-handle.p-mod-hidden, /* </DEPRECATED> */
.lm-SplitPanel-handle.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-SplitPanel-handle:after, /* </DEPRECATED> */
.lm-SplitPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='horizontal'] > .p-SplitPanel-handle,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle {
  cursor: ew-resize;
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='vertical'] > .p-SplitPanel-handle,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle {
  cursor: ns-resize;
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='horizontal'] > .p-SplitPanel-handle:after,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='vertical'] > .p-SplitPanel-handle:after,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-TabBar, /* </DEPRECATED> */
.lm-TabBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-TabBar[data-orientation='horizontal'], /* </DEPRECATED> */
.lm-TabBar[data-orientation='horizontal'] {
  flex-direction: row;
}


/* <DEPRECATED> */ .p-TabBar[data-orientation='vertical'], /* </DEPRECATED> */
.lm-TabBar[data-orientation='vertical'] {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-TabBar-content, /* </DEPRECATED> */
.lm-TabBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex: 1 1 auto;
  list-style-type: none;
}


/* <DEPRECATED> */
.p-TabBar[data-orientation='horizontal'] > .p-TabBar-content,
/* </DEPRECATED> */
.lm-TabBar[data-orientation='horizontal'] > .lm-TabBar-content {
  flex-direction: row;
}


/* <DEPRECATED> */
.p-TabBar[data-orientation='vertical'] > .p-TabBar-content,
/* </DEPRECATED> */
.lm-TabBar[data-orientation='vertical'] > .lm-TabBar-content {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-TabBar-tab, /* </DEPRECATED> */
.lm-TabBar-tab {
  display: flex;
  flex-direction: row;
  box-sizing: border-box;
  overflow: hidden;
}


/* <DEPRECATED> */
.p-TabBar-tabIcon,
.p-TabBar-tabCloseIcon,
/* </DEPRECATED> */
.lm-TabBar-tabIcon,
.lm-TabBar-tabCloseIcon {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-TabBar-tabLabel, /* </DEPRECATED> */
.lm-TabBar-tabLabel {
  flex: 1 1 auto;
  overflow: hidden;
  white-space: nowrap;
}


/* <DEPRECATED> */ .p-TabBar-tab.p-mod-hidden, /* </DEPRECATED> */
.lm-TabBar-tab.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-TabBar.p-mod-dragging .p-TabBar-tab, /* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging .lm-TabBar-tab {
  position: relative;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging[data-orientation='horizontal'] .p-TabBar-tab,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging[data-orientation='horizontal'] .lm-TabBar-tab {
  left: 0;
  transition: left 150ms ease;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging[data-orientation='vertical'] .p-TabBar-tab,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging[data-orientation='vertical'] .lm-TabBar-tab {
  top: 0;
  transition: top 150ms ease;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging .p-TabBar-tab.p-mod-dragging
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging .lm-TabBar-tab.lm-mod-dragging {
  transition: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-TabPanel-tabBar, /* </DEPRECATED> */
.lm-TabPanel-tabBar {
  z-index: 1;
}


/* <DEPRECATED> */ .p-TabPanel-stackedPanel, /* </DEPRECATED> */
.lm-TabPanel-stackedPanel {
  z-index: 0;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

@charset "UTF-8";
/*!

Copyright 2015-present Palantir Technologies, Inc. All rights reserved.
Licensed under the Apache License, Version 2.0.

*/
html{
  -webkit-box-sizing:border-box;
          box-sizing:border-box; }

*,
*::before,
*::after{
  -webkit-box-sizing:inherit;
          box-sizing:inherit; }

body{
  text-transform:none;
  line-height:1.28581;
  letter-spacing:0;
  font-size:14px;
  font-weight:400;
  color:#182026;
  font-family:-apple-system, "BlinkMacSystemFont", "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Open Sans", "Helvetica Neue", "Icons16", sans-serif; }

p{
  margin-top:0;
  margin-bottom:10px; }

small{
  font-size:12px; }

strong{
  font-weight:600; }

::-moz-selection{
  background:rgba(125, 188, 255, 0.6); }

::selection{
  background:rgba(125, 188, 255, 0.6); }
.bp3-heading{
  color:#182026;
  font-weight:600;
  margin:0 0 10px;
  padding:0; }
  .bp3-dark .bp3-heading{
    color:#f5f8fa; }

h1.bp3-heading, .bp3-running-text h1{
  line-height:40px;
  font-size:36px; }

h2.bp3-heading, .bp3-running-text h2{
  line-height:32px;
  font-size:28px; }

h3.bp3-heading, .bp3-running-text h3{
  line-height:25px;
  font-size:22px; }

h4.bp3-heading, .bp3-running-text h4{
  line-height:21px;
  font-size:18px; }

h5.bp3-heading, .bp3-running-text h5{
  line-height:19px;
  font-size:16px; }

h6.bp3-heading, .bp3-running-text h6{
  line-height:16px;
  font-size:14px; }
.bp3-ui-text{
  text-transform:none;
  line-height:1.28581;
  letter-spacing:0;
  font-size:14px;
  font-weight:400; }

.bp3-monospace-text{
  text-transform:none;
  font-family:monospace; }

.bp3-text-muted{
  color:#5c7080; }
  .bp3-dark .bp3-text-muted{
    color:#a7b6c2; }

.bp3-text-disabled{
  color:rgba(92, 112, 128, 0.6); }
  .bp3-dark .bp3-text-disabled{
    color:rgba(167, 182, 194, 0.6); }

.bp3-text-overflow-ellipsis{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal; }
.bp3-running-text{
  line-height:1.5;
  font-size:14px; }
  .bp3-running-text h1{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h1{
      color:#f5f8fa; }
  .bp3-running-text h2{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h2{
      color:#f5f8fa; }
  .bp3-running-text h3{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h3{
      color:#f5f8fa; }
  .bp3-running-text h4{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h4{
      color:#f5f8fa; }
  .bp3-running-text h5{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h5{
      color:#f5f8fa; }
  .bp3-running-text h6{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h6{
      color:#f5f8fa; }
  .bp3-running-text hr{
    margin:20px 0;
    border:none;
    border-bottom:1px solid rgba(16, 22, 26, 0.15); }
    .bp3-dark .bp3-running-text hr{
      border-color:rgba(255, 255, 255, 0.15); }
  .bp3-running-text p{
    margin:0 0 10px;
    padding:0; }

.bp3-text-large{
  font-size:16px; }

.bp3-text-small{
  font-size:12px; }
a{
  text-decoration:none;
  color:#106ba3; }
  a:hover{
    cursor:pointer;
    text-decoration:underline;
    color:#106ba3; }
  a .bp3-icon, a .bp3-icon-standard, a .bp3-icon-large{
    color:inherit; }
  a code,
  .bp3-dark a code{
    color:inherit; }
  .bp3-dark a,
  .bp3-dark a:hover{
    color:#48aff0; }
    .bp3-dark a .bp3-icon, .bp3-dark a .bp3-icon-standard, .bp3-dark a .bp3-icon-large,
    .bp3-dark a:hover .bp3-icon,
    .bp3-dark a:hover .bp3-icon-standard,
    .bp3-dark a:hover .bp3-icon-large{
      color:inherit; }
.bp3-running-text code, .bp3-code{
  text-transform:none;
  font-family:monospace;
  border-radius:3px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2);
  background:rgba(255, 255, 255, 0.7);
  padding:2px 5px;
  color:#5c7080;
  font-size:smaller; }
  .bp3-dark .bp3-running-text code, .bp3-running-text .bp3-dark code, .bp3-dark .bp3-code{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#a7b6c2; }
  .bp3-running-text a > code, a > .bp3-code{
    color:#137cbd; }
    .bp3-dark .bp3-running-text a > code, .bp3-running-text .bp3-dark a > code, .bp3-dark a > .bp3-code{
      color:inherit; }

.bp3-running-text pre, .bp3-code-block{
  text-transform:none;
  font-family:monospace;
  display:block;
  margin:10px 0;
  border-radius:3px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
  background:rgba(255, 255, 255, 0.7);
  padding:13px 15px 12px;
  line-height:1.4;
  color:#182026;
  font-size:13px;
  word-break:break-all;
  word-wrap:break-word; }
  .bp3-dark .bp3-running-text pre, .bp3-running-text .bp3-dark pre, .bp3-dark .bp3-code-block{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa; }
  .bp3-running-text pre > code, .bp3-code-block > code{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none;
    padding:0;
    color:inherit;
    font-size:inherit; }

.bp3-running-text kbd, .bp3-key{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  min-width:24px;
  height:24px;
  padding:3px 6px;
  vertical-align:middle;
  line-height:24px;
  color:#5c7080;
  font-family:inherit;
  font-size:12px; }
  .bp3-running-text kbd .bp3-icon, .bp3-key .bp3-icon, .bp3-running-text kbd .bp3-icon-standard, .bp3-key .bp3-icon-standard, .bp3-running-text kbd .bp3-icon-large, .bp3-key .bp3-icon-large{
    margin-right:5px; }
  .bp3-dark .bp3-running-text kbd, .bp3-running-text .bp3-dark kbd, .bp3-dark .bp3-key{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
    background:#394b59;
    color:#a7b6c2; }
.bp3-running-text blockquote, .bp3-blockquote{
  margin:0 0 10px;
  border-left:solid 4px rgba(167, 182, 194, 0.5);
  padding:0 20px; }
  .bp3-dark .bp3-running-text blockquote, .bp3-running-text .bp3-dark blockquote, .bp3-dark .bp3-blockquote{
    border-color:rgba(115, 134, 148, 0.5); }
.bp3-running-text ul,
.bp3-running-text ol, .bp3-list{
  margin:10px 0;
  padding-left:30px; }
  .bp3-running-text ul li:not(:last-child), .bp3-running-text ol li:not(:last-child), .bp3-list li:not(:last-child){
    margin-bottom:5px; }
  .bp3-running-text ul ol, .bp3-running-text ol ol, .bp3-list ol,
  .bp3-running-text ul ul,
  .bp3-running-text ol ul,
  .bp3-list ul{
    margin-top:5px; }

.bp3-list-unstyled{
  margin:0;
  padding:0;
  list-style:none; }
  .bp3-list-unstyled li{
    padding:0; }
.bp3-rtl{
  text-align:right; }

.bp3-dark{
  color:#f5f8fa; }

:focus{
  outline:rgba(19, 124, 189, 0.6) auto 2px;
  outline-offset:2px;
  -moz-outline-radius:6px; }

.bp3-focus-disabled :focus{
  outline:none !important; }
  .bp3-focus-disabled :focus ~ .bp3-control-indicator{
    outline:none !important; }

.bp3-alert{
  max-width:400px;
  padding:20px; }

.bp3-alert-body{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }
  .bp3-alert-body .bp3-icon{
    margin-top:0;
    margin-right:20px;
    font-size:40px; }

.bp3-alert-footer{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:reverse;
      -ms-flex-direction:row-reverse;
          flex-direction:row-reverse;
  margin-top:10px; }
  .bp3-alert-footer .bp3-button{
    margin-left:10px; }
.bp3-breadcrumbs{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-wrap:wrap;
      flex-wrap:wrap;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  margin:0;
  cursor:default;
  height:30px;
  padding:0;
  list-style:none; }
  .bp3-breadcrumbs > li{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center; }
    .bp3-breadcrumbs > li::after{
      display:block;
      margin:0 5px;
      background:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M10.71 7.29l-4-4a1.003 1.003 0 0 0-1.42 1.42L8.59 8 5.3 11.29c-.19.18-.3.43-.3.71a1.003 1.003 0 0 0 1.71.71l4-4c.18-.18.29-.43.29-.71 0-.28-.11-.53-.29-.71z' fill='%235C7080'/%3e%3c/svg%3e");
      width:16px;
      height:16px;
      content:""; }
    .bp3-breadcrumbs > li:last-of-type::after{
      display:none; }

.bp3-breadcrumb,
.bp3-breadcrumb-current,
.bp3-breadcrumbs-collapsed{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  font-size:16px; }

.bp3-breadcrumb,
.bp3-breadcrumbs-collapsed{
  color:#5c7080; }

.bp3-breadcrumb:hover{
  text-decoration:none; }

.bp3-breadcrumb.bp3-disabled{
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-breadcrumb .bp3-icon{
  margin-right:5px; }

.bp3-breadcrumb-current{
  color:inherit;
  font-weight:600; }
  .bp3-breadcrumb-current .bp3-input{
    vertical-align:baseline;
    font-size:inherit;
    font-weight:inherit; }

.bp3-breadcrumbs-collapsed{
  margin-right:2px;
  border:none;
  border-radius:3px;
  background:#ced9e0;
  cursor:pointer;
  padding:1px 5px;
  vertical-align:text-bottom; }
  .bp3-breadcrumbs-collapsed::before{
    display:block;
    background:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cg fill='%235C7080'%3e%3ccircle cx='2' cy='8.03' r='2'/%3e%3ccircle cx='14' cy='8.03' r='2'/%3e%3ccircle cx='8' cy='8.03' r='2'/%3e%3c/g%3e%3c/svg%3e") center no-repeat;
    width:16px;
    height:16px;
    content:""; }
  .bp3-breadcrumbs-collapsed:hover{
    background:#bfccd6;
    text-decoration:none;
    color:#182026; }

.bp3-dark .bp3-breadcrumb,
.bp3-dark .bp3-breadcrumbs-collapsed{
  color:#a7b6c2; }

.bp3-dark .bp3-breadcrumbs > li::after{
  color:#a7b6c2; }

.bp3-dark .bp3-breadcrumb.bp3-disabled{
  color:rgba(167, 182, 194, 0.6); }

.bp3-dark .bp3-breadcrumb-current{
  color:#f5f8fa; }

.bp3-dark .bp3-breadcrumbs-collapsed{
  background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-breadcrumbs-collapsed:hover{
    background:rgba(16, 22, 26, 0.6);
    color:#f5f8fa; }
.bp3-button{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  border:none;
  border-radius:3px;
  cursor:pointer;
  padding:5px 10px;
  vertical-align:middle;
  text-align:left;
  font-size:14px;
  min-width:30px;
  min-height:30px; }
  .bp3-button > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-button > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-button::before,
  .bp3-button > *{
    margin-right:7px; }
  .bp3-button:empty::before,
  .bp3-button > :last-child{
    margin-right:0; }
  .bp3-button:empty{
    padding:0 !important; }
  .bp3-button:disabled, .bp3-button.bp3-disabled{
    cursor:not-allowed; }
  .bp3-button.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-button.bp3-align-right,
  .bp3-align-right .bp3-button{
    text-align:right; }
  .bp3-button.bp3-align-left,
  .bp3-align-left .bp3-button{
    text-align:left; }
  .bp3-button:not([class*="bp3-intent-"]){
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    color:#182026; }
    .bp3-button:not([class*="bp3-intent-"]):hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
      background-clip:padding-box;
      background-color:#ebf1f5; }
    .bp3-button:not([class*="bp3-intent-"]):active, .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#d8e1e8;
      background-image:none; }
    .bp3-button:not([class*="bp3-intent-"]):disabled, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled{
      outline:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(206, 217, 224, 0.5);
      background-image:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active, .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active:hover, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active:hover{
        background:rgba(206, 217, 224, 0.7); }
  .bp3-button.bp3-intent-primary{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-primary:hover, .bp3-button.bp3-intent-primary:active, .bp3-button.bp3-intent-primary.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-primary:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#106ba3; }
    .bp3-button.bp3-intent-primary:active, .bp3-button.bp3-intent-primary.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#0e5a8a;
      background-image:none; }
    .bp3-button.bp3-intent-primary:disabled, .bp3-button.bp3-intent-primary.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(19, 124, 189, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-success{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#0f9960;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-success:hover, .bp3-button.bp3-intent-success:active, .bp3-button.bp3-intent-success.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-success:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#0d8050; }
    .bp3-button.bp3-intent-success:active, .bp3-button.bp3-intent-success.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#0a6640;
      background-image:none; }
    .bp3-button.bp3-intent-success:disabled, .bp3-button.bp3-intent-success.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(15, 153, 96, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-warning{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#d9822b;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-warning:hover, .bp3-button.bp3-intent-warning:active, .bp3-button.bp3-intent-warning.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-warning:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#bf7326; }
    .bp3-button.bp3-intent-warning:active, .bp3-button.bp3-intent-warning.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#a66321;
      background-image:none; }
    .bp3-button.bp3-intent-warning:disabled, .bp3-button.bp3-intent-warning.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(217, 130, 43, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-danger{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#db3737;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-danger:hover, .bp3-button.bp3-intent-danger:active, .bp3-button.bp3-intent-danger.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-danger:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#c23030; }
    .bp3-button.bp3-intent-danger:active, .bp3-button.bp3-intent-danger.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#a82a2a;
      background-image:none; }
    .bp3-button.bp3-intent-danger:disabled, .bp3-button.bp3-intent-danger.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(219, 55, 55, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button[class*="bp3-intent-"] .bp3-button-spinner .bp3-spinner-head{
    stroke:#ffffff; }
  .bp3-button.bp3-large,
  .bp3-large .bp3-button{
    min-width:40px;
    min-height:40px;
    padding:5px 15px;
    font-size:16px; }
    .bp3-button.bp3-large::before,
    .bp3-button.bp3-large > *,
    .bp3-large .bp3-button::before,
    .bp3-large .bp3-button > *{
      margin-right:10px; }
    .bp3-button.bp3-large:empty::before,
    .bp3-button.bp3-large > :last-child,
    .bp3-large .bp3-button:empty::before,
    .bp3-large .bp3-button > :last-child{
      margin-right:0; }
  .bp3-button.bp3-small,
  .bp3-small .bp3-button{
    min-width:24px;
    min-height:24px;
    padding:0 7px; }
  .bp3-button.bp3-loading{
    position:relative; }
    .bp3-button.bp3-loading[class*="bp3-icon-"]::before{
      visibility:hidden; }
    .bp3-button.bp3-loading .bp3-button-spinner{
      position:absolute;
      margin:0; }
    .bp3-button.bp3-loading > :not(.bp3-button-spinner){
      visibility:hidden; }
  .bp3-button[class*="bp3-icon-"]::before{
    line-height:1;
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-weight:400;
    font-style:normal;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    color:#5c7080; }
  .bp3-button .bp3-icon, .bp3-button .bp3-icon-standard, .bp3-button .bp3-icon-large{
    color:#5c7080; }
    .bp3-button .bp3-icon.bp3-align-right, .bp3-button .bp3-icon-standard.bp3-align-right, .bp3-button .bp3-icon-large.bp3-align-right{
      margin-left:7px; }
  .bp3-button .bp3-icon:first-child:last-child,
  .bp3-button .bp3-spinner + .bp3-icon:last-child{
    margin:0 -7px; }
  .bp3-dark .bp3-button:not([class*="bp3-intent-"]){
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#394b59;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
    color:#f5f8fa; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):hover, .bp3-dark .bp3-button:not([class*="bp3-intent-"]):active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      color:#f5f8fa; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#30404d; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#202b33;
      background-image:none; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):disabled, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(57, 75, 89, 0.5);
      background-image:none;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active{
        background:rgba(57, 75, 89, 0.7); }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-button-spinner .bp3-spinner-head{
      background:rgba(16, 22, 26, 0.5);
      stroke:#8a9ba8; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"])[class*="bp3-icon-"]::before{
      color:#a7b6c2; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon, .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon-standard, .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon-large{
      color:#a7b6c2; }
  .bp3-dark .bp3-button[class*="bp3-intent-"]{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:active, .bp3-dark .bp3-button[class*="bp3-intent-"].bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:disabled, .bp3-dark .bp3-button[class*="bp3-intent-"].bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background-image:none;
      color:rgba(255, 255, 255, 0.3); }
    .bp3-dark .bp3-button[class*="bp3-intent-"] .bp3-button-spinner .bp3-spinner-head{
      stroke:#8a9ba8; }
  .bp3-button:disabled::before,
  .bp3-button:disabled .bp3-icon, .bp3-button:disabled .bp3-icon-standard, .bp3-button:disabled .bp3-icon-large, .bp3-button.bp3-disabled::before,
  .bp3-button.bp3-disabled .bp3-icon, .bp3-button.bp3-disabled .bp3-icon-standard, .bp3-button.bp3-disabled .bp3-icon-large, .bp3-button[class*="bp3-intent-"]::before,
  .bp3-button[class*="bp3-intent-"] .bp3-icon, .bp3-button[class*="bp3-intent-"] .bp3-icon-standard, .bp3-button[class*="bp3-intent-"] .bp3-icon-large{
    color:inherit !important; }
  .bp3-button.bp3-minimal{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none; }
    .bp3-button.bp3-minimal:hover{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(167, 182, 194, 0.3);
      text-decoration:none;
      color:#182026; }
    .bp3-button.bp3-minimal:active, .bp3-button.bp3-minimal.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(115, 134, 148, 0.3);
      color:#182026; }
    .bp3-button.bp3-minimal:disabled, .bp3-button.bp3-minimal:disabled:hover, .bp3-button.bp3-minimal.bp3-disabled, .bp3-button.bp3-minimal.bp3-disabled:hover{
      background:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-button.bp3-minimal:disabled.bp3-active, .bp3-button.bp3-minimal:disabled:hover.bp3-active, .bp3-button.bp3-minimal.bp3-disabled.bp3-active, .bp3-button.bp3-minimal.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button.bp3-minimal{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:inherit; }
      .bp3-dark .bp3-button.bp3-minimal:hover, .bp3-dark .bp3-button.bp3-minimal:active, .bp3-dark .bp3-button.bp3-minimal.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none; }
      .bp3-dark .bp3-button.bp3-minimal:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button.bp3-minimal:active, .bp3-dark .bp3-button.bp3-minimal.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button.bp3-minimal:disabled, .bp3-dark .bp3-button.bp3-minimal:disabled:hover, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled:hover{
        background:none;
        cursor:not-allowed;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-button.bp3-minimal:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal:disabled:hover.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:hover, .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:disabled, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-primary:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-success{
      color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:hover, .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:disabled, .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-success:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:hover, .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:disabled, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-warning:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-danger{
      color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:hover, .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:disabled, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-danger:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }

a.bp3-button{
  text-align:center;
  text-decoration:none;
  -webkit-transition:none;
  transition:none; }
  a.bp3-button, a.bp3-button:hover, a.bp3-button:active{
    color:#182026; }
  a.bp3-button.bp3-disabled{
    color:rgba(92, 112, 128, 0.6); }

.bp3-button-text{
  -webkit-box-flex:0;
      -ms-flex:0 1 auto;
          flex:0 1 auto; }

.bp3-button.bp3-align-left .bp3-button-text, .bp3-button.bp3-align-right .bp3-button-text,
.bp3-button-group.bp3-align-left .bp3-button-text,
.bp3-button-group.bp3-align-right .bp3-button-text{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto; }
.bp3-button-group{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex; }
  .bp3-button-group .bp3-button{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    position:relative;
    z-index:4; }
    .bp3-button-group .bp3-button:focus{
      z-index:5; }
    .bp3-button-group .bp3-button:hover{
      z-index:6; }
    .bp3-button-group .bp3-button:active, .bp3-button-group .bp3-button.bp3-active{
      z-index:7; }
    .bp3-button-group .bp3-button:disabled, .bp3-button-group .bp3-button.bp3-disabled{
      z-index:3; }
    .bp3-button-group .bp3-button[class*="bp3-intent-"]{
      z-index:9; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:focus{
        z-index:10; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:hover{
        z-index:11; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:active, .bp3-button-group .bp3-button[class*="bp3-intent-"].bp3-active{
        z-index:12; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:disabled, .bp3-button-group .bp3-button[class*="bp3-intent-"].bp3-disabled{
        z-index:8; }
  .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:first-child) .bp3-button,
  .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:first-child){
    border-top-left-radius:0;
    border-bottom-left-radius:0; }
  .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:last-child){
    margin-right:-1px;
    border-top-right-radius:0;
    border-bottom-right-radius:0; }
  .bp3-button-group.bp3-minimal .bp3-button{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none; }
    .bp3-button-group.bp3-minimal .bp3-button:hover{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(167, 182, 194, 0.3);
      text-decoration:none;
      color:#182026; }
    .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(115, 134, 148, 0.3);
      color:#182026; }
    .bp3-button-group.bp3-minimal .bp3-button:disabled, .bp3-button-group.bp3-minimal .bp3-button:disabled:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover{
      background:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-button-group.bp3-minimal .bp3-button:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button:disabled:hover.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button-group.bp3-minimal .bp3-button{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:inherit; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:hover, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled:hover, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover{
        background:none;
        cursor:not-allowed;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled:hover.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success{
      color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger{
      color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }
  .bp3-button-group .bp3-popover-wrapper,
  .bp3-button-group .bp3-popover-target{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-button-group.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-button-group .bp3-button.bp3-fill,
  .bp3-button-group.bp3-fill .bp3-button:not(.bp3-fixed){
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-button-group.bp3-vertical{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column;
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch;
    vertical-align:top; }
    .bp3-button-group.bp3-vertical.bp3-fill{
      width:unset;
      height:100%; }
    .bp3-button-group.bp3-vertical .bp3-button{
      margin-right:0 !important;
      width:100%; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:first-child .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:first-child{
      border-radius:3px 3px 0 0; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:last-child .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:last-child{
      border-radius:0 0 3px 3px; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:not(:last-child){
      margin-bottom:-1px; }
  .bp3-button-group.bp3-align-left .bp3-button{
    text-align:left; }
  .bp3-dark .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-dark .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:last-child){
    margin-right:1px; }
  .bp3-dark .bp3-button-group.bp3-vertical > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-dark .bp3-button-group.bp3-vertical > .bp3-button:not(:last-child){
    margin-bottom:1px; }
.bp3-callout{
  line-height:1.5;
  font-size:14px;
  position:relative;
  border-radius:3px;
  background-color:rgba(138, 155, 168, 0.15);
  width:100%;
  padding:10px 12px 9px; }
  .bp3-callout[class*="bp3-icon-"]{
    padding-left:40px; }
    .bp3-callout[class*="bp3-icon-"]::before{
      line-height:1;
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-weight:400;
      font-style:normal;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased;
      position:absolute;
      top:10px;
      left:10px;
      color:#5c7080; }
  .bp3-callout.bp3-callout-icon{
    padding-left:40px; }
    .bp3-callout.bp3-callout-icon > .bp3-icon:first-child{
      position:absolute;
      top:10px;
      left:10px;
      color:#5c7080; }
  .bp3-callout .bp3-heading{
    margin-top:0;
    margin-bottom:5px;
    line-height:20px; }
    .bp3-callout .bp3-heading:last-child{
      margin-bottom:0; }
  .bp3-dark .bp3-callout{
    background-color:rgba(138, 155, 168, 0.2); }
    .bp3-dark .bp3-callout[class*="bp3-icon-"]::before{
      color:#a7b6c2; }
  .bp3-callout.bp3-intent-primary{
    background-color:rgba(19, 124, 189, 0.15); }
    .bp3-callout.bp3-intent-primary[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-primary > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-primary .bp3-heading{
      color:#106ba3; }
    .bp3-dark .bp3-callout.bp3-intent-primary{
      background-color:rgba(19, 124, 189, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-primary[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-primary > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-primary .bp3-heading{
        color:#48aff0; }
  .bp3-callout.bp3-intent-success{
    background-color:rgba(15, 153, 96, 0.15); }
    .bp3-callout.bp3-intent-success[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-success > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-success .bp3-heading{
      color:#0d8050; }
    .bp3-dark .bp3-callout.bp3-intent-success{
      background-color:rgba(15, 153, 96, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-success[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-success > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-success .bp3-heading{
        color:#3dcc91; }
  .bp3-callout.bp3-intent-warning{
    background-color:rgba(217, 130, 43, 0.15); }
    .bp3-callout.bp3-intent-warning[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-warning > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-warning .bp3-heading{
      color:#bf7326; }
    .bp3-dark .bp3-callout.bp3-intent-warning{
      background-color:rgba(217, 130, 43, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-warning[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-warning > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-warning .bp3-heading{
        color:#ffb366; }
  .bp3-callout.bp3-intent-danger{
    background-color:rgba(219, 55, 55, 0.15); }
    .bp3-callout.bp3-intent-danger[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-danger > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-danger .bp3-heading{
      color:#c23030; }
    .bp3-dark .bp3-callout.bp3-intent-danger{
      background-color:rgba(219, 55, 55, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-danger[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-danger > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-danger .bp3-heading{
        color:#ff7373; }
  .bp3-running-text .bp3-callout{
    margin:20px 0; }
.bp3-card{
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
  background-color:#ffffff;
  padding:20px;
  -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-card.bp3-dark,
  .bp3-dark .bp3-card{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
    background-color:#30404d; }

.bp3-elevation-0{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }
  .bp3-elevation-0.bp3-dark,
  .bp3-dark .bp3-elevation-0{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }

.bp3-elevation-1{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-1.bp3-dark,
  .bp3-dark .bp3-elevation-1{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-elevation-2{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 1px 1px rgba(16, 22, 26, 0.2), 0 2px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 1px 1px rgba(16, 22, 26, 0.2), 0 2px 6px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-2.bp3-dark,
  .bp3-dark .bp3-elevation-2{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.4), 0 2px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.4), 0 2px 6px rgba(16, 22, 26, 0.4); }

.bp3-elevation-3{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-3.bp3-dark,
  .bp3-dark .bp3-elevation-3{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }

.bp3-elevation-4{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-4.bp3-dark,
  .bp3-dark .bp3-elevation-4{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4); }

.bp3-card.bp3-interactive:hover{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  cursor:pointer; }
  .bp3-card.bp3-interactive:hover.bp3-dark,
  .bp3-dark .bp3-card.bp3-interactive:hover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }

.bp3-card.bp3-interactive:active{
  opacity:0.9;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  -webkit-transition-duration:0;
          transition-duration:0; }
  .bp3-card.bp3-interactive:active.bp3-dark,
  .bp3-dark .bp3-card.bp3-interactive:active{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-collapse{
  height:0;
  overflow-y:hidden;
  -webkit-transition:height 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:height 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-collapse .bp3-collapse-body{
    -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-collapse .bp3-collapse-body[aria-hidden="true"]{
      display:none; }

.bp3-context-menu .bp3-popover-target{
  display:block; }

.bp3-context-menu-popover-target{
  position:fixed; }

.bp3-divider{
  margin:5px;
  border-right:1px solid rgba(16, 22, 26, 0.15);
  border-bottom:1px solid rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-divider{
    border-color:rgba(16, 22, 26, 0.4); }
.bp3-dialog-container{
  opacity:1;
  -webkit-transform:scale(1);
          transform:scale(1);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  width:100%;
  min-height:100%;
  pointer-events:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-dialog-container.bp3-overlay-enter > .bp3-dialog, .bp3-dialog-container.bp3-overlay-appear > .bp3-dialog{
    opacity:0;
    -webkit-transform:scale(0.5);
            transform:scale(0.5); }
  .bp3-dialog-container.bp3-overlay-enter-active > .bp3-dialog, .bp3-dialog-container.bp3-overlay-appear-active > .bp3-dialog{
    opacity:1;
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-property:opacity, -webkit-transform;
    transition-property:opacity, -webkit-transform;
    transition-property:opacity, transform;
    transition-property:opacity, transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-dialog-container.bp3-overlay-exit > .bp3-dialog{
    opacity:1;
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-dialog-container.bp3-overlay-exit-active > .bp3-dialog{
    opacity:0;
    -webkit-transform:scale(0.5);
            transform:scale(0.5);
    -webkit-transition-property:opacity, -webkit-transform;
    transition-property:opacity, -webkit-transform;
    transition-property:opacity, transform;
    transition-property:opacity, transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }

.bp3-dialog{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:30px 0;
  border-radius:6px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  background:#ebf1f5;
  width:500px;
  padding-bottom:20px;
  pointer-events:all;
  -webkit-user-select:text;
     -moz-user-select:text;
      -ms-user-select:text;
          user-select:text; }
  .bp3-dialog:focus{
    outline:0; }
  .bp3-dialog.bp3-dark,
  .bp3-dark .bp3-dialog{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    background:#293742;
    color:#f5f8fa; }

.bp3-dialog-header{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  border-radius:6px 6px 0 0;
  -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
  background:#ffffff;
  min-height:40px;
  padding-right:5px;
  padding-left:20px; }
  .bp3-dialog-header .bp3-icon-large,
  .bp3-dialog-header .bp3-icon{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    margin-right:10px;
    color:#5c7080; }
  .bp3-dialog-header .bp3-heading{
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    margin:0;
    line-height:inherit; }
    .bp3-dialog-header .bp3-heading:last-child{
      margin-right:20px; }
  .bp3-dark .bp3-dialog-header{
    -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
    background:#30404d; }
    .bp3-dark .bp3-dialog-header .bp3-icon-large,
    .bp3-dark .bp3-dialog-header .bp3-icon{
      color:#a7b6c2; }

.bp3-dialog-body{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  margin:20px;
  line-height:18px; }

.bp3-dialog-footer{
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  margin:0 20px; }

.bp3-dialog-footer-actions{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-pack:end;
      -ms-flex-pack:end;
          justify-content:flex-end; }
  .bp3-dialog-footer-actions .bp3-button{
    margin-left:10px; }
.bp3-drawer{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:0;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  padding:0; }
  .bp3-drawer:focus{
    outline:0; }
  .bp3-drawer.bp3-position-top{
    top:0;
    right:0;
    left:0;
    height:50%; }
    .bp3-drawer.bp3-position-top.bp3-overlay-enter, .bp3-drawer.bp3-position-top.bp3-overlay-appear{
      -webkit-transform:translateY(-100%);
              transform:translateY(-100%); }
    .bp3-drawer.bp3-position-top.bp3-overlay-enter-active, .bp3-drawer.bp3-position-top.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-top.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer.bp3-position-top.bp3-overlay-exit-active{
      -webkit-transform:translateY(-100%);
              transform:translateY(-100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-position-bottom{
    right:0;
    bottom:0;
    left:0;
    height:50%; }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-enter, .bp3-drawer.bp3-position-bottom.bp3-overlay-appear{
      -webkit-transform:translateY(100%);
              transform:translateY(100%); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-enter-active, .bp3-drawer.bp3-position-bottom.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-exit-active{
      -webkit-transform:translateY(100%);
              transform:translateY(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-position-left{
    top:0;
    bottom:0;
    left:0;
    width:50%; }
    .bp3-drawer.bp3-position-left.bp3-overlay-enter, .bp3-drawer.bp3-position-left.bp3-overlay-appear{
      -webkit-transform:translateX(-100%);
              transform:translateX(-100%); }
    .bp3-drawer.bp3-position-left.bp3-overlay-enter-active, .bp3-drawer.bp3-position-left.bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-left.bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer.bp3-position-left.bp3-overlay-exit-active{
      -webkit-transform:translateX(-100%);
              transform:translateX(-100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-position-right{
    top:0;
    right:0;
    bottom:0;
    width:50%; }
    .bp3-drawer.bp3-position-right.bp3-overlay-enter, .bp3-drawer.bp3-position-right.bp3-overlay-appear{
      -webkit-transform:translateX(100%);
              transform:translateX(100%); }
    .bp3-drawer.bp3-position-right.bp3-overlay-enter-active, .bp3-drawer.bp3-position-right.bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-right.bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer.bp3-position-right.bp3-overlay-exit-active{
      -webkit-transform:translateX(100%);
              transform:translateX(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
  .bp3-position-right):not(.bp3-vertical){
    top:0;
    right:0;
    bottom:0;
    width:50%; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-enter, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-appear{
      -webkit-transform:translateX(100%);
              transform:translateX(100%); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-enter-active, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-exit-active{
      -webkit-transform:translateX(100%);
              transform:translateX(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
  .bp3-position-right).bp3-vertical{
    right:0;
    bottom:0;
    left:0;
    height:50%; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-enter, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-appear{
      -webkit-transform:translateY(100%);
              transform:translateY(100%); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-enter-active, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-exit-active{
      -webkit-transform:translateY(100%);
              transform:translateY(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-dark,
  .bp3-dark .bp3-drawer{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    background:#30404d;
    color:#f5f8fa; }

.bp3-drawer-header{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  position:relative;
  border-radius:0;
  -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
  min-height:40px;
  padding:5px;
  padding-left:20px; }
  .bp3-drawer-header .bp3-icon-large,
  .bp3-drawer-header .bp3-icon{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    margin-right:10px;
    color:#5c7080; }
  .bp3-drawer-header .bp3-heading{
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    margin:0;
    line-height:inherit; }
    .bp3-drawer-header .bp3-heading:last-child{
      margin-right:20px; }
  .bp3-dark .bp3-drawer-header{
    -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:0 1px 0 rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-drawer-header .bp3-icon-large,
    .bp3-dark .bp3-drawer-header .bp3-icon{
      color:#a7b6c2; }

.bp3-drawer-body{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  overflow:auto;
  line-height:18px; }

.bp3-drawer-footer{
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  position:relative;
  -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
  padding:10px 20px; }
  .bp3-dark .bp3-drawer-footer{
    -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.4); }
.bp3-editable-text{
  display:inline-block;
  position:relative;
  cursor:text;
  max-width:100%;
  vertical-align:top;
  white-space:nowrap; }
  .bp3-editable-text::before{
    position:absolute;
    top:-3px;
    right:-3px;
    bottom:-3px;
    left:-3px;
    border-radius:3px;
    content:"";
    -webkit-transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-editable-text:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-editable-text.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
    background-color:#ffffff; }
  .bp3-editable-text.bp3-disabled::before{
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-editable-text.bp3-intent-primary .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-primary .bp3-editable-text-content{
    color:#137cbd; }
  .bp3-editable-text.bp3-intent-primary:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(19, 124, 189, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(19, 124, 189, 0.4); }
  .bp3-editable-text.bp3-intent-primary.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-success .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-success .bp3-editable-text-content{
    color:#0f9960; }
  .bp3-editable-text.bp3-intent-success:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px rgba(15, 153, 96, 0.4);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px rgba(15, 153, 96, 0.4); }
  .bp3-editable-text.bp3-intent-success.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-warning .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-warning .bp3-editable-text-content{
    color:#d9822b; }
  .bp3-editable-text.bp3-intent-warning:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px rgba(217, 130, 43, 0.4);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px rgba(217, 130, 43, 0.4); }
  .bp3-editable-text.bp3-intent-warning.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-danger .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-danger .bp3-editable-text-content{
    color:#db3737; }
  .bp3-editable-text.bp3-intent-danger:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px rgba(219, 55, 55, 0.4);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px rgba(219, 55, 55, 0.4); }
  .bp3-editable-text.bp3-intent-danger.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-editable-text:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(255, 255, 255, 0.15); }
  .bp3-dark .bp3-editable-text.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background-color:rgba(16, 22, 26, 0.3); }
  .bp3-dark .bp3-editable-text.bp3-disabled::before{
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-dark .bp3-editable-text.bp3-intent-primary .bp3-editable-text-content{
    color:#48aff0; }
  .bp3-dark .bp3-editable-text.bp3-intent-primary:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(72, 175, 240, 0), 0 0 0 0 rgba(72, 175, 240, 0), inset 0 0 0 1px rgba(72, 175, 240, 0.4);
            box-shadow:0 0 0 0 rgba(72, 175, 240, 0), 0 0 0 0 rgba(72, 175, 240, 0), inset 0 0 0 1px rgba(72, 175, 240, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-primary.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #48aff0, 0 0 0 3px rgba(72, 175, 240, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #48aff0, 0 0 0 3px rgba(72, 175, 240, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-success .bp3-editable-text-content{
    color:#3dcc91; }
  .bp3-dark .bp3-editable-text.bp3-intent-success:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(61, 204, 145, 0), 0 0 0 0 rgba(61, 204, 145, 0), inset 0 0 0 1px rgba(61, 204, 145, 0.4);
            box-shadow:0 0 0 0 rgba(61, 204, 145, 0), 0 0 0 0 rgba(61, 204, 145, 0), inset 0 0 0 1px rgba(61, 204, 145, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-success.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #3dcc91, 0 0 0 3px rgba(61, 204, 145, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #3dcc91, 0 0 0 3px rgba(61, 204, 145, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-warning .bp3-editable-text-content{
    color:#ffb366; }
  .bp3-dark .bp3-editable-text.bp3-intent-warning:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(255, 179, 102, 0), 0 0 0 0 rgba(255, 179, 102, 0), inset 0 0 0 1px rgba(255, 179, 102, 0.4);
            box-shadow:0 0 0 0 rgba(255, 179, 102, 0), 0 0 0 0 rgba(255, 179, 102, 0), inset 0 0 0 1px rgba(255, 179, 102, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-warning.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #ffb366, 0 0 0 3px rgba(255, 179, 102, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #ffb366, 0 0 0 3px rgba(255, 179, 102, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-danger .bp3-editable-text-content{
    color:#ff7373; }
  .bp3-dark .bp3-editable-text.bp3-intent-danger:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(255, 115, 115, 0), 0 0 0 0 rgba(255, 115, 115, 0), inset 0 0 0 1px rgba(255, 115, 115, 0.4);
            box-shadow:0 0 0 0 rgba(255, 115, 115, 0), 0 0 0 0 rgba(255, 115, 115, 0), inset 0 0 0 1px rgba(255, 115, 115, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-danger.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #ff7373, 0 0 0 3px rgba(255, 115, 115, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #ff7373, 0 0 0 3px rgba(255, 115, 115, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-editable-text-input,
.bp3-editable-text-content{
  display:inherit;
  position:relative;
  min-width:inherit;
  max-width:inherit;
  vertical-align:top;
  text-transform:inherit;
  letter-spacing:inherit;
  color:inherit;
  font:inherit;
  resize:none; }

.bp3-editable-text-input{
  border:none;
  -webkit-box-shadow:none;
          box-shadow:none;
  background:none;
  width:100%;
  padding:0;
  white-space:pre-wrap; }
  .bp3-editable-text-input::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input:focus{
    outline:none; }
  .bp3-editable-text-input::-ms-clear{
    display:none; }

.bp3-editable-text-content{
  overflow:hidden;
  padding-right:2px;
  text-overflow:ellipsis;
  white-space:pre; }
  .bp3-editable-text-editing > .bp3-editable-text-content{
    position:absolute;
    left:0;
    visibility:hidden; }
  .bp3-editable-text-placeholder > .bp3-editable-text-content{
    color:rgba(92, 112, 128, 0.6); }
    .bp3-dark .bp3-editable-text-placeholder > .bp3-editable-text-content{
      color:rgba(167, 182, 194, 0.6); }

.bp3-editable-text.bp3-multiline{
  display:block; }
  .bp3-editable-text.bp3-multiline .bp3-editable-text-content{
    overflow:auto;
    white-space:pre-wrap;
    word-wrap:break-word; }
.bp3-control-group{
  -webkit-transform:translateZ(0);
          transform:translateZ(0);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:stretch;
      -ms-flex-align:stretch;
          align-items:stretch; }
  .bp3-control-group > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-control-group > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-control-group .bp3-button,
  .bp3-control-group .bp3-html-select,
  .bp3-control-group .bp3-input,
  .bp3-control-group .bp3-select{
    position:relative; }
  .bp3-control-group .bp3-input{
    z-index:2;
    border-radius:inherit; }
    .bp3-control-group .bp3-input:focus{
      z-index:14;
      border-radius:3px; }
    .bp3-control-group .bp3-input[class*="bp3-intent"]{
      z-index:13; }
      .bp3-control-group .bp3-input[class*="bp3-intent"]:focus{
        z-index:15; }
    .bp3-control-group .bp3-input[readonly], .bp3-control-group .bp3-input:disabled, .bp3-control-group .bp3-input.bp3-disabled{
      z-index:1; }
  .bp3-control-group .bp3-input-group[class*="bp3-intent"] .bp3-input{
    z-index:13; }
    .bp3-control-group .bp3-input-group[class*="bp3-intent"] .bp3-input:focus{
      z-index:15; }
  .bp3-control-group .bp3-button,
  .bp3-control-group .bp3-html-select select,
  .bp3-control-group .bp3-select select{
    -webkit-transform:translateZ(0);
            transform:translateZ(0);
    z-index:4;
    border-radius:inherit; }
    .bp3-control-group .bp3-button:focus,
    .bp3-control-group .bp3-html-select select:focus,
    .bp3-control-group .bp3-select select:focus{
      z-index:5; }
    .bp3-control-group .bp3-button:hover,
    .bp3-control-group .bp3-html-select select:hover,
    .bp3-control-group .bp3-select select:hover{
      z-index:6; }
    .bp3-control-group .bp3-button:active,
    .bp3-control-group .bp3-html-select select:active,
    .bp3-control-group .bp3-select select:active{
      z-index:7; }
    .bp3-control-group .bp3-button[readonly], .bp3-control-group .bp3-button:disabled, .bp3-control-group .bp3-button.bp3-disabled,
    .bp3-control-group .bp3-html-select select[readonly],
    .bp3-control-group .bp3-html-select select:disabled,
    .bp3-control-group .bp3-html-select select.bp3-disabled,
    .bp3-control-group .bp3-select select[readonly],
    .bp3-control-group .bp3-select select:disabled,
    .bp3-control-group .bp3-select select.bp3-disabled{
      z-index:3; }
    .bp3-control-group .bp3-button[class*="bp3-intent"],
    .bp3-control-group .bp3-html-select select[class*="bp3-intent"],
    .bp3-control-group .bp3-select select[class*="bp3-intent"]{
      z-index:9; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:focus,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:focus,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:focus{
        z-index:10; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:hover,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:hover,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:hover{
        z-index:11; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:active,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:active,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:active{
        z-index:12; }
      .bp3-control-group .bp3-button[class*="bp3-intent"][readonly], .bp3-control-group .bp3-button[class*="bp3-intent"]:disabled, .bp3-control-group .bp3-button[class*="bp3-intent"].bp3-disabled,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"][readonly],
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:disabled,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"].bp3-disabled,
      .bp3-control-group .bp3-select select[class*="bp3-intent"][readonly],
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:disabled,
      .bp3-control-group .bp3-select select[class*="bp3-intent"].bp3-disabled{
        z-index:8; }
  .bp3-control-group .bp3-input-group > .bp3-icon,
  .bp3-control-group .bp3-input-group > .bp3-button,
  .bp3-control-group .bp3-input-group > .bp3-input-action{
    z-index:16; }
  .bp3-control-group .bp3-select::after,
  .bp3-control-group .bp3-html-select::after,
  .bp3-control-group .bp3-select > .bp3-icon,
  .bp3-control-group .bp3-html-select > .bp3-icon{
    z-index:17; }
  .bp3-control-group:not(.bp3-vertical) > *{
    margin-right:-1px; }
  .bp3-dark .bp3-control-group:not(.bp3-vertical) > *{
    margin-right:0; }
  .bp3-dark .bp3-control-group:not(.bp3-vertical) > .bp3-button + .bp3-button{
    margin-left:1px; }
  .bp3-control-group .bp3-popover-wrapper,
  .bp3-control-group .bp3-popover-target{
    border-radius:inherit; }
  .bp3-control-group > :first-child{
    border-radius:3px 0 0 3px; }
  .bp3-control-group > :last-child{
    margin-right:0;
    border-radius:0 3px 3px 0; }
  .bp3-control-group > :only-child{
    margin-right:0;
    border-radius:3px; }
  .bp3-control-group .bp3-input-group .bp3-button{
    border-radius:3px; }
  .bp3-control-group > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-control-group.bp3-fill > *:not(.bp3-fixed){
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-control-group.bp3-vertical{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column; }
    .bp3-control-group.bp3-vertical > *{
      margin-top:-1px; }
    .bp3-control-group.bp3-vertical > :first-child{
      margin-top:0;
      border-radius:3px 3px 0 0; }
    .bp3-control-group.bp3-vertical > :last-child{
      border-radius:0 0 3px 3px; }
.bp3-control{
  display:block;
  position:relative;
  margin-bottom:10px;
  cursor:pointer;
  text-transform:none; }
  .bp3-control input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
  .bp3-control:hover input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#106ba3; }
  .bp3-control input:not(:disabled):active:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background:#0e5a8a; }
  .bp3-control input:disabled:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(19, 124, 189, 0.5); }
  .bp3-dark .bp3-control input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control:hover input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#106ba3; }
  .bp3-dark .bp3-control input:not(:disabled):active:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#0e5a8a; }
  .bp3-dark .bp3-control input:disabled:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(14, 90, 138, 0.5); }
  .bp3-control:not(.bp3-align-right){
    padding-left:26px; }
    .bp3-control:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-26px; }
  .bp3-control.bp3-align-right{
    padding-right:26px; }
    .bp3-control.bp3-align-right .bp3-control-indicator{
      margin-right:-26px; }
  .bp3-control.bp3-disabled{
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-control.bp3-inline{
    display:inline-block;
    margin-right:20px; }
  .bp3-control input{
    position:absolute;
    top:0;
    left:0;
    opacity:0;
    z-index:-1; }
  .bp3-control .bp3-control-indicator{
    display:inline-block;
    position:relative;
    margin-top:-3px;
    margin-right:10px;
    border:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    cursor:pointer;
    width:1em;
    height:1em;
    vertical-align:middle;
    font-size:16px;
    -webkit-user-select:none;
       -moz-user-select:none;
        -ms-user-select:none;
            user-select:none; }
    .bp3-control .bp3-control-indicator::before{
      display:block;
      width:1em;
      height:1em;
      content:""; }
  .bp3-control:hover .bp3-control-indicator{
    background-color:#ebf1f5; }
  .bp3-control input:not(:disabled):active ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background:#d8e1e8; }
  .bp3-control input:disabled ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(206, 217, 224, 0.5);
    cursor:not-allowed; }
  .bp3-control input:focus ~ .bp3-control-indicator{
    outline:rgba(19, 124, 189, 0.6) auto 2px;
    outline-offset:2px;
    -moz-outline-radius:6px; }
  .bp3-control.bp3-align-right .bp3-control-indicator{
    float:right;
    margin-top:1px;
    margin-left:10px; }
  .bp3-control.bp3-large{
    font-size:16px; }
    .bp3-control.bp3-large:not(.bp3-align-right){
      padding-left:30px; }
      .bp3-control.bp3-large:not(.bp3-align-right) .bp3-control-indicator{
        margin-left:-30px; }
    .bp3-control.bp3-large.bp3-align-right{
      padding-right:30px; }
      .bp3-control.bp3-large.bp3-align-right .bp3-control-indicator{
        margin-right:-30px; }
    .bp3-control.bp3-large .bp3-control-indicator{
      font-size:20px; }
    .bp3-control.bp3-large.bp3-align-right .bp3-control-indicator{
      margin-top:0; }
  .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
  .bp3-control.bp3-checkbox:hover input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#106ba3; }
  .bp3-control.bp3-checkbox input:not(:disabled):active:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background:#0e5a8a; }
  .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(19, 124, 189, 0.5); }
  .bp3-dark .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-checkbox:hover input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#106ba3; }
  .bp3-dark .bp3-control.bp3-checkbox input:not(:disabled):active:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#0e5a8a; }
  .bp3-dark .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(14, 90, 138, 0.5); }
  .bp3-control.bp3-checkbox .bp3-control-indicator{
    border-radius:3px; }
  .bp3-control.bp3-checkbox input:checked ~ .bp3-control-indicator::before{
    background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M12 5c-.28 0-.53.11-.71.29L7 9.59l-2.29-2.3a1.003 1.003 0 0 0-1.42 1.42l3 3c.18.18.43.29.71.29s.53-.11.71-.29l5-5A1.003 1.003 0 0 0 12 5z' fill='white'/%3e%3c/svg%3e"); }
  .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator::before{
    background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M11 7H5c-.55 0-1 .45-1 1s.45 1 1 1h6c.55 0 1-.45 1-1s-.45-1-1-1z' fill='white'/%3e%3c/svg%3e"); }
  .bp3-control.bp3-radio .bp3-control-indicator{
    border-radius:50%; }
  .bp3-control.bp3-radio input:checked ~ .bp3-control-indicator::before{
    background-image:radial-gradient(#ffffff, #ffffff 28%, transparent 32%); }
  .bp3-control.bp3-radio input:checked:disabled ~ .bp3-control-indicator::before{
    opacity:0.5; }
  .bp3-control.bp3-radio input:focus ~ .bp3-control-indicator{
    -moz-outline-radius:16px; }
  .bp3-control.bp3-switch input ~ .bp3-control-indicator{
    background:rgba(167, 182, 194, 0.5); }
  .bp3-control.bp3-switch:hover input ~ .bp3-control-indicator{
    background:rgba(115, 134, 148, 0.5); }
  .bp3-control.bp3-switch input:not(:disabled):active ~ .bp3-control-indicator{
    background:rgba(92, 112, 128, 0.5); }
  .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator{
    background:rgba(206, 217, 224, 0.5); }
    .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator::before{
      background:rgba(255, 255, 255, 0.8); }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator{
    background:#137cbd; }
  .bp3-control.bp3-switch:hover input:checked ~ .bp3-control-indicator{
    background:#106ba3; }
  .bp3-control.bp3-switch input:checked:not(:disabled):active ~ .bp3-control-indicator{
    background:#0e5a8a; }
  .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator{
    background:rgba(19, 124, 189, 0.5); }
    .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator::before{
      background:rgba(255, 255, 255, 0.8); }
  .bp3-control.bp3-switch:not(.bp3-align-right){
    padding-left:38px; }
    .bp3-control.bp3-switch:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-38px; }
  .bp3-control.bp3-switch.bp3-align-right{
    padding-right:38px; }
    .bp3-control.bp3-switch.bp3-align-right .bp3-control-indicator{
      margin-right:-38px; }
  .bp3-control.bp3-switch .bp3-control-indicator{
    border:none;
    border-radius:1.75em;
    -webkit-box-shadow:none !important;
            box-shadow:none !important;
    width:auto;
    min-width:1.75em;
    -webkit-transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-control.bp3-switch .bp3-control-indicator::before{
      position:absolute;
      left:0;
      margin:2px;
      border-radius:50%;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
      background:#ffffff;
      width:calc(1em - 4px);
      height:calc(1em - 4px);
      -webkit-transition:left 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
      transition:left 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator::before{
    left:calc(100% - 1em); }
  .bp3-control.bp3-switch.bp3-large:not(.bp3-align-right){
    padding-left:45px; }
    .bp3-control.bp3-switch.bp3-large:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-45px; }
  .bp3-control.bp3-switch.bp3-large.bp3-align-right{
    padding-right:45px; }
    .bp3-control.bp3-switch.bp3-large.bp3-align-right .bp3-control-indicator{
      margin-right:-45px; }
  .bp3-dark .bp3-control.bp3-switch input ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.5); }
  .bp3-dark .bp3-control.bp3-switch:hover input ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.7); }
  .bp3-dark .bp3-control.bp3-switch input:not(:disabled):active ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.9); }
  .bp3-dark .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator{
    background:rgba(57, 75, 89, 0.5); }
    .bp3-dark .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator::before{
      background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator{
    background:#137cbd; }
  .bp3-dark .bp3-control.bp3-switch:hover input:checked ~ .bp3-control-indicator{
    background:#106ba3; }
  .bp3-dark .bp3-control.bp3-switch input:checked:not(:disabled):active ~ .bp3-control-indicator{
    background:#0e5a8a; }
  .bp3-dark .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator{
    background:rgba(14, 90, 138, 0.5); }
    .bp3-dark .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator::before{
      background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch .bp3-control-indicator::before{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background:#394b59; }
  .bp3-dark .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator::before{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-control.bp3-switch .bp3-switch-inner-text{
    text-align:center;
    font-size:0.7em; }
  .bp3-control.bp3-switch .bp3-control-indicator-child:first-child{
    visibility:hidden;
    margin-right:1.2em;
    margin-left:0.5em;
    line-height:0; }
  .bp3-control.bp3-switch .bp3-control-indicator-child:last-child{
    visibility:visible;
    margin-right:0.5em;
    margin-left:1.2em;
    line-height:1em; }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator .bp3-control-indicator-child:first-child{
    visibility:visible;
    line-height:1em; }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator .bp3-control-indicator-child:last-child{
    visibility:hidden;
    line-height:0; }
  .bp3-dark .bp3-control{
    color:#f5f8fa; }
    .bp3-dark .bp3-control.bp3-disabled{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-control .bp3-control-indicator{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#394b59;
      background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
      background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0)); }
    .bp3-dark .bp3-control:hover .bp3-control-indicator{
      background-color:#30404d; }
    .bp3-dark .bp3-control input:not(:disabled):active ~ .bp3-control-indicator{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background:#202b33; }
    .bp3-dark .bp3-control input:disabled ~ .bp3-control-indicator{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      cursor:not-allowed; }
    .bp3-dark .bp3-control.bp3-checkbox input:disabled:checked ~ .bp3-control-indicator, .bp3-dark .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
      color:rgba(167, 182, 194, 0.6); }
.bp3-file-input{
  display:inline-block;
  position:relative;
  cursor:pointer;
  height:30px; }
  .bp3-file-input input{
    opacity:0;
    margin:0;
    min-width:200px; }
    .bp3-file-input input:disabled + .bp3-file-upload-input,
    .bp3-file-input input.bp3-disabled + .bp3-file-upload-input{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(206, 217, 224, 0.5);
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6);
      resize:none; }
      .bp3-file-input input:disabled + .bp3-file-upload-input::after,
      .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after{
        outline:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        background-color:rgba(206, 217, 224, 0.5);
        background-image:none;
        cursor:not-allowed;
        color:rgba(92, 112, 128, 0.6); }
        .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active, .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active:hover,
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active,
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active:hover{
          background:rgba(206, 217, 224, 0.7); }
      .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input, .bp3-dark
      .bp3-file-input input.bp3-disabled + .bp3-file-upload-input{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:rgba(57, 75, 89, 0.5);
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input::after, .bp3-dark
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after{
          -webkit-box-shadow:none;
                  box-shadow:none;
          background-color:rgba(57, 75, 89, 0.5);
          background-image:none;
          color:rgba(167, 182, 194, 0.6); }
          .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active, .bp3-dark
          .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active{
            background:rgba(57, 75, 89, 0.7); }
  .bp3-file-input.bp3-file-input-has-selection .bp3-file-upload-input{
    color:#182026; }
  .bp3-dark .bp3-file-input.bp3-file-input-has-selection .bp3-file-upload-input{
    color:#f5f8fa; }
  .bp3-file-input.bp3-fill{
    width:100%; }
  .bp3-file-input.bp3-large,
  .bp3-large .bp3-file-input{
    height:40px; }
  .bp3-file-input .bp3-file-upload-input-custom-text::after{
    content:attr(bp3-button-text); }

.bp3-file-upload-input{
  outline:none;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  height:30px;
  padding:0 10px;
  vertical-align:middle;
  line-height:30px;
  color:#182026;
  font-size:14px;
  font-weight:400;
  -webkit-transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  -webkit-appearance:none;
     -moz-appearance:none;
          appearance:none;
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  position:absolute;
  top:0;
  right:0;
  left:0;
  padding-right:80px;
  color:rgba(92, 112, 128, 0.6);
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-file-upload-input::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input:focus, .bp3-file-upload-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-file-upload-input[type="search"], .bp3-file-upload-input.bp3-round{
    border-radius:30px;
    -webkit-box-sizing:border-box;
            box-sizing:border-box;
    padding-left:10px; }
  .bp3-file-upload-input[readonly]{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-file-upload-input:disabled, .bp3-file-upload-input.bp3-disabled{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(206, 217, 224, 0.5);
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6);
    resize:none; }
  .bp3-file-upload-input::after{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    color:#182026;
    min-width:24px;
    min-height:24px;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    position:absolute;
    top:0;
    right:0;
    margin:3px;
    border-radius:3px;
    width:70px;
    text-align:center;
    line-height:24px;
    content:"Browse"; }
    .bp3-file-upload-input::after:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
      background-clip:padding-box;
      background-color:#ebf1f5; }
    .bp3-file-upload-input::after:active, .bp3-file-upload-input::after.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#d8e1e8;
      background-image:none; }
    .bp3-file-upload-input::after:disabled, .bp3-file-upload-input::after.bp3-disabled{
      outline:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(206, 217, 224, 0.5);
      background-image:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-file-upload-input::after:disabled.bp3-active, .bp3-file-upload-input::after:disabled.bp3-active:hover, .bp3-file-upload-input::after.bp3-disabled.bp3-active, .bp3-file-upload-input::after.bp3-disabled.bp3-active:hover{
        background:rgba(206, 217, 224, 0.7); }
  .bp3-file-upload-input:hover::after{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5; }
  .bp3-file-upload-input:active::after{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none; }
  .bp3-large .bp3-file-upload-input{
    height:40px;
    line-height:40px;
    font-size:16px;
    padding-right:95px; }
    .bp3-large .bp3-file-upload-input[type="search"], .bp3-large .bp3-file-upload-input.bp3-round{
      padding:0 15px; }
    .bp3-large .bp3-file-upload-input::after{
      min-width:30px;
      min-height:30px;
      margin:5px;
      width:85px;
      line-height:30px; }
  .bp3-dark .bp3-file-upload-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa;
    color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input:disabled, .bp3-dark .bp3-file-upload-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::after{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#394b59;
      background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
      background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
      color:#f5f8fa; }
      .bp3-dark .bp3-file-upload-input::after:hover, .bp3-dark .bp3-file-upload-input::after:active, .bp3-dark .bp3-file-upload-input::after.bp3-active{
        color:#f5f8fa; }
      .bp3-dark .bp3-file-upload-input::after:hover{
        -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
        background-color:#30404d; }
      .bp3-dark .bp3-file-upload-input::after:active, .bp3-dark .bp3-file-upload-input::after.bp3-active{
        -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
                box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
        background-color:#202b33;
        background-image:none; }
      .bp3-dark .bp3-file-upload-input::after:disabled, .bp3-dark .bp3-file-upload-input::after.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none;
        background-color:rgba(57, 75, 89, 0.5);
        background-image:none;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-file-upload-input::after:disabled.bp3-active, .bp3-dark .bp3-file-upload-input::after.bp3-disabled.bp3-active{
          background:rgba(57, 75, 89, 0.7); }
      .bp3-dark .bp3-file-upload-input::after .bp3-button-spinner .bp3-spinner-head{
        background:rgba(16, 22, 26, 0.5);
        stroke:#8a9ba8; }
    .bp3-dark .bp3-file-upload-input:hover::after{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#30404d; }
    .bp3-dark .bp3-file-upload-input:active::after{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#202b33;
      background-image:none; }

.bp3-file-upload-input::after{
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
.bp3-form-group{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:0 0 15px; }
  .bp3-form-group label.bp3-label{
    margin-bottom:5px; }
  .bp3-form-group .bp3-control{
    margin-top:7px; }
  .bp3-form-group .bp3-form-helper-text{
    margin-top:5px;
    color:#5c7080;
    font-size:12px; }
  .bp3-form-group.bp3-intent-primary .bp3-form-helper-text{
    color:#106ba3; }
  .bp3-form-group.bp3-intent-success .bp3-form-helper-text{
    color:#0d8050; }
  .bp3-form-group.bp3-intent-warning .bp3-form-helper-text{
    color:#bf7326; }
  .bp3-form-group.bp3-intent-danger .bp3-form-helper-text{
    color:#c23030; }
  .bp3-form-group.bp3-inline{
    -webkit-box-orient:horizontal;
    -webkit-box-direction:normal;
        -ms-flex-direction:row;
            flex-direction:row;
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
    .bp3-form-group.bp3-inline.bp3-large label.bp3-label{
      margin:0 10px 0 0;
      line-height:40px; }
    .bp3-form-group.bp3-inline label.bp3-label{
      margin:0 10px 0 0;
      line-height:30px; }
  .bp3-form-group.bp3-disabled .bp3-label,
  .bp3-form-group.bp3-disabled .bp3-text-muted,
  .bp3-form-group.bp3-disabled .bp3-form-helper-text{
    color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-dark .bp3-form-group.bp3-intent-primary .bp3-form-helper-text{
    color:#48aff0; }
  .bp3-dark .bp3-form-group.bp3-intent-success .bp3-form-helper-text{
    color:#3dcc91; }
  .bp3-dark .bp3-form-group.bp3-intent-warning .bp3-form-helper-text{
    color:#ffb366; }
  .bp3-dark .bp3-form-group.bp3-intent-danger .bp3-form-helper-text{
    color:#ff7373; }
  .bp3-dark .bp3-form-group .bp3-form-helper-text{
    color:#a7b6c2; }
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-label,
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-text-muted,
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-form-helper-text{
    color:rgba(167, 182, 194, 0.6) !important; }
.bp3-input-group{
  display:block;
  position:relative; }
  .bp3-input-group .bp3-input{
    position:relative;
    width:100%; }
    .bp3-input-group .bp3-input:not(:first-child){
      padding-left:30px; }
    .bp3-input-group .bp3-input:not(:last-child){
      padding-right:30px; }
  .bp3-input-group .bp3-input-action,
  .bp3-input-group > .bp3-button,
  .bp3-input-group > .bp3-icon{
    position:absolute;
    top:0; }
    .bp3-input-group .bp3-input-action:first-child,
    .bp3-input-group > .bp3-button:first-child,
    .bp3-input-group > .bp3-icon:first-child{
      left:0; }
    .bp3-input-group .bp3-input-action:last-child,
    .bp3-input-group > .bp3-button:last-child,
    .bp3-input-group > .bp3-icon:last-child{
      right:0; }
  .bp3-input-group .bp3-button{
    min-width:24px;
    min-height:24px;
    margin:3px;
    padding:0 7px; }
    .bp3-input-group .bp3-button:empty{
      padding:0; }
  .bp3-input-group > .bp3-icon{
    z-index:1;
    color:#5c7080; }
    .bp3-input-group > .bp3-icon:empty{
      line-height:1;
      font-family:"Icons16", sans-serif;
      font-size:16px;
      font-weight:400;
      font-style:normal;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased; }
  .bp3-input-group > .bp3-icon,
  .bp3-input-group .bp3-input-action > .bp3-spinner{
    margin:7px; }
  .bp3-input-group .bp3-tag{
    margin:5px; }
  .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus),
  .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus){
    color:#5c7080; }
    .bp3-dark .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus), .bp3-dark
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus){
      color:#a7b6c2; }
    .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-standard, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-large,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-standard,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-large{
      color:#5c7080; }
  .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled,
  .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled{
    color:rgba(92, 112, 128, 0.6) !important; }
    .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon-standard, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon-large,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon-standard,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon-large{
      color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-input-group.bp3-disabled{
    cursor:not-allowed; }
    .bp3-input-group.bp3-disabled .bp3-icon{
      color:rgba(92, 112, 128, 0.6); }
  .bp3-input-group.bp3-large .bp3-button{
    min-width:30px;
    min-height:30px;
    margin:5px; }
  .bp3-input-group.bp3-large > .bp3-icon,
  .bp3-input-group.bp3-large .bp3-input-action > .bp3-spinner{
    margin:12px; }
  .bp3-input-group.bp3-large .bp3-input{
    height:40px;
    line-height:40px;
    font-size:16px; }
    .bp3-input-group.bp3-large .bp3-input[type="search"], .bp3-input-group.bp3-large .bp3-input.bp3-round{
      padding:0 15px; }
    .bp3-input-group.bp3-large .bp3-input:not(:first-child){
      padding-left:40px; }
    .bp3-input-group.bp3-large .bp3-input:not(:last-child){
      padding-right:40px; }
  .bp3-input-group.bp3-small .bp3-button{
    min-width:20px;
    min-height:20px;
    margin:2px; }
  .bp3-input-group.bp3-small .bp3-tag{
    min-width:20px;
    min-height:20px;
    margin:2px; }
  .bp3-input-group.bp3-small > .bp3-icon,
  .bp3-input-group.bp3-small .bp3-input-action > .bp3-spinner{
    margin:4px; }
  .bp3-input-group.bp3-small .bp3-input{
    height:24px;
    padding-right:8px;
    padding-left:8px;
    line-height:24px;
    font-size:12px; }
    .bp3-input-group.bp3-small .bp3-input[type="search"], .bp3-input-group.bp3-small .bp3-input.bp3-round{
      padding:0 12px; }
    .bp3-input-group.bp3-small .bp3-input:not(:first-child){
      padding-left:24px; }
    .bp3-input-group.bp3-small .bp3-input:not(:last-child){
      padding-right:24px; }
  .bp3-input-group.bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:100%; }
  .bp3-input-group.bp3-round .bp3-button,
  .bp3-input-group.bp3-round .bp3-input,
  .bp3-input-group.bp3-round .bp3-tag{
    border-radius:30px; }
  .bp3-dark .bp3-input-group .bp3-icon{
    color:#a7b6c2; }
  .bp3-dark .bp3-input-group.bp3-disabled .bp3-icon{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-input-group.bp3-intent-primary .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-primary .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-primary .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #137cbd;
              box-shadow:inset 0 0 0 1px #137cbd; }
    .bp3-input-group.bp3-intent-primary .bp3-input:disabled, .bp3-input-group.bp3-intent-primary .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-primary > .bp3-icon{
    color:#106ba3; }
    .bp3-dark .bp3-input-group.bp3-intent-primary > .bp3-icon{
      color:#48aff0; }
  .bp3-input-group.bp3-intent-success .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-success .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-success .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #0f9960;
              box-shadow:inset 0 0 0 1px #0f9960; }
    .bp3-input-group.bp3-intent-success .bp3-input:disabled, .bp3-input-group.bp3-intent-success .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-success > .bp3-icon{
    color:#0d8050; }
    .bp3-dark .bp3-input-group.bp3-intent-success > .bp3-icon{
      color:#3dcc91; }
  .bp3-input-group.bp3-intent-warning .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-warning .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-warning .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #d9822b;
              box-shadow:inset 0 0 0 1px #d9822b; }
    .bp3-input-group.bp3-intent-warning .bp3-input:disabled, .bp3-input-group.bp3-intent-warning .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-warning > .bp3-icon{
    color:#bf7326; }
    .bp3-dark .bp3-input-group.bp3-intent-warning > .bp3-icon{
      color:#ffb366; }
  .bp3-input-group.bp3-intent-danger .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-danger .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-danger .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #db3737;
              box-shadow:inset 0 0 0 1px #db3737; }
    .bp3-input-group.bp3-intent-danger .bp3-input:disabled, .bp3-input-group.bp3-intent-danger .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-danger > .bp3-icon{
    color:#c23030; }
    .bp3-dark .bp3-input-group.bp3-intent-danger > .bp3-icon{
      color:#ff7373; }
.bp3-input{
  outline:none;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  height:30px;
  padding:0 10px;
  vertical-align:middle;
  line-height:30px;
  color:#182026;
  font-size:14px;
  font-weight:400;
  -webkit-transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  -webkit-appearance:none;
     -moz-appearance:none;
          appearance:none; }
  .bp3-input::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input:focus, .bp3-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-input[type="search"], .bp3-input.bp3-round{
    border-radius:30px;
    -webkit-box-sizing:border-box;
            box-sizing:border-box;
    padding-left:10px; }
  .bp3-input[readonly]{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-input:disabled, .bp3-input.bp3-disabled{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(206, 217, 224, 0.5);
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6);
    resize:none; }
  .bp3-input.bp3-large{
    height:40px;
    line-height:40px;
    font-size:16px; }
    .bp3-input.bp3-large[type="search"], .bp3-input.bp3-large.bp3-round{
      padding:0 15px; }
  .bp3-input.bp3-small{
    height:24px;
    padding-right:8px;
    padding-left:8px;
    line-height:24px;
    font-size:12px; }
    .bp3-input.bp3-small[type="search"], .bp3-input.bp3-small.bp3-round{
      padding:0 12px; }
  .bp3-input.bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:100%; }
  .bp3-dark .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa; }
    .bp3-dark .bp3-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-input:disabled, .bp3-dark .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      color:rgba(167, 182, 194, 0.6); }
  .bp3-input.bp3-intent-primary{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-primary:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-primary[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #137cbd;
              box-shadow:inset 0 0 0 1px #137cbd; }
    .bp3-input.bp3-intent-primary:disabled, .bp3-input.bp3-intent-primary.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-primary:focus{
        -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-primary[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #137cbd;
                box-shadow:inset 0 0 0 1px #137cbd; }
      .bp3-dark .bp3-input.bp3-intent-primary:disabled, .bp3-dark .bp3-input.bp3-intent-primary.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-success{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-success:focus{
      -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-success[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #0f9960;
              box-shadow:inset 0 0 0 1px #0f9960; }
    .bp3-input.bp3-intent-success:disabled, .bp3-input.bp3-intent-success.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-success{
      -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-success:focus{
        -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #0f9960, 0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-success[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #0f9960;
                box-shadow:inset 0 0 0 1px #0f9960; }
      .bp3-dark .bp3-input.bp3-intent-success:disabled, .bp3-dark .bp3-input.bp3-intent-success.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-warning{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-warning:focus{
      -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-warning[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #d9822b;
              box-shadow:inset 0 0 0 1px #d9822b; }
    .bp3-input.bp3-intent-warning:disabled, .bp3-input.bp3-intent-warning.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-warning:focus{
        -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #d9822b, 0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-warning[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #d9822b;
                box-shadow:inset 0 0 0 1px #d9822b; }
      .bp3-dark .bp3-input.bp3-intent-warning:disabled, .bp3-dark .bp3-input.bp3-intent-warning.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-danger{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-danger:focus{
      -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-danger[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #db3737;
              box-shadow:inset 0 0 0 1px #db3737; }
    .bp3-input.bp3-intent-danger:disabled, .bp3-input.bp3-intent-danger.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-danger:focus{
        -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #db3737, 0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-danger[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #db3737;
                box-shadow:inset 0 0 0 1px #db3737; }
      .bp3-dark .bp3-input.bp3-intent-danger:disabled, .bp3-dark .bp3-input.bp3-intent-danger.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input::-ms-clear{
    display:none; }
textarea.bp3-input{
  max-width:100%;
  padding:10px; }
  textarea.bp3-input, textarea.bp3-input.bp3-large, textarea.bp3-input.bp3-small{
    height:auto;
    line-height:inherit; }
  textarea.bp3-input.bp3-small{
    padding:8px; }
  .bp3-dark textarea.bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa; }
    .bp3-dark textarea.bp3-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark textarea.bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark textarea.bp3-input:disabled, .bp3-dark textarea.bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      color:rgba(167, 182, 194, 0.6); }
label.bp3-label{
  display:block;
  margin-top:0;
  margin-bottom:15px; }
  label.bp3-label .bp3-html-select,
  label.bp3-label .bp3-input,
  label.bp3-label .bp3-select,
  label.bp3-label .bp3-slider,
  label.bp3-label .bp3-popover-wrapper{
    display:block;
    margin-top:5px;
    text-transform:none; }
  label.bp3-label .bp3-button-group{
    margin-top:5px; }
  label.bp3-label .bp3-select select,
  label.bp3-label .bp3-html-select select{
    width:100%;
    vertical-align:top;
    font-weight:400; }
  label.bp3-label.bp3-disabled,
  label.bp3-label.bp3-disabled .bp3-text-muted{
    color:rgba(92, 112, 128, 0.6); }
  label.bp3-label.bp3-inline{
    line-height:30px; }
    label.bp3-label.bp3-inline .bp3-html-select,
    label.bp3-label.bp3-inline .bp3-input,
    label.bp3-label.bp3-inline .bp3-input-group,
    label.bp3-label.bp3-inline .bp3-select,
    label.bp3-label.bp3-inline .bp3-popover-wrapper{
      display:inline-block;
      margin:0 0 0 5px;
      vertical-align:top; }
    label.bp3-label.bp3-inline .bp3-button-group{
      margin:0 0 0 5px; }
    label.bp3-label.bp3-inline .bp3-input-group .bp3-input{
      margin-left:0; }
    label.bp3-label.bp3-inline.bp3-large{
      line-height:40px; }
  label.bp3-label:not(.bp3-inline) .bp3-popover-target{
    display:block; }
  .bp3-dark label.bp3-label{
    color:#f5f8fa; }
    .bp3-dark label.bp3-label.bp3-disabled,
    .bp3-dark label.bp3-label.bp3-disabled .bp3-text-muted{
      color:rgba(167, 182, 194, 0.6); }
.bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button{
  -webkit-box-flex:1;
      -ms-flex:1 1 14px;
          flex:1 1 14px;
  width:30px;
  min-height:0;
  padding:0; }
  .bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button:first-child{
    border-radius:0 3px 0 0; }
  .bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button:last-child{
    border-radius:0 0 3px 0; }

.bp3-numeric-input .bp3-button-group.bp3-vertical:first-child > .bp3-button:first-child{
  border-radius:3px 0 0 0; }

.bp3-numeric-input .bp3-button-group.bp3-vertical:first-child > .bp3-button:last-child{
  border-radius:0 0 0 3px; }

.bp3-numeric-input.bp3-large .bp3-button-group.bp3-vertical > .bp3-button{
  width:40px; }

form{
  display:block; }
.bp3-html-select select,
.bp3-select select{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  border:none;
  border-radius:3px;
  cursor:pointer;
  padding:5px 10px;
  vertical-align:middle;
  text-align:left;
  font-size:14px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
  background-color:#f5f8fa;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
  color:#182026;
  border-radius:3px;
  width:100%;
  height:30px;
  padding:0 25px 0 10px;
  -moz-appearance:none;
  -webkit-appearance:none; }
  .bp3-html-select select > *, .bp3-select select > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-html-select select > .bp3-fill, .bp3-select select > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-html-select select::before,
  .bp3-select select::before, .bp3-html-select select > *, .bp3-select select > *{
    margin-right:7px; }
  .bp3-html-select select:empty::before,
  .bp3-select select:empty::before,
  .bp3-html-select select > :last-child,
  .bp3-select select > :last-child{
    margin-right:0; }
  .bp3-html-select select:hover,
  .bp3-select select:hover{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5; }
  .bp3-html-select select:active,
  .bp3-select select:active, .bp3-html-select select.bp3-active,
  .bp3-select select.bp3-active{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none; }
  .bp3-html-select select:disabled,
  .bp3-select select:disabled, .bp3-html-select select.bp3-disabled,
  .bp3-select select.bp3-disabled{
    outline:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    background-color:rgba(206, 217, 224, 0.5);
    background-image:none;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
    .bp3-html-select select:disabled.bp3-active,
    .bp3-select select:disabled.bp3-active, .bp3-html-select select:disabled.bp3-active:hover,
    .bp3-select select:disabled.bp3-active:hover, .bp3-html-select select.bp3-disabled.bp3-active,
    .bp3-select select.bp3-disabled.bp3-active, .bp3-html-select select.bp3-disabled.bp3-active:hover,
    .bp3-select select.bp3-disabled.bp3-active:hover{
      background:rgba(206, 217, 224, 0.7); }

.bp3-html-select.bp3-minimal select,
.bp3-select.bp3-minimal select{
  -webkit-box-shadow:none;
          box-shadow:none;
  background:none; }
  .bp3-html-select.bp3-minimal select:hover,
  .bp3-select.bp3-minimal select:hover{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(167, 182, 194, 0.3);
    text-decoration:none;
    color:#182026; }
  .bp3-html-select.bp3-minimal select:active,
  .bp3-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal select.bp3-active,
  .bp3-select.bp3-minimal select.bp3-active{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(115, 134, 148, 0.3);
    color:#182026; }
  .bp3-html-select.bp3-minimal select:disabled,
  .bp3-select.bp3-minimal select:disabled, .bp3-html-select.bp3-minimal select:disabled:hover,
  .bp3-select.bp3-minimal select:disabled:hover, .bp3-html-select.bp3-minimal select.bp3-disabled,
  .bp3-select.bp3-minimal select.bp3-disabled, .bp3-html-select.bp3-minimal select.bp3-disabled:hover,
  .bp3-select.bp3-minimal select.bp3-disabled:hover{
    background:none;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
    .bp3-html-select.bp3-minimal select:disabled.bp3-active,
    .bp3-select.bp3-minimal select:disabled.bp3-active, .bp3-html-select.bp3-minimal select:disabled:hover.bp3-active,
    .bp3-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-html-select.bp3-minimal select.bp3-disabled.bp3-active,
    .bp3-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-disabled:hover.bp3-active,
    .bp3-select.bp3-minimal select.bp3-disabled:hover.bp3-active{
      background:rgba(115, 134, 148, 0.3); }
  .bp3-dark .bp3-html-select.bp3-minimal select, .bp3-html-select.bp3-minimal .bp3-dark select,
  .bp3-dark .bp3-select.bp3-minimal select, .bp3-select.bp3-minimal .bp3-dark select{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none;
    color:inherit; }
    .bp3-dark .bp3-html-select.bp3-minimal select:hover, .bp3-html-select.bp3-minimal .bp3-dark select:hover,
    .bp3-dark .bp3-select.bp3-minimal select:hover, .bp3-select.bp3-minimal .bp3-dark select:hover, .bp3-dark .bp3-html-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal .bp3-dark select:active,
    .bp3-dark .bp3-select.bp3-minimal select:active, .bp3-select.bp3-minimal .bp3-dark select:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-active,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none; }
    .bp3-dark .bp3-html-select.bp3-minimal select:hover, .bp3-html-select.bp3-minimal .bp3-dark select:hover,
    .bp3-dark .bp3-select.bp3-minimal select:hover, .bp3-select.bp3-minimal .bp3-dark select:hover{
      background:rgba(138, 155, 168, 0.15); }
    .bp3-dark .bp3-html-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal .bp3-dark select:active,
    .bp3-dark .bp3-select.bp3-minimal select:active, .bp3-select.bp3-minimal .bp3-dark select:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-active,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-active{
      background:rgba(138, 155, 168, 0.3);
      color:#f5f8fa; }
    .bp3-dark .bp3-html-select.bp3-minimal select:disabled, .bp3-html-select.bp3-minimal .bp3-dark select:disabled,
    .bp3-dark .bp3-select.bp3-minimal select:disabled, .bp3-select.bp3-minimal .bp3-dark select:disabled, .bp3-dark .bp3-html-select.bp3-minimal select:disabled:hover, .bp3-html-select.bp3-minimal .bp3-dark select:disabled:hover,
    .bp3-dark .bp3-select.bp3-minimal select:disabled:hover, .bp3-select.bp3-minimal .bp3-dark select:disabled:hover, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled:hover,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled:hover{
      background:none;
      cursor:not-allowed;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-html-select.bp3-minimal select:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select:disabled.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select:disabled:hover.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-select.bp3-minimal .bp3-dark select:disabled:hover.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled:hover.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled:hover.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled:hover.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled:hover.bp3-active{
        background:rgba(138, 155, 168, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-primary,
  .bp3-select.bp3-minimal select.bp3-intent-primary{
    color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover,
    .bp3-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-html-select.bp3-minimal select.bp3-intent-primary:active,
    .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover,
    .bp3-select.bp3-minimal select.bp3-intent-primary:hover{
      background:rgba(19, 124, 189, 0.15);
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:active,
    .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active{
      background:rgba(19, 124, 189, 0.3);
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled{
      background:none;
      color:rgba(16, 107, 163, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active{
        background:rgba(19, 124, 189, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
      stroke:#106ba3; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary{
      color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.2);
        color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(72, 175, 240, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-success,
  .bp3-select.bp3-minimal select.bp3-intent-success{
    color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:hover,
    .bp3-select.bp3-minimal select.bp3-intent-success:hover, .bp3-html-select.bp3-minimal select.bp3-intent-success:active,
    .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:hover,
    .bp3-select.bp3-minimal select.bp3-intent-success:hover{
      background:rgba(15, 153, 96, 0.15);
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:active,
    .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active{
      background:rgba(15, 153, 96, 0.3);
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled{
      background:none;
      color:rgba(13, 128, 80, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active{
        background:rgba(15, 153, 96, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-success .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
      stroke:#0d8050; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success{
      color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.2);
        color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(61, 204, 145, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-warning,
  .bp3-select.bp3-minimal select.bp3-intent-warning{
    color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover,
    .bp3-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-html-select.bp3-minimal select.bp3-intent-warning:active,
    .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover,
    .bp3-select.bp3-minimal select.bp3-intent-warning:hover{
      background:rgba(217, 130, 43, 0.15);
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:active,
    .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active{
      background:rgba(217, 130, 43, 0.3);
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled{
      background:none;
      color:rgba(191, 115, 38, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active{
        background:rgba(217, 130, 43, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
      stroke:#bf7326; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning{
      color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.2);
        color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(255, 179, 102, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-danger,
  .bp3-select.bp3-minimal select.bp3-intent-danger{
    color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover,
    .bp3-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-html-select.bp3-minimal select.bp3-intent-danger:active,
    .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover,
    .bp3-select.bp3-minimal select.bp3-intent-danger:hover{
      background:rgba(219, 55, 55, 0.15);
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:active,
    .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active{
      background:rgba(219, 55, 55, 0.3);
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled{
      background:none;
      color:rgba(194, 48, 48, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active{
        background:rgba(219, 55, 55, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
      stroke:#c23030; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger{
      color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.2);
        color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(255, 115, 115, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }

.bp3-html-select.bp3-large select,
.bp3-select.bp3-large select{
  height:40px;
  padding-right:35px;
  font-size:16px; }

.bp3-dark .bp3-html-select select, .bp3-dark .bp3-select select{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
  background-color:#394b59;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
  color:#f5f8fa; }
  .bp3-dark .bp3-html-select select:hover, .bp3-dark .bp3-select select:hover, .bp3-dark .bp3-html-select select:active, .bp3-dark .bp3-select select:active, .bp3-dark .bp3-html-select select.bp3-active, .bp3-dark .bp3-select select.bp3-active{
    color:#f5f8fa; }
  .bp3-dark .bp3-html-select select:hover, .bp3-dark .bp3-select select:hover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#30404d; }
  .bp3-dark .bp3-html-select select:active, .bp3-dark .bp3-select select:active, .bp3-dark .bp3-html-select select.bp3-active, .bp3-dark .bp3-select select.bp3-active{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#202b33;
    background-image:none; }
  .bp3-dark .bp3-html-select select:disabled, .bp3-dark .bp3-select select:disabled, .bp3-dark .bp3-html-select select.bp3-disabled, .bp3-dark .bp3-select select.bp3-disabled{
    -webkit-box-shadow:none;
            box-shadow:none;
    background-color:rgba(57, 75, 89, 0.5);
    background-image:none;
    color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-html-select select:disabled.bp3-active, .bp3-dark .bp3-select select:disabled.bp3-active, .bp3-dark .bp3-html-select select.bp3-disabled.bp3-active, .bp3-dark .bp3-select select.bp3-disabled.bp3-active{
      background:rgba(57, 75, 89, 0.7); }
  .bp3-dark .bp3-html-select select .bp3-button-spinner .bp3-spinner-head, .bp3-dark .bp3-select select .bp3-button-spinner .bp3-spinner-head{
    background:rgba(16, 22, 26, 0.5);
    stroke:#8a9ba8; }

.bp3-html-select select:disabled,
.bp3-select select:disabled{
  -webkit-box-shadow:none;
          box-shadow:none;
  background-color:rgba(206, 217, 224, 0.5);
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-html-select .bp3-icon,
.bp3-select .bp3-icon, .bp3-select::after{
  position:absolute;
  top:7px;
  right:7px;
  color:#5c7080;
  pointer-events:none; }
  .bp3-html-select .bp3-disabled.bp3-icon,
  .bp3-select .bp3-disabled.bp3-icon, .bp3-disabled.bp3-select::after{
    color:rgba(92, 112, 128, 0.6); }
.bp3-html-select,
.bp3-select{
  display:inline-block;
  position:relative;
  vertical-align:middle;
  letter-spacing:normal; }
  .bp3-html-select select::-ms-expand,
  .bp3-select select::-ms-expand{
    display:none; }
  .bp3-html-select .bp3-icon,
  .bp3-select .bp3-icon{
    color:#5c7080; }
    .bp3-html-select .bp3-icon:hover,
    .bp3-select .bp3-icon:hover{
      color:#182026; }
    .bp3-dark .bp3-html-select .bp3-icon, .bp3-dark
    .bp3-select .bp3-icon{
      color:#a7b6c2; }
      .bp3-dark .bp3-html-select .bp3-icon:hover, .bp3-dark
      .bp3-select .bp3-icon:hover{
        color:#f5f8fa; }
  .bp3-html-select.bp3-large::after,
  .bp3-html-select.bp3-large .bp3-icon,
  .bp3-select.bp3-large::after,
  .bp3-select.bp3-large .bp3-icon{
    top:12px;
    right:12px; }
  .bp3-html-select.bp3-fill,
  .bp3-html-select.bp3-fill select,
  .bp3-select.bp3-fill,
  .bp3-select.bp3-fill select{
    width:100%; }
  .bp3-dark .bp3-html-select option, .bp3-dark
  .bp3-select option{
    background-color:#30404d;
    color:#f5f8fa; }
  .bp3-dark .bp3-html-select::after, .bp3-dark
  .bp3-select::after{
    color:#a7b6c2; }

.bp3-select::after{
  line-height:1;
  font-family:"Icons16", sans-serif;
  font-size:16px;
  font-weight:400;
  font-style:normal;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  content:""; }
.bp3-running-text table, table.bp3-html-table{
  border-spacing:0;
  font-size:14px; }
  .bp3-running-text table th, table.bp3-html-table th,
  .bp3-running-text table td,
  table.bp3-html-table td{
    padding:11px;
    vertical-align:top;
    text-align:left; }
  .bp3-running-text table th, table.bp3-html-table th{
    color:#182026;
    font-weight:600; }
  
  .bp3-running-text table td,
  table.bp3-html-table td{
    color:#182026; }
  .bp3-running-text table tbody tr:first-child th, table.bp3-html-table tbody tr:first-child th,
  .bp3-running-text table tbody tr:first-child td,
  table.bp3-html-table tbody tr:first-child td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-running-text table th, .bp3-running-text .bp3-dark table th, .bp3-dark table.bp3-html-table th{
    color:#f5f8fa; }
  .bp3-dark .bp3-running-text table td, .bp3-running-text .bp3-dark table td, .bp3-dark table.bp3-html-table td{
    color:#f5f8fa; }
  .bp3-dark .bp3-running-text table tbody tr:first-child th, .bp3-running-text .bp3-dark table tbody tr:first-child th, .bp3-dark table.bp3-html-table tbody tr:first-child th,
  .bp3-dark .bp3-running-text table tbody tr:first-child td,
  .bp3-running-text .bp3-dark table tbody tr:first-child td,
  .bp3-dark table.bp3-html-table tbody tr:first-child td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15); }

table.bp3-html-table.bp3-html-table-condensed th,
table.bp3-html-table.bp3-html-table-condensed td, table.bp3-html-table.bp3-small th,
table.bp3-html-table.bp3-small td{
  padding-top:6px;
  padding-bottom:6px; }

table.bp3-html-table.bp3-html-table-striped tbody tr:nth-child(odd) td{
  background:rgba(191, 204, 214, 0.15); }

table.bp3-html-table.bp3-html-table-bordered th:not(:first-child){
  -webkit-box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-html-table-bordered tbody tr td{
  -webkit-box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15); }
  table.bp3-html-table.bp3-html-table-bordered tbody tr td:not(:first-child){
    -webkit-box-shadow:inset 1px 1px 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 1px 1px 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td{
  -webkit-box-shadow:none;
          box-shadow:none; }
  table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td:not(:first-child){
    -webkit-box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-interactive tbody tr:hover td{
  background-color:rgba(191, 204, 214, 0.3);
  cursor:pointer; }

table.bp3-html-table.bp3-interactive tbody tr:active td{
  background-color:rgba(191, 204, 214, 0.4); }

.bp3-dark table.bp3-html-table.bp3-html-table-striped tbody tr:nth-child(odd) td{
  background:rgba(92, 112, 128, 0.15); }

.bp3-dark table.bp3-html-table.bp3-html-table-bordered th:not(:first-child){
  -webkit-box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15); }

.bp3-dark table.bp3-html-table.bp3-html-table-bordered tbody tr td{
  -webkit-box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15);
          box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered tbody tr td:not(:first-child){
    -webkit-box-shadow:inset 1px 1px 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 1px 1px 0 0 rgba(255, 255, 255, 0.15); }

.bp3-dark table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td{
  -webkit-box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td:first-child{
    -webkit-box-shadow:none;
            box-shadow:none; }

.bp3-dark table.bp3-html-table.bp3-interactive tbody tr:hover td{
  background-color:rgba(92, 112, 128, 0.3);
  cursor:pointer; }

.bp3-dark table.bp3-html-table.bp3-interactive tbody tr:active td{
  background-color:rgba(92, 112, 128, 0.4); }

.bp3-key-combo{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center; }
  .bp3-key-combo > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-key-combo > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-key-combo::before,
  .bp3-key-combo > *{
    margin-right:5px; }
  .bp3-key-combo:empty::before,
  .bp3-key-combo > :last-child{
    margin-right:0; }

.bp3-hotkey-dialog{
  top:40px;
  padding-bottom:0; }
  .bp3-hotkey-dialog .bp3-dialog-body{
    margin:0;
    padding:0; }
  .bp3-hotkey-dialog .bp3-hotkey-label{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1; }

.bp3-hotkey-column{
  margin:auto;
  max-height:80vh;
  overflow-y:auto;
  padding:30px; }
  .bp3-hotkey-column .bp3-heading{
    margin-bottom:20px; }
    .bp3-hotkey-column .bp3-heading:not(:first-child){
      margin-top:40px; }

.bp3-hotkey{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:justify;
      -ms-flex-pack:justify;
          justify-content:space-between;
  margin-right:0;
  margin-left:0; }
  .bp3-hotkey:not(:last-child){
    margin-bottom:10px; }
.bp3-icon{
  display:inline-block;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  vertical-align:text-bottom; }
  .bp3-icon:not(:empty)::before{
    content:"" !important;
    content:unset !important; }
  .bp3-icon > svg{
    display:block; }
    .bp3-icon > svg:not([fill]){
      fill:currentColor; }

.bp3-icon.bp3-intent-primary, .bp3-icon-standard.bp3-intent-primary, .bp3-icon-large.bp3-intent-primary{
  color:#106ba3; }
  .bp3-dark .bp3-icon.bp3-intent-primary, .bp3-dark .bp3-icon-standard.bp3-intent-primary, .bp3-dark .bp3-icon-large.bp3-intent-primary{
    color:#48aff0; }

.bp3-icon.bp3-intent-success, .bp3-icon-standard.bp3-intent-success, .bp3-icon-large.bp3-intent-success{
  color:#0d8050; }
  .bp3-dark .bp3-icon.bp3-intent-success, .bp3-dark .bp3-icon-standard.bp3-intent-success, .bp3-dark .bp3-icon-large.bp3-intent-success{
    color:#3dcc91; }

.bp3-icon.bp3-intent-warning, .bp3-icon-standard.bp3-intent-warning, .bp3-icon-large.bp3-intent-warning{
  color:#bf7326; }
  .bp3-dark .bp3-icon.bp3-intent-warning, .bp3-dark .bp3-icon-standard.bp3-intent-warning, .bp3-dark .bp3-icon-large.bp3-intent-warning{
    color:#ffb366; }

.bp3-icon.bp3-intent-danger, .bp3-icon-standard.bp3-intent-danger, .bp3-icon-large.bp3-intent-danger{
  color:#c23030; }
  .bp3-dark .bp3-icon.bp3-intent-danger, .bp3-dark .bp3-icon-standard.bp3-intent-danger, .bp3-dark .bp3-icon-large.bp3-intent-danger{
    color:#ff7373; }

span.bp3-icon-standard{
  line-height:1;
  font-family:"Icons16", sans-serif;
  font-size:16px;
  font-weight:400;
  font-style:normal;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  display:inline-block; }

span.bp3-icon-large{
  line-height:1;
  font-family:"Icons20", sans-serif;
  font-size:20px;
  font-weight:400;
  font-style:normal;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  display:inline-block; }

span.bp3-icon:empty{
  line-height:1;
  font-family:"Icons20";
  font-size:inherit;
  font-weight:400;
  font-style:normal; }
  span.bp3-icon:empty::before{
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased; }

.bp3-icon-add::before{
  content:""; }

.bp3-icon-add-column-left::before{
  content:""; }

.bp3-icon-add-column-right::before{
  content:""; }

.bp3-icon-add-row-bottom::before{
  content:""; }

.bp3-icon-add-row-top::before{
  content:""; }

.bp3-icon-add-to-artifact::before{
  content:""; }

.bp3-icon-add-to-folder::before{
  content:""; }

.bp3-icon-airplane::before{
  content:""; }

.bp3-icon-align-center::before{
  content:""; }

.bp3-icon-align-justify::before{
  content:""; }

.bp3-icon-align-left::before{
  content:""; }

.bp3-icon-align-right::before{
  content:""; }

.bp3-icon-alignment-bottom::before{
  content:""; }

.bp3-icon-alignment-horizontal-center::before{
  content:""; }

.bp3-icon-alignment-left::before{
  content:""; }

.bp3-icon-alignment-right::before{
  content:""; }

.bp3-icon-alignment-top::before{
  content:""; }

.bp3-icon-alignment-vertical-center::before{
  content:""; }

.bp3-icon-annotation::before{
  content:""; }

.bp3-icon-application::before{
  content:""; }

.bp3-icon-applications::before{
  content:""; }

.bp3-icon-archive::before{
  content:""; }

.bp3-icon-arrow-bottom-left::before{
  content:"↙"; }

.bp3-icon-arrow-bottom-right::before{
  content:"↘"; }

.bp3-icon-arrow-down::before{
  content:"↓"; }

.bp3-icon-arrow-left::before{
  content:"←"; }

.bp3-icon-arrow-right::before{
  content:"→"; }

.bp3-icon-arrow-top-left::before{
  content:"↖"; }

.bp3-icon-arrow-top-right::before{
  content:"↗"; }

.bp3-icon-arrow-up::before{
  content:"↑"; }

.bp3-icon-arrows-horizontal::before{
  content:"↔"; }

.bp3-icon-arrows-vertical::before{
  content:"↕"; }

.bp3-icon-asterisk::before{
  content:"*"; }

.bp3-icon-automatic-updates::before{
  content:""; }

.bp3-icon-badge::before{
  content:""; }

.bp3-icon-ban-circle::before{
  content:""; }

.bp3-icon-bank-account::before{
  content:""; }

.bp3-icon-barcode::before{
  content:""; }

.bp3-icon-blank::before{
  content:""; }

.bp3-icon-blocked-person::before{
  content:""; }

.bp3-icon-bold::before{
  content:""; }

.bp3-icon-book::before{
  content:""; }

.bp3-icon-bookmark::before{
  content:""; }

.bp3-icon-box::before{
  content:""; }

.bp3-icon-briefcase::before{
  content:""; }

.bp3-icon-bring-data::before{
  content:""; }

.bp3-icon-build::before{
  content:""; }

.bp3-icon-calculator::before{
  content:""; }

.bp3-icon-calendar::before{
  content:""; }

.bp3-icon-camera::before{
  content:""; }

.bp3-icon-caret-down::before{
  content:"⌄"; }

.bp3-icon-caret-left::before{
  content:"〈"; }

.bp3-icon-caret-right::before{
  content:"〉"; }

.bp3-icon-caret-up::before{
  content:"⌃"; }

.bp3-icon-cell-tower::before{
  content:""; }

.bp3-icon-changes::before{
  content:""; }

.bp3-icon-chart::before{
  content:""; }

.bp3-icon-chat::before{
  content:""; }

.bp3-icon-chevron-backward::before{
  content:""; }

.bp3-icon-chevron-down::before{
  content:""; }

.bp3-icon-chevron-forward::before{
  content:""; }

.bp3-icon-chevron-left::before{
  content:""; }

.bp3-icon-chevron-right::before{
  content:""; }

.bp3-icon-chevron-up::before{
  content:""; }

.bp3-icon-circle::before{
  content:""; }

.bp3-icon-circle-arrow-down::before{
  content:""; }

.bp3-icon-circle-arrow-left::before{
  content:""; }

.bp3-icon-circle-arrow-right::before{
  content:""; }

.bp3-icon-circle-arrow-up::before{
  content:""; }

.bp3-icon-citation::before{
  content:""; }

.bp3-icon-clean::before{
  content:""; }

.bp3-icon-clipboard::before{
  content:""; }

.bp3-icon-cloud::before{
  content:"☁"; }

.bp3-icon-cloud-download::before{
  content:""; }

.bp3-icon-cloud-upload::before{
  content:""; }

.bp3-icon-code::before{
  content:""; }

.bp3-icon-code-block::before{
  content:""; }

.bp3-icon-cog::before{
  content:""; }

.bp3-icon-collapse-all::before{
  content:""; }

.bp3-icon-column-layout::before{
  content:""; }

.bp3-icon-comment::before{
  content:""; }

.bp3-icon-comparison::before{
  content:""; }

.bp3-icon-compass::before{
  content:""; }

.bp3-icon-compressed::before{
  content:""; }

.bp3-icon-confirm::before{
  content:""; }

.bp3-icon-console::before{
  content:""; }

.bp3-icon-contrast::before{
  content:""; }

.bp3-icon-control::before{
  content:""; }

.bp3-icon-credit-card::before{
  content:""; }

.bp3-icon-cross::before{
  content:"✗"; }

.bp3-icon-crown::before{
  content:""; }

.bp3-icon-cube::before{
  content:""; }

.bp3-icon-cube-add::before{
  content:""; }

.bp3-icon-cube-remove::before{
  content:""; }

.bp3-icon-curved-range-chart::before{
  content:""; }

.bp3-icon-cut::before{
  content:""; }

.bp3-icon-dashboard::before{
  content:""; }

.bp3-icon-data-lineage::before{
  content:""; }

.bp3-icon-database::before{
  content:""; }

.bp3-icon-delete::before{
  content:""; }

.bp3-icon-delta::before{
  content:"Δ"; }

.bp3-icon-derive-column::before{
  content:""; }

.bp3-icon-desktop::before{
  content:""; }

.bp3-icon-diagram-tree::before{
  content:""; }

.bp3-icon-direction-left::before{
  content:""; }

.bp3-icon-direction-right::before{
  content:""; }

.bp3-icon-disable::before{
  content:""; }

.bp3-icon-document::before{
  content:""; }

.bp3-icon-document-open::before{
  content:""; }

.bp3-icon-document-share::before{
  content:""; }

.bp3-icon-dollar::before{
  content:"$"; }

.bp3-icon-dot::before{
  content:"•"; }

.bp3-icon-double-caret-horizontal::before{
  content:""; }

.bp3-icon-double-caret-vertical::before{
  content:""; }

.bp3-icon-double-chevron-down::before{
  content:""; }

.bp3-icon-double-chevron-left::before{
  content:""; }

.bp3-icon-double-chevron-right::before{
  content:""; }

.bp3-icon-double-chevron-up::before{
  content:""; }

.bp3-icon-doughnut-chart::before{
  content:""; }

.bp3-icon-download::before{
  content:""; }

.bp3-icon-drag-handle-horizontal::before{
  content:""; }

.bp3-icon-drag-handle-vertical::before{
  content:""; }

.bp3-icon-draw::before{
  content:""; }

.bp3-icon-drive-time::before{
  content:""; }

.bp3-icon-duplicate::before{
  content:""; }

.bp3-icon-edit::before{
  content:"✎"; }

.bp3-icon-eject::before{
  content:"⏏"; }

.bp3-icon-endorsed::before{
  content:""; }

.bp3-icon-envelope::before{
  content:"✉"; }

.bp3-icon-equals::before{
  content:""; }

.bp3-icon-eraser::before{
  content:""; }

.bp3-icon-error::before{
  content:""; }

.bp3-icon-euro::before{
  content:"€"; }

.bp3-icon-exchange::before{
  content:""; }

.bp3-icon-exclude-row::before{
  content:""; }

.bp3-icon-expand-all::before{
  content:""; }

.bp3-icon-export::before{
  content:""; }

.bp3-icon-eye-off::before{
  content:""; }

.bp3-icon-eye-on::before{
  content:""; }

.bp3-icon-eye-open::before{
  content:""; }

.bp3-icon-fast-backward::before{
  content:""; }

.bp3-icon-fast-forward::before{
  content:""; }

.bp3-icon-feed::before{
  content:""; }

.bp3-icon-feed-subscribed::before{
  content:""; }

.bp3-icon-film::before{
  content:""; }

.bp3-icon-filter::before{
  content:""; }

.bp3-icon-filter-keep::before{
  content:""; }

.bp3-icon-filter-list::before{
  content:""; }

.bp3-icon-filter-open::before{
  content:""; }

.bp3-icon-filter-remove::before{
  content:""; }

.bp3-icon-flag::before{
  content:"⚑"; }

.bp3-icon-flame::before{
  content:""; }

.bp3-icon-flash::before{
  content:""; }

.bp3-icon-floppy-disk::before{
  content:""; }

.bp3-icon-flow-branch::before{
  content:""; }

.bp3-icon-flow-end::before{
  content:""; }

.bp3-icon-flow-linear::before{
  content:""; }

.bp3-icon-flow-review::before{
  content:""; }

.bp3-icon-flow-review-branch::before{
  content:""; }

.bp3-icon-flows::before{
  content:""; }

.bp3-icon-folder-close::before{
  content:""; }

.bp3-icon-folder-new::before{
  content:""; }

.bp3-icon-folder-open::before{
  content:""; }

.bp3-icon-folder-shared::before{
  content:""; }

.bp3-icon-folder-shared-open::before{
  content:""; }

.bp3-icon-follower::before{
  content:""; }

.bp3-icon-following::before{
  content:""; }

.bp3-icon-font::before{
  content:""; }

.bp3-icon-fork::before{
  content:""; }

.bp3-icon-form::before{
  content:""; }

.bp3-icon-full-circle::before{
  content:""; }

.bp3-icon-full-stacked-chart::before{
  content:""; }

.bp3-icon-fullscreen::before{
  content:""; }

.bp3-icon-function::before{
  content:""; }

.bp3-icon-gantt-chart::before{
  content:""; }

.bp3-icon-geolocation::before{
  content:""; }

.bp3-icon-geosearch::before{
  content:""; }

.bp3-icon-git-branch::before{
  content:""; }

.bp3-icon-git-commit::before{
  content:""; }

.bp3-icon-git-merge::before{
  content:""; }

.bp3-icon-git-new-branch::before{
  content:""; }

.bp3-icon-git-pull::before{
  content:""; }

.bp3-icon-git-push::before{
  content:""; }

.bp3-icon-git-repo::before{
  content:""; }

.bp3-icon-glass::before{
  content:""; }

.bp3-icon-globe::before{
  content:""; }

.bp3-icon-globe-network::before{
  content:""; }

.bp3-icon-graph::before{
  content:""; }

.bp3-icon-graph-remove::before{
  content:""; }

.bp3-icon-greater-than::before{
  content:""; }

.bp3-icon-greater-than-or-equal-to::before{
  content:""; }

.bp3-icon-grid::before{
  content:""; }

.bp3-icon-grid-view::before{
  content:""; }

.bp3-icon-group-objects::before{
  content:""; }

.bp3-icon-grouped-bar-chart::before{
  content:""; }

.bp3-icon-hand::before{
  content:""; }

.bp3-icon-hand-down::before{
  content:""; }

.bp3-icon-hand-left::before{
  content:""; }

.bp3-icon-hand-right::before{
  content:""; }

.bp3-icon-hand-up::before{
  content:""; }

.bp3-icon-header::before{
  content:""; }

.bp3-icon-header-one::before{
  content:""; }

.bp3-icon-header-two::before{
  content:""; }

.bp3-icon-headset::before{
  content:""; }

.bp3-icon-heart::before{
  content:"♥"; }

.bp3-icon-heart-broken::before{
  content:""; }

.bp3-icon-heat-grid::before{
  content:""; }

.bp3-icon-heatmap::before{
  content:""; }

.bp3-icon-help::before{
  content:"?"; }

.bp3-icon-helper-management::before{
  content:""; }

.bp3-icon-highlight::before{
  content:""; }

.bp3-icon-history::before{
  content:""; }

.bp3-icon-home::before{
  content:"⌂"; }

.bp3-icon-horizontal-bar-chart::before{
  content:""; }

.bp3-icon-horizontal-bar-chart-asc::before{
  content:""; }

.bp3-icon-horizontal-bar-chart-desc::before{
  content:""; }

.bp3-icon-horizontal-distribution::before{
  content:""; }

.bp3-icon-id-number::before{
  content:""; }

.bp3-icon-image-rotate-left::before{
  content:""; }

.bp3-icon-image-rotate-right::before{
  content:""; }

.bp3-icon-import::before{
  content:""; }

.bp3-icon-inbox::before{
  content:""; }

.bp3-icon-inbox-filtered::before{
  content:""; }

.bp3-icon-inbox-geo::before{
  content:""; }

.bp3-icon-inbox-search::before{
  content:""; }

.bp3-icon-inbox-update::before{
  content:""; }

.bp3-icon-info-sign::before{
  content:"ℹ"; }

.bp3-icon-inheritance::before{
  content:""; }

.bp3-icon-inner-join::before{
  content:""; }

.bp3-icon-insert::before{
  content:""; }

.bp3-icon-intersection::before{
  content:""; }

.bp3-icon-ip-address::before{
  content:""; }

.bp3-icon-issue::before{
  content:""; }

.bp3-icon-issue-closed::before{
  content:""; }

.bp3-icon-issue-new::before{
  content:""; }

.bp3-icon-italic::before{
  content:""; }

.bp3-icon-join-table::before{
  content:""; }

.bp3-icon-key::before{
  content:""; }

.bp3-icon-key-backspace::before{
  content:""; }

.bp3-icon-key-command::before{
  content:""; }

.bp3-icon-key-control::before{
  content:""; }

.bp3-icon-key-delete::before{
  content:""; }

.bp3-icon-key-enter::before{
  content:""; }

.bp3-icon-key-escape::before{
  content:""; }

.bp3-icon-key-option::before{
  content:""; }

.bp3-icon-key-shift::before{
  content:""; }

.bp3-icon-key-tab::before{
  content:""; }

.bp3-icon-known-vehicle::before{
  content:""; }

.bp3-icon-label::before{
  content:""; }

.bp3-icon-layer::before{
  content:""; }

.bp3-icon-layers::before{
  content:""; }

.bp3-icon-layout::before{
  content:""; }

.bp3-icon-layout-auto::before{
  content:""; }

.bp3-icon-layout-balloon::before{
  content:""; }

.bp3-icon-layout-circle::before{
  content:""; }

.bp3-icon-layout-grid::before{
  content:""; }

.bp3-icon-layout-group-by::before{
  content:""; }

.bp3-icon-layout-hierarchy::before{
  content:""; }

.bp3-icon-layout-linear::before{
  content:""; }

.bp3-icon-layout-skew-grid::before{
  content:""; }

.bp3-icon-layout-sorted-clusters::before{
  content:""; }

.bp3-icon-learning::before{
  content:""; }

.bp3-icon-left-join::before{
  content:""; }

.bp3-icon-less-than::before{
  content:""; }

.bp3-icon-less-than-or-equal-to::before{
  content:""; }

.bp3-icon-lifesaver::before{
  content:""; }

.bp3-icon-lightbulb::before{
  content:""; }

.bp3-icon-link::before{
  content:""; }

.bp3-icon-list::before{
  content:"☰"; }

.bp3-icon-list-columns::before{
  content:""; }

.bp3-icon-list-detail-view::before{
  content:""; }

.bp3-icon-locate::before{
  content:""; }

.bp3-icon-lock::before{
  content:""; }

.bp3-icon-log-in::before{
  content:""; }

.bp3-icon-log-out::before{
  content:""; }

.bp3-icon-manual::before{
  content:""; }

.bp3-icon-manually-entered-data::before{
  content:""; }

.bp3-icon-map::before{
  content:""; }

.bp3-icon-map-create::before{
  content:""; }

.bp3-icon-map-marker::before{
  content:""; }

.bp3-icon-maximize::before{
  content:""; }

.bp3-icon-media::before{
  content:""; }

.bp3-icon-menu::before{
  content:""; }

.bp3-icon-menu-closed::before{
  content:""; }

.bp3-icon-menu-open::before{
  content:""; }

.bp3-icon-merge-columns::before{
  content:""; }

.bp3-icon-merge-links::before{
  content:""; }

.bp3-icon-minimize::before{
  content:""; }

.bp3-icon-minus::before{
  content:"−"; }

.bp3-icon-mobile-phone::before{
  content:""; }

.bp3-icon-mobile-video::before{
  content:""; }

.bp3-icon-moon::before{
  content:""; }

.bp3-icon-more::before{
  content:""; }

.bp3-icon-mountain::before{
  content:""; }

.bp3-icon-move::before{
  content:""; }

.bp3-icon-mugshot::before{
  content:""; }

.bp3-icon-multi-select::before{
  content:""; }

.bp3-icon-music::before{
  content:""; }

.bp3-icon-new-drawing::before{
  content:""; }

.bp3-icon-new-grid-item::before{
  content:""; }

.bp3-icon-new-layer::before{
  content:""; }

.bp3-icon-new-layers::before{
  content:""; }

.bp3-icon-new-link::before{
  content:""; }

.bp3-icon-new-object::before{
  content:""; }

.bp3-icon-new-person::before{
  content:""; }

.bp3-icon-new-prescription::before{
  content:""; }

.bp3-icon-new-text-box::before{
  content:""; }

.bp3-icon-ninja::before{
  content:""; }

.bp3-icon-not-equal-to::before{
  content:""; }

.bp3-icon-notifications::before{
  content:""; }

.bp3-icon-notifications-updated::before{
  content:""; }

.bp3-icon-numbered-list::before{
  content:""; }

.bp3-icon-numerical::before{
  content:""; }

.bp3-icon-office::before{
  content:""; }

.bp3-icon-offline::before{
  content:""; }

.bp3-icon-oil-field::before{
  content:""; }

.bp3-icon-one-column::before{
  content:""; }

.bp3-icon-outdated::before{
  content:""; }

.bp3-icon-page-layout::before{
  content:""; }

.bp3-icon-panel-stats::before{
  content:""; }

.bp3-icon-panel-table::before{
  content:""; }

.bp3-icon-paperclip::before{
  content:""; }

.bp3-icon-paragraph::before{
  content:""; }

.bp3-icon-path::before{
  content:""; }

.bp3-icon-path-search::before{
  content:""; }

.bp3-icon-pause::before{
  content:""; }

.bp3-icon-people::before{
  content:""; }

.bp3-icon-percentage::before{
  content:""; }

.bp3-icon-person::before{
  content:""; }

.bp3-icon-phone::before{
  content:"☎"; }

.bp3-icon-pie-chart::before{
  content:""; }

.bp3-icon-pin::before{
  content:""; }

.bp3-icon-pivot::before{
  content:""; }

.bp3-icon-pivot-table::before{
  content:""; }

.bp3-icon-play::before{
  content:""; }

.bp3-icon-plus::before{
  content:"+"; }

.bp3-icon-polygon-filter::before{
  content:""; }

.bp3-icon-power::before{
  content:""; }

.bp3-icon-predictive-analysis::before{
  content:""; }

.bp3-icon-prescription::before{
  content:""; }

.bp3-icon-presentation::before{
  content:""; }

.bp3-icon-print::before{
  content:"⎙"; }

.bp3-icon-projects::before{
  content:""; }

.bp3-icon-properties::before{
  content:""; }

.bp3-icon-property::before{
  content:""; }

.bp3-icon-publish-function::before{
  content:""; }

.bp3-icon-pulse::before{
  content:""; }

.bp3-icon-random::before{
  content:""; }

.bp3-icon-record::before{
  content:""; }

.bp3-icon-redo::before{
  content:""; }

.bp3-icon-refresh::before{
  content:""; }

.bp3-icon-regression-chart::before{
  content:""; }

.bp3-icon-remove::before{
  content:""; }

.bp3-icon-remove-column::before{
  content:""; }

.bp3-icon-remove-column-left::before{
  content:""; }

.bp3-icon-remove-column-right::before{
  content:""; }

.bp3-icon-remove-row-bottom::before{
  content:""; }

.bp3-icon-remove-row-top::before{
  content:""; }

.bp3-icon-repeat::before{
  content:""; }

.bp3-icon-reset::before{
  content:""; }

.bp3-icon-resolve::before{
  content:""; }

.bp3-icon-rig::before{
  content:""; }

.bp3-icon-right-join::before{
  content:""; }

.bp3-icon-ring::before{
  content:""; }

.bp3-icon-rotate-document::before{
  content:""; }

.bp3-icon-rotate-page::before{
  content:""; }

.bp3-icon-satellite::before{
  content:""; }

.bp3-icon-saved::before{
  content:""; }

.bp3-icon-scatter-plot::before{
  content:""; }

.bp3-icon-search::before{
  content:""; }

.bp3-icon-search-around::before{
  content:""; }

.bp3-icon-search-template::before{
  content:""; }

.bp3-icon-search-text::before{
  content:""; }

.bp3-icon-segmented-control::before{
  content:""; }

.bp3-icon-select::before{
  content:""; }

.bp3-icon-selection::before{
  content:"⦿"; }

.bp3-icon-send-to::before{
  content:""; }

.bp3-icon-send-to-graph::before{
  content:""; }

.bp3-icon-send-to-map::before{
  content:""; }

.bp3-icon-series-add::before{
  content:""; }

.bp3-icon-series-configuration::before{
  content:""; }

.bp3-icon-series-derived::before{
  content:""; }

.bp3-icon-series-filtered::before{
  content:""; }

.bp3-icon-series-search::before{
  content:""; }

.bp3-icon-settings::before{
  content:""; }

.bp3-icon-share::before{
  content:""; }

.bp3-icon-shield::before{
  content:""; }

.bp3-icon-shop::before{
  content:""; }

.bp3-icon-shopping-cart::before{
  content:""; }

.bp3-icon-signal-search::before{
  content:""; }

.bp3-icon-sim-card::before{
  content:""; }

.bp3-icon-slash::before{
  content:""; }

.bp3-icon-small-cross::before{
  content:""; }

.bp3-icon-small-minus::before{
  content:""; }

.bp3-icon-small-plus::before{
  content:""; }

.bp3-icon-small-tick::before{
  content:""; }

.bp3-icon-snowflake::before{
  content:""; }

.bp3-icon-social-media::before{
  content:""; }

.bp3-icon-sort::before{
  content:""; }

.bp3-icon-sort-alphabetical::before{
  content:""; }

.bp3-icon-sort-alphabetical-desc::before{
  content:""; }

.bp3-icon-sort-asc::before{
  content:""; }

.bp3-icon-sort-desc::before{
  content:""; }

.bp3-icon-sort-numerical::before{
  content:""; }

.bp3-icon-sort-numerical-desc::before{
  content:""; }

.bp3-icon-split-columns::before{
  content:""; }

.bp3-icon-square::before{
  content:""; }

.bp3-icon-stacked-chart::before{
  content:""; }

.bp3-icon-star::before{
  content:"★"; }

.bp3-icon-star-empty::before{
  content:"☆"; }

.bp3-icon-step-backward::before{
  content:""; }

.bp3-icon-step-chart::before{
  content:""; }

.bp3-icon-step-forward::before{
  content:""; }

.bp3-icon-stop::before{
  content:""; }

.bp3-icon-stopwatch::before{
  content:""; }

.bp3-icon-strikethrough::before{
  content:""; }

.bp3-icon-style::before{
  content:""; }

.bp3-icon-swap-horizontal::before{
  content:""; }

.bp3-icon-swap-vertical::before{
  content:""; }

.bp3-icon-symbol-circle::before{
  content:""; }

.bp3-icon-symbol-cross::before{
  content:""; }

.bp3-icon-symbol-diamond::before{
  content:""; }

.bp3-icon-symbol-square::before{
  content:""; }

.bp3-icon-symbol-triangle-down::before{
  content:""; }

.bp3-icon-symbol-triangle-up::before{
  content:""; }

.bp3-icon-tag::before{
  content:""; }

.bp3-icon-take-action::before{
  content:""; }

.bp3-icon-taxi::before{
  content:""; }

.bp3-icon-text-highlight::before{
  content:""; }

.bp3-icon-th::before{
  content:""; }

.bp3-icon-th-derived::before{
  content:""; }

.bp3-icon-th-disconnect::before{
  content:""; }

.bp3-icon-th-filtered::before{
  content:""; }

.bp3-icon-th-list::before{
  content:""; }

.bp3-icon-thumbs-down::before{
  content:""; }

.bp3-icon-thumbs-up::before{
  content:""; }

.bp3-icon-tick::before{
  content:"✓"; }

.bp3-icon-tick-circle::before{
  content:""; }

.bp3-icon-time::before{
  content:"⏲"; }

.bp3-icon-timeline-area-chart::before{
  content:""; }

.bp3-icon-timeline-bar-chart::before{
  content:""; }

.bp3-icon-timeline-events::before{
  content:""; }

.bp3-icon-timeline-line-chart::before{
  content:""; }

.bp3-icon-tint::before{
  content:""; }

.bp3-icon-torch::before{
  content:""; }

.bp3-icon-tractor::before{
  content:""; }

.bp3-icon-train::before{
  content:""; }

.bp3-icon-translate::before{
  content:""; }

.bp3-icon-trash::before{
  content:""; }

.bp3-icon-tree::before{
  content:""; }

.bp3-icon-trending-down::before{
  content:""; }

.bp3-icon-trending-up::before{
  content:""; }

.bp3-icon-truck::before{
  content:""; }

.bp3-icon-two-columns::before{
  content:""; }

.bp3-icon-unarchive::before{
  content:""; }

.bp3-icon-underline::before{
  content:"⎁"; }

.bp3-icon-undo::before{
  content:"⎌"; }

.bp3-icon-ungroup-objects::before{
  content:""; }

.bp3-icon-unknown-vehicle::before{
  content:""; }

.bp3-icon-unlock::before{
  content:""; }

.bp3-icon-unpin::before{
  content:""; }

.bp3-icon-unresolve::before{
  content:""; }

.bp3-icon-updated::before{
  content:""; }

.bp3-icon-upload::before{
  content:""; }

.bp3-icon-user::before{
  content:""; }

.bp3-icon-variable::before{
  content:""; }

.bp3-icon-vertical-bar-chart-asc::before{
  content:""; }

.bp3-icon-vertical-bar-chart-desc::before{
  content:""; }

.bp3-icon-vertical-distribution::before{
  content:""; }

.bp3-icon-video::before{
  content:""; }

.bp3-icon-volume-down::before{
  content:""; }

.bp3-icon-volume-off::before{
  content:""; }

.bp3-icon-volume-up::before{
  content:""; }

.bp3-icon-walk::before{
  content:""; }

.bp3-icon-warning-sign::before{
  content:""; }

.bp3-icon-waterfall-chart::before{
  content:""; }

.bp3-icon-widget::before{
  content:""; }

.bp3-icon-widget-button::before{
  content:""; }

.bp3-icon-widget-footer::before{
  content:""; }

.bp3-icon-widget-header::before{
  content:""; }

.bp3-icon-wrench::before{
  content:""; }

.bp3-icon-zoom-in::before{
  content:""; }

.bp3-icon-zoom-out::before{
  content:""; }

.bp3-icon-zoom-to-fit::before{
  content:""; }
.bp3-submenu > .bp3-popover-wrapper{
  display:block; }

.bp3-submenu .bp3-popover-target{
  display:block; }

.bp3-submenu.bp3-popover{
  -webkit-box-shadow:none;
          box-shadow:none;
  padding:0 5px; }
  .bp3-submenu.bp3-popover > .bp3-popover-content{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-submenu.bp3-popover, .bp3-submenu.bp3-popover.bp3-dark{
    -webkit-box-shadow:none;
            box-shadow:none; }
    .bp3-dark .bp3-submenu.bp3-popover > .bp3-popover-content, .bp3-submenu.bp3-popover.bp3-dark > .bp3-popover-content{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
.bp3-menu{
  margin:0;
  border-radius:3px;
  background:#ffffff;
  min-width:180px;
  padding:5px;
  list-style:none;
  text-align:left;
  color:#182026; }

.bp3-menu-divider{
  display:block;
  margin:5px;
  border-top:1px solid rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-menu-divider{
    border-top-color:rgba(255, 255, 255, 0.15); }

.bp3-menu-item{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  border-radius:2px;
  padding:5px 7px;
  text-decoration:none;
  line-height:20px;
  color:inherit;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-menu-item > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-menu-item > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-menu-item::before,
  .bp3-menu-item > *{
    margin-right:7px; }
  .bp3-menu-item:empty::before,
  .bp3-menu-item > :last-child{
    margin-right:0; }
  .bp3-menu-item > .bp3-fill{
    word-break:break-word; }
  .bp3-menu-item:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
    background-color:rgba(167, 182, 194, 0.3);
    cursor:pointer;
    text-decoration:none; }
  .bp3-menu-item.bp3-disabled{
    background-color:inherit;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-dark .bp3-menu-item{
    color:inherit; }
    .bp3-dark .bp3-menu-item:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
      background-color:rgba(138, 155, 168, 0.15);
      color:inherit; }
    .bp3-dark .bp3-menu-item.bp3-disabled{
      background-color:inherit;
      color:rgba(167, 182, 194, 0.6); }
  .bp3-menu-item.bp3-intent-primary{
    color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-primary::before, .bp3-menu-item.bp3-intent-primary::after,
    .bp3-menu-item.bp3-intent-primary .bp3-menu-item-label{
      color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-menu-item.bp3-intent-primary.bp3-active{
      background-color:#137cbd; }
    .bp3-menu-item.bp3-intent-primary:active{
      background-color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-menu-item.bp3-intent-primary:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-menu-item.bp3-intent-primary:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-primary:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-primary:active, .bp3-menu-item.bp3-intent-primary:active::before, .bp3-menu-item.bp3-intent-primary:active::after,
    .bp3-menu-item.bp3-intent-primary:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-primary.bp3-active, .bp3-menu-item.bp3-intent-primary.bp3-active::before, .bp3-menu-item.bp3-intent-primary.bp3-active::after,
    .bp3-menu-item.bp3-intent-primary.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-success{
    color:#0d8050; }
    .bp3-menu-item.bp3-intent-success .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-success::before, .bp3-menu-item.bp3-intent-success::after,
    .bp3-menu-item.bp3-intent-success .bp3-menu-item-label{
      color:#0d8050; }
    .bp3-menu-item.bp3-intent-success:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-menu-item.bp3-intent-success.bp3-active{
      background-color:#0f9960; }
    .bp3-menu-item.bp3-intent-success:active{
      background-color:#0d8050; }
    .bp3-menu-item.bp3-intent-success:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-menu-item.bp3-intent-success:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-menu-item.bp3-intent-success:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-success:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-success:active, .bp3-menu-item.bp3-intent-success:active::before, .bp3-menu-item.bp3-intent-success:active::after,
    .bp3-menu-item.bp3-intent-success:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-success.bp3-active, .bp3-menu-item.bp3-intent-success.bp3-active::before, .bp3-menu-item.bp3-intent-success.bp3-active::after,
    .bp3-menu-item.bp3-intent-success.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-warning{
    color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-warning::before, .bp3-menu-item.bp3-intent-warning::after,
    .bp3-menu-item.bp3-intent-warning .bp3-menu-item-label{
      color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-menu-item.bp3-intent-warning.bp3-active{
      background-color:#d9822b; }
    .bp3-menu-item.bp3-intent-warning:active{
      background-color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-menu-item.bp3-intent-warning:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-menu-item.bp3-intent-warning:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-warning:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-warning:active, .bp3-menu-item.bp3-intent-warning:active::before, .bp3-menu-item.bp3-intent-warning:active::after,
    .bp3-menu-item.bp3-intent-warning:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-warning.bp3-active, .bp3-menu-item.bp3-intent-warning.bp3-active::before, .bp3-menu-item.bp3-intent-warning.bp3-active::after,
    .bp3-menu-item.bp3-intent-warning.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-danger{
    color:#c23030; }
    .bp3-menu-item.bp3-intent-danger .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-danger::before, .bp3-menu-item.bp3-intent-danger::after,
    .bp3-menu-item.bp3-intent-danger .bp3-menu-item-label{
      color:#c23030; }
    .bp3-menu-item.bp3-intent-danger:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-menu-item.bp3-intent-danger.bp3-active{
      background-color:#db3737; }
    .bp3-menu-item.bp3-intent-danger:active{
      background-color:#c23030; }
    .bp3-menu-item.bp3-intent-danger:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-menu-item.bp3-intent-danger:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-menu-item.bp3-intent-danger:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-danger:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-danger:active, .bp3-menu-item.bp3-intent-danger:active::before, .bp3-menu-item.bp3-intent-danger:active::after,
    .bp3-menu-item.bp3-intent-danger:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-danger.bp3-active, .bp3-menu-item.bp3-intent-danger.bp3-active::before, .bp3-menu-item.bp3-intent-danger.bp3-active::after,
    .bp3-menu-item.bp3-intent-danger.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item::before{
    line-height:1;
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-weight:400;
    font-style:normal;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    margin-right:7px; }
  .bp3-menu-item::before,
  .bp3-menu-item > .bp3-icon{
    margin-top:2px;
    color:#5c7080; }
  .bp3-menu-item .bp3-menu-item-label{
    color:#5c7080; }
  .bp3-menu-item:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
    color:inherit; }
  .bp3-menu-item.bp3-active, .bp3-menu-item:active{
    background-color:rgba(115, 134, 148, 0.3); }
  .bp3-menu-item.bp3-disabled{
    outline:none !important;
    background-color:inherit !important;
    cursor:not-allowed !important;
    color:rgba(92, 112, 128, 0.6) !important; }
    .bp3-menu-item.bp3-disabled::before,
    .bp3-menu-item.bp3-disabled > .bp3-icon,
    .bp3-menu-item.bp3-disabled .bp3-menu-item-label{
      color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-large .bp3-menu-item{
    padding:9px 7px;
    line-height:22px;
    font-size:16px; }
    .bp3-large .bp3-menu-item .bp3-icon{
      margin-top:3px; }
    .bp3-large .bp3-menu-item::before{
      line-height:1;
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-weight:400;
      font-style:normal;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased;
      margin-top:1px;
      margin-right:10px; }

button.bp3-menu-item{
  border:none;
  background:none;
  width:100%;
  text-align:left; }
.bp3-menu-header{
  display:block;
  margin:5px;
  border-top:1px solid rgba(16, 22, 26, 0.15);
  cursor:default;
  padding-left:2px; }
  .bp3-dark .bp3-menu-header{
    border-top-color:rgba(255, 255, 255, 0.15); }
  .bp3-menu-header:first-of-type{
    border-top:none; }
  .bp3-menu-header > h6{
    color:#182026;
    font-weight:600;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    margin:0;
    padding:10px 7px 0 1px;
    line-height:17px; }
    .bp3-dark .bp3-menu-header > h6{
      color:#f5f8fa; }
  .bp3-menu-header:first-of-type > h6{
    padding-top:0; }
  .bp3-large .bp3-menu-header > h6{
    padding-top:15px;
    padding-bottom:5px;
    font-size:18px; }
  .bp3-large .bp3-menu-header:first-of-type > h6{
    padding-top:0; }

.bp3-dark .bp3-menu{
  background:#30404d;
  color:#f5f8fa; }

.bp3-dark .bp3-menu-item.bp3-intent-primary{
  color:#48aff0; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary::before, .bp3-dark .bp3-menu-item.bp3-intent-primary::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary .bp3-menu-item-label{
    color:#48aff0; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active{
    background-color:#137cbd; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary:active{
    background-color:#106ba3; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-primary:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-primary:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-primary:active, .bp3-dark .bp3-menu-item.bp3-intent-primary:active::before, .bp3-dark .bp3-menu-item.bp3-intent-primary:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item.bp3-intent-success{
  color:#3dcc91; }
  .bp3-dark .bp3-menu-item.bp3-intent-success .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-success::before, .bp3-dark .bp3-menu-item.bp3-intent-success::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success .bp3-menu-item-label{
    color:#3dcc91; }
  .bp3-dark .bp3-menu-item.bp3-intent-success:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active{
    background-color:#0f9960; }
  .bp3-dark .bp3-menu-item.bp3-intent-success:active{
    background-color:#0d8050; }
  .bp3-dark .bp3-menu-item.bp3-intent-success:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-success:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-success:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-success:active, .bp3-dark .bp3-menu-item.bp3-intent-success:active::before, .bp3-dark .bp3-menu-item.bp3-intent-success:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item.bp3-intent-warning{
  color:#ffb366; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning::before, .bp3-dark .bp3-menu-item.bp3-intent-warning::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning .bp3-menu-item-label{
    color:#ffb366; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active{
    background-color:#d9822b; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning:active{
    background-color:#bf7326; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-warning:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-warning:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-warning:active, .bp3-dark .bp3-menu-item.bp3-intent-warning:active::before, .bp3-dark .bp3-menu-item.bp3-intent-warning:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item.bp3-intent-danger{
  color:#ff7373; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger::before, .bp3-dark .bp3-menu-item.bp3-intent-danger::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger .bp3-menu-item-label{
    color:#ff7373; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active{
    background-color:#db3737; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger:active{
    background-color:#c23030; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-danger:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-danger:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-danger:active, .bp3-dark .bp3-menu-item.bp3-intent-danger:active::before, .bp3-dark .bp3-menu-item.bp3-intent-danger:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item::before,
.bp3-dark .bp3-menu-item > .bp3-icon{
  color:#a7b6c2; }

.bp3-dark .bp3-menu-item .bp3-menu-item-label{
  color:#a7b6c2; }

.bp3-dark .bp3-menu-item.bp3-active, .bp3-dark .bp3-menu-item:active{
  background-color:rgba(138, 155, 168, 0.3); }

.bp3-dark .bp3-menu-item.bp3-disabled{
  color:rgba(167, 182, 194, 0.6) !important; }
  .bp3-dark .bp3-menu-item.bp3-disabled::before,
  .bp3-dark .bp3-menu-item.bp3-disabled > .bp3-icon,
  .bp3-dark .bp3-menu-item.bp3-disabled .bp3-menu-item-label{
    color:rgba(167, 182, 194, 0.6) !important; }

.bp3-dark .bp3-menu-divider,
.bp3-dark .bp3-menu-header{
  border-color:rgba(255, 255, 255, 0.15); }

.bp3-dark .bp3-menu-header > h6{
  color:#f5f8fa; }

.bp3-label .bp3-menu{
  margin-top:5px; }
.bp3-navbar{
  position:relative;
  z-index:10;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  background-color:#ffffff;
  width:100%;
  height:50px;
  padding:0 15px; }
  .bp3-navbar.bp3-dark,
  .bp3-dark .bp3-navbar{
    background-color:#394b59; }
  .bp3-navbar.bp3-dark{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-navbar{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-navbar.bp3-fixed-top{
    position:fixed;
    top:0;
    right:0;
    left:0; }

.bp3-navbar-heading{
  margin-right:15px;
  font-size:16px; }

.bp3-navbar-group{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  height:50px; }
  .bp3-navbar-group.bp3-align-left{
    float:left; }
  .bp3-navbar-group.bp3-align-right{
    float:right; }

.bp3-navbar-divider{
  margin:0 10px;
  border-left:1px solid rgba(16, 22, 26, 0.15);
  height:20px; }
  .bp3-dark .bp3-navbar-divider{
    border-left-color:rgba(255, 255, 255, 0.15); }
.bp3-non-ideal-state{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  width:100%;
  height:100%;
  text-align:center; }
  .bp3-non-ideal-state > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-non-ideal-state > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-non-ideal-state::before,
  .bp3-non-ideal-state > *{
    margin-bottom:20px; }
  .bp3-non-ideal-state:empty::before,
  .bp3-non-ideal-state > :last-child{
    margin-bottom:0; }
  .bp3-non-ideal-state > *{
    max-width:400px; }

.bp3-non-ideal-state-visual{
  color:rgba(92, 112, 128, 0.6);
  font-size:60px; }
  .bp3-dark .bp3-non-ideal-state-visual{
    color:rgba(167, 182, 194, 0.6); }

.bp3-overflow-list{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-wrap:nowrap;
      flex-wrap:nowrap;
  min-width:0; }

.bp3-overflow-list-spacer{
  -ms-flex-negative:1;
      flex-shrink:1;
  width:1px; }

body.bp3-overlay-open{
  overflow:hidden; }

.bp3-overlay{
  position:static;
  top:0;
  right:0;
  bottom:0;
  left:0;
  z-index:20; }
  .bp3-overlay:not(.bp3-overlay-open){
    pointer-events:none; }
  .bp3-overlay.bp3-overlay-container{
    position:fixed;
    overflow:hidden; }
    .bp3-overlay.bp3-overlay-container.bp3-overlay-inline{
      position:absolute; }
  .bp3-overlay.bp3-overlay-scroll-container{
    position:fixed;
    overflow:auto; }
    .bp3-overlay.bp3-overlay-scroll-container.bp3-overlay-inline{
      position:absolute; }
  .bp3-overlay.bp3-overlay-inline{
    display:inline;
    overflow:visible; }

.bp3-overlay-content{
  position:fixed;
  z-index:20; }
  .bp3-overlay-inline .bp3-overlay-content,
  .bp3-overlay-scroll-container .bp3-overlay-content{
    position:absolute; }

.bp3-overlay-backdrop{
  position:fixed;
  top:0;
  right:0;
  bottom:0;
  left:0;
  opacity:1;
  z-index:20;
  background-color:rgba(16, 22, 26, 0.7);
  overflow:auto;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-overlay-backdrop.bp3-overlay-enter, .bp3-overlay-backdrop.bp3-overlay-appear{
    opacity:0; }
  .bp3-overlay-backdrop.bp3-overlay-enter-active, .bp3-overlay-backdrop.bp3-overlay-appear-active{
    opacity:1;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-overlay-backdrop.bp3-overlay-exit{
    opacity:1; }
  .bp3-overlay-backdrop.bp3-overlay-exit-active{
    opacity:0;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-overlay-backdrop:focus{
    outline:none; }
  .bp3-overlay-inline .bp3-overlay-backdrop{
    position:absolute; }
.bp3-panel-stack{
  position:relative;
  overflow:hidden; }

.bp3-panel-stack-header{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-negative:0;
      flex-shrink:0;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  z-index:1;
  -webkit-box-shadow:0 1px rgba(16, 22, 26, 0.15);
          box-shadow:0 1px rgba(16, 22, 26, 0.15);
  height:30px; }
  .bp3-dark .bp3-panel-stack-header{
    -webkit-box-shadow:0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 1px rgba(255, 255, 255, 0.15); }
  .bp3-panel-stack-header > span{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1;
            flex:1;
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch; }
  .bp3-panel-stack-header .bp3-heading{
    margin:0 5px; }

.bp3-button.bp3-panel-stack-header-back{
  margin-left:5px;
  padding-left:0;
  white-space:nowrap; }
  .bp3-button.bp3-panel-stack-header-back .bp3-icon{
    margin:0 2px; }

.bp3-panel-stack-view{
  position:absolute;
  top:0;
  right:0;
  bottom:0;
  left:0;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin-right:-1px;
  border-right:1px solid rgba(16, 22, 26, 0.15);
  background-color:#ffffff;
  overflow-y:auto; }
  .bp3-dark .bp3-panel-stack-view{
    background-color:#30404d; }

.bp3-panel-stack-push .bp3-panel-stack-enter, .bp3-panel-stack-push .bp3-panel-stack-appear{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0; }

.bp3-panel-stack-push .bp3-panel-stack-enter-active, .bp3-panel-stack-push .bp3-panel-stack-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }

.bp3-panel-stack-push .bp3-panel-stack-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack-push .bp3-panel-stack-exit-active{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }

.bp3-panel-stack-pop .bp3-panel-stack-enter, .bp3-panel-stack-pop .bp3-panel-stack-appear{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0; }

.bp3-panel-stack-pop .bp3-panel-stack-enter-active, .bp3-panel-stack-pop .bp3-panel-stack-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }

.bp3-panel-stack-pop .bp3-panel-stack-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack-pop .bp3-panel-stack-exit-active{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }
.bp3-popover{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  -webkit-transform:scale(1);
          transform:scale(1);
  display:inline-block;
  z-index:20;
  border-radius:3px; }
  .bp3-popover .bp3-popover-arrow{
    position:absolute;
    width:30px;
    height:30px; }
    .bp3-popover .bp3-popover-arrow::before{
      margin:5px;
      width:20px;
      height:20px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover{
    margin-top:-17px;
    margin-bottom:17px; }
    .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow{
      bottom:-11px; }
      .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(-90deg);
                transform:rotate(-90deg); }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover{
    margin-left:17px; }
    .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow{
      left:-11px; }
      .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(0);
                transform:rotate(0); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover{
    margin-top:17px; }
    .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow{
      top:-11px; }
      .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(90deg);
                transform:rotate(90deg); }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover{
    margin-right:17px;
    margin-left:-17px; }
    .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow{
      right:-11px; }
      .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(180deg);
                transform:rotate(180deg); }
  .bp3-tether-element-attached-middle > .bp3-popover > .bp3-popover-arrow{
    top:50%;
    -webkit-transform:translateY(-50%);
            transform:translateY(-50%); }
  .bp3-tether-element-attached-center > .bp3-popover > .bp3-popover-arrow{
    right:50%;
    -webkit-transform:translateX(50%);
            transform:translateX(50%); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow{
    top:-0.3934px; }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow{
    right:-0.3934px; }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow{
    left:-0.3934px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow{
    bottom:-0.3934px; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:top left;
            transform-origin:top left; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:top center;
            transform-origin:top center; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:top right;
            transform-origin:top right; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:center left;
            transform-origin:center left; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:center center;
            transform-origin:center center; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:center right;
            transform-origin:center right; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:bottom left;
            transform-origin:bottom left; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:bottom center;
            transform-origin:bottom center; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:bottom right;
            transform-origin:bottom right; }
  .bp3-popover .bp3-popover-content{
    background:#ffffff;
    color:inherit; }
  .bp3-popover .bp3-popover-arrow::before{
    -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2);
            box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2); }
  .bp3-popover .bp3-popover-arrow-border{
    fill:#10161a;
    fill-opacity:0.1; }
  .bp3-popover .bp3-popover-arrow-fill{
    fill:#ffffff; }
  .bp3-popover-enter > .bp3-popover, .bp3-popover-appear > .bp3-popover{
    -webkit-transform:scale(0.3);
            transform:scale(0.3); }
  .bp3-popover-enter-active > .bp3-popover, .bp3-popover-appear-active > .bp3-popover{
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-popover-exit > .bp3-popover{
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-popover-exit-active > .bp3-popover{
    -webkit-transform:scale(0.3);
            transform:scale(0.3);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-popover .bp3-popover-content{
    position:relative;
    border-radius:3px; }
  .bp3-popover.bp3-popover-content-sizing .bp3-popover-content{
    max-width:350px;
    padding:20px; }
  .bp3-popover-target + .bp3-overlay .bp3-popover.bp3-popover-content-sizing{
    width:350px; }
  .bp3-popover.bp3-minimal{
    margin:0 !important; }
    .bp3-popover.bp3-minimal .bp3-popover-arrow{
      display:none; }
    .bp3-popover.bp3-minimal.bp3-popover{
      -webkit-transform:scale(1);
              transform:scale(1); }
      .bp3-popover-enter > .bp3-popover.bp3-minimal.bp3-popover, .bp3-popover-appear > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1); }
      .bp3-popover-enter-active > .bp3-popover.bp3-minimal.bp3-popover, .bp3-popover-appear-active > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1);
        -webkit-transition-property:-webkit-transform;
        transition-property:-webkit-transform;
        transition-property:transform;
        transition-property:transform, -webkit-transform;
        -webkit-transition-duration:100ms;
                transition-duration:100ms;
        -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
                transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
        -webkit-transition-delay:0;
                transition-delay:0; }
      .bp3-popover-exit > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1); }
      .bp3-popover-exit-active > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1);
        -webkit-transition-property:-webkit-transform;
        transition-property:-webkit-transform;
        transition-property:transform;
        transition-property:transform, -webkit-transform;
        -webkit-transition-duration:100ms;
                transition-duration:100ms;
        -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
                transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
        -webkit-transition-delay:0;
                transition-delay:0; }
  .bp3-popover.bp3-dark,
  .bp3-dark .bp3-popover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
    .bp3-popover.bp3-dark .bp3-popover-content,
    .bp3-dark .bp3-popover .bp3-popover-content{
      background:#30404d;
      color:inherit; }
    .bp3-popover.bp3-dark .bp3-popover-arrow::before,
    .bp3-dark .bp3-popover .bp3-popover-arrow::before{
      -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4);
              box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4); }
    .bp3-popover.bp3-dark .bp3-popover-arrow-border,
    .bp3-dark .bp3-popover .bp3-popover-arrow-border{
      fill:#10161a;
      fill-opacity:0.2; }
    .bp3-popover.bp3-dark .bp3-popover-arrow-fill,
    .bp3-dark .bp3-popover .bp3-popover-arrow-fill{
      fill:#30404d; }

.bp3-popover-arrow::before{
  display:block;
  position:absolute;
  -webkit-transform:rotate(45deg);
          transform:rotate(45deg);
  border-radius:2px;
  content:""; }

.bp3-tether-pinned .bp3-popover-arrow{
  display:none; }

.bp3-popover-backdrop{
  background:rgba(255, 255, 255, 0); }

.bp3-transition-container{
  opacity:1;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  z-index:20; }
  .bp3-transition-container.bp3-popover-enter, .bp3-transition-container.bp3-popover-appear{
    opacity:0; }
  .bp3-transition-container.bp3-popover-enter-active, .bp3-transition-container.bp3-popover-appear-active{
    opacity:1;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-transition-container.bp3-popover-exit{
    opacity:1; }
  .bp3-transition-container.bp3-popover-exit-active{
    opacity:0;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-transition-container:focus{
    outline:none; }
  .bp3-transition-container.bp3-popover-leave .bp3-popover-content{
    pointer-events:none; }
  .bp3-transition-container[data-x-out-of-boundaries]{
    display:none; }

span.bp3-popover-target{
  display:inline-block; }

.bp3-popover-wrapper.bp3-fill{
  width:100%; }

.bp3-portal{
  position:absolute;
  top:0;
  right:0;
  left:0; }
@-webkit-keyframes linear-progress-bar-stripes{
  from{
    background-position:0 0; }
  to{
    background-position:30px 0; } }
@keyframes linear-progress-bar-stripes{
  from{
    background-position:0 0; }
  to{
    background-position:30px 0; } }

.bp3-progress-bar{
  display:block;
  position:relative;
  border-radius:40px;
  background:rgba(92, 112, 128, 0.2);
  width:100%;
  height:8px;
  overflow:hidden; }
  .bp3-progress-bar .bp3-progress-meter{
    position:absolute;
    border-radius:40px;
    background:linear-gradient(-45deg, rgba(255, 255, 255, 0.2) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.2) 50%, rgba(255, 255, 255, 0.2) 75%, transparent 75%);
    background-color:rgba(92, 112, 128, 0.8);
    background-size:30px 30px;
    width:100%;
    height:100%;
    -webkit-transition:width 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:width 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-progress-bar:not(.bp3-no-animation):not(.bp3-no-stripes) .bp3-progress-meter{
    animation:linear-progress-bar-stripes 300ms linear infinite reverse; }
  .bp3-progress-bar.bp3-no-stripes .bp3-progress-meter{
    background-image:none; }

.bp3-dark .bp3-progress-bar{
  background:rgba(16, 22, 26, 0.5); }
  .bp3-dark .bp3-progress-bar .bp3-progress-meter{
    background-color:#8a9ba8; }

.bp3-progress-bar.bp3-intent-primary .bp3-progress-meter{
  background-color:#137cbd; }

.bp3-progress-bar.bp3-intent-success .bp3-progress-meter{
  background-color:#0f9960; }

.bp3-progress-bar.bp3-intent-warning .bp3-progress-meter{
  background-color:#d9822b; }

.bp3-progress-bar.bp3-intent-danger .bp3-progress-meter{
  background-color:#db3737; }
@-webkit-keyframes skeleton-glow{
  from{
    border-color:rgba(206, 217, 224, 0.2);
    background:rgba(206, 217, 224, 0.2); }
  to{
    border-color:rgba(92, 112, 128, 0.2);
    background:rgba(92, 112, 128, 0.2); } }
@keyframes skeleton-glow{
  from{
    border-color:rgba(206, 217, 224, 0.2);
    background:rgba(206, 217, 224, 0.2); }
  to{
    border-color:rgba(92, 112, 128, 0.2);
    background:rgba(92, 112, 128, 0.2); } }
.bp3-skeleton{
  border-color:rgba(206, 217, 224, 0.2) !important;
  border-radius:2px;
  -webkit-box-shadow:none !important;
          box-shadow:none !important;
  background:rgba(206, 217, 224, 0.2);
  background-clip:padding-box !important;
  cursor:default;
  color:transparent !important;
  -webkit-animation:1000ms linear infinite alternate skeleton-glow;
          animation:1000ms linear infinite alternate skeleton-glow;
  pointer-events:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-skeleton::before, .bp3-skeleton::after,
  .bp3-skeleton *{
    visibility:hidden !important; }
.bp3-slider{
  width:100%;
  min-width:150px;
  height:40px;
  position:relative;
  outline:none;
  cursor:default;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-slider:hover{
    cursor:pointer; }
  .bp3-slider:active{
    cursor:-webkit-grabbing;
    cursor:grabbing; }
  .bp3-slider.bp3-disabled{
    opacity:0.5;
    cursor:not-allowed; }
  .bp3-slider.bp3-slider-unlabeled{
    height:16px; }

.bp3-slider-track,
.bp3-slider-progress{
  top:5px;
  right:0;
  left:0;
  height:6px;
  position:absolute; }

.bp3-slider-track{
  border-radius:3px;
  overflow:hidden; }

.bp3-slider-progress{
  background:rgba(92, 112, 128, 0.2); }
  .bp3-dark .bp3-slider-progress{
    background:rgba(16, 22, 26, 0.5); }
  .bp3-slider-progress.bp3-intent-primary{
    background-color:#137cbd; }
  .bp3-slider-progress.bp3-intent-success{
    background-color:#0f9960; }
  .bp3-slider-progress.bp3-intent-warning{
    background-color:#d9822b; }
  .bp3-slider-progress.bp3-intent-danger{
    background-color:#db3737; }

.bp3-slider-handle{
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
  background-color:#f5f8fa;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
  color:#182026;
  position:absolute;
  top:0;
  left:0;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
  cursor:pointer;
  width:16px;
  height:16px; }
  .bp3-slider-handle:hover{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5; }
  .bp3-slider-handle:active, .bp3-slider-handle.bp3-active{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none; }
  .bp3-slider-handle:disabled, .bp3-slider-handle.bp3-disabled{
    outline:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    background-color:rgba(206, 217, 224, 0.5);
    background-image:none;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
    .bp3-slider-handle:disabled.bp3-active, .bp3-slider-handle:disabled.bp3-active:hover, .bp3-slider-handle.bp3-disabled.bp3-active, .bp3-slider-handle.bp3-disabled.bp3-active:hover{
      background:rgba(206, 217, 224, 0.7); }
  .bp3-slider-handle:focus{
    z-index:1; }
  .bp3-slider-handle:hover{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5;
    z-index:2;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
    cursor:-webkit-grab;
    cursor:grab; }
  .bp3-slider-handle.bp3-active{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 1px rgba(16, 22, 26, 0.1);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 1px rgba(16, 22, 26, 0.1);
    cursor:-webkit-grabbing;
    cursor:grabbing; }
  .bp3-disabled .bp3-slider-handle{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:#bfccd6;
    pointer-events:none; }
  .bp3-dark .bp3-slider-handle{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#394b59;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
    color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle:hover, .bp3-dark .bp3-slider-handle:active, .bp3-dark .bp3-slider-handle.bp3-active{
      color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle:hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#30404d; }
    .bp3-dark .bp3-slider-handle:active, .bp3-dark .bp3-slider-handle.bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#202b33;
      background-image:none; }
    .bp3-dark .bp3-slider-handle:disabled, .bp3-dark .bp3-slider-handle.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(57, 75, 89, 0.5);
      background-image:none;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-slider-handle:disabled.bp3-active, .bp3-dark .bp3-slider-handle.bp3-disabled.bp3-active{
        background:rgba(57, 75, 89, 0.7); }
    .bp3-dark .bp3-slider-handle .bp3-button-spinner .bp3-spinner-head{
      background:rgba(16, 22, 26, 0.5);
      stroke:#8a9ba8; }
    .bp3-dark .bp3-slider-handle, .bp3-dark .bp3-slider-handle:hover{
      background-color:#394b59; }
    .bp3-dark .bp3-slider-handle.bp3-active{
      background-color:#293742; }
  .bp3-dark .bp3-disabled .bp3-slider-handle{
    border-color:#5c7080;
    -webkit-box-shadow:none;
            box-shadow:none;
    background:#5c7080; }
  .bp3-slider-handle .bp3-slider-label{
    margin-left:8px;
    border-radius:3px;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
    background:#394b59;
    color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle .bp3-slider-label{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
      background:#e1e8ed;
      color:#394b59; }
    .bp3-disabled .bp3-slider-handle .bp3-slider-label{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-slider-handle.bp3-start, .bp3-slider-handle.bp3-end{
    width:8px; }
  .bp3-slider-handle.bp3-start{
    border-top-right-radius:0;
    border-bottom-right-radius:0; }
  .bp3-slider-handle.bp3-end{
    margin-left:8px;
    border-top-left-radius:0;
    border-bottom-left-radius:0; }
    .bp3-slider-handle.bp3-end .bp3-slider-label{
      margin-left:0; }

.bp3-slider-label{
  -webkit-transform:translate(-50%, 20px);
          transform:translate(-50%, 20px);
  display:inline-block;
  position:absolute;
  padding:2px 5px;
  vertical-align:top;
  line-height:1;
  font-size:12px; }

.bp3-slider.bp3-vertical{
  width:40px;
  min-width:40px;
  height:150px; }
  .bp3-slider.bp3-vertical .bp3-slider-track,
  .bp3-slider.bp3-vertical .bp3-slider-progress{
    top:0;
    bottom:0;
    left:5px;
    width:6px;
    height:auto; }
  .bp3-slider.bp3-vertical .bp3-slider-progress{
    top:auto; }
  .bp3-slider.bp3-vertical .bp3-slider-label{
    -webkit-transform:translate(20px, 50%);
            transform:translate(20px, 50%); }
  .bp3-slider.bp3-vertical .bp3-slider-handle{
    top:auto; }
    .bp3-slider.bp3-vertical .bp3-slider-handle .bp3-slider-label{
      margin-top:-8px;
      margin-left:0; }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-end, .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start{
      margin-left:0;
      width:16px;
      height:8px; }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start{
      border-top-left-radius:0;
      border-bottom-right-radius:3px; }
      .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start .bp3-slider-label{
        -webkit-transform:translate(20px);
                transform:translate(20px); }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-end{
      margin-bottom:8px;
      border-top-left-radius:3px;
      border-bottom-left-radius:0;
      border-bottom-right-radius:0; }

@-webkit-keyframes pt-spinner-animation{
  from{
    -webkit-transform:rotate(0deg);
            transform:rotate(0deg); }
  to{
    -webkit-transform:rotate(360deg);
            transform:rotate(360deg); } }

@keyframes pt-spinner-animation{
  from{
    -webkit-transform:rotate(0deg);
            transform:rotate(0deg); }
  to{
    -webkit-transform:rotate(360deg);
            transform:rotate(360deg); } }

.bp3-spinner{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  overflow:visible;
  vertical-align:middle; }
  .bp3-spinner svg{
    display:block; }
  .bp3-spinner path{
    fill-opacity:0; }
  .bp3-spinner .bp3-spinner-head{
    -webkit-transform-origin:center;
            transform-origin:center;
    -webkit-transition:stroke-dashoffset 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:stroke-dashoffset 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    stroke:rgba(92, 112, 128, 0.8);
    stroke-linecap:round; }
  .bp3-spinner .bp3-spinner-track{
    stroke:rgba(92, 112, 128, 0.2); }

.bp3-spinner-animation{
  -webkit-animation:pt-spinner-animation 500ms linear infinite;
          animation:pt-spinner-animation 500ms linear infinite; }
  .bp3-no-spin > .bp3-spinner-animation{
    -webkit-animation:none;
            animation:none; }

.bp3-dark .bp3-spinner .bp3-spinner-head{
  stroke:#8a9ba8; }

.bp3-dark .bp3-spinner .bp3-spinner-track{
  stroke:rgba(16, 22, 26, 0.5); }

.bp3-spinner.bp3-intent-primary .bp3-spinner-head{
  stroke:#137cbd; }

.bp3-spinner.bp3-intent-success .bp3-spinner-head{
  stroke:#0f9960; }

.bp3-spinner.bp3-intent-warning .bp3-spinner-head{
  stroke:#d9822b; }

.bp3-spinner.bp3-intent-danger .bp3-spinner-head{
  stroke:#db3737; }
.bp3-tabs.bp3-vertical{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }
  .bp3-tabs.bp3-vertical > .bp3-tab-list{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column;
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
    .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab{
      border-radius:3px;
      width:100%;
      padding:0 10px; }
      .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab[aria-selected="true"]{
        -webkit-box-shadow:none;
                box-shadow:none;
        background-color:rgba(19, 124, 189, 0.2); }
    .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab-indicator-wrapper .bp3-tab-indicator{
      top:0;
      right:0;
      bottom:0;
      left:0;
      border-radius:3px;
      background-color:rgba(19, 124, 189, 0.2);
      height:auto; }
  .bp3-tabs.bp3-vertical > .bp3-tab-panel{
    margin-top:0;
    padding-left:20px; }

.bp3-tab-list{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  -webkit-box-align:end;
      -ms-flex-align:end;
          align-items:flex-end;
  position:relative;
  margin:0;
  border:none;
  padding:0;
  list-style:none; }
  .bp3-tab-list > *:not(:last-child){
    margin-right:20px; }

.bp3-tab{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  position:relative;
  cursor:pointer;
  max-width:100%;
  vertical-align:top;
  line-height:30px;
  color:#182026;
  font-size:14px; }
  .bp3-tab a{
    display:block;
    text-decoration:none;
    color:inherit; }
  .bp3-tab-indicator-wrapper ~ .bp3-tab{
    -webkit-box-shadow:none !important;
            box-shadow:none !important;
    background-color:transparent !important; }
  .bp3-tab[aria-disabled="true"]{
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-tab[aria-selected="true"]{
    border-radius:0;
    -webkit-box-shadow:inset 0 -3px 0 #106ba3;
            box-shadow:inset 0 -3px 0 #106ba3; }
  .bp3-tab[aria-selected="true"], .bp3-tab:not([aria-disabled="true"]):hover{
    color:#106ba3; }
  .bp3-tab:focus{
    -moz-outline-radius:0; }
  .bp3-large > .bp3-tab{
    line-height:40px;
    font-size:16px; }

.bp3-tab-panel{
  margin-top:20px; }
  .bp3-tab-panel[aria-hidden="true"]{
    display:none; }

.bp3-tab-indicator-wrapper{
  position:absolute;
  top:0;
  left:0;
  -webkit-transform:translateX(0), translateY(0);
          transform:translateX(0), translateY(0);
  -webkit-transition:height, width, -webkit-transform;
  transition:height, width, -webkit-transform;
  transition:height, transform, width;
  transition:height, transform, width, -webkit-transform;
  -webkit-transition-duration:200ms;
          transition-duration:200ms;
  -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
          transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
  pointer-events:none; }
  .bp3-tab-indicator-wrapper .bp3-tab-indicator{
    position:absolute;
    right:0;
    bottom:0;
    left:0;
    background-color:#106ba3;
    height:3px; }
  .bp3-tab-indicator-wrapper.bp3-no-animation{
    -webkit-transition:none;
    transition:none; }

.bp3-dark .bp3-tab{
  color:#f5f8fa; }
  .bp3-dark .bp3-tab[aria-disabled="true"]{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-tab[aria-selected="true"]{
    -webkit-box-shadow:inset 0 -3px 0 #48aff0;
            box-shadow:inset 0 -3px 0 #48aff0; }
  .bp3-dark .bp3-tab[aria-selected="true"], .bp3-dark .bp3-tab:not([aria-disabled="true"]):hover{
    color:#48aff0; }

.bp3-dark .bp3-tab-indicator{
  background-color:#48aff0; }

.bp3-flex-expander{
  -webkit-box-flex:1;
      -ms-flex:1 1;
          flex:1 1; }
.bp3-tag{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  position:relative;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:none;
          box-shadow:none;
  background-color:#5c7080;
  min-width:20px;
  max-width:100%;
  min-height:20px;
  padding:2px 6px;
  line-height:16px;
  color:#f5f8fa;
  font-size:12px; }
  .bp3-tag.bp3-interactive{
    cursor:pointer; }
    .bp3-tag.bp3-interactive:hover{
      background-color:rgba(92, 112, 128, 0.85); }
    .bp3-tag.bp3-interactive.bp3-active, .bp3-tag.bp3-interactive:active{
      background-color:rgba(92, 112, 128, 0.7); }
  .bp3-tag > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-tag > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-tag::before,
  .bp3-tag > *{
    margin-right:4px; }
  .bp3-tag:empty::before,
  .bp3-tag > :last-child{
    margin-right:0; }
  .bp3-tag:focus{
    outline:rgba(19, 124, 189, 0.6) auto 2px;
    outline-offset:0;
    -moz-outline-radius:6px; }
  .bp3-tag.bp3-round{
    border-radius:30px;
    padding-right:8px;
    padding-left:8px; }
  .bp3-dark .bp3-tag{
    background-color:#bfccd6;
    color:#182026; }
    .bp3-dark .bp3-tag.bp3-interactive{
      cursor:pointer; }
      .bp3-dark .bp3-tag.bp3-interactive:hover{
        background-color:rgba(191, 204, 214, 0.85); }
      .bp3-dark .bp3-tag.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-interactive:active{
        background-color:rgba(191, 204, 214, 0.7); }
    .bp3-dark .bp3-tag > .bp3-icon, .bp3-dark .bp3-tag .bp3-icon-standard, .bp3-dark .bp3-tag .bp3-icon-large{
      fill:currentColor; }
  .bp3-tag > .bp3-icon, .bp3-tag .bp3-icon-standard, .bp3-tag .bp3-icon-large{
    fill:#ffffff; }
  .bp3-tag.bp3-large,
  .bp3-large .bp3-tag{
    min-width:30px;
    min-height:30px;
    padding:0 10px;
    line-height:20px;
    font-size:14px; }
    .bp3-tag.bp3-large::before,
    .bp3-tag.bp3-large > *,
    .bp3-large .bp3-tag::before,
    .bp3-large .bp3-tag > *{
      margin-right:7px; }
    .bp3-tag.bp3-large:empty::before,
    .bp3-tag.bp3-large > :last-child,
    .bp3-large .bp3-tag:empty::before,
    .bp3-large .bp3-tag > :last-child{
      margin-right:0; }
    .bp3-tag.bp3-large.bp3-round,
    .bp3-large .bp3-tag.bp3-round{
      padding-right:12px;
      padding-left:12px; }
  .bp3-tag.bp3-intent-primary{
    background:#137cbd;
    color:#ffffff; }
    .bp3-tag.bp3-intent-primary.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-primary.bp3-interactive:hover{
        background-color:rgba(19, 124, 189, 0.85); }
      .bp3-tag.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-primary.bp3-interactive:active{
        background-color:rgba(19, 124, 189, 0.7); }
  .bp3-tag.bp3-intent-success{
    background:#0f9960;
    color:#ffffff; }
    .bp3-tag.bp3-intent-success.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-success.bp3-interactive:hover{
        background-color:rgba(15, 153, 96, 0.85); }
      .bp3-tag.bp3-intent-success.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-success.bp3-interactive:active{
        background-color:rgba(15, 153, 96, 0.7); }
  .bp3-tag.bp3-intent-warning{
    background:#d9822b;
    color:#ffffff; }
    .bp3-tag.bp3-intent-warning.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-warning.bp3-interactive:hover{
        background-color:rgba(217, 130, 43, 0.85); }
      .bp3-tag.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-warning.bp3-interactive:active{
        background-color:rgba(217, 130, 43, 0.7); }
  .bp3-tag.bp3-intent-danger{
    background:#db3737;
    color:#ffffff; }
    .bp3-tag.bp3-intent-danger.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-danger.bp3-interactive:hover{
        background-color:rgba(219, 55, 55, 0.85); }
      .bp3-tag.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-danger.bp3-interactive:active{
        background-color:rgba(219, 55, 55, 0.7); }
  .bp3-tag.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-tag.bp3-minimal > .bp3-icon, .bp3-tag.bp3-minimal .bp3-icon-standard, .bp3-tag.bp3-minimal .bp3-icon-large{
    fill:#5c7080; }
  .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]){
    background-color:rgba(138, 155, 168, 0.2);
    color:#182026; }
    .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:hover{
        background-color:rgba(92, 112, 128, 0.3); }
      .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive.bp3-active, .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:active{
        background-color:rgba(92, 112, 128, 0.4); }
    .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]){
      color:#f5f8fa; }
      .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:hover{
          background-color:rgba(191, 204, 214, 0.3); }
        .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:active{
          background-color:rgba(191, 204, 214, 0.4); }
      .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) > .bp3-icon, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) .bp3-icon-standard, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) .bp3-icon-large{
        fill:#a7b6c2; }
  .bp3-tag.bp3-minimal.bp3-intent-primary{
    background-color:rgba(19, 124, 189, 0.15);
    color:#106ba3; }
    .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:hover{
        background-color:rgba(19, 124, 189, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:active{
        background-color:rgba(19, 124, 189, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-primary > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-primary .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-primary .bp3-icon-large{
      fill:#137cbd; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary{
      background-color:rgba(19, 124, 189, 0.25);
      color:#48aff0; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:hover{
          background-color:rgba(19, 124, 189, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:active{
          background-color:rgba(19, 124, 189, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-success{
    background-color:rgba(15, 153, 96, 0.15);
    color:#0d8050; }
    .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:hover{
        background-color:rgba(15, 153, 96, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:active{
        background-color:rgba(15, 153, 96, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-success > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-success .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-success .bp3-icon-large{
      fill:#0f9960; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success{
      background-color:rgba(15, 153, 96, 0.25);
      color:#3dcc91; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:hover{
          background-color:rgba(15, 153, 96, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:active{
          background-color:rgba(15, 153, 96, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-warning{
    background-color:rgba(217, 130, 43, 0.15);
    color:#bf7326; }
    .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:hover{
        background-color:rgba(217, 130, 43, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:active{
        background-color:rgba(217, 130, 43, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-warning > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-warning .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-warning .bp3-icon-large{
      fill:#d9822b; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning{
      background-color:rgba(217, 130, 43, 0.25);
      color:#ffb366; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:hover{
          background-color:rgba(217, 130, 43, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:active{
          background-color:rgba(217, 130, 43, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-danger{
    background-color:rgba(219, 55, 55, 0.15);
    color:#c23030; }
    .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:hover{
        background-color:rgba(219, 55, 55, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:active{
        background-color:rgba(219, 55, 55, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-danger > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-danger .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-danger .bp3-icon-large{
      fill:#db3737; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger{
      background-color:rgba(219, 55, 55, 0.25);
      color:#ff7373; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:hover{
          background-color:rgba(219, 55, 55, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:active{
          background-color:rgba(219, 55, 55, 0.45); }

.bp3-tag-remove{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  opacity:0.5;
  margin-top:-2px;
  margin-right:-6px !important;
  margin-bottom:-2px;
  border:none;
  background:none;
  cursor:pointer;
  padding:2px;
  padding-left:0;
  color:inherit; }
  .bp3-tag-remove:hover{
    opacity:0.8;
    background:none;
    text-decoration:none; }
  .bp3-tag-remove:active{
    opacity:1; }
  .bp3-tag-remove:empty::before{
    line-height:1;
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-weight:400;
    font-style:normal;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    content:""; }
  .bp3-large .bp3-tag-remove{
    margin-right:-10px !important;
    padding:5px;
    padding-left:0; }
    .bp3-large .bp3-tag-remove:empty::before{
      line-height:1;
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-weight:400;
      font-style:normal; }
.bp3-tag-input{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  cursor:text;
  height:auto;
  min-height:30px;
  padding-right:0;
  padding-left:5px;
  line-height:inherit; }
  .bp3-tag-input > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-tag-input > .bp3-tag-input-values{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-tag-input .bp3-tag-input-icon{
    margin-top:7px;
    margin-right:7px;
    margin-left:2px;
    color:#5c7080; }
  .bp3-tag-input .bp3-tag-input-values{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-orient:horizontal;
    -webkit-box-direction:normal;
        -ms-flex-direction:row;
            flex-direction:row;
    -ms-flex-wrap:wrap;
        flex-wrap:wrap;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center;
    -ms-flex-item-align:stretch;
        align-self:stretch;
    margin-top:5px;
    margin-right:7px;
    min-width:0; }
    .bp3-tag-input .bp3-tag-input-values > *{
      -webkit-box-flex:0;
          -ms-flex-positive:0;
              flex-grow:0;
      -ms-flex-negative:0;
          flex-shrink:0; }
    .bp3-tag-input .bp3-tag-input-values > .bp3-fill{
      -webkit-box-flex:1;
          -ms-flex-positive:1;
              flex-grow:1;
      -ms-flex-negative:1;
          flex-shrink:1; }
    .bp3-tag-input .bp3-tag-input-values::before,
    .bp3-tag-input .bp3-tag-input-values > *{
      margin-right:5px; }
    .bp3-tag-input .bp3-tag-input-values:empty::before,
    .bp3-tag-input .bp3-tag-input-values > :last-child{
      margin-right:0; }
    .bp3-tag-input .bp3-tag-input-values:first-child .bp3-input-ghost:first-child{
      padding-left:5px; }
    .bp3-tag-input .bp3-tag-input-values > *{
      margin-bottom:5px; }
  .bp3-tag-input .bp3-tag{
    overflow-wrap:break-word; }
    .bp3-tag-input .bp3-tag.bp3-active{
      outline:rgba(19, 124, 189, 0.6) auto 2px;
      outline-offset:0;
      -moz-outline-radius:6px; }
  .bp3-tag-input .bp3-input-ghost{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:80px;
    line-height:20px; }
    .bp3-tag-input .bp3-input-ghost:disabled, .bp3-tag-input .bp3-input-ghost.bp3-disabled{
      cursor:not-allowed; }
  .bp3-tag-input .bp3-button,
  .bp3-tag-input .bp3-spinner{
    margin:3px;
    margin-left:0; }
  .bp3-tag-input .bp3-button{
    min-width:24px;
    min-height:24px;
    padding:0 7px; }
  .bp3-tag-input.bp3-large{
    height:auto;
    min-height:40px; }
    .bp3-tag-input.bp3-large::before,
    .bp3-tag-input.bp3-large > *{
      margin-right:10px; }
    .bp3-tag-input.bp3-large:empty::before,
    .bp3-tag-input.bp3-large > :last-child{
      margin-right:0; }
    .bp3-tag-input.bp3-large .bp3-tag-input-icon{
      margin-top:10px;
      margin-left:5px; }
    .bp3-tag-input.bp3-large .bp3-input-ghost{
      line-height:30px; }
    .bp3-tag-input.bp3-large .bp3-button{
      min-width:30px;
      min-height:30px;
      padding:5px 10px;
      margin:5px;
      margin-left:0; }
    .bp3-tag-input.bp3-large .bp3-spinner{
      margin:8px;
      margin-left:0; }
  .bp3-tag-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
    background-color:#ffffff; }
    .bp3-tag-input.bp3-active.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-success{
      -webkit-box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-tag-input .bp3-tag-input-icon, .bp3-tag-input.bp3-dark .bp3-tag-input-icon{
    color:#a7b6c2; }
  .bp3-dark .bp3-tag-input .bp3-input-ghost, .bp3-tag-input.bp3-dark .bp3-input-ghost{
    color:#f5f8fa; }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-webkit-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-moz-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost:-ms-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-ms-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::placeholder{
      color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-tag-input.bp3-active, .bp3-tag-input.bp3-dark.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background-color:rgba(16, 22, 26, 0.3); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-primary, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-success, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-success{
      -webkit-box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-warning, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-danger, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-input-ghost{
  border:none;
  -webkit-box-shadow:none;
          box-shadow:none;
  background:none;
  padding:0; }
  .bp3-input-ghost::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost:focus{
    outline:none !important; }
.bp3-toast{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  position:relative !important;
  margin:20px 0 0;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  background-color:#ffffff;
  min-width:300px;
  max-width:500px;
  pointer-events:all; }
  .bp3-toast.bp3-toast-enter, .bp3-toast.bp3-toast-appear{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px); }
  .bp3-toast.bp3-toast-enter-active, .bp3-toast.bp3-toast-appear-active{
    -webkit-transform:translateY(0);
            transform:translateY(0);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-toast.bp3-toast-enter ~ .bp3-toast, .bp3-toast.bp3-toast-appear ~ .bp3-toast{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px); }
  .bp3-toast.bp3-toast-enter-active ~ .bp3-toast, .bp3-toast.bp3-toast-appear-active ~ .bp3-toast{
    -webkit-transform:translateY(0);
            transform:translateY(0);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-toast.bp3-toast-exit{
    opacity:1;
    -webkit-filter:blur(0);
            filter:blur(0); }
  .bp3-toast.bp3-toast-exit-active{
    opacity:0;
    -webkit-filter:blur(10px);
            filter:blur(10px);
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:opacity, filter;
    transition-property:opacity, filter, -webkit-filter;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-toast.bp3-toast-exit ~ .bp3-toast{
    -webkit-transform:translateY(0);
            transform:translateY(0); }
  .bp3-toast.bp3-toast-exit-active ~ .bp3-toast{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:50ms;
            transition-delay:50ms; }
  .bp3-toast .bp3-button-group{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    padding:5px;
    padding-left:0; }
  .bp3-toast > .bp3-icon{
    margin:12px;
    margin-right:0;
    color:#5c7080; }
  .bp3-toast.bp3-dark,
  .bp3-dark .bp3-toast{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
    background-color:#394b59; }
    .bp3-toast.bp3-dark > .bp3-icon,
    .bp3-dark .bp3-toast > .bp3-icon{
      color:#a7b6c2; }
  .bp3-toast[class*="bp3-intent-"] a{
    color:rgba(255, 255, 255, 0.7); }
    .bp3-toast[class*="bp3-intent-"] a:hover{
      color:#ffffff; }
  .bp3-toast[class*="bp3-intent-"] > .bp3-icon{
    color:#ffffff; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button, .bp3-toast[class*="bp3-intent-"] .bp3-button::before,
  .bp3-toast[class*="bp3-intent-"] .bp3-button .bp3-icon, .bp3-toast[class*="bp3-intent-"] .bp3-button:active{
    color:rgba(255, 255, 255, 0.7) !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:focus{
    outline-color:rgba(255, 255, 255, 0.5); }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:hover{
    background-color:rgba(255, 255, 255, 0.15) !important;
    color:#ffffff !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:active{
    background-color:rgba(255, 255, 255, 0.3) !important;
    color:#ffffff !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button::after{
    background:rgba(255, 255, 255, 0.3) !important; }
  .bp3-toast.bp3-intent-primary{
    background-color:#137cbd;
    color:#ffffff; }
  .bp3-toast.bp3-intent-success{
    background-color:#0f9960;
    color:#ffffff; }
  .bp3-toast.bp3-intent-warning{
    background-color:#d9822b;
    color:#ffffff; }
  .bp3-toast.bp3-intent-danger{
    background-color:#db3737;
    color:#ffffff; }

.bp3-toast-message{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  padding:11px;
  word-break:break-word; }

.bp3-toast-container{
  display:-webkit-box !important;
  display:-ms-flexbox !important;
  display:flex !important;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  position:fixed;
  right:0;
  left:0;
  z-index:40;
  overflow:hidden;
  padding:0 20px 20px;
  pointer-events:none; }
  .bp3-toast-container.bp3-toast-container-top{
    top:0;
    bottom:auto; }
  .bp3-toast-container.bp3-toast-container-bottom{
    -webkit-box-orient:vertical;
    -webkit-box-direction:reverse;
        -ms-flex-direction:column-reverse;
            flex-direction:column-reverse;
    top:auto;
    bottom:0; }
  .bp3-toast-container.bp3-toast-container-left{
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
  .bp3-toast-container.bp3-toast-container-right{
    -webkit-box-align:end;
        -ms-flex-align:end;
            align-items:flex-end; }

.bp3-toast-container-bottom .bp3-toast.bp3-toast-enter:not(.bp3-toast-enter-active),
.bp3-toast-container-bottom .bp3-toast.bp3-toast-enter:not(.bp3-toast-enter-active) ~ .bp3-toast, .bp3-toast-container-bottom .bp3-toast.bp3-toast-appear:not(.bp3-toast-appear-active),
.bp3-toast-container-bottom .bp3-toast.bp3-toast-appear:not(.bp3-toast-appear-active) ~ .bp3-toast,
.bp3-toast-container-bottom .bp3-toast.bp3-toast-leave-active ~ .bp3-toast{
  -webkit-transform:translateY(60px);
          transform:translateY(60px); }
.bp3-tooltip{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  -webkit-transform:scale(1);
          transform:scale(1); }
  .bp3-tooltip .bp3-popover-arrow{
    position:absolute;
    width:22px;
    height:22px; }
    .bp3-tooltip .bp3-popover-arrow::before{
      margin:4px;
      width:14px;
      height:14px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip{
    margin-top:-11px;
    margin-bottom:11px; }
    .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow{
      bottom:-8px; }
      .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(-90deg);
                transform:rotate(-90deg); }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip{
    margin-left:11px; }
    .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow{
      left:-8px; }
      .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(0);
                transform:rotate(0); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip{
    margin-top:11px; }
    .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow{
      top:-8px; }
      .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(90deg);
                transform:rotate(90deg); }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip{
    margin-right:11px;
    margin-left:-11px; }
    .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow{
      right:-8px; }
      .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(180deg);
                transform:rotate(180deg); }
  .bp3-tether-element-attached-middle > .bp3-tooltip > .bp3-popover-arrow{
    top:50%;
    -webkit-transform:translateY(-50%);
            transform:translateY(-50%); }
  .bp3-tether-element-attached-center > .bp3-tooltip > .bp3-popover-arrow{
    right:50%;
    -webkit-transform:translateX(50%);
            transform:translateX(50%); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow{
    top:-0.22183px; }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow{
    right:-0.22183px; }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow{
    left:-0.22183px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow{
    bottom:-0.22183px; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:top left;
            transform-origin:top left; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:top center;
            transform-origin:top center; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:top right;
            transform-origin:top right; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:center left;
            transform-origin:center left; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:center center;
            transform-origin:center center; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:center right;
            transform-origin:center right; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:bottom left;
            transform-origin:bottom left; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:bottom center;
            transform-origin:bottom center; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:bottom right;
            transform-origin:bottom right; }
  .bp3-tooltip .bp3-popover-content{
    background:#394b59;
    color:#f5f8fa; }
  .bp3-tooltip .bp3-popover-arrow::before{
    -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2);
            box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2); }
  .bp3-tooltip .bp3-popover-arrow-border{
    fill:#10161a;
    fill-opacity:0.1; }
  .bp3-tooltip .bp3-popover-arrow-fill{
    fill:#394b59; }
  .bp3-popover-enter > .bp3-tooltip, .bp3-popover-appear > .bp3-tooltip{
    -webkit-transform:scale(0.8);
            transform:scale(0.8); }
  .bp3-popover-enter-active > .bp3-tooltip, .bp3-popover-appear-active > .bp3-tooltip{
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-popover-exit > .bp3-tooltip{
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-popover-exit-active > .bp3-tooltip{
    -webkit-transform:scale(0.8);
            transform:scale(0.8);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-tooltip .bp3-popover-content{
    padding:10px 12px; }
  .bp3-tooltip.bp3-dark,
  .bp3-dark .bp3-tooltip{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
    .bp3-tooltip.bp3-dark .bp3-popover-content,
    .bp3-dark .bp3-tooltip .bp3-popover-content{
      background:#e1e8ed;
      color:#394b59; }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow::before,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow::before{
      -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4);
              box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4); }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow-border,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow-border{
      fill:#10161a;
      fill-opacity:0.2; }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow-fill,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow-fill{
      fill:#e1e8ed; }
  .bp3-tooltip.bp3-intent-primary .bp3-popover-content{
    background:#137cbd;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-primary .bp3-popover-arrow-fill{
    fill:#137cbd; }
  .bp3-tooltip.bp3-intent-success .bp3-popover-content{
    background:#0f9960;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-success .bp3-popover-arrow-fill{
    fill:#0f9960; }
  .bp3-tooltip.bp3-intent-warning .bp3-popover-content{
    background:#d9822b;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-warning .bp3-popover-arrow-fill{
    fill:#d9822b; }
  .bp3-tooltip.bp3-intent-danger .bp3-popover-content{
    background:#db3737;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-danger .bp3-popover-arrow-fill{
    fill:#db3737; }

.bp3-tooltip-indicator{
  border-bottom:dotted 1px;
  cursor:help; }
.bp3-tree .bp3-icon, .bp3-tree .bp3-icon-standard, .bp3-tree .bp3-icon-large{
  color:#5c7080; }
  .bp3-tree .bp3-icon.bp3-intent-primary, .bp3-tree .bp3-icon-standard.bp3-intent-primary, .bp3-tree .bp3-icon-large.bp3-intent-primary{
    color:#137cbd; }
  .bp3-tree .bp3-icon.bp3-intent-success, .bp3-tree .bp3-icon-standard.bp3-intent-success, .bp3-tree .bp3-icon-large.bp3-intent-success{
    color:#0f9960; }
  .bp3-tree .bp3-icon.bp3-intent-warning, .bp3-tree .bp3-icon-standard.bp3-intent-warning, .bp3-tree .bp3-icon-large.bp3-intent-warning{
    color:#d9822b; }
  .bp3-tree .bp3-icon.bp3-intent-danger, .bp3-tree .bp3-icon-standard.bp3-intent-danger, .bp3-tree .bp3-icon-large.bp3-intent-danger{
    color:#db3737; }

.bp3-tree-node-list{
  margin:0;
  padding-left:0;
  list-style:none; }

.bp3-tree-root{
  position:relative;
  background-color:transparent;
  cursor:default;
  padding-left:0; }

.bp3-tree-node-content-0{
  padding-left:0px; }

.bp3-tree-node-content-1{
  padding-left:23px; }

.bp3-tree-node-content-2{
  padding-left:46px; }

.bp3-tree-node-content-3{
  padding-left:69px; }

.bp3-tree-node-content-4{
  padding-left:92px; }

.bp3-tree-node-content-5{
  padding-left:115px; }

.bp3-tree-node-content-6{
  padding-left:138px; }

.bp3-tree-node-content-7{
  padding-left:161px; }

.bp3-tree-node-content-8{
  padding-left:184px; }

.bp3-tree-node-content-9{
  padding-left:207px; }

.bp3-tree-node-content-10{
  padding-left:230px; }

.bp3-tree-node-content-11{
  padding-left:253px; }

.bp3-tree-node-content-12{
  padding-left:276px; }

.bp3-tree-node-content-13{
  padding-left:299px; }

.bp3-tree-node-content-14{
  padding-left:322px; }

.bp3-tree-node-content-15{
  padding-left:345px; }

.bp3-tree-node-content-16{
  padding-left:368px; }

.bp3-tree-node-content-17{
  padding-left:391px; }

.bp3-tree-node-content-18{
  padding-left:414px; }

.bp3-tree-node-content-19{
  padding-left:437px; }

.bp3-tree-node-content-20{
  padding-left:460px; }

.bp3-tree-node-content{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  width:100%;
  height:30px;
  padding-right:5px; }
  .bp3-tree-node-content:hover{
    background-color:rgba(191, 204, 214, 0.4); }

.bp3-tree-node-caret,
.bp3-tree-node-caret-none{
  min-width:30px; }

.bp3-tree-node-caret{
  color:#5c7080;
  -webkit-transform:rotate(0deg);
          transform:rotate(0deg);
  cursor:pointer;
  padding:7px;
  -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-tree-node-caret:hover{
    color:#182026; }
  .bp3-dark .bp3-tree-node-caret{
    color:#a7b6c2; }
    .bp3-dark .bp3-tree-node-caret:hover{
      color:#f5f8fa; }
  .bp3-tree-node-caret.bp3-tree-node-caret-open{
    -webkit-transform:rotate(90deg);
            transform:rotate(90deg); }
  .bp3-tree-node-caret.bp3-icon-standard::before{
    content:""; }

.bp3-tree-node-icon{
  position:relative;
  margin-right:7px; }

.bp3-tree-node-label{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  position:relative;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-tree-node-label span{
    display:inline; }

.bp3-tree-node-secondary-label{
  padding:0 5px;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-tree-node-secondary-label .bp3-popover-wrapper,
  .bp3-tree-node-secondary-label .bp3-popover-target{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center; }

.bp3-tree-node.bp3-disabled .bp3-tree-node-content{
  background-color:inherit;
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-tree-node.bp3-disabled .bp3-tree-node-caret,
.bp3-tree-node.bp3-disabled .bp3-tree-node-icon{
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content{
  background-color:#137cbd; }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content,
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon, .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon-standard, .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon-large{
    color:#ffffff; }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-tree-node-caret::before{
    color:rgba(255, 255, 255, 0.7); }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-tree-node-caret:hover::before{
    color:#ffffff; }

.bp3-dark .bp3-tree-node-content:hover{
  background-color:rgba(92, 112, 128, 0.3); }

.bp3-dark .bp3-tree .bp3-icon, .bp3-dark .bp3-tree .bp3-icon-standard, .bp3-dark .bp3-tree .bp3-icon-large{
  color:#a7b6c2; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-primary, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-primary, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-primary{
    color:#137cbd; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-success, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-success, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-success{
    color:#0f9960; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-warning, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-warning, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-warning{
    color:#d9822b; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-danger, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-danger, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-danger{
    color:#db3737; }

.bp3-dark .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content{
  background-color:#137cbd; }
/*!

Copyright 2017-present Palantir Technologies, Inc. All rights reserved.
Licensed under the Apache License, Version 2.0.

*/
.bp3-omnibar{
  -webkit-filter:blur(0);
          filter:blur(0);
  opacity:1;
  top:20vh;
  left:calc(50% - 250px);
  z-index:21;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  background-color:#ffffff;
  width:500px; }
  .bp3-omnibar.bp3-overlay-enter, .bp3-omnibar.bp3-overlay-appear{
    -webkit-filter:blur(20px);
            filter:blur(20px);
    opacity:0.2; }
  .bp3-omnibar.bp3-overlay-enter-active, .bp3-omnibar.bp3-overlay-appear-active{
    -webkit-filter:blur(0);
            filter:blur(0);
    opacity:1;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:filter, opacity;
    transition-property:filter, opacity, -webkit-filter;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-omnibar.bp3-overlay-exit{
    -webkit-filter:blur(0);
            filter:blur(0);
    opacity:1; }
  .bp3-omnibar.bp3-overlay-exit-active{
    -webkit-filter:blur(20px);
            filter:blur(20px);
    opacity:0.2;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:filter, opacity;
    transition-property:filter, opacity, -webkit-filter;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-omnibar .bp3-input{
    border-radius:0;
    background-color:transparent; }
    .bp3-omnibar .bp3-input, .bp3-omnibar .bp3-input:focus{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-omnibar .bp3-menu{
    border-radius:0;
    -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
    background-color:transparent;
    max-height:calc(60vh - 40px);
    overflow:auto; }
    .bp3-omnibar .bp3-menu:empty{
      display:none; }
  .bp3-dark .bp3-omnibar, .bp3-omnibar.bp3-dark{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    background-color:#30404d; }

.bp3-omnibar-overlay .bp3-overlay-backdrop{
  background-color:rgba(16, 22, 26, 0.2); }

.bp3-select-popover .bp3-popover-content{
  padding:5px; }

.bp3-select-popover .bp3-input-group{
  margin-bottom:0; }

.bp3-select-popover .bp3-menu{
  max-width:400px;
  max-height:300px;
  overflow:auto;
  padding:0; }
  .bp3-select-popover .bp3-menu:not(:first-child){
    padding-top:5px; }

.bp3-multi-select{
  min-width:150px; }

.bp3-multi-select-popover .bp3-menu{
  max-width:400px;
  max-height:300px;
  overflow:auto; }

.bp3-select-popover .bp3-popover-content{
  padding:5px; }

.bp3-select-popover .bp3-input-group{
  margin-bottom:0; }

.bp3-select-popover .bp3-menu{
  max-width:400px;
  max-height:300px;
  overflow:auto;
  padding:0; }
  .bp3-select-popover .bp3-menu:not(:first-child){
    padding-top:5px; }
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensureUiComponents() in @jupyterlab/buildutils */

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

/* Icons urls */

:root {
  --jp-icon-add: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDEzaC02djZoLTJ2LTZINXYtMmg2VjVoMnY2aDZ2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-bug: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDhoLTIuODFjLS40NS0uNzgtMS4wNy0xLjQ1LTEuODItMS45NkwxNyA0LjQxIDE1LjU5IDNsLTIuMTcgMi4xN0MxMi45NiA1LjA2IDEyLjQ5IDUgMTIgNWMtLjQ5IDAtLjk2LjA2LTEuNDEuMTdMOC40MSAzIDcgNC40MWwxLjYyIDEuNjNDNy44OCA2LjU1IDcuMjYgNy4yMiA2LjgxIDhINHYyaDIuMDljLS4wNS4zMy0uMDkuNjYtLjA5IDF2MUg0djJoMnYxYzAgLjM0LjA0LjY3LjA5IDFINHYyaDIuODFjMS4wNCAxLjc5IDIuOTcgMyA1LjE5IDNzNC4xNS0xLjIxIDUuMTktM0gyMHYtMmgtMi4wOWMuMDUtLjMzLjA5LS42Ni4wOS0xdi0xaDJ2LTJoLTJ2LTFjMC0uMzQtLjA0LS42Ny0uMDktMUgyMFY4em0tNiA4aC00di0yaDR2MnptMC00aC00di0yaDR2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-build: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE0LjkgMTcuNDVDMTYuMjUgMTcuNDUgMTcuMzUgMTYuMzUgMTcuMzUgMTVDMTcuMzUgMTMuNjUgMTYuMjUgMTIuNTUgMTQuOSAxMi41NUMxMy41NCAxMi41NSAxMi40NSAxMy42NSAxMi40NSAxNUMxMi40NSAxNi4zNSAxMy41NCAxNy40NSAxNC45IDE3LjQ1Wk0yMC4xIDE1LjY4TDIxLjU4IDE2Ljg0QzIxLjcxIDE2Ljk1IDIxLjc1IDE3LjEzIDIxLjY2IDE3LjI5TDIwLjI2IDE5LjcxQzIwLjE3IDE5Ljg2IDIwIDE5LjkyIDE5LjgzIDE5Ljg2TDE4LjA5IDE5LjE2QzE3LjczIDE5LjQ0IDE3LjMzIDE5LjY3IDE2LjkxIDE5Ljg1TDE2LjY0IDIxLjdDMTYuNjIgMjEuODcgMTYuNDcgMjIgMTYuMyAyMkgxMy41QzEzLjMyIDIyIDEzLjE4IDIxLjg3IDEzLjE1IDIxLjdMMTIuODkgMTkuODVDMTIuNDYgMTkuNjcgMTIuMDcgMTkuNDQgMTEuNzEgMTkuMTZMOS45NjAwMiAxOS44NkM5LjgxMDAyIDE5LjkyIDkuNjIwMDIgMTkuODYgOS41NDAwMiAxOS43MUw4LjE0MDAyIDE3LjI5QzguMDUwMDIgMTcuMTMgOC4wOTAwMiAxNi45NSA4LjIyMDAyIDE2Ljg0TDkuNzAwMDIgMTUuNjhMOS42NTAwMSAxNUw5LjcwMDAyIDE0LjMxTDguMjIwMDIgMTMuMTZDOC4wOTAwMiAxMy4wNSA4LjA1MDAyIDEyLjg2IDguMTQwMDIgMTIuNzFMOS41NDAwMiAxMC4yOUM5LjYyMDAyIDEwLjEzIDkuODEwMDIgMTAuMDcgOS45NjAwMiAxMC4xM0wxMS43MSAxMC44NEMxMi4wNyAxMC41NiAxMi40NiAxMC4zMiAxMi44OSAxMC4xNUwxMy4xNSA4LjI4OTk4QzEzLjE4IDguMTI5OTggMTMuMzIgNy45OTk5OCAxMy41IDcuOTk5OThIMTYuM0MxNi40NyA3Ljk5OTk4IDE2LjYyIDguMTI5OTggMTYuNjQgOC4yODk5OEwxNi45MSAxMC4xNUMxNy4zMyAxMC4zMiAxNy43MyAxMC41NiAxOC4wOSAxMC44NEwxOS44MyAxMC4xM0MyMCAxMC4wNyAyMC4xNyAxMC4xMyAyMC4yNiAxMC4yOUwyMS42NiAxMi43MUMyMS43NSAxMi44NiAyMS43MSAxMy4wNSAyMS41OCAxMy4xNkwyMC4xIDE0LjMxTDIwLjE1IDE1TDIwLjEgMTUuNjhaIi8+CiAgICA8cGF0aCBkPSJNNy4zMjk2NiA3LjQ0NDU0QzguMDgzMSA3LjAwOTU0IDguMzM5MzIgNi4wNTMzMiA3LjkwNDMyIDUuMjk5ODhDNy40NjkzMiA0LjU0NjQzIDYuNTA4MSA0LjI4MTU2IDUuNzU0NjYgNC43MTY1NkM1LjM5MTc2IDQuOTI2MDggNS4xMjY5NSA1LjI3MTE4IDUuMDE4NDkgNS42NzU5NEM0LjkxMDA0IDYuMDgwNzEgNC45NjY4MiA2LjUxMTk4IDUuMTc2MzQgNi44NzQ4OEM1LjYxMTM0IDcuNjI4MzIgNi41NzYyMiA3Ljg3OTU0IDcuMzI5NjYgNy40NDQ1NFpNOS42NTcxOCA0Ljc5NTkzTDEwLjg2NzIgNC45NTE3OUMxMC45NjI4IDQuOTc3NDEgMTEuMDQwMiA1LjA3MTMzIDExLjAzODIgNS4xODc5M0wxMS4wMzg4IDYuOTg4OTNDMTEuMDQ1NSA3LjEwMDU0IDEwLjk2MTYgNy4xOTUxOCAxMC44NTUgNy4yMTA1NEw5LjY2MDAxIDcuMzgwODNMOS4yMzkxNSA4LjEzMTg4TDkuNjY5NjEgOS4yNTc0NUM5LjcwNzI5IDkuMzYyNzEgOS42NjkzNCA5LjQ3Njk5IDkuNTc0MDggOS41MzE5OUw4LjAxNTIzIDEwLjQzMkM3LjkxMTMxIDEwLjQ5MiA3Ljc5MzM3IDEwLjQ2NzcgNy43MjEwNSAxMC4zODI0TDYuOTg3NDggOS40MzE4OEw2LjEwOTMxIDkuNDMwODNMNS4zNDcwNCAxMC4zOTA1QzUuMjg5MDkgMTAuNDcwMiA1LjE3MzgzIDEwLjQ5MDUgNS4wNzE4NyAxMC40MzM5TDMuNTEyNDUgOS41MzI5M0MzLjQxMDQ5IDkuNDc2MzMgMy4zNzY0NyA5LjM1NzQxIDMuNDEwNzUgOS4yNTY3OUwzLjg2MzQ3IDguMTQwOTNMMy42MTc0OSA3Ljc3NDg4TDMuNDIzNDcgNy4zNzg4M0wyLjIzMDc1IDcuMjEyOTdDMi4xMjY0NyA3LjE5MjM1IDIuMDQwNDkgNy4xMDM0MiAyLjA0MjQ1IDYuOTg2ODJMMi4wNDE4NyA1LjE4NTgyQzIuMDQzODMgNS4wNjkyMiAyLjExOTA5IDQuOTc5NTggMi4yMTcwNCA0Ljk2OTIyTDMuNDIwNjUgNC43OTM5M0wzLjg2NzQ5IDQuMDI3ODhMMy40MTEwNSAyLjkxNzMxQzMuMzczMzcgMi44MTIwNCAzLjQxMTMxIDIuNjk3NzYgMy41MTUyMyAyLjYzNzc2TDUuMDc0MDggMS43Mzc3NkM1LjE2OTM0IDEuNjgyNzYgNS4yODcyOSAxLjcwNzA0IDUuMzU5NjEgMS43OTIzMUw2LjExOTE1IDIuNzI3ODhMNi45ODAwMSAyLjczODkzTDcuNzI0OTYgMS43ODkyMkM3Ljc5MTU2IDEuNzA0NTggNy45MTU0OCAxLjY3OTIyIDguMDA4NzkgMS43NDA4Mkw5LjU2ODIxIDIuNjQxODJDOS42NzAxNyAyLjY5ODQyIDkuNzEyODUgMi44MTIzNCA5LjY4NzIzIDIuOTA3OTdMOS4yMTcxOCA0LjAzMzgzTDkuNDYzMTYgNC4zOTk4OEw5LjY1NzE4IDQuNzk1OTNaIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iOS45LDEzLjYgMy42LDcuNCA0LjQsNi42IDkuOSwxMi4yIDE1LjQsNi43IDE2LjEsNy40ICIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNS45TDksOS43bDMuOC0zLjhsMS4yLDEuMmwtNC45LDVsLTQuOS01TDUuMiw1Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNy41TDksMTEuMmwzLjgtMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-left: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik0xMC44LDEyLjhMNy4xLDlsMy44LTMuOGwwLDcuNkgxMC44eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-right: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik03LjIsNS4yTDEwLjksOWwtMy44LDMuOFY1LjJINy4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-up-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iMTUuNCwxMy4zIDkuOSw3LjcgNC40LDEzLjIgMy42LDEyLjUgOS45LDYuMyAxNi4xLDEyLjYgIi8+Cgk8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-up: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik01LjIsMTAuNUw5LDYuOGwzLjgsMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-case-sensitive: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgogIDxnIGNsYXNzPSJqcC1pY29uLWFjY2VudDIiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTcuNiw4aDAuOWwzLjUsOGgtMS4xTDEwLDE0SDZsLTAuOSwySDRMNy42LDh6IE04LDkuMUw2LjQsMTNoMy4yTDgsOS4xeiIvPgogICAgPHBhdGggZD0iTTE2LjYsOS44Yy0wLjIsMC4xLTAuNCwwLjEtMC43LDAuMWMtMC4yLDAtMC40LTAuMS0wLjYtMC4yYy0wLjEtMC4xLTAuMi0wLjQtMC4yLTAuNyBjLTAuMywwLjMtMC42LDAuNS0wLjksMC43Yy0wLjMsMC4xLTAuNywwLjItMS4xLDAuMmMtMC4zLDAtMC41LDAtMC43LTAuMWMtMC4yLTAuMS0wLjQtMC4yLTAuNi0wLjNjLTAuMi0wLjEtMC4zLTAuMy0wLjQtMC41IGMtMC4xLTAuMi0wLjEtMC40LTAuMS0wLjdjMC0wLjMsMC4xLTAuNiwwLjItMC44YzAuMS0wLjIsMC4zLTAuNCwwLjQtMC41QzEyLDcsMTIuMiw2LjksMTIuNSw2LjhjMC4yLTAuMSwwLjUtMC4xLDAuNy0wLjIgYzAuMy0wLjEsMC41LTAuMSwwLjctMC4xYzAuMiwwLDAuNC0wLjEsMC42LTAuMWMwLjIsMCwwLjMtMC4xLDAuNC0wLjJjMC4xLTAuMSwwLjItMC4yLDAuMi0wLjRjMC0xLTEuMS0xLTEuMy0xIGMtMC40LDAtMS40LDAtMS40LDEuMmgtMC45YzAtMC40LDAuMS0wLjcsMC4yLTFjMC4xLTAuMiwwLjMtMC40LDAuNS0wLjZjMC4yLTAuMiwwLjUtMC4zLDAuOC0wLjNDMTMuMyw0LDEzLjYsNCwxMy45LDQgYzAuMywwLDAuNSwwLDAuOCwwLjFjMC4zLDAsMC41LDAuMSwwLjcsMC4yYzAuMiwwLjEsMC40LDAuMywwLjUsMC41QzE2LDUsMTYsNS4yLDE2LDUuNnYyLjljMCwwLjIsMCwwLjQsMCwwLjUgYzAsMC4xLDAuMSwwLjIsMC4zLDAuMmMwLjEsMCwwLjIsMCwwLjMsMFY5Ljh6IE0xNS4yLDYuOWMtMS4yLDAuNi0zLjEsMC4yLTMuMSwxLjRjMCwxLjQsMy4xLDEsMy4xLTAuNVY2Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-check: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkgMTYuMTdMNC44MyAxMmwtMS40MiAxLjQxTDkgMTkgMjEgN2wtMS40MS0xLjQxeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDJDNi40NyAyIDIgNi40NyAyIDEyczQuNDcgMTAgMTAgMTAgMTAtNC40NyAxMC0xMFMxNy41MyAyIDEyIDJ6bTAgMThjLTQuNDEgMC04LTMuNTktOC04czMuNTktOCA4LTggOCAzLjU5IDggOC0zLjU5IDgtOCA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iOSIgY3k9IjkiIHI9IjgiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-clear: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8bWFzayBpZD0iZG9udXRIb2xlIj4KICAgIDxyZWN0IHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgZmlsbD0id2hpdGUiIC8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSI4IiBmaWxsPSJibGFjayIvPgogIDwvbWFzaz4KCiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxyZWN0IGhlaWdodD0iMTgiIHdpZHRoPSIyIiB4PSIxMSIgeT0iMyIgdHJhbnNmb3JtPSJyb3RhdGUoMzE1LCAxMiwgMTIpIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCIgbWFzaz0idXJsKCNkb251dEhvbGUpIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-close: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1ub25lIGpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIGpwLWljb24zLWhvdmVyIiBmaWxsPSJub25lIj4KICAgIDxjaXJjbGUgY3g9IjEyIiBjeT0iMTIiIHI9IjExIi8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIGpwLWljb24tYWNjZW50Mi1ob3ZlciIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMTkgNi40MUwxNy41OSA1IDEyIDEwLjU5IDYuNDEgNSA1IDYuNDEgMTAuNTkgMTIgNSAxNy41OSA2LjQxIDE5IDEyIDEzLjQxIDE3LjU5IDE5IDE5IDE3LjU5IDEzLjQxIDEyeiIvPgogIDwvZz4KCiAgPGcgY2xhc3M9ImpwLWljb24tbm9uZSBqcC1pY29uLWJ1c3kiIGZpbGw9Im5vbmUiPgogICAgPGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-console: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwMCAyMDAiPgogIDxnIGNsYXNzPSJqcC1pY29uLWJyYW5kMSBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMjg4RDEiPgogICAgPHBhdGggZD0iTTIwIDE5LjhoMTYwdjE1OS45SDIweiIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNmZmYiPgogICAgPHBhdGggZD0iTTEwNSAxMjcuM2g0MHYxMi44aC00MHpNNTEuMSA3N0w3NCA5OS45bC0yMy4zIDIzLjMgMTAuNSAxMC41IDIzLjMtMjMuM0w5NSA5OS45IDg0LjUgODkuNCA2MS42IDY2LjV6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-copy: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTExLjksMUgzLjJDMi40LDEsMS43LDEuNywxLjcsMi41djEwLjJoMS41VjIuNWg4LjdWMXogTTE0LjEsMy45aC04Yy0wLjgsMC0xLjUsMC43LTEuNSwxLjV2MTAuMmMwLDAuOCwwLjcsMS41LDEuNSwxLjVoOCBjMC44LDAsMS41LTAuNywxLjUtMS41VjUuNEMxNS41LDQuNiwxNC45LDMuOSwxNC4xLDMuOXogTTE0LjEsMTUuNWgtOFY1LjRoOFYxNS41eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-cut: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkuNjQgNy42NGMuMjMtLjUuMzYtMS4wNS4zNi0xLjY0IDAtMi4yMS0xLjc5LTQtNC00UzIgMy43OSAyIDZzMS43OSA0IDQgNGMuNTkgMCAxLjE0LS4xMyAxLjY0LS4zNkwxMCAxMmwtMi4zNiAyLjM2QzcuMTQgMTQuMTMgNi41OSAxNCA2IDE0Yy0yLjIxIDAtNCAxLjc5LTQgNHMxLjc5IDQgNCA0IDQtMS43OSA0LTRjMC0uNTktLjEzLTEuMTQtLjM2LTEuNjRMMTIgMTRsNyA3aDN2LTFMOS42NCA3LjY0ek02IDhjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTAgMTJjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTYtNy41Yy0uMjggMC0uNS0uMjItLjUtLjVzLjIyLS41LjUtLjUuNS4yMi41LjUtLjIyLjUtLjUuNXpNMTkgM2wtNiA2IDIgMiA3LTdWM3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-download: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDloLTRWM0g5djZINWw3IDcgNy03ek01IDE4djJoMTR2LTJINXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-edit: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMgMTcuMjVWMjFoMy43NUwxNy44MSA5Ljk0bC0zLjc1LTMuNzVMMyAxNy4yNXpNMjAuNzEgNy4wNGMuMzktLjM5LjM5LTEuMDIgMC0xLjQxbC0yLjM0LTIuMzRjLS4zOS0uMzktMS4wMi0uMzktMS40MSAwbC0xLjgzIDEuODMgMy43NSAzLjc1IDEuODMtMS44M3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-ellipses: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iNSIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxOSIgY3k9IjEyIiByPSIyIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-extension: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwLjUgMTFIMTlWN2MwLTEuMS0uOS0yLTItMmgtNFYzLjVDMTMgMi4xMiAxMS44OCAxIDEwLjUgMVM4IDIuMTIgOCAzLjVWNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAydjMuOEgzLjVjMS40OSAwIDIuNyAxLjIxIDIuNyAyLjdzLTEuMjEgMi43LTIuNyAyLjdIMlYyMGMwIDEuMS45IDIgMiAyaDMuOHYtMS41YzAtMS40OSAxLjIxLTIuNyAyLjctMi43IDEuNDkgMCAyLjcgMS4yMSAyLjcgMi43VjIySDE3YzEuMSAwIDItLjkgMi0ydi00aDEuNWMxLjM4IDAgMi41LTEuMTIgMi41LTIuNVMyMS44OCAxMSAyMC41IDExeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-fast-forward: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTQgMThsOC41LTZMNCA2djEyem05LTEydjEybDguNS02TDEzIDZ6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-file-upload: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkgMTZoNnYtNmg0bC03LTctNyA3aDR6bS00IDJoMTR2Mkg1eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-file: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuMyA4LjJsLTUuNS01LjVjLS4zLS4zLS43LS41LTEuMi0uNUgzLjljLS44LjEtMS42LjktMS42IDEuOHYxNC4xYzAgLjkuNyAxLjYgMS42IDEuNmgxNC4yYy45IDAgMS42LS43IDEuNi0xLjZWOS40Yy4xLS41LS4xLS45LS40LTEuMnptLTUuOC0zLjNsMy40IDMuNmgtMy40VjQuOXptMy45IDEyLjdINC43Yy0uMSAwLS4yIDAtLjItLjJWNC43YzAtLjIuMS0uMy4yLS4zaDcuMnY0LjRzMCAuOC4zIDEuMWMuMy4zIDEuMS4zIDEuMS4zaDQuM3Y3LjJzLS4xLjItLjIuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-filter-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEwIDE4aDR2LTJoLTR2MnpNMyA2djJoMThWNkgzem0zIDdoMTJ2LTJINnYyeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY4YzAtMS4xLS45LTItMi0yaC04bC0yLTJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-html5: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMDAiIGQ9Ik0xMDguNCAwaDIzdjIyLjhoMjEuMlYwaDIzdjY5aC0yM1Y0NmgtMjF2MjNoLTIzLjJNMjA2IDIzaC0yMC4zVjBoNjMuN3YyM0gyMjl2NDZoLTIzbTUzLjUtNjloMjQuMWwxNC44IDI0LjNMMzEzLjIgMGgyNC4xdjY5aC0yM1YzNC44bC0xNi4xIDI0LjgtMTYuMS0yNC44VjY5aC0yMi42bTg5LjItNjloMjN2NDYuMmgzMi42VjY5aC01NS42Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI2U0NGQyNiIgZD0iTTEwNy42IDQ3MWwtMzMtMzcwLjRoMzYyLjhsLTMzIDM3MC4yTDI1NS43IDUxMiIvPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNmMTY1MjkiIGQ9Ik0yNTYgNDgwLjVWMTMxaDE0OC4zTDM3NiA0NDciLz4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNlYmViZWIiIGQ9Ik0xNDIgMTc2LjNoMTE0djQ1LjRoLTY0LjJsNC4yIDQ2LjVoNjB2NDUuM0gxNTQuNG0yIDIyLjhIMjAybDMuMiAzNi4zIDUwLjggMTMuNnY0Ny40bC05My4yLTI2Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIiBmaWxsPSIjZmZmIiBkPSJNMzY5LjYgMTc2LjNIMjU1Ljh2NDUuNGgxMDkuNm0tNC4xIDQ2LjVIMjU1Ljh2NDUuNGg1NmwtNS4zIDU5LTUwLjcgMTMuNnY0Ny4ybDkzLTI1LjgiLz4KPC9zdmc+Cg==);
  --jp-icon-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1icmFuZDQganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNGRkYiIGQ9Ik0yLjIgMi4yaDE3LjV2MTcuNUgyLjJ6Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzNGNTFCNSIgZD0iTTIuMiAyLjJ2MTcuNWgxNy41bC4xLTE3LjVIMi4yem0xMi4xIDIuMmMxLjIgMCAyLjIgMSAyLjIgMi4ycy0xIDIuMi0yLjIgMi4yLTIuMi0xLTIuMi0yLjIgMS0yLjIgMi4yLTIuMnpNNC40IDE3LjZsMy4zLTguOCAzLjMgNi42IDIuMi0zLjIgNC40IDUuNEg0LjR6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-inspector: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY2YzAtMS4xLS45LTItMi0yem0tNSAxNEg0di00aDExdjR6bTAtNUg0VjloMTF2NHptNSA1aC00VjloNHY5eiIvPgo8L3N2Zz4K);
  --jp-icon-json: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMSBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNGOUE4MjUiPgogICAgPHBhdGggZD0iTTIwLjIgMTEuOGMtMS42IDAtMS43LjUtMS43IDEgMCAuNC4xLjkuMSAxLjMuMS41LjEuOS4xIDEuMyAwIDEuNy0xLjQgMi4zLTMuNSAyLjNoLS45di0xLjloLjVjMS4xIDAgMS40IDAgMS40LS44IDAtLjMgMC0uNi0uMS0xIDAtLjQtLjEtLjgtLjEtMS4yIDAtMS4zIDAtMS44IDEuMy0yLTEuMy0uMi0xLjMtLjctMS4zLTIgMC0uNC4xLS44LjEtMS4yLjEtLjQuMS0uNy4xLTEgMC0uOC0uNC0uNy0xLjQtLjhoLS41VjQuMWguOWMyLjIgMCAzLjUuNyAzLjUgMi4zIDAgLjQtLjEuOS0uMSAxLjMtLjEuNS0uMS45LS4xIDEuMyAwIC41LjIgMSAxLjcgMXYxLjh6TTEuOCAxMC4xYzEuNiAwIDEuNy0uNSAxLjctMSAwLS40LS4xLS45LS4xLTEuMy0uMS0uNS0uMS0uOS0uMS0xLjMgMC0xLjYgMS40LTIuMyAzLjUtMi4zaC45djEuOWgtLjVjLTEgMC0xLjQgMC0xLjQuOCAwIC4zIDAgLjYuMSAxIDAgLjIuMS42LjEgMSAwIDEuMyAwIDEuOC0xLjMgMkM2IDExLjIgNiAxMS43IDYgMTNjMCAuNC0uMS44LS4xIDEuMi0uMS4zLS4xLjctLjEgMSAwIC44LjMuOCAxLjQuOGguNXYxLjloLS45Yy0yLjEgMC0zLjUtLjYtMy41LTIuMyAwLS40LjEtLjkuMS0xLjMuMS0uNS4xLS45LjEtMS4zIDAtLjUtLjItMS0xLjctMXYtMS45eiIvPgogICAgPGNpcmNsZSBjeD0iMTEiIGN5PSIxMy44IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY3g9IjExIiBjeT0iOC4yIiByPSIyLjEiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter-favicon: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTUyIiBoZWlnaHQ9IjE2NSIgdmlld0JveD0iMCAwIDE1MiAxNjUiIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA3ODk0NywgMTEwLjU4MjkyNykiIGQ9Ik03NS45NDIyODQyLDI5LjU4MDQ1NjEgQzQzLjMwMjM5NDcsMjkuNTgwNDU2MSAxNC43OTY3ODMyLDE3LjY1MzQ2MzQgMCwwIEM1LjUxMDgzMjExLDE1Ljg0MDY4MjkgMTUuNzgxNTM4OSwyOS41NjY3NzMyIDI5LjM5MDQ5NDcsMzkuMjc4NDE3MSBDNDIuOTk5Nyw0OC45ODk4NTM3IDU5LjI3MzcsNTQuMjA2NzgwNSA3NS45NjA1Nzg5LDU0LjIwNjc4MDUgQzkyLjY0NzQ1NzksNTQuMjA2NzgwNSAxMDguOTIxNDU4LDQ4Ljk4OTg1MzcgMTIyLjUzMDY2MywzOS4yNzg0MTcxIEMxMzYuMTM5NDUzLDI5LjU2Njc3MzIgMTQ2LjQxMDI4NCwxNS44NDA2ODI5IDE1MS45MjExNTgsMCBDMTM3LjA4Nzg2OCwxNy42NTM0NjM0IDEwOC41ODI1ODksMjkuNTgwNDU2MSA3NS45NDIyODQyLDI5LjU4MDQ1NjEgTDc1Ljk0MjI4NDIsMjkuNTgwNDU2MSBaIiAvPgogICAgPHBhdGggdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMzczNjgsIDAuNzA0ODc4KSIgZD0iTTc1Ljk3ODQ1NzksMjQuNjI2NDA3MyBDMTA4LjYxODc2MywyNC42MjY0MDczIDEzNy4xMjQ0NTgsMzYuNTUzNDQxNSAxNTEuOTIxMTU4LDU0LjIwNjc4MDUgQzE0Ni40MTAyODQsMzguMzY2MjIyIDEzNi4xMzk0NTMsMjQuNjQwMTMxNyAxMjIuNTMwNjYzLDE0LjkyODQ4NzggQzEwOC45MjE0NTgsNS4yMTY4NDM5IDkyLjY0NzQ1NzksMCA3NS45NjA1Nzg5LDAgQzU5LjI3MzcsMCA0Mi45OTk3LDUuMjE2ODQzOSAyOS4zOTA0OTQ3LDE0LjkyODQ4NzggQzE1Ljc4MTUzODksMjQuNjQwMTMxNyA1LjUxMDgzMjExLDM4LjM2NjIyMiAwLDU0LjIwNjc4MDUgQzE0LjgzMzA4MTYsMzYuNTg5OTI5MyA0My4zMzg1Njg0LDI0LjYyNjQwNzMgNzUuOTc4NDU3OSwyNC42MjY0MDczIEw3NS45Nzg0NTc5LDI0LjYyNjQwNzMgWiIgLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzkiIGhlaWdodD0iNTEiIHZpZXdCb3g9IjAgMCAzOSA1MSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMTYzOCAtMjI4MSkiPgogICAgPGcgY2xhc3M9ImpwLWljb24td2FybjAiIGZpbGw9IiNGMzc3MjYiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5Ljc0IDIzMTEuOTgpIiBkPSJNIDE4LjI2NDYgNy4xMzQxMUMgMTAuNDE0NSA3LjEzNDExIDMuNTU4NzIgNC4yNTc2IDAgMEMgMS4zMjUzOSAzLjgyMDQgMy43OTU1NiA3LjEzMDgxIDcuMDY4NiA5LjQ3MzAzQyAxMC4zNDE3IDExLjgxNTIgMTQuMjU1NyAxMy4wNzM0IDE4LjI2OSAxMy4wNzM0QyAyMi4yODIzIDEzLjA3MzQgMjYuMTk2MyAxMS44MTUyIDI5LjQ2OTQgOS40NzMwM0MgMzIuNzQyNCA3LjEzMDgxIDM1LjIxMjYgMy44MjA0IDM2LjUzOCAwQyAzMi45NzA1IDQuMjU3NiAyNi4xMTQ4IDcuMTM0MTEgMTguMjY0NiA3LjEzNDExWiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5LjczIDIyODUuNDgpIiBkPSJNIDE4LjI3MzMgNS45MzkzMUMgMjYuMTIzNSA1LjkzOTMxIDMyLjk3OTMgOC44MTU4MyAzNi41MzggMTMuMDczNEMgMzUuMjEyNiA5LjI1MzAzIDMyLjc0MjQgNS45NDI2MiAyOS40Njk0IDMuNjAwNEMgMjYuMTk2MyAxLjI1ODE4IDIyLjI4MjMgMCAxOC4yNjkgMEMgMTQuMjU1NyAwIDEwLjM0MTcgMS4yNTgxOCA3LjA2ODYgMy42MDA0QyAzLjc5NTU2IDUuOTQyNjIgMS4zMjUzOSA5LjI1MzAzIDAgMTMuMDczNEMgMy41Njc0NSA4LjgyNDYzIDEwLjQyMzIgNS45MzkzMSAxOC4yNzMzIDUuOTM5MzFaIi8+CiAgICA8L2c+CiAgICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjY5LjMgMjI4MS4zMSkiIGQ9Ik0gNS44OTM1MyAyLjg0NEMgNS45MTg4OSAzLjQzMTY1IDUuNzcwODUgNC4wMTM2NyA1LjQ2ODE1IDQuNTE2NDVDIDUuMTY1NDUgNS4wMTkyMiA0LjcyMTY4IDUuNDIwMTUgNC4xOTI5OSA1LjY2ODUxQyAzLjY2NDMgNS45MTY4OCAzLjA3NDQ0IDYuMDAxNTEgMi40OTgwNSA1LjkxMTcxQyAxLjkyMTY2IDUuODIxOSAxLjM4NDYzIDUuNTYxNyAwLjk1NDg5OCA1LjE2NDAxQyAwLjUyNTE3IDQuNzY2MzMgMC4yMjIwNTYgNC4yNDkwMyAwLjA4MzkwMzcgMy42Nzc1N0MgLTAuMDU0MjQ4MyAzLjEwNjExIC0wLjAyMTIzIDIuNTA2MTcgMC4xNzg3ODEgMS45NTM2NEMgMC4zNzg3OTMgMS40MDExIDAuNzM2ODA5IDAuOTIwODE3IDEuMjA3NTQgMC41NzM1MzhDIDEuNjc4MjYgMC4yMjYyNTkgMi4yNDA1NSAwLjAyNzU5MTkgMi44MjMyNiAwLjAwMjY3MjI5QyAzLjYwMzg5IC0wLjAzMDcxMTUgNC4zNjU3MyAwLjI0OTc4OSA0Ljk0MTQyIDAuNzgyNTUxQyA1LjUxNzExIDEuMzE1MzEgNS44NTk1NiAyLjA1Njc2IDUuODkzNTMgMi44NDRaIi8+CiAgICAgIDxwYXRoIHRyYW5zZm9ybT0idHJhbnNsYXRlKDE2MzkuOCAyMzIzLjgxKSIgZD0iTSA3LjQyNzg5IDMuNTgzMzhDIDcuNDYwMDggNC4zMjQzIDcuMjczNTUgNS4wNTgxOSA2Ljg5MTkzIDUuNjkyMTNDIDYuNTEwMzEgNi4zMjYwNyA1Ljk1MDc1IDYuODMxNTYgNS4yODQxMSA3LjE0NDZDIDQuNjE3NDcgNy40NTc2MyAzLjg3MzcxIDcuNTY0MTQgMy4xNDcwMiA3LjQ1MDYzQyAyLjQyMDMyIDcuMzM3MTIgMS43NDMzNiA3LjAwODcgMS4yMDE4NCA2LjUwNjk1QyAwLjY2MDMyOCA2LjAwNTIgMC4yNzg2MSA1LjM1MjY4IDAuMTA1MDE3IDQuNjMyMDJDIC0wLjA2ODU3NTcgMy45MTEzNSAtMC4wMjYyMzYxIDMuMTU0OTQgMC4yMjY2NzUgMi40NTg1NkMgMC40Nzk1ODcgMS43NjIxNyAwLjkzMTY5NyAxLjE1NzEzIDEuNTI1NzYgMC43MjAwMzNDIDIuMTE5ODMgMC4yODI5MzUgMi44MjkxNCAwLjAzMzQzOTUgMy41NjM4OSAwLjAwMzEzMzQ0QyA0LjU0NjY3IC0wLjAzNzQwMzMgNS41MDUyOSAwLjMxNjcwNiA2LjIyOTYxIDAuOTg3ODM1QyA2Ljk1MzkzIDEuNjU4OTYgNy4zODQ4NCAyLjU5MjM1IDcuNDI3ODkgMy41ODMzOEwgNy40Mjc4OSAzLjU4MzM4WiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM4LjM2IDIyODYuMDYpIiBkPSJNIDIuMjc0NzEgNC4zOTYyOUMgMS44NDM2MyA0LjQxNTA4IDEuNDE2NzEgNC4zMDQ0NSAxLjA0Nzk5IDQuMDc4NDNDIDAuNjc5MjY4IDMuODUyNCAwLjM4NTMyOCAzLjUyMTE0IDAuMjAzMzcxIDMuMTI2NTZDIDAuMDIxNDEzNiAyLjczMTk4IC0wLjA0MDM3OTggMi4yOTE4MyAwLjAyNTgxMTYgMS44NjE4MUMgMC4wOTIwMDMxIDEuNDMxOCAwLjI4MzIwNCAxLjAzMTI2IDAuNTc1MjEzIDAuNzEwODgzQyAwLjg2NzIyMiAwLjM5MDUxIDEuMjQ2OTEgMC4xNjQ3MDggMS42NjYyMiAwLjA2MjA1OTJDIDIuMDg1NTMgLTAuMDQwNTg5NyAyLjUyNTYxIC0wLjAxNTQ3MTQgMi45MzA3NiAwLjEzNDIzNUMgMy4zMzU5MSAwLjI4Mzk0MSAzLjY4NzkyIDAuNTUxNTA1IDMuOTQyMjIgMC45MDMwNkMgNC4xOTY1MiAxLjI1NDYyIDQuMzQxNjkgMS42NzQzNiA0LjM1OTM1IDIuMTA5MTZDIDQuMzgyOTkgMi42OTEwNyA0LjE3Njc4IDMuMjU4NjkgMy43ODU5NyAzLjY4NzQ2QyAzLjM5NTE2IDQuMTE2MjQgMi44NTE2NiA0LjM3MTE2IDIuMjc0NzEgNC4zOTYyOUwgMi4yNzQ3MSA0LjM5NjI5WiIvPgogICAgPC9nPgogIDwvZz4+Cjwvc3ZnPgo=);
  --jp-icon-jupyterlab-wordmark: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyMDAiIHZpZXdCb3g9IjAgMCAxODYwLjggNDc1Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0RTRFNEUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDQ4MC4xMzY0MDEsIDY0LjI3MTQ5MykiPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMDAwMDAsIDU4Ljg3NTU2NikiPgogICAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA4NzYwMywgMC4xNDAyOTQpIj4KICAgICAgICA8cGF0aCBkPSJNLTQyNi45LDE2OS44YzAsNDguNy0zLjcsNjQuNy0xMy42LDc2LjRjLTEwLjgsMTAtMjUsMTUuNS0zOS43LDE1LjVsMy43LDI5IGMyMi44LDAuMyw0NC44LTcuOSw2MS45LTIzLjFjMTcuOC0xOC41LDI0LTQ0LjEsMjQtODMuM1YwSC00Mjd2MTcwLjFMLTQyNi45LDE2OS44TC00MjYuOSwxNjkuOHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTU1LjA0NTI5NiwgNTYuODM3MTA0KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuNTYyNDUzLCAxLjc5OTg0MikiPgogICAgICAgIDxwYXRoIGQ9Ik0tMzEyLDE0OGMwLDIxLDAsMzkuNSwxLjcsNTUuNGgtMzEuOGwtMi4xLTMzLjNoLTAuOGMtNi43LDExLjYtMTYuNCwyMS4zLTI4LDI3LjkgYy0xMS42LDYuNi0yNC44LDEwLTM4LjIsOS44Yy0zMS40LDAtNjktMTcuNy02OS04OVYwaDM2LjR2MTEyLjdjMCwzOC43LDExLjYsNjQuNyw0NC42LDY0LjdjMTAuMy0wLjIsMjAuNC0zLjUsMjguOS05LjQgYzguNS01LjksMTUuMS0xNC4zLDE4LjktMjMuOWMyLjItNi4xLDMuMy0xMi41LDMuMy0xOC45VjAuMmgzNi40VjE0OEgtMzEyTC0zMTIsMTQ4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzOTAuMDEzMzIyLCA1My40Nzk2MzgpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS43MDY0NTgsIDAuMjMxNDI1KSI+CiAgICAgICAgPHBhdGggZD0iTS00NzguNiw3MS40YzAtMjYtMC44LTQ3LTEuNy02Ni43aDMyLjdsMS43LDM0LjhoMC44YzcuMS0xMi41LDE3LjUtMjIuOCwzMC4xLTI5LjcgYzEyLjUtNywyNi43LTEwLjMsNDEtOS44YzQ4LjMsMCw4NC43LDQxLjcsODQuNywxMDMuM2MwLDczLjEtNDMuNywxMDkuMi05MSwxMDkuMmMtMTIuMSwwLjUtMjQuMi0yLjItMzUtNy44IGMtMTAuOC01LjYtMTkuOS0xMy45LTI2LjYtMjQuMmgtMC44VjI5MWgtMzZ2LTIyMEwtNDc4LjYsNzEuNEwtNDc4LjYsNzEuNHogTS00NDIuNiwxMjUuNmMwLjEsNS4xLDAuNiwxMC4xLDEuNywxNS4xIGMzLDEyLjMsOS45LDIzLjMsMTkuOCwzMS4xYzkuOSw3LjgsMjIuMSwxMi4xLDM0LjcsMTIuMWMzOC41LDAsNjAuNy0zMS45LDYwLjctNzguNWMwLTQwLjctMjEuMS03NS42LTU5LjUtNzUuNiBjLTEyLjksMC40LTI1LjMsNS4xLTM1LjMsMTMuNGMtOS45LDguMy0xNi45LDE5LjctMTkuNiwzMi40Yy0xLjUsNC45LTIuMywxMC0yLjUsMTUuMVYxMjUuNkwtNDQyLjYsMTI1LjZMLTQ0Mi42LDEyNS42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2MDYuNzQwNzI2LCA1Ni44MzcxMDQpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC43NTEyMjYsIDEuOTg5Mjk5KSI+CiAgICAgICAgPHBhdGggZD0iTS00NDAuOCwwbDQzLjcsMTIwLjFjNC41LDEzLjQsOS41LDI5LjQsMTIuOCw0MS43aDAuOGMzLjctMTIuMiw3LjktMjcuNywxMi44LTQyLjQgbDM5LjctMTE5LjJoMzguNUwtMzQ2LjksMTQ1Yy0yNiw2OS43LTQzLjcsMTA1LjQtNjguNiwxMjcuMmMtMTIuNSwxMS43LTI3LjksMjAtNDQuNiwyMy45bC05LjEtMzEuMSBjMTEuNy0zLjksMjIuNS0xMC4xLDMxLjgtMTguMWMxMy4yLTExLjEsMjMuNy0yNS4yLDMwLjYtNDEuMmMxLjUtMi44LDIuNS01LjcsMi45LTguOGMtMC4zLTMuMy0xLjItNi42LTIuNS05LjdMLTQ4MC4yLDAuMSBoMzkuN0wtNDQwLjgsMEwtNDQwLjgsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoODIyLjc0ODEwNCwgMC4wMDAwMDApIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS40NjQwNTAsIDAuMzc4OTE0KSI+CiAgICAgICAgPHBhdGggZD0iTS00MTMuNywwdjU4LjNoNTJ2MjguMmgtNTJWMTk2YzAsMjUsNywzOS41LDI3LjMsMzkuNWM3LjEsMC4xLDE0LjItMC43LDIxLjEtMi41IGwxLjcsMjcuN2MtMTAuMywzLjctMjEuMyw1LjQtMzIuMiw1Yy03LjMsMC40LTE0LjYtMC43LTIxLjMtMy40Yy02LjgtMi43LTEyLjktNi44LTE3LjktMTIuMWMtMTAuMy0xMC45LTE0LjEtMjktMTQuMS01Mi45IFY4Ni41aC0zMVY1OC4zaDMxVjkuNkwtNDEzLjcsMEwtNDEzLjcsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOTc0LjQzMzI4NiwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDAuOTkwMDM0LCAwLjYxMDMzOSkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDQ1LjgsMTEzYzAuOCw1MCwzMi4yLDcwLjYsNjguNiw3MC42YzE5LDAuNiwzNy45LTMsNTUuMy0xMC41bDYuMiwyNi40IGMtMjAuOSw4LjktNDMuNSwxMy4xLTY2LjIsMTIuNmMtNjEuNSwwLTk4LjMtNDEuMi05OC4zLTEwMi41Qy00ODAuMiw0OC4yLTQ0NC43LDAtMzg2LjUsMGM2NS4yLDAsODIuNyw1OC4zLDgyLjcsOTUuNyBjLTAuMSw1LjgtMC41LDExLjUtMS4yLDE3LjJoLTE0MC42SC00NDUuOEwtNDQ1LjgsMTEzeiBNLTMzOS4yLDg2LjZjMC40LTIzLjUtOS41LTYwLjEtNTAuNC02MC4xIGMtMzYuOCwwLTUyLjgsMzQuNC01NS43LDYwLjFILTMzOS4yTC0zMzkuMiw4Ni42TC0zMzkuMiw4Ni42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMjAxLjk2MTA1OCwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuMTc5NjQwLCAwLjcwNTA2OCkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDc4LjYsNjhjMC0yMy45LTAuNC00NC41LTEuNy02My40aDMxLjhsMS4yLDM5LjloMS43YzkuMS0yNy4zLDMxLTQ0LjUsNTUuMy00NC41IGMzLjUtMC4xLDcsMC40LDEwLjMsMS4ydjM0LjhjLTQuMS0wLjktOC4yLTEuMy0xMi40LTEuMmMtMjUuNiwwLTQzLjcsMTkuNy00OC43LDQ3LjRjLTEsNS43LTEuNiwxMS41LTEuNywxNy4ydjEwOC4zaC0zNlY2OCBMLTQ3OC42LDY4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCBkPSJNMTM1Mi4zLDMyNi4yaDM3VjI4aC0zN1YzMjYuMnogTTE2MDQuOCwzMjYuMmMtMi41LTEzLjktMy40LTMxLjEtMy40LTQ4Ljd2LTc2IGMwLTQwLjctMTUuMS04My4xLTc3LjMtODMuMWMtMjUuNiwwLTUwLDcuMS02Ni44LDE4LjFsOC40LDI0LjRjMTQuMy05LjIsMzQtMTUuMSw1My0xNS4xYzQxLjYsMCw0Ni4yLDMwLjIsNDYuMiw0N3Y0LjIgYy03OC42LTAuNC0xMjIuMywyNi41LTEyMi4zLDc1LjZjMCwyOS40LDIxLDU4LjQsNjIuMiw1OC40YzI5LDAsNTAuOS0xNC4zLDYyLjItMzAuMmgxLjNsMi45LDI1LjZIMTYwNC44eiBNMTU2NS43LDI1Ny43IGMwLDMuOC0wLjgsOC0yLjEsMTEuOGMtNS45LDE3LjItMjIuNywzNC00OS4yLDM0Yy0xOC45LDAtMzQuOS0xMS4zLTM0LjktMzUuM2MwLTM5LjUsNDUuOC00Ni42LDg2LjItNDUuOFYyNTcuN3ogTTE2OTguNSwzMjYuMiBsMS43LTMzLjZoMS4zYzE1LjEsMjYuOSwzOC43LDM4LjIsNjguMSwzOC4yYzQ1LjQsMCw5MS4yLTM2LjEsOTEuMi0xMDguOGMwLjQtNjEuNy0zNS4zLTEwMy43LTg1LjctMTAzLjcgYy0zMi44LDAtNTYuMywxNC43LTY5LjMsMzcuNGgtMC44VjI4aC0zNi42djI0NS43YzAsMTguMS0wLjgsMzguNi0xLjcsNTIuNUgxNjk4LjV6IE0xNzA0LjgsMjA4LjJjMC01LjksMS4zLTEwLjksMi4xLTE1LjEgYzcuNi0yOC4xLDMxLjEtNDUuNCw1Ni4zLTQ1LjRjMzkuNSwwLDYwLjUsMzQuOSw2MC41LDc1LjZjMCw0Ni42LTIzLjEsNzguMS02MS44LDc4LjFjLTI2LjksMC00OC4zLTE3LjYtNTUuNS00My4zIGMtMC44LTQuMi0xLjctOC44LTEuNy0xMy40VjIwOC4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgZmlsbD0iIzYxNjE2MSIgZD0iTTE1IDlIOXY2aDZWOXptLTIgNGgtMnYtMmgydjJ6bTgtMlY5aC0yVjdjMC0xLjEtLjktMi0yLTJoLTJWM2gtMnYyaC0yVjNIOXYySDdjLTEuMSAwLTIgLjktMiAydjJIM3YyaDJ2MkgzdjJoMnYyYzAgMS4xLjkgMiAyIDJoMnYyaDJ2LTJoMnYyaDJ2LTJoMmMxLjEgMCAyLS45IDItMnYtMmgydi0yaC0ydi0yaDJ6bS00IDZIN1Y3aDEwdjEweiIvPgo8L3N2Zz4K);
  --jp-icon-keyboard: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMTdjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY3YzAtMS4xLS45LTItMi0yem0tOSAzaDJ2MmgtMlY4em0wIDNoMnYyaC0ydi0yek04IDhoMnYySDhWOHptMCAzaDJ2Mkg4di0yem0tMSAySDV2LTJoMnYyem0wLTNINVY4aDJ2MnptOSA3SDh2LTJoOHYyem0wLTRoLTJ2LTJoMnYyem0wLTNoLTJWOGgydjJ6bTMgM2gtMnYtMmgydjJ6bTAtM2gtMlY4aDJ2MnoiLz4KPC9zdmc+Cg==);
  --jp-icon-launcher: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkgMTlINVY1aDdWM0g1YTIgMiAwIDAwLTIgMnYxNGEyIDIgMCAwMDIgMmgxNGMxLjEgMCAyLS45IDItMnYtN2gtMnY3ek0xNCAzdjJoMy41OWwtOS44MyA5LjgzIDEuNDEgMS40MUwxOSA2LjQxVjEwaDJWM2gtN3oiLz4KPC9zdmc+Cg==);
  --jp-icon-line-form: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGZpbGw9IndoaXRlIiBkPSJNNS44OCA0LjEyTDEzLjc2IDEybC03Ljg4IDcuODhMOCAyMmwxMC0xMEw4IDJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-link: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMuOSAxMmMwLTEuNzEgMS4zOS0zLjEgMy4xLTMuMWg0VjdIN2MtMi43NiAwLTUgMi4yNC01IDVzMi4yNCA1IDUgNWg0di0xLjlIN2MtMS43MSAwLTMuMS0xLjM5LTMuMS0zLjF6TTggMTNoOHYtMkg4djJ6bTktNmgtNHYxLjloNGMxLjcxIDAgMy4xIDEuMzkgMy4xIDMuMXMtMS4zOSAzLjEtMy4xIDMuMWgtNFYxN2g0YzIuNzYgMCA1LTIuMjQgNS01cy0yLjI0LTUtNS01eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xOSA1djE0SDVWNWgxNG0xLjEtMkgzLjljLS41IDAtLjkuNC0uOS45djE2LjJjMCAuNC40LjkuOS45aDE2LjJjLjQgMCAuOS0uNS45LS45VjMuOWMwLS41LS41LS45LS45LS45ek0xMSA3aDZ2MmgtNlY3em0wIDRoNnYyaC02di0yem0wIDRoNnYyaC02ek03IDdoMnYySDd6bTAgNGgydjJIN3ptMCA0aDJ2Mkg3eiIvPgo8L3N2Zz4=);
  --jp-icon-listings-info: url(data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iaXNvLTg4NTktMSI/Pg0KPHN2ZyB2ZXJzaW9uPSIxLjEiIGlkPSJDYXBhXzEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgeG1sbnM6eGxpbms9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGxpbmsiIHg9IjBweCIgeT0iMHB4Ig0KCSB2aWV3Qm94PSIwIDAgNTAuOTc4IDUwLjk3OCIgc3R5bGU9ImVuYWJsZS1iYWNrZ3JvdW5kOm5ldyAwIDAgNTAuOTc4IDUwLjk3ODsiIHhtbDpzcGFjZT0icHJlc2VydmUiPg0KPGc+DQoJPGc+DQoJCTxnPg0KCQkJPHBhdGggc3R5bGU9ImZpbGw6IzAxMDAwMjsiIGQ9Ik00My41Miw3LjQ1OEMzOC43MTEsMi42NDgsMzIuMzA3LDAsMjUuNDg5LDBDMTguNjcsMCwxMi4yNjYsMi42NDgsNy40NTgsNy40NTgNCgkJCQljLTkuOTQzLDkuOTQxLTkuOTQzLDI2LjExOSwwLDM2LjA2MmM0LjgwOSw0LjgwOSwxMS4yMTIsNy40NTYsMTguMDMxLDcuNDU4YzAsMCwwLjAwMSwwLDAuMDAyLDANCgkJCQljNi44MTYsMCwxMy4yMjEtMi42NDgsMTguMDI5LTcuNDU4YzQuODA5LTQuODA5LDcuNDU3LTExLjIxMiw3LjQ1Ny0xOC4wM0M1MC45NzcsMTguNjcsNDguMzI4LDEyLjI2Niw0My41Miw3LjQ1OHoNCgkJCQkgTTQyLjEwNiw0Mi4xMDVjLTQuNDMyLDQuNDMxLTEwLjMzMiw2Ljg3Mi0xNi42MTUsNi44NzJoLTAuMDAyYy02LjI4NS0wLjAwMS0xMi4xODctMi40NDEtMTYuNjE3LTYuODcyDQoJCQkJYy05LjE2Mi05LjE2My05LjE2Mi0yNC4wNzEsMC0zMy4yMzNDMTMuMzAzLDQuNDQsMTkuMjA0LDIsMjUuNDg5LDJjNi4yODQsMCwxMi4xODYsMi40NCwxNi42MTcsNi44NzINCgkJCQljNC40MzEsNC40MzEsNi44NzEsMTAuMzMyLDYuODcxLDE2LjYxN0M0OC45NzcsMzEuNzcyLDQ2LjUzNiwzNy42NzUsNDIuMTA2LDQyLjEwNXoiLz4NCgkJPC9nPg0KCQk8Zz4NCgkJCTxwYXRoIHN0eWxlPSJmaWxsOiMwMTAwMDI7IiBkPSJNMjMuNTc4LDMyLjIxOGMtMC4wMjMtMS43MzQsMC4xNDMtMy4wNTksMC40OTYtMy45NzJjMC4zNTMtMC45MTMsMS4xMS0xLjk5NywyLjI3Mi0zLjI1Mw0KCQkJCWMwLjQ2OC0wLjUzNiwwLjkyMy0xLjA2MiwxLjM2Ny0xLjU3NWMwLjYyNi0wLjc1MywxLjEwNC0xLjQ3OCwxLjQzNi0yLjE3NWMwLjMzMS0wLjcwNywwLjQ5NS0xLjU0MSwwLjQ5NS0yLjUNCgkJCQljMC0xLjA5Ni0wLjI2LTIuMDg4LTAuNzc5LTIuOTc5Yy0wLjU2NS0wLjg3OS0xLjUwMS0xLjMzNi0yLjgwNi0xLjM2OWMtMS44MDIsMC4wNTctMi45ODUsMC42NjctMy41NSwxLjgzMg0KCQkJCWMtMC4zMDEsMC41MzUtMC41MDMsMS4xNDEtMC42MDcsMS44MTRjLTAuMTM5LDAuNzA3LTAuMjA3LDEuNDMyLTAuMjA3LDIuMTc0aC0yLjkzN2MtMC4wOTEtMi4yMDgsMC40MDctNC4xMTQsMS40OTMtNS43MTkNCgkJCQljMS4wNjItMS42NCwyLjg1NS0yLjQ4MSw1LjM3OC0yLjUyN2MyLjE2LDAuMDIzLDMuODc0LDAuNjA4LDUuMTQxLDEuNzU4YzEuMjc4LDEuMTYsMS45MjksMi43NjQsMS45NSw0LjgxMQ0KCQkJCWMwLDEuMTQyLTAuMTM3LDIuMTExLTAuNDEsMi45MTFjLTAuMzA5LDAuODQ1LTAuNzMxLDEuNTkzLTEuMjY4LDIuMjQzYy0wLjQ5MiwwLjY1LTEuMDY4LDEuMzE4LTEuNzMsMi4wMDINCgkJCQljLTAuNjUsMC42OTctMS4zMTMsMS40NzktMS45ODcsMi4zNDZjLTAuMjM5LDAuMzc3LTAuNDI5LDAuNzc3LTAuNTY1LDEuMTk5Yy0wLjE2LDAuOTU5LTAuMjE3LDEuOTUxLTAuMTcxLDIuOTc5DQoJCQkJQzI2LjU4OSwzMi4yMTgsMjMuNTc4LDMyLjIxOCwyMy41NzgsMzIuMjE4eiBNMjMuNTc4LDM4LjIydi0zLjQ4NGgzLjA3NnYzLjQ4NEgyMy41Nzh6Ii8+DQoJCTwvZz4NCgk8L2c+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8L3N2Zz4NCg==);
  --jp-icon-markdown: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjN0IxRkEyIiBkPSJNNSAxNC45aDEybC02LjEgNnptOS40LTYuOGMwLTEuMy0uMS0yLjktLjEtNC41LS40IDEuNC0uOSAyLjktMS4zIDQuM2wtMS4zIDQuM2gtMkw4LjUgNy45Yy0uNC0xLjMtLjctMi45LTEtNC4zLS4xIDEuNi0uMSAzLjItLjIgNC42TDcgMTIuNEg0LjhsLjctMTFoMy4zTDEwIDVjLjQgMS4yLjcgMi43IDEgMy45LjMtMS4yLjctMi42IDEtMy45bDEuMi0zLjdoMy4zbC42IDExaC0yLjRsLS4zLTQuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-new-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDZoLThsLTItMkg0Yy0xLjExIDAtMS45OS44OS0xLjk5IDJMMiAxOGMwIDEuMTEuODkgMiAyIDJoMTZjMS4xMSAwIDItLjg5IDItMlY4YzAtMS4xMS0uODktMi0yLTJ6bS0xIDhoLTN2M2gtMnYtM2gtM3YtMmgzVjloMnYzaDN2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-not-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI1IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDMgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMTkgMTcuMTg0NCAyLjk2OTY4IDE0LjMwMzIgMS44NjA5NCAxMS40NDA5WiIvPgogICAgPHBhdGggY2xhc3M9ImpwLWljb24yIiBzdHJva2U9IiMzMzMzMzMiIHN0cm9rZS13aWR0aD0iMiIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOS4zMTU5MiA5LjMyMDMxKSIgZD0iTTcuMzY4NDIgMEwwIDcuMzY0NzkiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDkuMzE1OTIgMTYuNjgzNikgc2NhbGUoMSAtMSkiIGQ9Ik03LjM2ODQyIDBMMCA3LjM2NDc5Ii8+Cjwvc3ZnPgo=);
  --jp-icon-notebook: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNFRjZDMDAiPgogICAgPHBhdGggZD0iTTE4LjcgMy4zdjE1LjRIMy4zVjMuM2gxNS40bTEuNS0xLjVIMS44djE4LjNoMTguM2wuMS0xOC4zeiIvPgogICAgPHBhdGggZD0iTTE2LjUgMTYuNWwtNS40LTQuMy01LjYgNC4zdi0xMWgxMXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-palette: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE4IDEzVjIwSDRWNkg5LjAyQzkuMDcgNS4yOSA5LjI0IDQuNjIgOS41IDRINEMyLjkgNCAyIDQuOSAyIDZWMjBDMiAyMS4xIDIuOSAyMiA0IDIySDE4QzE5LjEgMjIgMjAgMjEuMSAyMCAyMFYxNUwxOCAxM1pNMTkuMyA4Ljg5QzE5Ljc0IDguMTkgMjAgNy4zOCAyMCA2LjVDMjAgNC4wMSAxNy45OSAyIDE1LjUgMkMxMy4wMSAyIDExIDQuMDEgMTEgNi41QzExIDguOTkgMTMuMDEgMTEgMTUuNDkgMTFDMTYuMzcgMTEgMTcuMTkgMTAuNzQgMTcuODggMTAuM0wyMSAxMy40MkwyMi40MiAxMkwxOS4zIDguODlaTTE1LjUgOUMxNC4xMiA5IDEzIDcuODggMTMgNi41QzEzIDUuMTIgMTQuMTIgNCAxNS41IDRDMTYuODggNCAxOCA1LjEyIDE4IDYuNUMxOCA3Ljg4IDE2Ljg4IDkgMTUuNSA5WiIvPgogICAgPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik00IDZIOS4wMTg5NEM5LjAwNjM5IDYuMTY1MDIgOSA2LjMzMTc2IDkgNi41QzkgOC44MTU3NyAxMC4yMTEgMTAuODQ4NyAxMi4wMzQzIDEySDlWMTRIMTZWMTIuOTgxMUMxNi41NzAzIDEyLjkzNzcgMTcuMTIgMTIuODIwNyAxNy42Mzk2IDEyLjYzOTZMMTggMTNWMjBINFY2Wk04IDhINlYxMEg4VjhaTTYgMTJIOFYxNEg2VjEyWk04IDE2SDZWMThIOFYxNlpNOSAxNkgxNlYxOEg5VjE2WiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-paste: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE5IDJoLTQuMThDMTQuNC44NCAxMy4zIDAgMTIgMGMtMS4zIDAtMi40Ljg0LTIuODIgMkg1Yy0xLjEgMC0yIC45LTIgMnYxNmMwIDEuMS45IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjRjMC0xLjEtLjktMi0yLTJ6bS03IDBjLjU1IDAgMSAuNDUgMSAxcy0uNDUgMS0xIDEtMS0uNDUtMS0xIC40NS0xIDEtMXptNyAxOEg1VjRoMnYzaDEwVjRoMnYxNnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-python: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1icmFuZDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMEQ0N0ExIj4KICAgIDxwYXRoIGQ9Ik0xMS4xIDYuOVY1LjhINi45YzAtLjUgMC0xLjMuMi0xLjYuNC0uNy44LTEuMSAxLjctMS40IDEuNy0uMyAyLjUtLjMgMy45LS4xIDEgLjEgMS45LjkgMS45IDEuOXY0LjJjMCAuNS0uOSAxLjYtMiAxLjZIOC44Yy0xLjUgMC0yLjQgMS40LTIuNCAyLjh2Mi4ySDQuN0MzLjUgMTUuMSAzIDE0IDMgMTMuMVY5Yy0uMS0xIC42LTIgMS44LTIgMS41LS4xIDYuMy0uMSA2LjMtLjF6Ii8+CiAgICA8cGF0aCBkPSJNMTAuOSAxNS4xdjEuMWg0LjJjMCAuNSAwIDEuMy0uMiAxLjYtLjQuNy0uOCAxLjEtMS43IDEuNC0xLjcuMy0yLjUuMy0zLjkuMS0xLS4xLTEuOS0uOS0xLjktMS45di00LjJjMC0uNS45LTEuNiAyLTEuNmgzLjhjMS41IDAgMi40LTEuNCAyLjQtMi44VjYuNmgxLjdDMTguNSA2LjkgMTkgOCAxOSA4LjlWMTNjMCAxLS43IDIuMS0xLjkgMi4xaC02LjJ6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-r-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjE5NkYzIiBkPSJNNC40IDIuNWMxLjItLjEgMi45LS4zIDQuOS0uMyAyLjUgMCA0LjEuNCA1LjIgMS4zIDEgLjcgMS41IDEuOSAxLjUgMy41IDAgMi0xLjQgMy41LTIuOSA0LjEgMS4yLjQgMS43IDEuNiAyLjIgMyAuNiAxLjkgMSAzLjkgMS4zIDQuNmgtMy44Yy0uMy0uNC0uOC0xLjctMS4yLTMuN3MtMS4yLTIuNi0yLjYtMi42aC0uOXY2LjRINC40VjIuNXptMy43IDYuOWgxLjRjMS45IDAgMi45LS45IDIuOS0yLjNzLTEtMi4zLTIuOC0yLjNjLS43IDAtMS4zIDAtMS42LjJ2NC41aC4xdi0uMXoiLz4KPC9zdmc+Cg==);
  --jp-icon-react: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMTUwIDE1MCA1NDEuOSAyOTUuMyI+CiAgPGcgY2xhc3M9ImpwLWljb24tYnJhbmQyIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzYxREFGQiI+CiAgICA8cGF0aCBkPSJNNjY2LjMgMjk2LjVjMC0zMi41LTQwLjctNjMuMy0xMDMuMS04Mi40IDE0LjQtNjMuNiA4LTExNC4yLTIwLjItMTMwLjQtNi41LTMuOC0xNC4xLTUuNi0yMi40LTUuNnYyMi4zYzQuNiAwIDguMy45IDExLjQgMi42IDEzLjYgNy44IDE5LjUgMzcuNSAxNC45IDc1LjctMS4xIDkuNC0yLjkgMTkuMy01LjEgMjkuNC0xOS42LTQuOC00MS04LjUtNjMuNS0xMC45LTEzLjUtMTguNS0yNy41LTM1LjMtNDEuNi01MCAzMi42LTMwLjMgNjMuMi00Ni45IDg0LTQ2LjlWNzhjLTI3LjUgMC02My41IDE5LjYtOTkuOSA1My42LTM2LjQtMzMuOC03Mi40LTUzLjItOTkuOS01My4ydjIyLjNjMjAuNyAwIDUxLjQgMTYuNSA4NCA0Ni42LTE0IDE0LjctMjggMzEuNC00MS4zIDQ5LjktMjIuNiAyLjQtNDQgNi4xLTYzLjYgMTEtMi4zLTEwLTQtMTkuNy01LjItMjktNC43LTM4LjIgMS4xLTY3LjkgMTQuNi03NS44IDMtMS44IDYuOS0yLjYgMTEuNS0yLjZWNzguNWMtOC40IDAtMTYgMS44LTIyLjYgNS42LTI4LjEgMTYuMi0zNC40IDY2LjctMTkuOSAxMzAuMS02Mi4yIDE5LjItMTAyLjcgNDkuOS0xMDIuNyA4Mi4zIDAgMzIuNSA0MC43IDYzLjMgMTAzLjEgODIuNC0xNC40IDYzLjYtOCAxMTQuMiAyMC4yIDEzMC40IDYuNSAzLjggMTQuMSA1LjYgMjIuNSA1LjYgMjcuNSAwIDYzLjUtMTkuNiA5OS45LTUzLjYgMzYuNCAzMy44IDcyLjQgNTMuMiA5OS45IDUzLjIgOC40IDAgMTYtMS44IDIyLjYtNS42IDI4LjEtMTYuMiAzNC40LTY2LjcgMTkuOS0xMzAuMSA2Mi0xOS4xIDEwMi41LTQ5LjkgMTAyLjUtODIuM3ptLTEzMC4yLTY2LjdjLTMuNyAxMi45LTguMyAyNi4yLTEzLjUgMzkuNS00LjEtOC04LjQtMTYtMTMuMS0yNC00LjYtOC05LjUtMTUuOC0xNC40LTIzLjQgMTQuMiAyLjEgMjcuOSA0LjcgNDEgNy45em0tNDUuOCAxMDYuNWMtNy44IDEzLjUtMTUuOCAyNi4zLTI0LjEgMzguMi0xNC45IDEuMy0zMCAyLTQ1LjIgMi0xNS4xIDAtMzAuMi0uNy00NS0xLjktOC4zLTExLjktMTYuNC0yNC42LTI0LjItMzgtNy42LTEzLjEtMTQuNS0yNi40LTIwLjgtMzkuOCA2LjItMTMuNCAxMy4yLTI2LjggMjAuNy0zOS45IDcuOC0xMy41IDE1LjgtMjYuMyAyNC4xLTM4LjIgMTQuOS0xLjMgMzAtMiA0NS4yLTIgMTUuMSAwIDMwLjIuNyA0NSAxLjkgOC4zIDExLjkgMTYuNCAyNC42IDI0LjIgMzggNy42IDEzLjEgMTQuNSAyNi40IDIwLjggMzkuOC02LjMgMTMuNC0xMy4yIDI2LjgtMjAuNyAzOS45em0zMi4zLTEzYzUuNCAxMy40IDEwIDI2LjggMTMuOCAzOS44LTEzLjEgMy4yLTI2LjkgNS45LTQxLjIgOCA0LjktNy43IDkuOC0xNS42IDE0LjQtMjMuNyA0LjYtOCA4LjktMTYuMSAxMy0yNC4xek00MjEuMiA0MzBjLTkuMy05LjYtMTguNi0yMC4zLTI3LjgtMzIgOSAuNCAxOC4yLjcgMjcuNS43IDkuNCAwIDE4LjctLjIgMjcuOC0uNy05IDExLjctMTguMyAyMi40LTI3LjUgMzJ6bS03NC40LTU4LjljLTE0LjItMi4xLTI3LjktNC43LTQxLTcuOSAzLjctMTIuOSA4LjMtMjYuMiAxMy41LTM5LjUgNC4xIDggOC40IDE2IDEzLjEgMjQgNC43IDggOS41IDE1LjggMTQuNCAyMy40ek00MjAuNyAxNjNjOS4zIDkuNiAxOC42IDIwLjMgMjcuOCAzMi05LS40LTE4LjItLjctMjcuNS0uNy05LjQgMC0xOC43LjItMjcuOC43IDktMTEuNyAxOC4zLTIyLjQgMjcuNS0zMnptLTc0IDU4LjljLTQuOSA3LjctOS44IDE1LjYtMTQuNCAyMy43LTQuNiA4LTguOSAxNi0xMyAyNC01LjQtMTMuNC0xMC0yNi44LTEzLjgtMzkuOCAxMy4xLTMuMSAyNi45LTUuOCA0MS4yLTcuOXptLTkwLjUgMTI1LjJjLTM1LjQtMTUuMS01OC4zLTM0LjktNTguMy01MC42IDAtMTUuNyAyMi45LTM1LjYgNTguMy01MC42IDguNi0zLjcgMTgtNyAyNy43LTEwLjEgNS43IDE5LjYgMTMuMiA0MCAyMi41IDYwLjktOS4yIDIwLjgtMTYuNiA0MS4xLTIyLjIgNjAuNi05LjktMy4xLTE5LjMtNi41LTI4LTEwLjJ6TTMxMCA0OTBjLTEzLjYtNy44LTE5LjUtMzcuNS0xNC45LTc1LjcgMS4xLTkuNCAyLjktMTkuMyA1LjEtMjkuNCAxOS42IDQuOCA0MSA4LjUgNjMuNSAxMC45IDEzLjUgMTguNSAyNy41IDM1LjMgNDEuNiA1MC0zMi42IDMwLjMtNjMuMiA0Ni45LTg0IDQ2LjktNC41LS4xLTguMy0xLTExLjMtMi43em0yMzcuMi03Ni4yYzQuNyAzOC4yLTEuMSA2Ny45LTE0LjYgNzUuOC0zIDEuOC02LjkgMi42LTExLjUgMi42LTIwLjcgMC01MS40LTE2LjUtODQtNDYuNiAxNC0xNC43IDI4LTMxLjQgNDEuMy00OS45IDIyLjYtMi40IDQ0LTYuMSA2My42LTExIDIuMyAxMC4xIDQuMSAxOS44IDUuMiAyOS4xem0zOC41LTY2LjdjLTguNiAzLjctMTggNy0yNy43IDEwLjEtNS43LTE5LjYtMTMuMi00MC0yMi41LTYwLjkgOS4yLTIwLjggMTYuNi00MS4xIDIyLjItNjAuNiA5LjkgMy4xIDE5LjMgNi41IDI4LjEgMTAuMiAzNS40IDE1LjEgNTguMyAzNC45IDU4LjMgNTAuNi0uMSAxNS43LTIzIDM1LjYtNTguNCA1MC42ek0zMjAuOCA3OC40eiIvPgogICAgPGNpcmNsZSBjeD0iNDIwLjkiIGN5PSIyOTYuNSIgcj0iNDUuNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-refresh: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTkgMTMuNWMtMi40OSAwLTQuNS0yLjAxLTQuNS00LjVTNi41MSA0LjUgOSA0LjVjMS4yNCAwIDIuMzYuNTIgMy4xNyAxLjMzTDEwIDhoNVYzbC0xLjc2IDEuNzZDMTIuMTUgMy42OCAxMC42NiAzIDkgMyA1LjY5IDMgMy4wMSA1LjY5IDMuMDEgOVM1LjY5IDE1IDkgMTVjMi45NyAwIDUuNDMtMi4xNiA1LjktNWgtMS41MmMtLjQ2IDItMi4yNCAzLjUtNC4zOCAzLjV6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-regex: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi1hY2NlbnQyIiBmaWxsPSIjRkZGIj4KICAgIDxjaXJjbGUgY2xhc3M9InN0MiIgY3g9IjUuNSIgY3k9IjE0LjUiIHI9IjEuNSIvPgogICAgPHJlY3QgeD0iMTIiIHk9IjQiIGNsYXNzPSJzdDIiIHdpZHRoPSIxIiBoZWlnaHQ9IjgiLz4KICAgIDxyZWN0IHg9IjguNSIgeT0iNy41IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjg2NiAtMC41IDAuNSAwLjg2NiAtMi4zMjU1IDcuMzIxOSkiIGNsYXNzPSJzdDIiIHdpZHRoPSI4IiBoZWlnaHQ9IjEiLz4KICAgIDxyZWN0IHg9IjEyIiB5PSI0IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjUgLTAuODY2IDAuODY2IDAuNSAtMC42Nzc5IDE0LjgyNTIpIiBjbGFzcz0ic3QyIiB3aWR0aD0iMSIgaGVpZ2h0PSI4Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-run: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTggNXYxNGwxMS03eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-running: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMjU2IDhDMTE5IDggOCAxMTkgOCAyNTZzMTExIDI0OCAyNDggMjQ4IDI0OC0xMTEgMjQ4LTI0OFMzOTMgOCAyNTYgOHptOTYgMzI4YzAgOC44LTcuMiAxNi0xNiAxNkgxNzZjLTguOCAwLTE2LTcuMi0xNi0xNlYxNzZjMC04LjggNy4yLTE2IDE2LTE2aDE2MGM4LjggMCAxNiA3LjIgMTYgMTZ2MTYweiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-save: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE3IDNINWMtMS4xMSAwLTIgLjktMiAydjE0YzAgMS4xLjg5IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjdsLTQtNHptLTUgMTZjLTEuNjYgMC0zLTEuMzQtMy0zczEuMzQtMyAzLTMgMyAxLjM0IDMgMy0xLjM0IDMtMyAzem0zLTEwSDVWNWgxMHY0eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-search: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjEsMTAuOWgtMC43bC0wLjItMC4yYzAuOC0wLjksMS4zLTIuMiwxLjMtMy41YzAtMy0yLjQtNS40LTUuNC01LjRTMS44LDQuMiwxLjgsNy4xczIuNCw1LjQsNS40LDUuNCBjMS4zLDAsMi41LTAuNSwzLjUtMS4zbDAuMiwwLjJ2MC43bDQuMSw0LjFsMS4yLTEuMkwxMi4xLDEwLjl6IE03LjEsMTAuOWMtMi4xLDAtMy43LTEuNy0zLjctMy43czEuNy0zLjcsMy43LTMuN3MzLjcsMS43LDMuNywzLjcgUzkuMiwxMC45LDcuMSwxMC45eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-settings: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuNDMgMTIuOThjLjA0LS4zMi4wNy0uNjQuMDctLjk4cy0uMDMtLjY2LS4wNy0uOThsMi4xMS0xLjY1Yy4xOS0uMTUuMjQtLjQyLjEyLS42NGwtMi0zLjQ2Yy0uMTItLjIyLS4zOS0uMy0uNjEtLjIybC0yLjQ5IDFjLS41Mi0uNC0xLjA4LS43My0xLjY5LS45OGwtLjM4LTIuNjVBLjQ4OC40ODggMCAwMDE0IDJoLTRjLS4yNSAwLS40Ni4xOC0uNDkuNDJsLS4zOCAyLjY1Yy0uNjEuMjUtMS4xNy41OS0xLjY5Ljk4bC0yLjQ5LTFjLS4yMy0uMDktLjQ5IDAtLjYxLjIybC0yIDMuNDZjLS4xMy4yMi0uMDcuNDkuMTIuNjRsMi4xMSAxLjY1Yy0uMDQuMzItLjA3LjY1LS4wNy45OHMuMDMuNjYuMDcuOThsLTIuMTEgMS42NWMtLjE5LjE1LS4yNC40Mi0uMTIuNjRsMiAzLjQ2Yy4xMi4yMi4zOS4zLjYxLjIybDIuNDktMWMuNTIuNCAxLjA4LjczIDEuNjkuOThsLjM4IDIuNjVjLjAzLjI0LjI0LjQyLjQ5LjQyaDRjLjI1IDAgLjQ2LS4xOC40OS0uNDJsLjM4LTIuNjVjLjYxLS4yNSAxLjE3LS41OSAxLjY5LS45OGwyLjQ5IDFjLjIzLjA5LjQ5IDAgLjYxLS4yMmwyLTMuNDZjLjEyLS4yMi4wNy0uNDktLjEyLS42NGwtMi4xMS0xLjY1ek0xMiAxNS41Yy0xLjkzIDAtMy41LTEuNTctMy41LTMuNXMxLjU3LTMuNSAzLjUtMy41IDMuNSAxLjU3IDMuNSAzLjUtMS41NyAzLjUtMy41IDMuNXoiLz4KPC9zdmc+Cg==);
  --jp-icon-spreadsheet: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNENBRjUwIiBkPSJNMi4yIDIuMnYxNy42aDE3LjZWMi4ySDIuMnptMTUuNCA3LjdoLTUuNVY0LjRoNS41djUuNXpNOS45IDQuNHY1LjVINC40VjQuNGg1LjV6bS01LjUgNy43aDUuNXY1LjVINC40di01LjV6bTcuNyA1LjV2LTUuNWg1LjV2NS41aC01LjV6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-stop: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik02IDZoMTJ2MTJINnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tab: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIxIDNIM2MtMS4xIDAtMiAuOS0yIDJ2MTRjMCAxLjEuOSAyIDIgMmgxOGMxLjEgMCAyLS45IDItMlY1YzAtMS4xLS45LTItMi0yem0wIDE2SDNWNWgxMHY0aDh2MTB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-terminal: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0IiA+CiAgICA8cmVjdCBjbGFzcz0ianAtaWNvbjIganAtaWNvbi1zZWxlY3RhYmxlIiB3aWR0aD0iMjAiIGhlaWdodD0iMjAiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMikiIGZpbGw9IiMzMzMzMzMiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uLWFjY2VudDIganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGQ9Ik01LjA1NjY0IDguNzYxNzJDNS4wNTY2NCA4LjU5NzY2IDUuMDMxMjUgOC40NTMxMiA0Ljk4MDQ3IDguMzI4MTJDNC45MzM1OSA4LjE5OTIyIDQuODU1NDcgOC4wODIwMyA0Ljc0NjA5IDcuOTc2NTZDNC42NDA2MiA3Ljg3MTA5IDQuNSA3Ljc3NTM5IDQuMzI0MjIgNy42ODk0NUM0LjE1MjM0IDcuNTk5NjEgMy45NDMzNiA3LjUxMTcyIDMuNjk3MjcgNy40MjU3OEMzLjMwMjczIDcuMjg1MTYgMi45NDMzNiA3LjEzNjcyIDIuNjE5MTQgNi45ODA0N0MyLjI5NDkyIDYuODI0MjIgMi4wMTc1OCA2LjY0MjU4IDEuNzg3MTEgNi40MzU1NUMxLjU2MDU1IDYuMjI4NTIgMS4zODQ3NyA1Ljk4ODI4IDEuMjU5NzcgNS43MTQ4NEMxLjEzNDc3IDUuNDM3NSAxLjA3MjI3IDUuMTA5MzggMS4wNzIyNyA0LjczMDQ3QzEuMDcyMjcgNC4zOTg0NCAxLjEyODkxIDQuMDk1NyAxLjI0MjE5IDMuODIyMjdDMS4zNTU0NyAzLjU0NDkyIDEuNTE1NjIgMy4zMDQ2OSAxLjcyMjY2IDMuMTAxNTZDMS45Mjk2OSAyLjg5ODQ0IDIuMTc5NjkgMi43MzQzNyAyLjQ3MjY2IDIuNjA5MzhDMi43NjU2MiAyLjQ4NDM4IDMuMDkxOCAyLjQwNDMgMy40NTExNyAyLjM2OTE0VjEuMTA5MzhINC4zODg2N1YyLjM4MDg2QzQuNzQwMjMgMi40Mjc3MyA1LjA1NjY0IDIuNTIzNDQgNS4zMzc4OSAyLjY2Nzk3QzUuNjE5MTQgMi44MTI1IDUuODU3NDIgMy4wMDE5NSA2LjA1MjczIDMuMjM2MzNDNi4yNTE5NSAzLjQ2NjggNi40MDQzIDMuNzQwMjMgNi41MDk3NyA0LjA1NjY0QzYuNjE5MTQgNC4zNjkxNCA2LjY3MzgzIDQuNzIwNyA2LjY3MzgzIDUuMTExMzNINS4wNDQ5MkM1LjA0NDkyIDQuNjM4NjcgNC45Mzc1IDQuMjgxMjUgNC43MjI2NiA0LjAzOTA2QzQuNTA3ODEgMy43OTI5NyA0LjIxNjggMy42Njk5MiAzLjg0OTYxIDMuNjY5OTJDMy42NTAzOSAzLjY2OTkyIDMuNDc2NTYgMy42OTcyNyAzLjMyODEyIDMuNzUxOTVDMy4xODM1OSAzLjgwMjczIDMuMDY0NDUgMy44NzY5NSAyLjk3MDcgMy45NzQ2MUMyLjg3Njk1IDQuMDY4MzYgMi44MDY2NCA0LjE3OTY5IDIuNzU5NzcgNC4zMDg1OUMyLjcxNjggNC40Mzc1IDIuNjk1MzEgNC41NzgxMiAyLjY5NTMxIDQuNzMwNDdDMi42OTUzMSA0Ljg4MjgxIDIuNzE2OCA1LjAxOTUzIDIuNzU5NzcgNS4xNDA2MkMyLjgwNjY0IDUuMjU3ODEgMi44ODI4MSA1LjM2NzE5IDIuOTg4MjggNS40Njg3NUMzLjA5NzY2IDUuNTcwMzEgMy4yNDAyMyA1LjY2Nzk3IDMuNDE2MDIgNS43NjE3MkMzLjU5MTggNS44NTE1NiAzLjgxMDU1IDUuOTQzMzYgNC4wNzIyNyA2LjAzNzExQzQuNDY2OCA2LjE4NTU1IDQuODI0MjIgNi4zMzk4NCA1LjE0NDUzIDYuNUM1LjQ2NDg0IDYuNjU2MjUgNS43MzgyOCA2LjgzOTg0IDUuOTY0ODQgNy4wNTA3OEM2LjE5NTMxIDcuMjU3ODEgNi4zNzEwOSA3LjUgNi40OTIxOSA3Ljc3NzM0QzYuNjE3MTkgOC4wNTA3OCA2LjY3OTY5IDguMzc1IDYuNjc5NjkgOC43NUM2LjY3OTY5IDkuMDkzNzUgNi42MjMwNSA5LjQwNDMgNi41MDk3NyA5LjY4MTY0QzYuMzk2NDggOS45NTUwOCA2LjIzNDM4IDEwLjE5MTQgNi4wMjM0NCAxMC4zOTA2QzUuODEyNSAxMC41ODk4IDUuNTU4NTkgMTAuNzUgNS4yNjE3MiAxMC44NzExQzQuOTY0ODQgMTAuOTg4MyA0LjYzMjgxIDExLjA2NDUgNC4yNjU2MiAxMS4wOTk2VjEyLjI0OEgzLjMzMzk4VjExLjA5OTZDMy4wMDE5NSAxMS4wNjg0IDIuNjc5NjkgMTAuOTk2MSAyLjM2NzE5IDEwLjg4MjhDMi4wNTQ2OSAxMC43NjU2IDEuNzc3MzQgMTAuNTk3NyAxLjUzNTE2IDEwLjM3ODlDMS4yOTY4OCAxMC4xNjAyIDEuMTA1NDcgOS44ODQ3NyAwLjk2MDkzOCA5LjU1MjczQzAuODE2NDA2IDkuMjE2OCAwLjc0NDE0MSA4LjgxNDQ1IDAuNzQ0MTQxIDguMzQ1N0gyLjM3ODkxQzIuMzc4OTEgOC42MjY5NSAyLjQxOTkyIDguODYzMjggMi41MDE5NSA5LjA1NDY5QzIuNTgzOTggOS4yNDIxOSAyLjY4OTQ1IDkuMzkyNTggMi44MTgzNiA5LjUwNTg2QzIuOTUxMTcgOS42MTUyMyAzLjEwMTU2IDkuNjkzMzYgMy4yNjk1MyA5Ljc0MDIzQzMuNDM3NSA5Ljc4NzExIDMuNjA5MzggOS44MTA1NSAzLjc4NTE2IDkuODEwNTVDNC4yMDMxMiA5LjgxMDU1IDQuNTE5NTMgOS43MTI4OSA0LjczNDM4IDkuNTE3NThDNC45NDkyMiA5LjMyMjI3IDUuMDU2NjQgOS4wNzAzMSA1LjA1NjY0IDguNzYxNzJaTTEzLjQxOCAxMi4yNzE1SDguMDc0MjJWMTFIMTMuNDE4VjEyLjI3MTVaIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzLjk1MjY0IDYpIiBmaWxsPSJ3aGl0ZSIvPgo8L3N2Zz4K);
  --jp-icon-text-editor: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTUgMTVIM3YyaDEydi0yem0wLThIM3YyaDEyVjd6TTMgMTNoMTh2LTJIM3Yyem0wIDhoMTh2LTJIM3Yyek0zIDN2MmgxOFYzSDN6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMiAxNy4xODQ0IDIuOTY5NjggMTQuMzAzMiAxLjg2MDk0IDExLjQ0MDlaIi8+CiAgICA8cGF0aCBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiMzMzMzMzMiIHN0cm9rZT0iIzMzMzMzMyIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOCA5Ljg2NzE5KSIgZD0iTTIuODYwMTUgNC44NjUzNUwwLjcyNjU0OSAyLjk5OTU5TDAgMy42MzA0NUwyLjg2MDE1IDYuMTMxNTdMOCAwLjYzMDg3Mkw3LjI3ODU3IDBMMi44NjAxNSA0Ljg2NTM1WiIvPgo8L3N2Zz4K);
  --jp-icon-undo: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjUgOGMtMi42NSAwLTUuMDUuOTktNi45IDIuNkwyIDd2OWg5bC0zLjYyLTMuNjJjMS4zOS0xLjE2IDMuMTYtMS44OCA1LjEyLTEuODggMy41NCAwIDYuNTUgMi4zMSA3LjYgNS41bDIuMzctLjc4QzIxLjA4IDExLjAzIDE3LjE1IDggMTIuNSA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-vega: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbjEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjEyMTIxIj4KICAgIDxwYXRoIGQ9Ik0xMC42IDUuNGwyLjItMy4ySDIuMnY3LjNsNC02LjZ6Ii8+CiAgICA8cGF0aCBkPSJNMTUuOCAyLjJsLTQuNCA2LjZMNyA2LjNsLTQuOCA4djUuNWgxNy42VjIuMmgtNHptLTcgMTUuNEg1LjV2LTQuNGgzLjN2NC40em00LjQgMEg5LjhWOS44aDMuNHY3Ljh6bTQuNCAwaC0zLjRWNi41aDMuNHYxMS4xeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-yaml: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1jb250cmFzdDIganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjRDgxQjYwIj4KICAgIDxwYXRoIGQ9Ik03LjIgMTguNnYtNS40TDMgNS42aDMuM2wxLjQgMy4xYy4zLjkuNiAxLjYgMSAyLjUuMy0uOC42LTEuNiAxLTIuNWwxLjQtMy4xaDMuNGwtNC40IDcuNnY1LjVsLTIuOS0uMXoiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxNi41IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxMSIgcj0iMi4xIi8+CiAgPC9nPgo8L3N2Zz4K);
}

/* Icon CSS class declarations */

.jp-AddIcon {
  background-image: var(--jp-icon-add);
}
.jp-BugIcon {
  background-image: var(--jp-icon-bug);
}
.jp-BuildIcon {
  background-image: var(--jp-icon-build);
}
.jp-CaretDownEmptyIcon {
  background-image: var(--jp-icon-caret-down-empty);
}
.jp-CaretDownEmptyThinIcon {
  background-image: var(--jp-icon-caret-down-empty-thin);
}
.jp-CaretDownIcon {
  background-image: var(--jp-icon-caret-down);
}
.jp-CaretLeftIcon {
  background-image: var(--jp-icon-caret-left);
}
.jp-CaretRightIcon {
  background-image: var(--jp-icon-caret-right);
}
.jp-CaretUpEmptyThinIcon {
  background-image: var(--jp-icon-caret-up-empty-thin);
}
.jp-CaretUpIcon {
  background-image: var(--jp-icon-caret-up);
}
.jp-CaseSensitiveIcon {
  background-image: var(--jp-icon-case-sensitive);
}
.jp-CheckIcon {
  background-image: var(--jp-icon-check);
}
.jp-CircleEmptyIcon {
  background-image: var(--jp-icon-circle-empty);
}
.jp-CircleIcon {
  background-image: var(--jp-icon-circle);
}
.jp-ClearIcon {
  background-image: var(--jp-icon-clear);
}
.jp-CloseIcon {
  background-image: var(--jp-icon-close);
}
.jp-ConsoleIcon {
  background-image: var(--jp-icon-console);
}
.jp-CopyIcon {
  background-image: var(--jp-icon-copy);
}
.jp-CutIcon {
  background-image: var(--jp-icon-cut);
}
.jp-DownloadIcon {
  background-image: var(--jp-icon-download);
}
.jp-EditIcon {
  background-image: var(--jp-icon-edit);
}
.jp-EllipsesIcon {
  background-image: var(--jp-icon-ellipses);
}
.jp-ExtensionIcon {
  background-image: var(--jp-icon-extension);
}
.jp-FastForwardIcon {
  background-image: var(--jp-icon-fast-forward);
}
.jp-FileIcon {
  background-image: var(--jp-icon-file);
}
.jp-FileUploadIcon {
  background-image: var(--jp-icon-file-upload);
}
.jp-FilterListIcon {
  background-image: var(--jp-icon-filter-list);
}
.jp-FolderIcon {
  background-image: var(--jp-icon-folder);
}
.jp-Html5Icon {
  background-image: var(--jp-icon-html5);
}
.jp-ImageIcon {
  background-image: var(--jp-icon-image);
}
.jp-InspectorIcon {
  background-image: var(--jp-icon-inspector);
}
.jp-JsonIcon {
  background-image: var(--jp-icon-json);
}
.jp-JupyterFaviconIcon {
  background-image: var(--jp-icon-jupyter-favicon);
}
.jp-JupyterIcon {
  background-image: var(--jp-icon-jupyter);
}
.jp-JupyterlabWordmarkIcon {
  background-image: var(--jp-icon-jupyterlab-wordmark);
}
.jp-KernelIcon {
  background-image: var(--jp-icon-kernel);
}
.jp-KeyboardIcon {
  background-image: var(--jp-icon-keyboard);
}
.jp-LauncherIcon {
  background-image: var(--jp-icon-launcher);
}
.jp-LineFormIcon {
  background-image: var(--jp-icon-line-form);
}
.jp-LinkIcon {
  background-image: var(--jp-icon-link);
}
.jp-ListIcon {
  background-image: var(--jp-icon-list);
}
.jp-ListingsInfoIcon {
  background-image: var(--jp-icon-listings-info);
}
.jp-MarkdownIcon {
  background-image: var(--jp-icon-markdown);
}
.jp-NewFolderIcon {
  background-image: var(--jp-icon-new-folder);
}
.jp-NotTrustedIcon {
  background-image: var(--jp-icon-not-trusted);
}
.jp-NotebookIcon {
  background-image: var(--jp-icon-notebook);
}
.jp-PaletteIcon {
  background-image: var(--jp-icon-palette);
}
.jp-PasteIcon {
  background-image: var(--jp-icon-paste);
}
.jp-PythonIcon {
  background-image: var(--jp-icon-python);
}
.jp-RKernelIcon {
  background-image: var(--jp-icon-r-kernel);
}
.jp-ReactIcon {
  background-image: var(--jp-icon-react);
}
.jp-RefreshIcon {
  background-image: var(--jp-icon-refresh);
}
.jp-RegexIcon {
  background-image: var(--jp-icon-regex);
}
.jp-RunIcon {
  background-image: var(--jp-icon-run);
}
.jp-RunningIcon {
  background-image: var(--jp-icon-running);
}
.jp-SaveIcon {
  background-image: var(--jp-icon-save);
}
.jp-SearchIcon {
  background-image: var(--jp-icon-search);
}
.jp-SettingsIcon {
  background-image: var(--jp-icon-settings);
}
.jp-SpreadsheetIcon {
  background-image: var(--jp-icon-spreadsheet);
}
.jp-StopIcon {
  background-image: var(--jp-icon-stop);
}
.jp-TabIcon {
  background-image: var(--jp-icon-tab);
}
.jp-TerminalIcon {
  background-image: var(--jp-icon-terminal);
}
.jp-TextEditorIcon {
  background-image: var(--jp-icon-text-editor);
}
.jp-TrustedIcon {
  background-image: var(--jp-icon-trusted);
}
.jp-UndoIcon {
  background-image: var(--jp-icon-undo);
}
.jp-VegaIcon {
  background-image: var(--jp-icon-vega);
}
.jp-YamlIcon {
  background-image: var(--jp-icon-yaml);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

:root {
  --jp-icon-search-white: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjEsMTAuOWgtMC43bC0wLjItMC4yYzAuOC0wLjksMS4zLTIuMiwxLjMtMy41YzAtMy0yLjQtNS40LTUuNC01LjRTMS44LDQuMiwxLjgsNy4xczIuNCw1LjQsNS40LDUuNCBjMS4zLDAsMi41LTAuNSwzLjUtMS4zbDAuMiwwLjJ2MC43bDQuMSw0LjFsMS4yLTEuMkwxMi4xLDEwLjl6IE03LjEsMTAuOWMtMi4xLDAtMy43LTEuNy0zLjctMy43czEuNy0zLjcsMy43LTMuN3MzLjcsMS43LDMuNywzLjcgUzkuMiwxMC45LDcuMSwxMC45eiIvPgogIDwvZz4KPC9zdmc+Cg==);
}

.jp-Icon,
.jp-MaterialIcon {
  background-position: center;
  background-repeat: no-repeat;
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-cover {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

/**
 * (DEPRECATED) Support for specific CSS icon sizes
 */

.jp-Icon-16 {
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-18 {
  background-size: 18px;
  min-width: 18px;
  min-height: 18px;
}

.jp-Icon-20 {
  background-size: 20px;
  min-width: 20px;
  min-height: 20px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for icons as inline SVG HTMLElements
 */

/* recolor the primary elements of an icon */
.jp-icon0[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon1[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon2[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon3[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}
/* recolor the accent elements of an icon */
.jp-icon-accent0[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-accent1[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-accent2[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-accent3[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-accent4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-accent0[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-accent1[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-accent2[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-accent3[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-accent4[stroke] {
  stroke: var(--jp-layout-color4);
}
/* set the color of an icon to transparent */
.jp-icon-none[fill] {
  fill: none;
}

.jp-icon-none[stroke] {
  stroke: none;
}
/* brand icon colors. Same for light and dark */
.jp-icon-brand0[fill] {
  fill: var(--jp-brand-color0);
}
.jp-icon-brand1[fill] {
  fill: var(--jp-brand-color1);
}
.jp-icon-brand2[fill] {
  fill: var(--jp-brand-color2);
}
.jp-icon-brand3[fill] {
  fill: var(--jp-brand-color3);
}
.jp-icon-brand4[fill] {
  fill: var(--jp-brand-color4);
}

.jp-icon-brand0[stroke] {
  stroke: var(--jp-brand-color0);
}
.jp-icon-brand1[stroke] {
  stroke: var(--jp-brand-color1);
}
.jp-icon-brand2[stroke] {
  stroke: var(--jp-brand-color2);
}
.jp-icon-brand3[stroke] {
  stroke: var(--jp-brand-color3);
}
.jp-icon-brand4[stroke] {
  stroke: var(--jp-brand-color4);
}
/* warn icon colors. Same for light and dark */
.jp-icon-warn0[fill] {
  fill: var(--jp-warn-color0);
}
.jp-icon-warn1[fill] {
  fill: var(--jp-warn-color1);
}
.jp-icon-warn2[fill] {
  fill: var(--jp-warn-color2);
}
.jp-icon-warn3[fill] {
  fill: var(--jp-warn-color3);
}

.jp-icon-warn0[stroke] {
  stroke: var(--jp-warn-color0);
}
.jp-icon-warn1[stroke] {
  stroke: var(--jp-warn-color1);
}
.jp-icon-warn2[stroke] {
  stroke: var(--jp-warn-color2);
}
.jp-icon-warn3[stroke] {
  stroke: var(--jp-warn-color3);
}
/* icon colors that contrast well with each other and most backgrounds */
.jp-icon-contrast0[fill] {
  fill: var(--jp-icon-contrast-color0);
}
.jp-icon-contrast1[fill] {
  fill: var(--jp-icon-contrast-color1);
}
.jp-icon-contrast2[fill] {
  fill: var(--jp-icon-contrast-color2);
}
.jp-icon-contrast3[fill] {
  fill: var(--jp-icon-contrast-color3);
}

.jp-icon-contrast0[stroke] {
  stroke: var(--jp-icon-contrast-color0);
}
.jp-icon-contrast1[stroke] {
  stroke: var(--jp-icon-contrast-color1);
}
.jp-icon-contrast2[stroke] {
  stroke: var(--jp-icon-contrast-color2);
}
.jp-icon-contrast3[stroke] {
  stroke: var(--jp-icon-contrast-color3);
}

/* CSS for icons in selected items in the settings editor */
#setting-editor .jp-PluginList .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}
#setting-editor
  .jp-PluginList
  .jp-mod-selected
  .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* CSS for icons in selected filebrowser listing items */
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* CSS for icons in selected tabs in the sidebar tab manager */
#tab-manager .lm-TabBar-tab.jp-mod-active .jp-icon-selectable[fill] {
  fill: #fff;
}

#tab-manager .lm-TabBar-tab.jp-mod-active .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}
#tab-manager
  .lm-TabBar-tab.jp-mod-active
  .jp-icon-hover
  :hover
  .jp-icon-selectable[fill] {
  fill: var(--jp-brand-color1);
}

#tab-manager
  .lm-TabBar-tab.jp-mod-active
  .jp-icon-hover
  :hover
  .jp-icon-selectable-inverse[fill] {
  fill: #fff;
}

/**
 * TODO: come up with non css-hack solution for showing the busy icon on top
 *  of the close icon
 * CSS for complex behavior of close icon of tabs in the sidebar tab manager
 */
#tab-manager
  .lm-TabBar-tab.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}
#tab-manager
  .lm-TabBar-tab.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

#tab-manager
  .lm-TabBar-tab.jp-mod-dirty.jp-mod-active
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: #fff;
}

/**
* TODO: come up with non css-hack solution for showing the busy icon on top
*  of the close icon
* CSS for complex behavior of close icon of tabs in the main area tabbar
*/
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

/* CSS for icons in status bar */
#jp-main-statusbar .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}

#jp-main-statusbar .jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}
/* special handling for splash icon CSS. While the theme CSS reloads during
   splash, the splash icon can loose theming. To prevent that, we set a
   default for its color variable */
:root {
  --jp-warn-color0: var(--md-orange-700);
}

/* not sure what to do with this one, used in filebrowser listing */
.jp-DragIcon {
  margin-right: 4px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for alt colors for icons as inline SVG HTMLElements
 */

/* alt recolor the primary elements of an icon */
.jp-icon-alt .jp-icon0[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-alt .jp-icon1[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-alt .jp-icon2[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-alt .jp-icon3[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-alt .jp-icon4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-alt .jp-icon0[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-alt .jp-icon1[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-alt .jp-icon2[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-alt .jp-icon3[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-alt .jp-icon4[stroke] {
  stroke: var(--jp-layout-color4);
}

/* alt recolor the accent elements of an icon */
.jp-icon-alt .jp-icon-accent0[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-alt .jp-icon-accent1[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-alt .jp-icon-accent2[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-alt .jp-icon-accent3[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-alt .jp-icon-accent4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-alt .jp-icon-accent0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-alt .jp-icon-accent1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-alt .jp-icon-accent2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-alt .jp-icon-accent3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-alt .jp-icon-accent4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-icon-hoverShow:not(:hover) svg {
  display: none !important;
}

/**
 * Support for hover colors for icons as inline SVG HTMLElements
 */

/**
 * regular colors
 */

/* recolor the primary elements of an icon */
.jp-icon-hover :hover .jp-icon0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-hover :hover .jp-icon1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-hover :hover .jp-icon2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-hover :hover .jp-icon3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-hover :hover .jp-icon4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-hover :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-hover :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-hover :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-hover :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/* recolor the accent elements of an icon */
.jp-icon-hover :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-hover :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-hover :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-hover :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-hover :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-hover :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-hover :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-hover :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-hover :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* set the color of an icon to transparent */
.jp-icon-hover :hover .jp-icon-none-hover[fill] {
  fill: none;
}

.jp-icon-hover :hover .jp-icon-none-hover[stroke] {
  stroke: none;
}

/**
 * inverse colors
 */

/* inverse recolor the primary elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* inverse recolor the accent elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* Sibling imports */

/* Override Blueprint's _reset.scss styles */
html {
  box-sizing: unset;
}

*,
*::before,
*::after {
  box-sizing: unset;
}

body {
  color: unset;
  font-family: var(--jp-ui-font-family);
}

p {
  margin-top: unset;
  margin-bottom: unset;
}

small {
  font-size: unset;
}

strong {
  font-weight: unset;
}

/* Override Blueprint's _typography.scss styles */
a {
  text-decoration: unset;
  color: unset;
}
a:hover {
  text-decoration: unset;
  color: unset;
}

/* Override Blueprint's _accessibility.scss styles */
:focus {
  outline: unset;
  outline-offset: unset;
  -moz-outline-radius: unset;
}

/* Styles for ui-components */
.jp-Button {
  border-radius: var(--jp-border-radius);
  padding: 0px 12px;
  font-size: var(--jp-ui-font-size1);
}

/* Use our own theme for hover styles */
button.jp-Button.bp3-button.bp3-minimal:hover {
  background-color: var(--jp-layout-color2);
}
.jp-Button.minimal {
  color: unset !important;
}

.jp-Button.jp-ToolbarButtonComponent {
  text-transform: none;
}

.jp-InputGroup input {
  box-sizing: border-box;
  border-radius: 0;
  background-color: transparent;
  color: var(--jp-ui-font-color0);
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.jp-InputGroup input:focus {
  box-shadow: inset 0 0 0 var(--jp-border-width)
      var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-InputGroup input::placeholder,
input::placeholder {
  color: var(--jp-ui-font-color3);
}

.jp-BPIcon {
  display: inline-block;
  vertical-align: middle;
  margin: auto;
}

/* Stop blueprint futzing with our icon fills */
.bp3-icon.jp-BPIcon > svg:not([fill]) {
  fill: var(--jp-inverse-layout-color3);
}

.jp-InputGroupAction {
  padding: 6px;
}

.jp-HTMLSelect.jp-DefaultStyle select {
  background-color: initial;
  border: none;
  border-radius: 0;
  box-shadow: none;
  color: var(--jp-ui-font-color0);
  display: block;
  font-size: var(--jp-ui-font-size1);
  height: 24px;
  line-height: 14px;
  padding: 0 25px 0 10px;
  text-align: left;
  -moz-appearance: none;
  -webkit-appearance: none;
}

/* Use our own theme for hover and option styles */
.jp-HTMLSelect.jp-DefaultStyle select:hover,
.jp-HTMLSelect.jp-DefaultStyle select > option {
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color0);
}
select {
  box-sizing: border-box;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapse {
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-top: 1px solid var(--jp-border-color2);
  border-bottom: 1px solid var(--jp-border-color2);
}

.jp-Collapse-header {
  padding: 1px 12px;
  color: var(--jp-ui-font-color1);
  background-color: var(--jp-layout-color1);
  font-size: var(--jp-ui-font-size2);
}

.jp-Collapse-header:hover {
  background-color: var(--jp-layout-color2);
}

.jp-Collapse-contents {
  padding: 0px 12px 0px 12px;
  background-color: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  overflow: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-commandpalette-search-height: 28px;
}

/*-----------------------------------------------------------------------------
| Overall styles
|----------------------------------------------------------------------------*/

.lm-CommandPalette {
  padding-bottom: 0px;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Search
|----------------------------------------------------------------------------*/

.lm-CommandPalette-search {
  padding: 4px;
  background-color: var(--jp-layout-color1);
  z-index: 2;
}

.lm-CommandPalette-wrapper {
  overflow: overlay;
  padding: 0px 9px;
  background-color: var(--jp-input-active-background);
  height: 30px;
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.lm-CommandPalette.lm-mod-focused .lm-CommandPalette-wrapper {
  box-shadow: inset 0 0 0 1px var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.lm-CommandPalette-wrapper::after {
  content: ' ';
  color: white;
  background-color: var(--jp-brand-color1);
  position: absolute;
  top: 4px;
  right: 4px;
  height: 30px;
  width: 10px;
  padding: 0px 10px;
  background-image: var(--jp-icon-search-white);
  background-size: 20px;
  background-repeat: no-repeat;
  background-position: center;
}

.lm-CommandPalette-input {
  background: transparent;
  width: calc(100% - 18px);
  float: left;
  border: none;
  outline: none;
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  line-height: var(--jp-private-commandpalette-search-height);
}

.lm-CommandPalette-input::-webkit-input-placeholder,
.lm-CommandPalette-input::-moz-placeholder,
.lm-CommandPalette-input:-ms-input-placeholder {
  color: var(--jp-ui-font-color3);
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Results
|----------------------------------------------------------------------------*/

.lm-CommandPalette-header:first-child {
  margin-top: 0px;
}

.lm-CommandPalette-header {
  border-bottom: solid var(--jp-border-width) var(--jp-border-color2);
  color: var(--jp-ui-font-color1);
  cursor: pointer;
  display: flex;
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  letter-spacing: 1px;
  margin-top: 8px;
  padding: 8px 0 8px 12px;
  text-transform: uppercase;
}

.lm-CommandPalette-header.lm-mod-active {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-header > mark {
  background-color: transparent;
  font-weight: bold;
  color: var(--jp-ui-font-color1);
}

.lm-CommandPalette-item {
  padding: 4px 12px 4px 4px;
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  font-weight: 400;
  display: flex;
}

.lm-CommandPalette-item.lm-mod-disabled {
  color: var(--jp-ui-font-color3);
}

.lm-CommandPalette-item.lm-mod-active {
  background: var(--jp-layout-color3);
}

.lm-CommandPalette-item.lm-mod-active:hover:not(.lm-mod-disabled) {
  background: var(--jp-layout-color4);
}

.lm-CommandPalette-item:hover:not(.lm-mod-active):not(.lm-mod-disabled) {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-itemContent {
  overflow: hidden;
}

.lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.lm-CommandPalette-item.lm-mod-disabled mark {
  color: var(--jp-ui-font-color3);
}

.lm-CommandPalette-item .lm-CommandPalette-itemIcon {
  margin: 0 4px 0 0;
  position: relative;
  width: 16px;
  top: 2px;
  flex: 0 0 auto;
}

.lm-CommandPalette-item.lm-mod-disabled .lm-CommandPalette-itemIcon {
  opacity: 0.4;
}

.lm-CommandPalette-item .lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemCaption {
  display: none;
}

.lm-CommandPalette-content {
  background-color: var(--jp-layout-color1);
}

.lm-CommandPalette-content:empty:after {
  content: 'No results';
  margin: auto;
  margin-top: 20px;
  width: 100px;
  display: block;
  font-size: var(--jp-ui-font-size2);
  font-family: var(--jp-ui-font-family);
  font-weight: lighter;
}

.lm-CommandPalette-emptyMessage {
  text-align: center;
  margin-top: 24px;
  line-height: 1.32;
  padding: 0px 8px;
  color: var(--jp-content-font-color3);
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Dialog {
  position: absolute;
  z-index: 10000;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  top: 0px;
  left: 0px;
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-dialog-background);
}

.jp-Dialog-content {
  display: flex;
  flex-direction: column;
  margin-left: auto;
  margin-right: auto;
  background: var(--jp-layout-color1);
  padding: 24px;
  padding-bottom: 12px;
  min-width: 300px;
  min-height: 150px;
  max-width: 1000px;
  max-height: 500px;
  box-sizing: border-box;
  box-shadow: var(--jp-elevation-z20);
  word-wrap: break-word;
  border-radius: var(--jp-border-radius);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color1);
}

.jp-Dialog-button {
  overflow: visible;
}

button.jp-Dialog-button:focus {
  outline: 1px solid var(--jp-brand-color1);
  outline-offset: 4px;
  -moz-outline-radius: 0px;
}

button.jp-Dialog-button:focus::-moz-focus-inner {
  border: 0;
}

.jp-Dialog-header {
  flex: 0 0 auto;
  padding-bottom: 12px;
  font-size: var(--jp-ui-font-size3);
  font-weight: 400;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-body {
  display: flex;
  flex-direction: column;
  flex: 1 1 auto;
  font-size: var(--jp-ui-font-size1);
  background: var(--jp-layout-color1);
  overflow: auto;
}

.jp-Dialog-footer {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  flex: 0 0 auto;
  margin-left: -12px;
  margin-right: -12px;
  padding: 12px;
}

.jp-Dialog-title {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.jp-Dialog-body > .jp-select-wrapper {
  width: 100%;
}

.jp-Dialog-body > button {
  padding: 0px 16px;
}

.jp-Dialog-body > label {
  line-height: 1.4;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-button.jp-mod-styled:not(:last-child) {
  margin-right: 12px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-HoverBox {
  position: fixed;
}

.jp-HoverBox.jp-mod-outofview {
  display: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-IFrame {
  width: 100%;
  height: 100%;
}

.jp-IFrame > iframe {
  border: none;
}

/*
When drag events occur, `p-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-IFrame {
  position: relative;
}

body.lm-mod-override-cursor .jp-IFrame:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MainAreaWidget > :focus {
  outline: none;
}

/**
 * google-material-color v1.2.6
 * https://github.com/danlevan/google-material-color
 */
:root {
  --md-red-50: #ffebee;
  --md-red-100: #ffcdd2;
  --md-red-200: #ef9a9a;
  --md-red-300: #e57373;
  --md-red-400: #ef5350;
  --md-red-500: #f44336;
  --md-red-600: #e53935;
  --md-red-700: #d32f2f;
  --md-red-800: #c62828;
  --md-red-900: #b71c1c;
  --md-red-A100: #ff8a80;
  --md-red-A200: #ff5252;
  --md-red-A400: #ff1744;
  --md-red-A700: #d50000;

  --md-pink-50: #fce4ec;
  --md-pink-100: #f8bbd0;
  --md-pink-200: #f48fb1;
  --md-pink-300: #f06292;
  --md-pink-400: #ec407a;
  --md-pink-500: #e91e63;
  --md-pink-600: #d81b60;
  --md-pink-700: #c2185b;
  --md-pink-800: #ad1457;
  --md-pink-900: #880e4f;
  --md-pink-A100: #ff80ab;
  --md-pink-A200: #ff4081;
  --md-pink-A400: #f50057;
  --md-pink-A700: #c51162;

  --md-purple-50: #f3e5f5;
  --md-purple-100: #e1bee7;
  --md-purple-200: #ce93d8;
  --md-purple-300: #ba68c8;
  --md-purple-400: #ab47bc;
  --md-purple-500: #9c27b0;
  --md-purple-600: #8e24aa;
  --md-purple-700: #7b1fa2;
  --md-purple-800: #6a1b9a;
  --md-purple-900: #4a148c;
  --md-purple-A100: #ea80fc;
  --md-purple-A200: #e040fb;
  --md-purple-A400: #d500f9;
  --md-purple-A700: #aa00ff;

  --md-deep-purple-50: #ede7f6;
  --md-deep-purple-100: #d1c4e9;
  --md-deep-purple-200: #b39ddb;
  --md-deep-purple-300: #9575cd;
  --md-deep-purple-400: #7e57c2;
  --md-deep-purple-500: #673ab7;
  --md-deep-purple-600: #5e35b1;
  --md-deep-purple-700: #512da8;
  --md-deep-purple-800: #4527a0;
  --md-deep-purple-900: #311b92;
  --md-deep-purple-A100: #b388ff;
  --md-deep-purple-A200: #7c4dff;
  --md-deep-purple-A400: #651fff;
  --md-deep-purple-A700: #6200ea;

  --md-indigo-50: #e8eaf6;
  --md-indigo-100: #c5cae9;
  --md-indigo-200: #9fa8da;
  --md-indigo-300: #7986cb;
  --md-indigo-400: #5c6bc0;
  --md-indigo-500: #3f51b5;
  --md-indigo-600: #3949ab;
  --md-indigo-700: #303f9f;
  --md-indigo-800: #283593;
  --md-indigo-900: #1a237e;
  --md-indigo-A100: #8c9eff;
  --md-indigo-A200: #536dfe;
  --md-indigo-A400: #3d5afe;
  --md-indigo-A700: #304ffe;

  --md-blue-50: #e3f2fd;
  --md-blue-100: #bbdefb;
  --md-blue-200: #90caf9;
  --md-blue-300: #64b5f6;
  --md-blue-400: #42a5f5;
  --md-blue-500: #2196f3;
  --md-blue-600: #1e88e5;
  --md-blue-700: #1976d2;
  --md-blue-800: #1565c0;
  --md-blue-900: #0d47a1;
  --md-blue-A100: #82b1ff;
  --md-blue-A200: #448aff;
  --md-blue-A400: #2979ff;
  --md-blue-A700: #2962ff;

  --md-light-blue-50: #e1f5fe;
  --md-light-blue-100: #b3e5fc;
  --md-light-blue-200: #81d4fa;
  --md-light-blue-300: #4fc3f7;
  --md-light-blue-400: #29b6f6;
  --md-light-blue-500: #03a9f4;
  --md-light-blue-600: #039be5;
  --md-light-blue-700: #0288d1;
  --md-light-blue-800: #0277bd;
  --md-light-blue-900: #01579b;
  --md-light-blue-A100: #80d8ff;
  --md-light-blue-A200: #40c4ff;
  --md-light-blue-A400: #00b0ff;
  --md-light-blue-A700: #0091ea;

  --md-cyan-50: #e0f7fa;
  --md-cyan-100: #b2ebf2;
  --md-cyan-200: #80deea;
  --md-cyan-300: #4dd0e1;
  --md-cyan-400: #26c6da;
  --md-cyan-500: #00bcd4;
  --md-cyan-600: #00acc1;
  --md-cyan-700: #0097a7;
  --md-cyan-800: #00838f;
  --md-cyan-900: #006064;
  --md-cyan-A100: #84ffff;
  --md-cyan-A200: #18ffff;
  --md-cyan-A400: #00e5ff;
  --md-cyan-A700: #00b8d4;

  --md-teal-50: #e0f2f1;
  --md-teal-100: #b2dfdb;
  --md-teal-200: #80cbc4;
  --md-teal-300: #4db6ac;
  --md-teal-400: #26a69a;
  --md-teal-500: #009688;
  --md-teal-600: #00897b;
  --md-teal-700: #00796b;
  --md-teal-800: #00695c;
  --md-teal-900: #004d40;
  --md-teal-A100: #a7ffeb;
  --md-teal-A200: #64ffda;
  --md-teal-A400: #1de9b6;
  --md-teal-A700: #00bfa5;

  --md-green-50: #e8f5e9;
  --md-green-100: #c8e6c9;
  --md-green-200: #a5d6a7;
  --md-green-300: #81c784;
  --md-green-400: #66bb6a;
  --md-green-500: #4caf50;
  --md-green-600: #43a047;
  --md-green-700: #388e3c;
  --md-green-800: #2e7d32;
  --md-green-900: #1b5e20;
  --md-green-A100: #b9f6ca;
  --md-green-A200: #69f0ae;
  --md-green-A400: #00e676;
  --md-green-A700: #00c853;

  --md-light-green-50: #f1f8e9;
  --md-light-green-100: #dcedc8;
  --md-light-green-200: #c5e1a5;
  --md-light-green-300: #aed581;
  --md-light-green-400: #9ccc65;
  --md-light-green-500: #8bc34a;
  --md-light-green-600: #7cb342;
  --md-light-green-700: #689f38;
  --md-light-green-800: #558b2f;
  --md-light-green-900: #33691e;
  --md-light-green-A100: #ccff90;
  --md-light-green-A200: #b2ff59;
  --md-light-green-A400: #76ff03;
  --md-light-green-A700: #64dd17;

  --md-lime-50: #f9fbe7;
  --md-lime-100: #f0f4c3;
  --md-lime-200: #e6ee9c;
  --md-lime-300: #dce775;
  --md-lime-400: #d4e157;
  --md-lime-500: #cddc39;
  --md-lime-600: #c0ca33;
  --md-lime-700: #afb42b;
  --md-lime-800: #9e9d24;
  --md-lime-900: #827717;
  --md-lime-A100: #f4ff81;
  --md-lime-A200: #eeff41;
  --md-lime-A400: #c6ff00;
  --md-lime-A700: #aeea00;

  --md-yellow-50: #fffde7;
  --md-yellow-100: #fff9c4;
  --md-yellow-200: #fff59d;
  --md-yellow-300: #fff176;
  --md-yellow-400: #ffee58;
  --md-yellow-500: #ffeb3b;
  --md-yellow-600: #fdd835;
  --md-yellow-700: #fbc02d;
  --md-yellow-800: #f9a825;
  --md-yellow-900: #f57f17;
  --md-yellow-A100: #ffff8d;
  --md-yellow-A200: #ffff00;
  --md-yellow-A400: #ffea00;
  --md-yellow-A700: #ffd600;

  --md-amber-50: #fff8e1;
  --md-amber-100: #ffecb3;
  --md-amber-200: #ffe082;
  --md-amber-300: #ffd54f;
  --md-amber-400: #ffca28;
  --md-amber-500: #ffc107;
  --md-amber-600: #ffb300;
  --md-amber-700: #ffa000;
  --md-amber-800: #ff8f00;
  --md-amber-900: #ff6f00;
  --md-amber-A100: #ffe57f;
  --md-amber-A200: #ffd740;
  --md-amber-A400: #ffc400;
  --md-amber-A700: #ffab00;

  --md-orange-50: #fff3e0;
  --md-orange-100: #ffe0b2;
  --md-orange-200: #ffcc80;
  --md-orange-300: #ffb74d;
  --md-orange-400: #ffa726;
  --md-orange-500: #ff9800;
  --md-orange-600: #fb8c00;
  --md-orange-700: #f57c00;
  --md-orange-800: #ef6c00;
  --md-orange-900: #e65100;
  --md-orange-A100: #ffd180;
  --md-orange-A200: #ffab40;
  --md-orange-A400: #ff9100;
  --md-orange-A700: #ff6d00;

  --md-deep-orange-50: #fbe9e7;
  --md-deep-orange-100: #ffccbc;
  --md-deep-orange-200: #ffab91;
  --md-deep-orange-300: #ff8a65;
  --md-deep-orange-400: #ff7043;
  --md-deep-orange-500: #ff5722;
  --md-deep-orange-600: #f4511e;
  --md-deep-orange-700: #e64a19;
  --md-deep-orange-800: #d84315;
  --md-deep-orange-900: #bf360c;
  --md-deep-orange-A100: #ff9e80;
  --md-deep-orange-A200: #ff6e40;
  --md-deep-orange-A400: #ff3d00;
  --md-deep-orange-A700: #dd2c00;

  --md-brown-50: #efebe9;
  --md-brown-100: #d7ccc8;
  --md-brown-200: #bcaaa4;
  --md-brown-300: #a1887f;
  --md-brown-400: #8d6e63;
  --md-brown-500: #795548;
  --md-brown-600: #6d4c41;
  --md-brown-700: #5d4037;
  --md-brown-800: #4e342e;
  --md-brown-900: #3e2723;

  --md-grey-50: #fafafa;
  --md-grey-100: #f5f5f5;
  --md-grey-200: #eeeeee;
  --md-grey-300: #e0e0e0;
  --md-grey-400: #bdbdbd;
  --md-grey-500: #9e9e9e;
  --md-grey-600: #757575;
  --md-grey-700: #616161;
  --md-grey-800: #424242;
  --md-grey-900: #212121;

  --md-blue-grey-50: #eceff1;
  --md-blue-grey-100: #cfd8dc;
  --md-blue-grey-200: #b0bec5;
  --md-blue-grey-300: #90a4ae;
  --md-blue-grey-400: #78909c;
  --md-blue-grey-500: #607d8b;
  --md-blue-grey-600: #546e7a;
  --md-blue-grey-700: #455a64;
  --md-blue-grey-800: #37474f;
  --md-blue-grey-900: #263238;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Spinner {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 10;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-layout-color0);
  outline: none;
}

.jp-SpinnerContent {
  font-size: 10px;
  margin: 50px auto;
  text-indent: -9999em;
  width: 3em;
  height: 3em;
  border-radius: 50%;
  background: var(--jp-brand-color3);
  background: linear-gradient(
    to right,
    #f37626 10%,
    rgba(255, 255, 255, 0) 42%
  );
  position: relative;
  animation: load3 1s infinite linear, fadeIn 1s;
}

.jp-SpinnerContent:before {
  width: 50%;
  height: 50%;
  background: #f37626;
  border-radius: 100% 0 0 0;
  position: absolute;
  top: 0;
  left: 0;
  content: '';
}

.jp-SpinnerContent:after {
  background: var(--jp-layout-color0);
  width: 75%;
  height: 75%;
  border-radius: 50%;
  content: '';
  margin: auto;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes load3 {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

button.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: none;
  box-sizing: border-box;
  text-align: center;
  line-height: 32px;
  height: 32px;
  padding: 0px 12px;
  letter-spacing: 0.8px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input.jp-mod-styled {
  background: var(--jp-input-background);
  height: 28px;
  box-sizing: border-box;
  border: var(--jp-border-width) solid var(--jp-border-color1);
  padding-left: 7px;
  padding-right: 7px;
  font-size: var(--jp-ui-font-size2);
  color: var(--jp-ui-font-color0);
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input.jp-mod-styled:focus {
  border: var(--jp-border-width) solid var(--md-blue-500);
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-select-wrapper {
  display: flex;
  position: relative;
  flex-direction: column;
  padding: 1px;
  background-color: var(--jp-layout-color1);
  height: 28px;
  box-sizing: border-box;
  margin-bottom: 12px;
}

.jp-select-wrapper.jp-mod-focused select.jp-mod-styled {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-input-active-background);
}

select.jp-mod-styled:hover {
  background-color: var(--jp-layout-color1);
  cursor: pointer;
  color: var(--jp-ui-font-color0);
  background-color: var(--jp-input-hover-background);
  box-shadow: inset 0 0px 1px rgba(0, 0, 0, 0.5);
}

select.jp-mod-styled {
  flex: 1 1 auto;
  height: 32px;
  width: 100%;
  font-size: var(--jp-ui-font-size2);
  background: var(--jp-input-background);
  color: var(--jp-ui-font-color0);
  padding: 0 25px 0 8px;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

:root {
  --jp-private-toolbar-height: calc(
    28px + var(--jp-border-width)
  ); /* leave 28px for content */
}

.jp-Toolbar {
  color: var(--jp-ui-font-color1);
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  background: var(--jp-toolbar-background);
  min-height: var(--jp-toolbar-micro-height);
  padding: 2px;
  z-index: 1;
}

/* Toolbar items */

.jp-Toolbar > .jp-Toolbar-item.jp-Toolbar-spacer {
  flex-grow: 1;
  flex-shrink: 1;
}

.jp-Toolbar-item.jp-Toolbar-kernelStatus {
  display: inline-block;
  width: 32px;
  background-repeat: no-repeat;
  background-position: center;
  background-size: 16px;
}

.jp-Toolbar > .jp-Toolbar-item {
  flex: 0 0 auto;
  display: flex;
  padding-left: 1px;
  padding-right: 1px;
  font-size: var(--jp-ui-font-size1);
  line-height: var(--jp-private-toolbar-height);
  height: 100%;
}

/* Toolbar buttons */

/* This is the div we use to wrap the react component into a Widget */
div.jp-ToolbarButton {
  color: transparent;
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0px;
  margin: 0px;
}

button.jp-ToolbarButtonComponent {
  background: var(--jp-layout-color1);
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0px 6px;
  margin: 0px;
  height: 24px;
  border-radius: var(--jp-border-radius);
  display: flex;
  align-items: center;
  text-align: center;
  font-size: 14px;
  min-width: unset;
  min-height: unset;
}

button.jp-ToolbarButtonComponent:disabled {
  opacity: 0.4;
}

button.jp-ToolbarButtonComponent span {
  padding: 0px;
  flex: 0 0 auto;
}

button.jp-ToolbarButtonComponent .jp-ToolbarButtonComponent-label {
  font-size: var(--jp-ui-font-size1);
  line-height: 100%;
  padding-left: 2px;
  color: var(--jp-ui-font-color1);
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ body.p-mod-override-cursor *, /* </DEPRECATED> */
body.lm-mod-override-cursor * {
  cursor: inherit !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-JSONEditor {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.jp-JSONEditor-host {
  flex: 1 1 auto;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0px;
  background: var(--jp-layout-color0);
  min-height: 50px;
  padding: 1px;
}

.jp-JSONEditor.jp-mod-error .jp-JSONEditor-host {
  border-color: red;
  outline-color: red;
}

.jp-JSONEditor-header {
  display: flex;
  flex: 1 0 auto;
  padding: 0 0 0 12px;
}

.jp-JSONEditor-header label {
  flex: 0 0 auto;
}

.jp-JSONEditor-commitButton {
  height: 16px;
  width: 16px;
  background-size: 18px;
  background-repeat: no-repeat;
  background-position: center;
}

.jp-JSONEditor-host.jp-mod-focused {
  background-color: var(--jp-input-active-background);
  border: 1px solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

.jp-Editor.jp-mod-dropTarget {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* BASICS */

.CodeMirror {
  /* Set height, width, borders, and global font properties here */
  font-family: monospace;
  height: 300px;
  color: black;
  direction: ltr;
}

/* PADDING */

.CodeMirror-lines {
  padding: 4px 0; /* Vertical padding around content */
}
.CodeMirror pre.CodeMirror-line,
.CodeMirror pre.CodeMirror-line-like {
  padding: 0 4px; /* Horizontal padding of content */
}

.CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  background-color: white; /* The little square between H and V scrollbars */
}

/* GUTTER */

.CodeMirror-gutters {
  border-right: 1px solid #ddd;
  background-color: #f7f7f7;
  white-space: nowrap;
}
.CodeMirror-linenumbers {}
.CodeMirror-linenumber {
  padding: 0 3px 0 5px;
  min-width: 20px;
  text-align: right;
  color: #999;
  white-space: nowrap;
}

.CodeMirror-guttermarker { color: black; }
.CodeMirror-guttermarker-subtle { color: #999; }

/* CURSOR */

.CodeMirror-cursor {
  border-left: 1px solid black;
  border-right: none;
  width: 0;
}
/* Shown when moving in bi-directional text */
.CodeMirror div.CodeMirror-secondarycursor {
  border-left: 1px solid silver;
}
.cm-fat-cursor .CodeMirror-cursor {
  width: auto;
  border: 0 !important;
  background: #7e7;
}
.cm-fat-cursor div.CodeMirror-cursors {
  z-index: 1;
}
.cm-fat-cursor-mark {
  background-color: rgba(20, 255, 20, 0.5);
  -webkit-animation: blink 1.06s steps(1) infinite;
  -moz-animation: blink 1.06s steps(1) infinite;
  animation: blink 1.06s steps(1) infinite;
}
.cm-animate-fat-cursor {
  width: auto;
  border: 0;
  -webkit-animation: blink 1.06s steps(1) infinite;
  -moz-animation: blink 1.06s steps(1) infinite;
  animation: blink 1.06s steps(1) infinite;
  background-color: #7e7;
}
@-moz-keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}
@-webkit-keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}
@keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}

/* Can style cursor different in overwrite (non-insert) mode */
.CodeMirror-overwrite .CodeMirror-cursor {}

.cm-tab { display: inline-block; text-decoration: inherit; }

.CodeMirror-rulers {
  position: absolute;
  left: 0; right: 0; top: -50px; bottom: 0;
  overflow: hidden;
}
.CodeMirror-ruler {
  border-left: 1px solid #ccc;
  top: 0; bottom: 0;
  position: absolute;
}

/* DEFAULT THEME */

.cm-s-default .cm-header {color: blue;}
.cm-s-default .cm-quote {color: #090;}
.cm-negative {color: #d44;}
.cm-positive {color: #292;}
.cm-header, .cm-strong {font-weight: bold;}
.cm-em {font-style: italic;}
.cm-link {text-decoration: underline;}
.cm-strikethrough {text-decoration: line-through;}

.cm-s-default .cm-keyword {color: #708;}
.cm-s-default .cm-atom {color: #219;}
.cm-s-default .cm-number {color: #164;}
.cm-s-default .cm-def {color: #00f;}
.cm-s-default .cm-variable,
.cm-s-default .cm-punctuation,
.cm-s-default .cm-property,
.cm-s-default .cm-operator {}
.cm-s-default .cm-variable-2 {color: #05a;}
.cm-s-default .cm-variable-3, .cm-s-default .cm-type {color: #085;}
.cm-s-default .cm-comment {color: #a50;}
.cm-s-default .cm-string {color: #a11;}
.cm-s-default .cm-string-2 {color: #f50;}
.cm-s-default .cm-meta {color: #555;}
.cm-s-default .cm-qualifier {color: #555;}
.cm-s-default .cm-builtin {color: #30a;}
.cm-s-default .cm-bracket {color: #997;}
.cm-s-default .cm-tag {color: #170;}
.cm-s-default .cm-attribute {color: #00c;}
.cm-s-default .cm-hr {color: #999;}
.cm-s-default .cm-link {color: #00c;}

.cm-s-default .cm-error {color: #f00;}
.cm-invalidchar {color: #f00;}

.CodeMirror-composing { border-bottom: 2px solid; }

/* Default styles for common addons */

div.CodeMirror span.CodeMirror-matchingbracket {color: #0b0;}
div.CodeMirror span.CodeMirror-nonmatchingbracket {color: #a22;}
.CodeMirror-matchingtag { background: rgba(255, 150, 0, .3); }
.CodeMirror-activeline-background {background: #e8f2ff;}

/* STOP */

/* The rest of this file contains styles related to the mechanics of
   the editor. You probably shouldn't touch them. */

.CodeMirror {
  position: relative;
  overflow: hidden;
  background: white;
}

.CodeMirror-scroll {
  overflow: scroll !important; /* Things will break if this is overridden */
  /* 30px is the magic margin used to hide the element's real scrollbars */
  /* See overflow: hidden in .CodeMirror */
  margin-bottom: -30px; margin-right: -30px;
  padding-bottom: 30px;
  height: 100%;
  outline: none; /* Prevent dragging from highlighting the element */
  position: relative;
}
.CodeMirror-sizer {
  position: relative;
  border-right: 30px solid transparent;
}

/* The fake, visible scrollbars. Used to force redraw during scrolling
   before actual scrolling happens, thus preventing shaking and
   flickering artifacts. */
.CodeMirror-vscrollbar, .CodeMirror-hscrollbar, .CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  position: absolute;
  z-index: 6;
  display: none;
}
.CodeMirror-vscrollbar {
  right: 0; top: 0;
  overflow-x: hidden;
  overflow-y: scroll;
}
.CodeMirror-hscrollbar {
  bottom: 0; left: 0;
  overflow-y: hidden;
  overflow-x: scroll;
}
.CodeMirror-scrollbar-filler {
  right: 0; bottom: 0;
}
.CodeMirror-gutter-filler {
  left: 0; bottom: 0;
}

.CodeMirror-gutters {
  position: absolute; left: 0; top: 0;
  min-height: 100%;
  z-index: 3;
}
.CodeMirror-gutter {
  white-space: normal;
  height: 100%;
  display: inline-block;
  vertical-align: top;
  margin-bottom: -30px;
}
.CodeMirror-gutter-wrapper {
  position: absolute;
  z-index: 4;
  background: none !important;
  border: none !important;
}
.CodeMirror-gutter-background {
  position: absolute;
  top: 0; bottom: 0;
  z-index: 4;
}
.CodeMirror-gutter-elt {
  position: absolute;
  cursor: default;
  z-index: 4;
}
.CodeMirror-gutter-wrapper ::selection { background-color: transparent }
.CodeMirror-gutter-wrapper ::-moz-selection { background-color: transparent }

.CodeMirror-lines {
  cursor: text;
  min-height: 1px; /* prevents collapsing before first draw */
}
.CodeMirror pre.CodeMirror-line,
.CodeMirror pre.CodeMirror-line-like {
  /* Reset some styles that the rest of the page might have set */
  -moz-border-radius: 0; -webkit-border-radius: 0; border-radius: 0;
  border-width: 0;
  background: transparent;
  font-family: inherit;
  font-size: inherit;
  margin: 0;
  white-space: pre;
  word-wrap: normal;
  line-height: inherit;
  color: inherit;
  z-index: 2;
  position: relative;
  overflow: visible;
  -webkit-tap-highlight-color: transparent;
  -webkit-font-variant-ligatures: contextual;
  font-variant-ligatures: contextual;
}
.CodeMirror-wrap pre.CodeMirror-line,
.CodeMirror-wrap pre.CodeMirror-line-like {
  word-wrap: break-word;
  white-space: pre-wrap;
  word-break: normal;
}

.CodeMirror-linebackground {
  position: absolute;
  left: 0; right: 0; top: 0; bottom: 0;
  z-index: 0;
}

.CodeMirror-linewidget {
  position: relative;
  z-index: 2;
  padding: 0.1px; /* Force widget margins to stay inside of the container */
}

.CodeMirror-widget {}

.CodeMirror-rtl pre { direction: rtl; }

.CodeMirror-code {
  outline: none;
}

/* Force content-box sizing for the elements where we expect it */
.CodeMirror-scroll,
.CodeMirror-sizer,
.CodeMirror-gutter,
.CodeMirror-gutters,
.CodeMirror-linenumber {
  -moz-box-sizing: content-box;
  box-sizing: content-box;
}

.CodeMirror-measure {
  position: absolute;
  width: 100%;
  height: 0;
  overflow: hidden;
  visibility: hidden;
}

.CodeMirror-cursor {
  position: absolute;
  pointer-events: none;
}
.CodeMirror-measure pre { position: static; }

div.CodeMirror-cursors {
  visibility: hidden;
  position: relative;
  z-index: 3;
}
div.CodeMirror-dragcursors {
  visibility: visible;
}

.CodeMirror-focused div.CodeMirror-cursors {
  visibility: visible;
}

.CodeMirror-selected { background: #d9d9d9; }
.CodeMirror-focused .CodeMirror-selected { background: #d7d4f0; }
.CodeMirror-crosshair { cursor: crosshair; }
.CodeMirror-line::selection, .CodeMirror-line > span::selection, .CodeMirror-line > span > span::selection { background: #d7d4f0; }
.CodeMirror-line::-moz-selection, .CodeMirror-line > span::-moz-selection, .CodeMirror-line > span > span::-moz-selection { background: #d7d4f0; }

.cm-searching {
  background-color: #ffa;
  background-color: rgba(255, 255, 0, .4);
}

/* Used to force a border model for a node */
.cm-force-border { padding-right: .1px; }

@media print {
  /* Hide the cursor when printing */
  .CodeMirror div.CodeMirror-cursors {
    visibility: hidden;
  }
}

/* See issue #2901 */
.cm-tab-wrap-hack:after { content: ''; }

/* Help users use markselection to safely style text background */
span.CodeMirror-selectedtext { background: none; }

.CodeMirror-dialog {
  position: absolute;
  left: 0; right: 0;
  background: inherit;
  z-index: 15;
  padding: .1em .8em;
  overflow: hidden;
  color: inherit;
}

.CodeMirror-dialog-top {
  border-bottom: 1px solid #eee;
  top: 0;
}

.CodeMirror-dialog-bottom {
  border-top: 1px solid #eee;
  bottom: 0;
}

.CodeMirror-dialog input {
  border: none;
  outline: none;
  background: transparent;
  width: 20em;
  color: inherit;
  font-family: monospace;
}

.CodeMirror-dialog button {
  font-size: 70%;
}

.CodeMirror-foldmarker {
  color: blue;
  text-shadow: #b9f 1px 1px 2px, #b9f -1px -1px 2px, #b9f 1px -1px 2px, #b9f -1px 1px 2px;
  font-family: arial;
  line-height: .3;
  cursor: pointer;
}
.CodeMirror-foldgutter {
  width: .7em;
}
.CodeMirror-foldgutter-open,
.CodeMirror-foldgutter-folded {
  cursor: pointer;
}
.CodeMirror-foldgutter-open:after {
  content: "\25BE";
}
.CodeMirror-foldgutter-folded:after {
  content: "\25B8";
}

/*
  Name:       material
  Author:     Mattia Astorino (http://github.com/equinusocio)
  Website:    https://material-theme.site/
*/

.cm-s-material.CodeMirror {
  background-color: #263238;
  color: #EEFFFF;
}

.cm-s-material .CodeMirror-gutters {
  background: #263238;
  color: #546E7A;
  border: none;
}

.cm-s-material .CodeMirror-guttermarker,
.cm-s-material .CodeMirror-guttermarker-subtle,
.cm-s-material .CodeMirror-linenumber {
  color: #546E7A;
}

.cm-s-material .CodeMirror-cursor {
  border-left: 1px solid #FFCC00;
}

.cm-s-material div.CodeMirror-selected {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material.CodeMirror-focused div.CodeMirror-selected {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material .CodeMirror-line::selection,
.cm-s-material .CodeMirror-line>span::selection,
.cm-s-material .CodeMirror-line>span>span::selection {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material .CodeMirror-line::-moz-selection,
.cm-s-material .CodeMirror-line>span::-moz-selection,
.cm-s-material .CodeMirror-line>span>span::-moz-selection {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material .CodeMirror-activeline-background {
  background: rgba(0, 0, 0, 0.5);
}

.cm-s-material .cm-keyword {
  color: #C792EA;
}

.cm-s-material .cm-operator {
  color: #89DDFF;
}

.cm-s-material .cm-variable-2 {
  color: #EEFFFF;
}

.cm-s-material .cm-variable-3,
.cm-s-material .cm-type {
  color: #f07178;
}

.cm-s-material .cm-builtin {
  color: #FFCB6B;
}

.cm-s-material .cm-atom {
  color: #F78C6C;
}

.cm-s-material .cm-number {
  color: #FF5370;
}

.cm-s-material .cm-def {
  color: #82AAFF;
}

.cm-s-material .cm-string {
  color: #C3E88D;
}

.cm-s-material .cm-string-2 {
  color: #f07178;
}

.cm-s-material .cm-comment {
  color: #546E7A;
}

.cm-s-material .cm-variable {
  color: #f07178;
}

.cm-s-material .cm-tag {
  color: #FF5370;
}

.cm-s-material .cm-meta {
  color: #FFCB6B;
}

.cm-s-material .cm-attribute {
  color: #C792EA;
}

.cm-s-material .cm-property {
  color: #C792EA;
}

.cm-s-material .cm-qualifier {
  color: #DECB6B;
}

.cm-s-material .cm-variable-3,
.cm-s-material .cm-type {
  color: #DECB6B;
}


.cm-s-material .cm-error {
  color: rgba(255, 255, 255, 1.0);
  background-color: #FF5370;
}

.cm-s-material .CodeMirror-matchingbracket {
  text-decoration: underline;
  color: white !important;
}
/**
 * "
 *  Using Zenburn color palette from the Emacs Zenburn Theme
 *  https://github.com/bbatsov/zenburn-emacs/blob/master/zenburn-theme.el
 *
 *  Also using parts of https://github.com/xavi/coderay-lighttable-theme
 * "
 * From: https://github.com/wisenomad/zenburn-lighttable-theme/blob/master/zenburn.css
 */

.cm-s-zenburn .CodeMirror-gutters { background: #3f3f3f !important; }
.cm-s-zenburn .CodeMirror-foldgutter-open, .CodeMirror-foldgutter-folded { color: #999; }
.cm-s-zenburn .CodeMirror-cursor { border-left: 1px solid white; }
.cm-s-zenburn { background-color: #3f3f3f; color: #dcdccc; }
.cm-s-zenburn span.cm-builtin { color: #dcdccc; font-weight: bold; }
.cm-s-zenburn span.cm-comment { color: #7f9f7f; }
.cm-s-zenburn span.cm-keyword { color: #f0dfaf; font-weight: bold; }
.cm-s-zenburn span.cm-atom { color: #bfebbf; }
.cm-s-zenburn span.cm-def { color: #dcdccc; }
.cm-s-zenburn span.cm-variable { color: #dfaf8f; }
.cm-s-zenburn span.cm-variable-2 { color: #dcdccc; }
.cm-s-zenburn span.cm-string { color: #cc9393; }
.cm-s-zenburn span.cm-string-2 { color: #cc9393; }
.cm-s-zenburn span.cm-number { color: #dcdccc; }
.cm-s-zenburn span.cm-tag { color: #93e0e3; }
.cm-s-zenburn span.cm-property { color: #dfaf8f; }
.cm-s-zenburn span.cm-attribute { color: #dfaf8f; }
.cm-s-zenburn span.cm-qualifier { color: #7cb8bb; }
.cm-s-zenburn span.cm-meta { color: #f0dfaf; }
.cm-s-zenburn span.cm-header { color: #f0efd0; }
.cm-s-zenburn span.cm-operator { color: #f0efd0; }
.cm-s-zenburn span.CodeMirror-matchingbracket { box-sizing: border-box; background: transparent; border-bottom: 1px solid; }
.cm-s-zenburn span.CodeMirror-nonmatchingbracket { border-bottom: 1px solid; background: none; }
.cm-s-zenburn .CodeMirror-activeline { background: #000000; }
.cm-s-zenburn .CodeMirror-activeline-background { background: #000000; }
.cm-s-zenburn div.CodeMirror-selected { background: #545454; }
.cm-s-zenburn .CodeMirror-focused div.CodeMirror-selected { background: #4f4f4f; }

.cm-s-abcdef.CodeMirror { background: #0f0f0f; color: #defdef; }
.cm-s-abcdef div.CodeMirror-selected { background: #515151; }
.cm-s-abcdef .CodeMirror-line::selection, .cm-s-abcdef .CodeMirror-line > span::selection, .cm-s-abcdef .CodeMirror-line > span > span::selection { background: rgba(56, 56, 56, 0.99); }
.cm-s-abcdef .CodeMirror-line::-moz-selection, .cm-s-abcdef .CodeMirror-line > span::-moz-selection, .cm-s-abcdef .CodeMirror-line > span > span::-moz-selection { background: rgba(56, 56, 56, 0.99); }
.cm-s-abcdef .CodeMirror-gutters { background: #555; border-right: 2px solid #314151; }
.cm-s-abcdef .CodeMirror-guttermarker { color: #222; }
.cm-s-abcdef .CodeMirror-guttermarker-subtle { color: azure; }
.cm-s-abcdef .CodeMirror-linenumber { color: #FFFFFF; }
.cm-s-abcdef .CodeMirror-cursor { border-left: 1px solid #00FF00; }

.cm-s-abcdef span.cm-keyword { color: darkgoldenrod; font-weight: bold; }
.cm-s-abcdef span.cm-atom { color: #77F; }
.cm-s-abcdef span.cm-number { color: violet; }
.cm-s-abcdef span.cm-def { color: #fffabc; }
.cm-s-abcdef span.cm-variable { color: #abcdef; }
.cm-s-abcdef span.cm-variable-2 { color: #cacbcc; }
.cm-s-abcdef span.cm-variable-3, .cm-s-abcdef span.cm-type { color: #def; }
.cm-s-abcdef span.cm-property { color: #fedcba; }
.cm-s-abcdef span.cm-operator { color: #ff0; }
.cm-s-abcdef span.cm-comment { color: #7a7b7c; font-style: italic;}
.cm-s-abcdef span.cm-string { color: #2b4; }
.cm-s-abcdef span.cm-meta { color: #C9F; }
.cm-s-abcdef span.cm-qualifier { color: #FFF700; }
.cm-s-abcdef span.cm-builtin { color: #30aabc; }
.cm-s-abcdef span.cm-bracket { color: #8a8a8a; }
.cm-s-abcdef span.cm-tag { color: #FFDD44; }
.cm-s-abcdef span.cm-attribute { color: #DDFF00; }
.cm-s-abcdef span.cm-error { color: #FF0000; }
.cm-s-abcdef span.cm-header { color: aquamarine; font-weight: bold; }
.cm-s-abcdef span.cm-link { color: blueviolet; }

.cm-s-abcdef .CodeMirror-activeline-background { background: #314151; }

/*

    Name:       Base16 Default Light
    Author:     Chris Kempson (http://chriskempson.com)

    CodeMirror template by Jan T. Sott (https://github.com/idleberg/base16-codemirror)
    Original Base16 color scheme by Chris Kempson (https://github.com/chriskempson/base16)

*/

.cm-s-base16-light.CodeMirror { background: #f5f5f5; color: #202020; }
.cm-s-base16-light div.CodeMirror-selected { background: #e0e0e0; }
.cm-s-base16-light .CodeMirror-line::selection, .cm-s-base16-light .CodeMirror-line > span::selection, .cm-s-base16-light .CodeMirror-line > span > span::selection { background: #e0e0e0; }
.cm-s-base16-light .CodeMirror-line::-moz-selection, .cm-s-base16-light .CodeMirror-line > span::-moz-selection, .cm-s-base16-light .CodeMirror-line > span > span::-moz-selection { background: #e0e0e0; }
.cm-s-base16-light .CodeMirror-gutters { background: #f5f5f5; border-right: 0px; }
.cm-s-base16-light .CodeMirror-guttermarker { color: #ac4142; }
.cm-s-base16-light .CodeMirror-guttermarker-subtle { color: #b0b0b0; }
.cm-s-base16-light .CodeMirror-linenumber { color: #b0b0b0; }
.cm-s-base16-light .CodeMirror-cursor { border-left: 1px solid #505050; }

.cm-s-base16-light span.cm-comment { color: #8f5536; }
.cm-s-base16-light span.cm-atom { color: #aa759f; }
.cm-s-base16-light span.cm-number { color: #aa759f; }

.cm-s-base16-light span.cm-property, .cm-s-base16-light span.cm-attribute { color: #90a959; }
.cm-s-base16-light span.cm-keyword { color: #ac4142; }
.cm-s-base16-light span.cm-string { color: #f4bf75; }

.cm-s-base16-light span.cm-variable { color: #90a959; }
.cm-s-base16-light span.cm-variable-2 { color: #6a9fb5; }
.cm-s-base16-light span.cm-def { color: #d28445; }
.cm-s-base16-light span.cm-bracket { color: #202020; }
.cm-s-base16-light span.cm-tag { color: #ac4142; }
.cm-s-base16-light span.cm-link { color: #aa759f; }
.cm-s-base16-light span.cm-error { background: #ac4142; color: #505050; }

.cm-s-base16-light .CodeMirror-activeline-background { background: #DDDCDC; }
.cm-s-base16-light .CodeMirror-matchingbracket { color: #f5f5f5 !important; background-color: #6A9FB5 !important}

/*

    Name:       Base16 Default Dark
    Author:     Chris Kempson (http://chriskempson.com)

    CodeMirror template by Jan T. Sott (https://github.com/idleberg/base16-codemirror)
    Original Base16 color scheme by Chris Kempson (https://github.com/chriskempson/base16)

*/

.cm-s-base16-dark.CodeMirror { background: #151515; color: #e0e0e0; }
.cm-s-base16-dark div.CodeMirror-selected { background: #303030; }
.cm-s-base16-dark .CodeMirror-line::selection, .cm-s-base16-dark .CodeMirror-line > span::selection, .cm-s-base16-dark .CodeMirror-line > span > span::selection { background: rgba(48, 48, 48, .99); }
.cm-s-base16-dark .CodeMirror-line::-moz-selection, .cm-s-base16-dark .CodeMirror-line > span::-moz-selection, .cm-s-base16-dark .CodeMirror-line > span > span::-moz-selection { background: rgba(48, 48, 48, .99); }
.cm-s-base16-dark .CodeMirror-gutters { background: #151515; border-right: 0px; }
.cm-s-base16-dark .CodeMirror-guttermarker { color: #ac4142; }
.cm-s-base16-dark .CodeMirror-guttermarker-subtle { color: #505050; }
.cm-s-base16-dark .CodeMirror-linenumber { color: #505050; }
.cm-s-base16-dark .CodeMirror-cursor { border-left: 1px solid #b0b0b0; }

.cm-s-base16-dark span.cm-comment { color: #8f5536; }
.cm-s-base16-dark span.cm-atom { color: #aa759f; }
.cm-s-base16-dark span.cm-number { color: #aa759f; }

.cm-s-base16-dark span.cm-property, .cm-s-base16-dark span.cm-attribute { color: #90a959; }
.cm-s-base16-dark span.cm-keyword { color: #ac4142; }
.cm-s-base16-dark span.cm-string { color: #f4bf75; }

.cm-s-base16-dark span.cm-variable { color: #90a959; }
.cm-s-base16-dark span.cm-variable-2 { color: #6a9fb5; }
.cm-s-base16-dark span.cm-def { color: #d28445; }
.cm-s-base16-dark span.cm-bracket { color: #e0e0e0; }
.cm-s-base16-dark span.cm-tag { color: #ac4142; }
.cm-s-base16-dark span.cm-link { color: #aa759f; }
.cm-s-base16-dark span.cm-error { background: #ac4142; color: #b0b0b0; }

.cm-s-base16-dark .CodeMirror-activeline-background { background: #202020; }
.cm-s-base16-dark .CodeMirror-matchingbracket { text-decoration: underline; color: white !important; }

/*

    Name:       dracula
    Author:     Michael Kaminsky (http://github.com/mkaminsky11)

    Original dracula color scheme by Zeno Rocha (https://github.com/zenorocha/dracula-theme)

*/


.cm-s-dracula.CodeMirror, .cm-s-dracula .CodeMirror-gutters {
  background-color: #282a36 !important;
  color: #f8f8f2 !important;
  border: none;
}
.cm-s-dracula .CodeMirror-gutters { color: #282a36; }
.cm-s-dracula .CodeMirror-cursor { border-left: solid thin #f8f8f0; }
.cm-s-dracula .CodeMirror-linenumber { color: #6D8A88; }
.cm-s-dracula .CodeMirror-selected { background: rgba(255, 255, 255, 0.10); }
.cm-s-dracula .CodeMirror-line::selection, .cm-s-dracula .CodeMirror-line > span::selection, .cm-s-dracula .CodeMirror-line > span > span::selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-dracula .CodeMirror-line::-moz-selection, .cm-s-dracula .CodeMirror-line > span::-moz-selection, .cm-s-dracula .CodeMirror-line > span > span::-moz-selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-dracula span.cm-comment { color: #6272a4; }
.cm-s-dracula span.cm-string, .cm-s-dracula span.cm-string-2 { color: #f1fa8c; }
.cm-s-dracula span.cm-number { color: #bd93f9; }
.cm-s-dracula span.cm-variable { color: #50fa7b; }
.cm-s-dracula span.cm-variable-2 { color: white; }
.cm-s-dracula span.cm-def { color: #50fa7b; }
.cm-s-dracula span.cm-operator { color: #ff79c6; }
.cm-s-dracula span.cm-keyword { color: #ff79c6; }
.cm-s-dracula span.cm-atom { color: #bd93f9; }
.cm-s-dracula span.cm-meta { color: #f8f8f2; }
.cm-s-dracula span.cm-tag { color: #ff79c6; }
.cm-s-dracula span.cm-attribute { color: #50fa7b; }
.cm-s-dracula span.cm-qualifier { color: #50fa7b; }
.cm-s-dracula span.cm-property { color: #66d9ef; }
.cm-s-dracula span.cm-builtin { color: #50fa7b; }
.cm-s-dracula span.cm-variable-3, .cm-s-dracula span.cm-type { color: #ffb86c; }

.cm-s-dracula .CodeMirror-activeline-background { background: rgba(255,255,255,0.1); }
.cm-s-dracula .CodeMirror-matchingbracket { text-decoration: underline; color: white !important; }

/*

    Name:       Hopscotch
    Author:     Jan T. Sott

    CodeMirror template by Jan T. Sott (https://github.com/idleberg/base16-codemirror)
    Original Base16 color scheme by Chris Kempson (https://github.com/chriskempson/base16)

*/

.cm-s-hopscotch.CodeMirror {background: #322931; color: #d5d3d5;}
.cm-s-hopscotch div.CodeMirror-selected {background: #433b42 !important;}
.cm-s-hopscotch .CodeMirror-gutters {background: #322931; border-right: 0px;}
.cm-s-hopscotch .CodeMirror-linenumber {color: #797379;}
.cm-s-hopscotch .CodeMirror-cursor {border-left: 1px solid #989498 !important;}

.cm-s-hopscotch span.cm-comment {color: #b33508;}
.cm-s-hopscotch span.cm-atom {color: #c85e7c;}
.cm-s-hopscotch span.cm-number {color: #c85e7c;}

.cm-s-hopscotch span.cm-property, .cm-s-hopscotch span.cm-attribute {color: #8fc13e;}
.cm-s-hopscotch span.cm-keyword {color: #dd464c;}
.cm-s-hopscotch span.cm-string {color: #fdcc59;}

.cm-s-hopscotch span.cm-variable {color: #8fc13e;}
.cm-s-hopscotch span.cm-variable-2 {color: #1290bf;}
.cm-s-hopscotch span.cm-def {color: #fd8b19;}
.cm-s-hopscotch span.cm-error {background: #dd464c; color: #989498;}
.cm-s-hopscotch span.cm-bracket {color: #d5d3d5;}
.cm-s-hopscotch span.cm-tag {color: #dd464c;}
.cm-s-hopscotch span.cm-link {color: #c85e7c;}

.cm-s-hopscotch .CodeMirror-matchingbracket { text-decoration: underline; color: white !important;}
.cm-s-hopscotch .CodeMirror-activeline-background { background: #302020; }

/****************************************************************/
/*   Based on mbonaci's Brackets mbo theme                      */
/*   https://github.com/mbonaci/global/blob/master/Mbo.tmTheme  */
/*   Create your own: http://tmtheme-editor.herokuapp.com       */
/****************************************************************/

.cm-s-mbo.CodeMirror { background: #2c2c2c; color: #ffffec; }
.cm-s-mbo div.CodeMirror-selected { background: #716C62; }
.cm-s-mbo .CodeMirror-line::selection, .cm-s-mbo .CodeMirror-line > span::selection, .cm-s-mbo .CodeMirror-line > span > span::selection { background: rgba(113, 108, 98, .99); }
.cm-s-mbo .CodeMirror-line::-moz-selection, .cm-s-mbo .CodeMirror-line > span::-moz-selection, .cm-s-mbo .CodeMirror-line > span > span::-moz-selection { background: rgba(113, 108, 98, .99); }
.cm-s-mbo .CodeMirror-gutters { background: #4e4e4e; border-right: 0px; }
.cm-s-mbo .CodeMirror-guttermarker { color: white; }
.cm-s-mbo .CodeMirror-guttermarker-subtle { color: grey; }
.cm-s-mbo .CodeMirror-linenumber { color: #dadada; }
.cm-s-mbo .CodeMirror-cursor { border-left: 1px solid #ffffec; }

.cm-s-mbo span.cm-comment { color: #95958a; }
.cm-s-mbo span.cm-atom { color: #00a8c6; }
.cm-s-mbo span.cm-number { color: #00a8c6; }

.cm-s-mbo span.cm-property, .cm-s-mbo span.cm-attribute { color: #9ddfe9; }
.cm-s-mbo span.cm-keyword { color: #ffb928; }
.cm-s-mbo span.cm-string { color: #ffcf6c; }
.cm-s-mbo span.cm-string.cm-property { color: #ffffec; }

.cm-s-mbo span.cm-variable { color: #ffffec; }
.cm-s-mbo span.cm-variable-2 { color: #00a8c6; }
.cm-s-mbo span.cm-def { color: #ffffec; }
.cm-s-mbo span.cm-bracket { color: #fffffc; font-weight: bold; }
.cm-s-mbo span.cm-tag { color: #9ddfe9; }
.cm-s-mbo span.cm-link { color: #f54b07; }
.cm-s-mbo span.cm-error { border-bottom: #636363; color: #ffffec; }
.cm-s-mbo span.cm-qualifier { color: #ffffec; }

.cm-s-mbo .CodeMirror-activeline-background { background: #494b41; }
.cm-s-mbo .CodeMirror-matchingbracket { color: #ffb928 !important; }
.cm-s-mbo .CodeMirror-matchingtag { background: rgba(255, 255, 255, .37); }

/*
  MDN-LIKE Theme - Mozilla
  Ported to CodeMirror by Peter Kroon <plakroon@gmail.com>
  Report bugs/issues here: https://github.com/codemirror/CodeMirror/issues
  GitHub: @peterkroon

  The mdn-like theme is inspired on the displayed code examples at: https://developer.mozilla.org/en-US/docs/Web/CSS/animation

*/
.cm-s-mdn-like.CodeMirror { color: #999; background-color: #fff; }
.cm-s-mdn-like div.CodeMirror-selected { background: #cfc; }
.cm-s-mdn-like .CodeMirror-line::selection, .cm-s-mdn-like .CodeMirror-line > span::selection, .cm-s-mdn-like .CodeMirror-line > span > span::selection { background: #cfc; }
.cm-s-mdn-like .CodeMirror-line::-moz-selection, .cm-s-mdn-like .CodeMirror-line > span::-moz-selection, .cm-s-mdn-like .CodeMirror-line > span > span::-moz-selection { background: #cfc; }

.cm-s-mdn-like .CodeMirror-gutters { background: #f8f8f8; border-left: 6px solid rgba(0,83,159,0.65); color: #333; }
.cm-s-mdn-like .CodeMirror-linenumber { color: #aaa; padding-left: 8px; }
.cm-s-mdn-like .CodeMirror-cursor { border-left: 2px solid #222; }

.cm-s-mdn-like .cm-keyword { color: #6262FF; }
.cm-s-mdn-like .cm-atom { color: #F90; }
.cm-s-mdn-like .cm-number { color:  #ca7841; }
.cm-s-mdn-like .cm-def { color: #8DA6CE; }
.cm-s-mdn-like span.cm-variable-2, .cm-s-mdn-like span.cm-tag { color: #690; }
.cm-s-mdn-like span.cm-variable-3, .cm-s-mdn-like span.cm-def, .cm-s-mdn-like span.cm-type { color: #07a; }

.cm-s-mdn-like .cm-variable { color: #07a; }
.cm-s-mdn-like .cm-property { color: #905; }
.cm-s-mdn-like .cm-qualifier { color: #690; }

.cm-s-mdn-like .cm-operator { color: #cda869; }
.cm-s-mdn-like .cm-comment { color:#777; font-weight:normal; }
.cm-s-mdn-like .cm-string { color:#07a; font-style:italic; }
.cm-s-mdn-like .cm-string-2 { color:#bd6b18; } /*?*/
.cm-s-mdn-like .cm-meta { color: #000; } /*?*/
.cm-s-mdn-like .cm-builtin { color: #9B7536; } /*?*/
.cm-s-mdn-like .cm-tag { color: #997643; }
.cm-s-mdn-like .cm-attribute { color: #d6bb6d; } /*?*/
.cm-s-mdn-like .cm-header { color: #FF6400; }
.cm-s-mdn-like .cm-hr { color: #AEAEAE; }
.cm-s-mdn-like .cm-link { color:#ad9361; font-style:italic; text-decoration:none; }
.cm-s-mdn-like .cm-error { border-bottom: 1px solid red; }

div.cm-s-mdn-like .CodeMirror-activeline-background { background: #efefff; }
div.cm-s-mdn-like span.CodeMirror-matchingbracket { outline:1px solid grey; color: inherit; }

.cm-s-mdn-like.CodeMirror { background-image: url(data:image/png;base64,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); }

/*

    Name:       seti
    Author:     Michael Kaminsky (http://github.com/mkaminsky11)

    Original seti color scheme by Jesse Weed (https://github.com/jesseweed/seti-syntax)

*/


.cm-s-seti.CodeMirror {
  background-color: #151718 !important;
  color: #CFD2D1 !important;
  border: none;
}
.cm-s-seti .CodeMirror-gutters {
  color: #404b53;
  background-color: #0E1112;
  border: none;
}
.cm-s-seti .CodeMirror-cursor { border-left: solid thin #f8f8f0; }
.cm-s-seti .CodeMirror-linenumber { color: #6D8A88; }
.cm-s-seti.CodeMirror-focused div.CodeMirror-selected { background: rgba(255, 255, 255, 0.10); }
.cm-s-seti .CodeMirror-line::selection, .cm-s-seti .CodeMirror-line > span::selection, .cm-s-seti .CodeMirror-line > span > span::selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-seti .CodeMirror-line::-moz-selection, .cm-s-seti .CodeMirror-line > span::-moz-selection, .cm-s-seti .CodeMirror-line > span > span::-moz-selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-seti span.cm-comment { color: #41535b; }
.cm-s-seti span.cm-string, .cm-s-seti span.cm-string-2 { color: #55b5db; }
.cm-s-seti span.cm-number { color: #cd3f45; }
.cm-s-seti span.cm-variable { color: #55b5db; }
.cm-s-seti span.cm-variable-2 { color: #a074c4; }
.cm-s-seti span.cm-def { color: #55b5db; }
.cm-s-seti span.cm-keyword { color: #ff79c6; }
.cm-s-seti span.cm-operator { color: #9fca56; }
.cm-s-seti span.cm-keyword { color: #e6cd69; }
.cm-s-seti span.cm-atom { color: #cd3f45; }
.cm-s-seti span.cm-meta { color: #55b5db; }
.cm-s-seti span.cm-tag { color: #55b5db; }
.cm-s-seti span.cm-attribute { color: #9fca56; }
.cm-s-seti span.cm-qualifier { color: #9fca56; }
.cm-s-seti span.cm-property { color: #a074c4; }
.cm-s-seti span.cm-variable-3, .cm-s-seti span.cm-type { color: #9fca56; }
.cm-s-seti span.cm-builtin { color: #9fca56; }
.cm-s-seti .CodeMirror-activeline-background { background: #101213; }
.cm-s-seti .CodeMirror-matchingbracket { text-decoration: underline; color: white !important; }

/*
Solarized theme for code-mirror
http://ethanschoonover.com/solarized
*/

/*
Solarized color palette
http://ethanschoonover.com/solarized/img/solarized-palette.png
*/

.solarized.base03 { color: #002b36; }
.solarized.base02 { color: #073642; }
.solarized.base01 { color: #586e75; }
.solarized.base00 { color: #657b83; }
.solarized.base0 { color: #839496; }
.solarized.base1 { color: #93a1a1; }
.solarized.base2 { color: #eee8d5; }
.solarized.base3  { color: #fdf6e3; }
.solarized.solar-yellow  { color: #b58900; }
.solarized.solar-orange  { color: #cb4b16; }
.solarized.solar-red { color: #dc322f; }
.solarized.solar-magenta { color: #d33682; }
.solarized.solar-violet  { color: #6c71c4; }
.solarized.solar-blue { color: #268bd2; }
.solarized.solar-cyan { color: #2aa198; }
.solarized.solar-green { color: #859900; }

/* Color scheme for code-mirror */

.cm-s-solarized {
  line-height: 1.45em;
  color-profile: sRGB;
  rendering-intent: auto;
}
.cm-s-solarized.cm-s-dark {
  color: #839496;
  background-color: #002b36;
  text-shadow: #002b36 0 1px;
}
.cm-s-solarized.cm-s-light {
  background-color: #fdf6e3;
  color: #657b83;
  text-shadow: #eee8d5 0 1px;
}

.cm-s-solarized .CodeMirror-widget {
  text-shadow: none;
}

.cm-s-solarized .cm-header { color: #586e75; }
.cm-s-solarized .cm-quote { color: #93a1a1; }

.cm-s-solarized .cm-keyword { color: #cb4b16; }
.cm-s-solarized .cm-atom { color: #d33682; }
.cm-s-solarized .cm-number { color: #d33682; }
.cm-s-solarized .cm-def { color: #2aa198; }

.cm-s-solarized .cm-variable { color: #839496; }
.cm-s-solarized .cm-variable-2 { color: #b58900; }
.cm-s-solarized .cm-variable-3, .cm-s-solarized .cm-type { color: #6c71c4; }

.cm-s-solarized .cm-property { color: #2aa198; }
.cm-s-solarized .cm-operator { color: #6c71c4; }

.cm-s-solarized .cm-comment { color: #586e75; font-style:italic; }

.cm-s-solarized .cm-string { color: #859900; }
.cm-s-solarized .cm-string-2 { color: #b58900; }

.cm-s-solarized .cm-meta { color: #859900; }
.cm-s-solarized .cm-qualifier { color: #b58900; }
.cm-s-solarized .cm-builtin { color: #d33682; }
.cm-s-solarized .cm-bracket { color: #cb4b16; }
.cm-s-solarized .CodeMirror-matchingbracket { color: #859900; }
.cm-s-solarized .CodeMirror-nonmatchingbracket { color: #dc322f; }
.cm-s-solarized .cm-tag { color: #93a1a1; }
.cm-s-solarized .cm-attribute { color: #2aa198; }
.cm-s-solarized .cm-hr {
  color: transparent;
  border-top: 1px solid #586e75;
  display: block;
}
.cm-s-solarized .cm-link { color: #93a1a1; cursor: pointer; }
.cm-s-solarized .cm-special { color: #6c71c4; }
.cm-s-solarized .cm-em {
  color: #999;
  text-decoration: underline;
  text-decoration-style: dotted;
}
.cm-s-solarized .cm-error,
.cm-s-solarized .cm-invalidchar {
  color: #586e75;
  border-bottom: 1px dotted #dc322f;
}

.cm-s-solarized.cm-s-dark div.CodeMirror-selected { background: #073642; }
.cm-s-solarized.cm-s-dark.CodeMirror ::selection { background: rgba(7, 54, 66, 0.99); }
.cm-s-solarized.cm-s-dark .CodeMirror-line::-moz-selection, .cm-s-dark .CodeMirror-line > span::-moz-selection, .cm-s-dark .CodeMirror-line > span > span::-moz-selection { background: rgba(7, 54, 66, 0.99); }

.cm-s-solarized.cm-s-light div.CodeMirror-selected { background: #eee8d5; }
.cm-s-solarized.cm-s-light .CodeMirror-line::selection, .cm-s-light .CodeMirror-line > span::selection, .cm-s-light .CodeMirror-line > span > span::selection { background: #eee8d5; }
.cm-s-solarized.cm-s-light .CodeMirror-line::-moz-selection, .cm-s-ligh .CodeMirror-line > span::-moz-selection, .cm-s-ligh .CodeMirror-line > span > span::-moz-selection { background: #eee8d5; }

/* Editor styling */



/* Little shadow on the view-port of the buffer view */
.cm-s-solarized.CodeMirror {
  -moz-box-shadow: inset 7px 0 12px -6px #000;
  -webkit-box-shadow: inset 7px 0 12px -6px #000;
  box-shadow: inset 7px 0 12px -6px #000;
}

/* Remove gutter border */
.cm-s-solarized .CodeMirror-gutters {
  border-right: 0;
}

/* Gutter colors and line number styling based of color scheme (dark / light) */

/* Dark */
.cm-s-solarized.cm-s-dark .CodeMirror-gutters {
  background-color: #073642;
}

.cm-s-solarized.cm-s-dark .CodeMirror-linenumber {
  color: #586e75;
  text-shadow: #021014 0 -1px;
}

/* Light */
.cm-s-solarized.cm-s-light .CodeMirror-gutters {
  background-color: #eee8d5;
}

.cm-s-solarized.cm-s-light .CodeMirror-linenumber {
  color: #839496;
}

/* Common */
.cm-s-solarized .CodeMirror-linenumber {
  padding: 0 5px;
}
.cm-s-solarized .CodeMirror-guttermarker-subtle { color: #586e75; }
.cm-s-solarized.cm-s-dark .CodeMirror-guttermarker { color: #ddd; }
.cm-s-solarized.cm-s-light .CodeMirror-guttermarker { color: #cb4b16; }

.cm-s-solarized .CodeMirror-gutter .CodeMirror-gutter-text {
  color: #586e75;
}

/* Cursor */
.cm-s-solarized .CodeMirror-cursor { border-left: 1px solid #819090; }

/* Fat cursor */
.cm-s-solarized.cm-s-light.cm-fat-cursor .CodeMirror-cursor { background: #77ee77; }
.cm-s-solarized.cm-s-light .cm-animate-fat-cursor { background-color: #77ee77; }
.cm-s-solarized.cm-s-dark.cm-fat-cursor .CodeMirror-cursor { background: #586e75; }
.cm-s-solarized.cm-s-dark .cm-animate-fat-cursor { background-color: #586e75; }

/* Active line */
.cm-s-solarized.cm-s-dark .CodeMirror-activeline-background {
  background: rgba(255, 255, 255, 0.06);
}
.cm-s-solarized.cm-s-light .CodeMirror-activeline-background {
  background: rgba(0, 0, 0, 0.06);
}

.cm-s-the-matrix.CodeMirror { background: #000000; color: #00FF00; }
.cm-s-the-matrix div.CodeMirror-selected { background: #2D2D2D; }
.cm-s-the-matrix .CodeMirror-line::selection, .cm-s-the-matrix .CodeMirror-line > span::selection, .cm-s-the-matrix .CodeMirror-line > span > span::selection { background: rgba(45, 45, 45, 0.99); }
.cm-s-the-matrix .CodeMirror-line::-moz-selection, .cm-s-the-matrix .CodeMirror-line > span::-moz-selection, .cm-s-the-matrix .CodeMirror-line > span > span::-moz-selection { background: rgba(45, 45, 45, 0.99); }
.cm-s-the-matrix .CodeMirror-gutters { background: #060; border-right: 2px solid #00FF00; }
.cm-s-the-matrix .CodeMirror-guttermarker { color: #0f0; }
.cm-s-the-matrix .CodeMirror-guttermarker-subtle { color: white; }
.cm-s-the-matrix .CodeMirror-linenumber { color: #FFFFFF; }
.cm-s-the-matrix .CodeMirror-cursor { border-left: 1px solid #00FF00; }

.cm-s-the-matrix span.cm-keyword { color: #008803; font-weight: bold; }
.cm-s-the-matrix span.cm-atom { color: #3FF; }
.cm-s-the-matrix span.cm-number { color: #FFB94F; }
.cm-s-the-matrix span.cm-def { color: #99C; }
.cm-s-the-matrix span.cm-variable { color: #F6C; }
.cm-s-the-matrix span.cm-variable-2 { color: #C6F; }
.cm-s-the-matrix span.cm-variable-3, .cm-s-the-matrix span.cm-type { color: #96F; }
.cm-s-the-matrix span.cm-property { color: #62FFA0; }
.cm-s-the-matrix span.cm-operator { color: #999; }
.cm-s-the-matrix span.cm-comment { color: #CCCCCC; }
.cm-s-the-matrix span.cm-string { color: #39C; }
.cm-s-the-matrix span.cm-meta { color: #C9F; }
.cm-s-the-matrix span.cm-qualifier { color: #FFF700; }
.cm-s-the-matrix span.cm-builtin { color: #30a; }
.cm-s-the-matrix span.cm-bracket { color: #cc7; }
.cm-s-the-matrix span.cm-tag { color: #FFBD40; }
.cm-s-the-matrix span.cm-attribute { color: #FFF700; }
.cm-s-the-matrix span.cm-error { color: #FF0000; }

.cm-s-the-matrix .CodeMirror-activeline-background { background: #040; }

/*
Copyright (C) 2011 by MarkLogic Corporation
Author: Mike Brevoort <mike@brevoort.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
*/
.cm-s-xq-light span.cm-keyword { line-height: 1em; font-weight: bold; color: #5A5CAD; }
.cm-s-xq-light span.cm-atom { color: #6C8CD5; }
.cm-s-xq-light span.cm-number { color: #164; }
.cm-s-xq-light span.cm-def { text-decoration:underline; }
.cm-s-xq-light span.cm-variable { color: black; }
.cm-s-xq-light span.cm-variable-2 { color:black; }
.cm-s-xq-light span.cm-variable-3, .cm-s-xq-light span.cm-type { color: black; }
.cm-s-xq-light span.cm-property {}
.cm-s-xq-light span.cm-operator {}
.cm-s-xq-light span.cm-comment { color: #0080FF; font-style: italic; }
.cm-s-xq-light span.cm-string { color: red; }
.cm-s-xq-light span.cm-meta { color: yellow; }
.cm-s-xq-light span.cm-qualifier { color: grey; }
.cm-s-xq-light span.cm-builtin { color: #7EA656; }
.cm-s-xq-light span.cm-bracket { color: #cc7; }
.cm-s-xq-light span.cm-tag { color: #3F7F7F; }
.cm-s-xq-light span.cm-attribute { color: #7F007F; }
.cm-s-xq-light span.cm-error { color: #f00; }

.cm-s-xq-light .CodeMirror-activeline-background { background: #e8f2ff; }
.cm-s-xq-light .CodeMirror-matchingbracket { outline:1px solid grey;color:black !important;background:yellow; }

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.CodeMirror {
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  border: 0;
  border-radius: 0;
  height: auto;
  /* Changed to auto to autogrow */
}

.CodeMirror pre {
  padding: 0 var(--jp-code-padding);
}

.jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-dialog {
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

/* This causes https://github.com/jupyter/jupyterlab/issues/522 */
/* May not cause it not because we changed it! */
.CodeMirror-lines {
  padding: var(--jp-code-padding) 0;
}

.CodeMirror-linenumber {
  padding: 0 8px;
}

.jp-CodeMirrorEditor-static {
  margin: var(--jp-code-padding);
}

.jp-CodeMirrorEditor,
.jp-CodeMirrorEditor-static {
  cursor: text;
}

.jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
  border-left: var(--jp-code-cursor-width0) solid var(--jp-editor-cursor-color);
}

/* When zoomed out 67% and 33% on a screen of 1440 width x 900 height */
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
    border-left: var(--jp-code-cursor-width1) solid
      var(--jp-editor-cursor-color);
  }
}

/* When zoomed out less than 33% */
@media screen and (min-width: 4320px) {
  .jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
    border-left: var(--jp-code-cursor-width2) solid
      var(--jp-editor-cursor-color);
  }
}

.CodeMirror.jp-mod-readOnly .CodeMirror-cursor {
  display: none;
}

.CodeMirror-gutters {
  border-right: 1px solid var(--jp-border-color2);
  background-color: var(--jp-layout-color0);
}

.jp-CollaboratorCursor {
  border-left: 5px solid transparent;
  border-right: 5px solid transparent;
  border-top: none;
  border-bottom: 3px solid;
  background-clip: content-box;
  margin-left: -5px;
  margin-right: -5px;
}

.CodeMirror-selectedtext.cm-searching {
  background-color: var(--jp-search-selected-match-background-color) !important;
  color: var(--jp-search-selected-match-color) !important;
}

.cm-searching {
  background-color: var(
    --jp-search-unselected-match-background-color
  ) !important;
  color: var(--jp-search-unselected-match-color) !important;
}

.CodeMirror-focused .CodeMirror-selected {
  background-color: var(--jp-editor-selected-focused-background);
}

.CodeMirror-selected {
  background-color: var(--jp-editor-selected-background);
}

.jp-CollaboratorCursor-hover {
  position: absolute;
  z-index: 1;
  transform: translateX(-50%);
  color: white;
  border-radius: 3px;
  padding-left: 4px;
  padding-right: 4px;
  padding-top: 1px;
  padding-bottom: 1px;
  text-align: center;
  font-size: var(--jp-ui-font-size1);
  white-space: nowrap;
}

.jp-CodeMirror-ruler {
  border-left: 1px dashed var(--jp-border-color2);
}

/**
 * Here is our jupyter theme for CodeMirror syntax highlighting
 * This is used in our marked.js syntax highlighting and CodeMirror itself
 * The string "jupyter" is set in ../codemirror/widget.DEFAULT_CODEMIRROR_THEME
 * This came from the classic notebook, which came form highlight.js/GitHub
 */

/**
 * CodeMirror themes are handling the background/color in this way. This works
 * fine for CodeMirror editors outside the notebook, but the notebook styles
 * these things differently.
 */
.CodeMirror.cm-s-jupyter {
  background: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

/* In the notebook, we want this styling to be handled by its container */
.jp-CodeConsole .CodeMirror.cm-s-jupyter,
.jp-Notebook .CodeMirror.cm-s-jupyter {
  background: transparent;
}

.cm-s-jupyter .CodeMirror-cursor {
  border-left: var(--jp-code-cursor-width0) solid var(--jp-editor-cursor-color);
}
.cm-s-jupyter span.cm-keyword {
  color: var(--jp-mirror-editor-keyword-color);
  font-weight: bold;
}
.cm-s-jupyter span.cm-atom {
  color: var(--jp-mirror-editor-atom-color);
}
.cm-s-jupyter span.cm-number {
  color: var(--jp-mirror-editor-number-color);
}
.cm-s-jupyter span.cm-def {
  color: var(--jp-mirror-editor-def-color);
}
.cm-s-jupyter span.cm-variable {
  color: var(--jp-mirror-editor-variable-color);
}
.cm-s-jupyter span.cm-variable-2 {
  color: var(--jp-mirror-editor-variable-2-color);
}
.cm-s-jupyter span.cm-variable-3 {
  color: var(--jp-mirror-editor-variable-3-color);
}
.cm-s-jupyter span.cm-punctuation {
  color: var(--jp-mirror-editor-punctuation-color);
}
.cm-s-jupyter span.cm-property {
  color: var(--jp-mirror-editor-property-color);
}
.cm-s-jupyter span.cm-operator {
  color: var(--jp-mirror-editor-operator-color);
  font-weight: bold;
}
.cm-s-jupyter span.cm-comment {
  color: var(--jp-mirror-editor-comment-color);
  font-style: italic;
}
.cm-s-jupyter span.cm-string {
  color: var(--jp-mirror-editor-string-color);
}
.cm-s-jupyter span.cm-string-2 {
  color: var(--jp-mirror-editor-string-2-color);
}
.cm-s-jupyter span.cm-meta {
  color: var(--jp-mirror-editor-meta-color);
}
.cm-s-jupyter span.cm-qualifier {
  color: var(--jp-mirror-editor-qualifier-color);
}
.cm-s-jupyter span.cm-builtin {
  color: var(--jp-mirror-editor-builtin-color);
}
.cm-s-jupyter span.cm-bracket {
  color: var(--jp-mirror-editor-bracket-color);
}
.cm-s-jupyter span.cm-tag {
  color: var(--jp-mirror-editor-tag-color);
}
.cm-s-jupyter span.cm-attribute {
  color: var(--jp-mirror-editor-attribute-color);
}
.cm-s-jupyter span.cm-header {
  color: var(--jp-mirror-editor-header-color);
}
.cm-s-jupyter span.cm-quote {
  color: var(--jp-mirror-editor-quote-color);
}
.cm-s-jupyter span.cm-link {
  color: var(--jp-mirror-editor-link-color);
}
.cm-s-jupyter span.cm-error {
  color: var(--jp-mirror-editor-error-color);
}
.cm-s-jupyter span.cm-hr {
  color: #999;
}

.cm-s-jupyter span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}

.cm-s-jupyter .CodeMirror-activeline-background,
.cm-s-jupyter .CodeMirror-gutter {
  background-color: var(--jp-layout-color2);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| RenderedText
|----------------------------------------------------------------------------*/

.jp-RenderedText {
  text-align: left;
  padding-left: var(--jp-code-padding);
  line-height: var(--jp-code-line-height);
  font-family: var(--jp-code-font-family);
}

.jp-RenderedText pre,
.jp-RenderedJavaScript pre,
.jp-RenderedHTMLCommon pre {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-code-font-size);
  border: none;
  margin: 0px;
  padding: 0px;
  line-height: normal;
}

.jp-RenderedText pre a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}
.jp-RenderedText pre a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}
.jp-RenderedText pre a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* console foregrounds and backgrounds */
.jp-RenderedText pre .ansi-black-fg {
  color: #3e424d;
}
.jp-RenderedText pre .ansi-red-fg {
  color: #e75c58;
}
.jp-RenderedText pre .ansi-green-fg {
  color: #00a250;
}
.jp-RenderedText pre .ansi-yellow-fg {
  color: #ddb62b;
}
.jp-RenderedText pre .ansi-blue-fg {
  color: #208ffb;
}
.jp-RenderedText pre .ansi-magenta-fg {
  color: #d160c4;
}
.jp-RenderedText pre .ansi-cyan-fg {
  color: #60c6c8;
}
.jp-RenderedText pre .ansi-white-fg {
  color: #c5c1b4;
}

.jp-RenderedText pre .ansi-black-bg {
  background-color: #3e424d;
}
.jp-RenderedText pre .ansi-red-bg {
  background-color: #e75c58;
}
.jp-RenderedText pre .ansi-green-bg {
  background-color: #00a250;
}
.jp-RenderedText pre .ansi-yellow-bg {
  background-color: #ddb62b;
}
.jp-RenderedText pre .ansi-blue-bg {
  background-color: #208ffb;
}
.jp-RenderedText pre .ansi-magenta-bg {
  background-color: #d160c4;
}
.jp-RenderedText pre .ansi-cyan-bg {
  background-color: #60c6c8;
}
.jp-RenderedText pre .ansi-white-bg {
  background-color: #c5c1b4;
}

.jp-RenderedText pre .ansi-black-intense-fg {
  color: #282c36;
}
.jp-RenderedText pre .ansi-red-intense-fg {
  color: #b22b31;
}
.jp-RenderedText pre .ansi-green-intense-fg {
  color: #007427;
}
.jp-RenderedText pre .ansi-yellow-intense-fg {
  color: #b27d12;
}
.jp-RenderedText pre .ansi-blue-intense-fg {
  color: #0065ca;
}
.jp-RenderedText pre .ansi-magenta-intense-fg {
  color: #a03196;
}
.jp-RenderedText pre .ansi-cyan-intense-fg {
  color: #258f8f;
}
.jp-RenderedText pre .ansi-white-intense-fg {
  color: #a1a6b2;
}

.jp-RenderedText pre .ansi-black-intense-bg {
  background-color: #282c36;
}
.jp-RenderedText pre .ansi-red-intense-bg {
  background-color: #b22b31;
}
.jp-RenderedText pre .ansi-green-intense-bg {
  background-color: #007427;
}
.jp-RenderedText pre .ansi-yellow-intense-bg {
  background-color: #b27d12;
}
.jp-RenderedText pre .ansi-blue-intense-bg {
  background-color: #0065ca;
}
.jp-RenderedText pre .ansi-magenta-intense-bg {
  background-color: #a03196;
}
.jp-RenderedText pre .ansi-cyan-intense-bg {
  background-color: #258f8f;
}
.jp-RenderedText pre .ansi-white-intense-bg {
  background-color: #a1a6b2;
}

.jp-RenderedText pre .ansi-default-inverse-fg {
  color: var(--jp-ui-inverse-font-color0);
}
.jp-RenderedText pre .ansi-default-inverse-bg {
  background-color: var(--jp-inverse-layout-color0);
}

.jp-RenderedText pre .ansi-bold {
  font-weight: bold;
}
.jp-RenderedText pre .ansi-underline {
  text-decoration: underline;
}

.jp-RenderedText[data-mime-type='application/vnd.jupyter.stderr'] {
  background: var(--jp-rendermime-error-background);
  padding-top: var(--jp-code-padding);
}

/*-----------------------------------------------------------------------------
| RenderedLatex
|----------------------------------------------------------------------------*/

.jp-RenderedLatex {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
}

/* Left-justify outputs.*/
.jp-OutputArea-output.jp-RenderedLatex {
  padding: var(--jp-code-padding);
  text-align: left;
}

/*-----------------------------------------------------------------------------
| RenderedHTML
|----------------------------------------------------------------------------*/

.jp-RenderedHTMLCommon {
  color: var(--jp-content-font-color1);
  font-family: var(--jp-content-font-family);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
  /* Give a bit more R padding on Markdown text to keep line lengths reasonable */
  padding-right: 20px;
}

.jp-RenderedHTMLCommon em {
  font-style: italic;
}

.jp-RenderedHTMLCommon strong {
  font-weight: bold;
}

.jp-RenderedHTMLCommon u {
  text-decoration: underline;
}

.jp-RenderedHTMLCommon a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* Headings */

.jp-RenderedHTMLCommon h1,
.jp-RenderedHTMLCommon h2,
.jp-RenderedHTMLCommon h3,
.jp-RenderedHTMLCommon h4,
.jp-RenderedHTMLCommon h5,
.jp-RenderedHTMLCommon h6 {
  line-height: var(--jp-content-heading-line-height);
  font-weight: var(--jp-content-heading-font-weight);
  font-style: normal;
  margin: var(--jp-content-heading-margin-top) 0
    var(--jp-content-heading-margin-bottom) 0;
}

.jp-RenderedHTMLCommon h1:first-child,
.jp-RenderedHTMLCommon h2:first-child,
.jp-RenderedHTMLCommon h3:first-child,
.jp-RenderedHTMLCommon h4:first-child,
.jp-RenderedHTMLCommon h5:first-child,
.jp-RenderedHTMLCommon h6:first-child {
  margin-top: calc(0.5 * var(--jp-content-heading-margin-top));
}

.jp-RenderedHTMLCommon h1:last-child,
.jp-RenderedHTMLCommon h2:last-child,
.jp-RenderedHTMLCommon h3:last-child,
.jp-RenderedHTMLCommon h4:last-child,
.jp-RenderedHTMLCommon h5:last-child,
.jp-RenderedHTMLCommon h6:last-child {
  margin-bottom: calc(0.5 * var(--jp-content-heading-margin-bottom));
}

.jp-RenderedHTMLCommon h1 {
  font-size: var(--jp-content-font-size5);
}

.jp-RenderedHTMLCommon h2 {
  font-size: var(--jp-content-font-size4);
}

.jp-RenderedHTMLCommon h3 {
  font-size: var(--jp-content-font-size3);
}

.jp-RenderedHTMLCommon h4 {
  font-size: var(--jp-content-font-size2);
}

.jp-RenderedHTMLCommon h5 {
  font-size: var(--jp-content-font-size1);
}

.jp-RenderedHTMLCommon h6 {
  font-size: var(--jp-content-font-size0);
}

/* Lists */

.jp-RenderedHTMLCommon ul:not(.list-inline),
.jp-RenderedHTMLCommon ol:not(.list-inline) {
  padding-left: 2em;
}

.jp-RenderedHTMLCommon ul {
  list-style: disc;
}

.jp-RenderedHTMLCommon ul ul {
  list-style: square;
}

.jp-RenderedHTMLCommon ul ul ul {
  list-style: circle;
}

.jp-RenderedHTMLCommon ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol ol {
  list-style: upper-alpha;
}

.jp-RenderedHTMLCommon ol ol ol {
  list-style: lower-alpha;
}

.jp-RenderedHTMLCommon ol ol ol ol {
  list-style: lower-roman;
}

.jp-RenderedHTMLCommon ol ol ol ol ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol,
.jp-RenderedHTMLCommon ul {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon ul ul,
.jp-RenderedHTMLCommon ul ol,
.jp-RenderedHTMLCommon ol ul,
.jp-RenderedHTMLCommon ol ol {
  margin-bottom: 0em;
}

.jp-RenderedHTMLCommon hr {
  color: var(--jp-border-color2);
  background-color: var(--jp-border-color1);
  margin-top: 1em;
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon > pre {
  margin: 1.5em 2em;
}

.jp-RenderedHTMLCommon pre,
.jp-RenderedHTMLCommon code {
  border: 0;
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  line-height: var(--jp-code-line-height);
  padding: 0;
  white-space: pre-wrap;
}

.jp-RenderedHTMLCommon :not(pre) > code {
  background-color: var(--jp-layout-color2);
  padding: 1px 5px;
}

/* Tables */

.jp-RenderedHTMLCommon table {
  border-collapse: collapse;
  border-spacing: 0;
  border: none;
  color: var(--jp-ui-font-color1);
  font-size: 12px;
  table-layout: fixed;
  margin-left: auto;
  margin-right: auto;
}

.jp-RenderedHTMLCommon thead {
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  vertical-align: bottom;
}

.jp-RenderedHTMLCommon td,
.jp-RenderedHTMLCommon th,
.jp-RenderedHTMLCommon tr {
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}

.jp-RenderedMarkdown.jp-RenderedHTMLCommon td,
.jp-RenderedMarkdown.jp-RenderedHTMLCommon th {
  max-width: none;
}

:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon td,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon th,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon tr {
  text-align: right;
}

.jp-RenderedHTMLCommon th {
  font-weight: bold;
}

.jp-RenderedHTMLCommon tbody tr:nth-child(odd) {
  background: var(--jp-layout-color0);
}

.jp-RenderedHTMLCommon tbody tr:nth-child(even) {
  background: var(--jp-rendermime-table-row-background);
}

.jp-RenderedHTMLCommon tbody tr:hover {
  background: var(--jp-rendermime-table-row-hover-background);
}

.jp-RenderedHTMLCommon table {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon p {
  text-align: left;
  margin: 0px;
}

.jp-RenderedHTMLCommon p {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon img {
  -moz-force-broken-image-icon: 1;
}

/* Restrict to direct children as other images could be nested in other content. */
.jp-RenderedHTMLCommon > img {
  display: block;
  margin-left: 0;
  margin-right: 0;
  margin-bottom: 1em;
}

/* Change color behind transparent images if they need it... */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-light-background {
  background-color: var(--jp-inverse-layout-color1);
}
[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-dark-background {
  background-color: var(--jp-inverse-layout-color1);
}
/* ...or leave it untouched if they don't */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-dark-background {
}
[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-light-background {
}

.jp-RenderedHTMLCommon img,
.jp-RenderedImage img,
.jp-RenderedHTMLCommon svg,
.jp-RenderedSVG svg {
  max-width: 100%;
  height: auto;
}

.jp-RenderedHTMLCommon img.jp-mod-unconfined,
.jp-RenderedImage img.jp-mod-unconfined,
.jp-RenderedHTMLCommon svg.jp-mod-unconfined,
.jp-RenderedSVG svg.jp-mod-unconfined {
  max-width: none;
}

.jp-RenderedHTMLCommon .alert {
  padding: var(--jp-notebook-padding);
  border: var(--jp-border-width) solid transparent;
  border-radius: var(--jp-border-radius);
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon .alert-info {
  color: var(--jp-info-color0);
  background-color: var(--jp-info-color3);
  border-color: var(--jp-info-color2);
}
.jp-RenderedHTMLCommon .alert-info hr {
  border-color: var(--jp-info-color3);
}
.jp-RenderedHTMLCommon .alert-info > p:last-child,
.jp-RenderedHTMLCommon .alert-info > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-warning {
  color: var(--jp-warn-color0);
  background-color: var(--jp-warn-color3);
  border-color: var(--jp-warn-color2);
}
.jp-RenderedHTMLCommon .alert-warning hr {
  border-color: var(--jp-warn-color3);
}
.jp-RenderedHTMLCommon .alert-warning > p:last-child,
.jp-RenderedHTMLCommon .alert-warning > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-success {
  color: var(--jp-success-color0);
  background-color: var(--jp-success-color3);
  border-color: var(--jp-success-color2);
}
.jp-RenderedHTMLCommon .alert-success hr {
  border-color: var(--jp-success-color3);
}
.jp-RenderedHTMLCommon .alert-success > p:last-child,
.jp-RenderedHTMLCommon .alert-success > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-danger {
  color: var(--jp-error-color0);
  background-color: var(--jp-error-color3);
  border-color: var(--jp-error-color2);
}
.jp-RenderedHTMLCommon .alert-danger hr {
  border-color: var(--jp-error-color3);
}
.jp-RenderedHTMLCommon .alert-danger > p:last-child,
.jp-RenderedHTMLCommon .alert-danger > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon blockquote {
  margin: 1em 2em;
  padding: 0 1em;
  border-left: 5px solid var(--jp-border-color2);
}

a.jp-InternalAnchorLink {
  visibility: hidden;
  margin-left: 8px;
  color: var(--md-blue-800);
}

h1:hover .jp-InternalAnchorLink,
h2:hover .jp-InternalAnchorLink,
h3:hover .jp-InternalAnchorLink,
h4:hover .jp-InternalAnchorLink,
h5:hover .jp-InternalAnchorLink,
h6:hover .jp-InternalAnchorLink {
  visibility: visible;
}

.jp-RenderedHTMLCommon kbd {
  background-color: var(--jp-rendermime-table-row-background);
  border: 1px solid var(--jp-border-color0);
  border-bottom-color: var(--jp-border-color2);
  border-radius: 3px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
  display: inline-block;
  font-size: 0.8em;
  line-height: 1em;
  padding: 0.2em 0.5em;
}

/* Most direct children of .jp-RenderedHTMLCommon have a margin-bottom of 1.0.
 * At the bottom of cells this is a bit too much as there is also spacing
 * between cells. Going all the way to 0 gets too tight between markdown and
 * code cells.
 */
.jp-RenderedHTMLCommon > *:last-child {
  margin-bottom: 0.5em;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MimeDocument {
  outline: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-filebrowser-button-height: 28px;
  --jp-private-filebrowser-button-width: 48px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-FileBrowser {
  display: flex;
  flex-direction: column;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  border-bottom: none;
  height: auto;
  margin: var(--jp-toolbar-header-margin);
  box-shadow: none;
}

.jp-BreadCrumbs {
  flex: 0 0 auto;
  margin: 4px 12px;
}

.jp-BreadCrumbs-item {
  margin: 0px 2px;
  padding: 0px 2px;
  border-radius: var(--jp-border-radius);
  cursor: pointer;
}

.jp-BreadCrumbs-item:hover {
  background-color: var(--jp-layout-color2);
}

.jp-BreadCrumbs-item:first-child {
  margin-left: 0px;
}

.jp-BreadCrumbs-item.jp-mod-dropTarget {
  background-color: var(--jp-brand-color2);
  opacity: 0.7;
}

/*-----------------------------------------------------------------------------
| Buttons
|----------------------------------------------------------------------------*/

.jp-FileBrowser-toolbar.jp-Toolbar {
  padding: 0px;
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  justify-content: space-evenly;
}

.jp-FileBrowser-toolbar.jp-Toolbar .jp-Toolbar-item {
  flex: 1;
}

.jp-FileBrowser-toolbar.jp-Toolbar .jp-ToolbarButtonComponent {
  width: 100%;
}

/*-----------------------------------------------------------------------------
| DirListing
|----------------------------------------------------------------------------*/

.jp-DirListing {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
  outline: 0;
}

.jp-DirListing-header {
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  overflow: hidden;
  border-top: var(--jp-border-width) solid var(--jp-border-color2);
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  box-shadow: var(--jp-toolbar-box-shadow);
  z-index: 2;
}

.jp-DirListing-headerItem {
  padding: 4px 12px 2px 12px;
  font-weight: 500;
}

.jp-DirListing-headerItem:hover {
  background: var(--jp-layout-color2);
}

.jp-DirListing-headerItem.jp-id-name {
  flex: 1 0 84px;
}

.jp-DirListing-headerItem.jp-id-modified {
  flex: 0 0 112px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
}

.jp-DirListing-narrow .jp-id-modified,
.jp-DirListing-narrow .jp-DirListing-itemModified {
  display: none;
}

.jp-DirListing-headerItem.jp-mod-selected {
  font-weight: 600;
}

/* increase specificity to override bundled default */
.jp-DirListing-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

/* Style the directory listing content when a user drops a file to upload */
.jp-DirListing.jp-mod-native-drop .jp-DirListing-content {
  outline: 5px dashed rgba(128, 128, 128, 0.5);
  outline-offset: -10px;
  cursor: copy;
}

.jp-DirListing-item {
  display: flex;
  flex-direction: row;
  padding: 4px 12px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-DirListing-item.jp-mod-selected {
  color: white;
  background: var(--jp-brand-color1);
}

.jp-DirListing-item.jp-mod-dropTarget {
  background: var(--jp-brand-color3);
}

.jp-DirListing-item:hover:not(.jp-mod-selected) {
  background: var(--jp-layout-color2);
}

.jp-DirListing-itemIcon {
  flex: 0 0 20px;
  margin-right: 4px;
}

.jp-DirListing-itemText {
  flex: 1 0 64px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  user-select: none;
}

.jp-DirListing-itemModified {
  flex: 0 0 125px;
  text-align: right;
}

.jp-DirListing-editor {
  flex: 1 0 64px;
  outline: none;
  border: none;
}

.jp-DirListing-item.jp-mod-running .jp-DirListing-itemIcon:before {
  color: limegreen;
  content: '\25CF';
  font-size: 8px;
  position: absolute;
  left: -8px;
}

.jp-DirListing-item.lm-mod-drag-image,
.jp-DirListing-item.jp-mod-selected.lm-mod-drag-image {
  font-size: var(--jp-ui-font-size1);
  padding-left: 4px;
  margin-left: 4px;
  width: 160px;
  background-color: var(--jp-ui-inverse-font-color2);
  box-shadow: var(--jp-elevation-z2);
  border-radius: 0px;
  color: var(--jp-ui-font-color1);
  transform: translateX(-40%) translateY(-58%);
}

.jp-DirListing-deadSpace {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

.jp-Document {
  min-width: 120px;
  min-height: 120px;
  outline: none;
}

.jp-FileDialog.jp-mod-conflict input {
  color: red;
}

.jp-FileDialog .jp-new-name-title {
  margin-top: 12px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
}

/*-----------------------------------------------------------------------------
| Main OutputArea
| OutputArea has a list of Outputs
|----------------------------------------------------------------------------*/

.jp-OutputArea {
  overflow-y: auto;
}

.jp-OutputArea-child {
  display: flex;
  flex-direction: row;
}

.jp-OutputPrompt {
  flex: 0 0 var(--jp-cell-prompt-width);
  color: var(--jp-cell-outprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);
  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-OutputArea-output {
  height: auto;
  overflow: auto;
  user-select: text;
  -moz-user-select: text;
  -webkit-user-select: text;
  -ms-user-select: text;
}

.jp-OutputArea-child .jp-OutputArea-output {
  flex-grow: 1;
  flex-shrink: 1;
}

/**
 * Isolated output.
 */
.jp-OutputArea-output.jp-mod-isolated {
  width: 100%;
  display: block;
}

/*
When drag events occur, `p-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated {
  position: relative;
}

body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/* pre */

.jp-OutputArea-output pre {
  border: none;
  margin: 0px;
  padding: 0px;
  overflow-x: auto;
  overflow-y: auto;
  word-break: break-all;
  word-wrap: break-word;
  white-space: pre-wrap;
}

/* tables */

.jp-OutputArea-output.jp-RenderedHTMLCommon table {
  margin-left: 0;
  margin-right: 0;
}

/* description lists */

.jp-OutputArea-output dl,
.jp-OutputArea-output dt,
.jp-OutputArea-output dd {
  display: block;
}

.jp-OutputArea-output dl {
  width: 100%;
  overflow: hidden;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dt {
  font-weight: bold;
  float: left;
  width: 20%;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dd {
  float: left;
  width: 80%;
  padding: 0;
  margin: 0;
}

/* Hide the gutter in case of
 *  - nested output areas (e.g. in the case of output widgets)
 *  - mirrored output areas
 */
.jp-OutputArea .jp-OutputArea .jp-OutputArea-prompt {
  display: none;
}

/*-----------------------------------------------------------------------------
| executeResult is added to any Output-result for the display of the object
| returned by a cell
|----------------------------------------------------------------------------*/

.jp-OutputArea-output.jp-OutputArea-executeResult {
  margin-left: 0px;
  flex: 1 1 auto;
}

.jp-OutputArea-executeResult.jp-RenderedText {
  padding-top: var(--jp-code-padding);
}

/*-----------------------------------------------------------------------------
| The Stdin output
|----------------------------------------------------------------------------*/

.jp-OutputArea-stdin {
  line-height: var(--jp-code-line-height);
  padding-top: var(--jp-code-padding);
  display: flex;
}

.jp-Stdin-prompt {
  color: var(--jp-content-font-color0);
  padding-right: var(--jp-code-padding);
  vertical-align: baseline;
  flex: 0 0 auto;
}

.jp-Stdin-input {
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  color: inherit;
  background-color: inherit;
  width: 42%;
  min-width: 200px;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
  flex: 0 0 70%;
}

.jp-Stdin-input:focus {
  box-shadow: none;
}

/*-----------------------------------------------------------------------------
| Output Area View
|----------------------------------------------------------------------------*/

.jp-LinkedOutputView .jp-OutputArea {
  height: 100%;
  display: block;
}

.jp-LinkedOutputView .jp-OutputArea-output:only-child {
  height: 100%;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapser {
  flex: 0 0 var(--jp-cell-collapser-width);
  padding: 0px;
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
  border-radius: var(--jp-border-radius);
  opacity: 1;
}

.jp-Collapser-child {
  display: block;
  width: 100%;
  box-sizing: border-box;
  /* height: 100% doesn't work because the height of its parent is computed from content */
  position: absolute;
  top: 0px;
  bottom: 0px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Header/Footer
|----------------------------------------------------------------------------*/

/* Hidden by zero height by default */
.jp-CellHeader,
.jp-CellFooter {
  height: 0px;
  width: 100%;
  padding: 0px;
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Input
|----------------------------------------------------------------------------*/

/* All input areas */
.jp-InputArea {
  display: flex;
  flex-direction: row;
}

.jp-InputArea-editor {
  flex: 1 1 auto;
}

.jp-InputArea-editor {
  /* This is the non-active, default styling */
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  border-radius: 0px;
  background: var(--jp-cell-editor-background);
}

.jp-InputPrompt {
  flex: 0 0 var(--jp-cell-prompt-width);
  color: var(--jp-cell-inprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  opacity: var(--jp-cell-prompt-opacity);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);
  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Placeholder {
  display: flex;
  flex-direction: row;
  flex: 1 1 auto;
}

.jp-Placeholder-prompt {
  box-sizing: border-box;
}

.jp-Placeholder-content {
  flex: 1 1 auto;
  border: none;
  background: transparent;
  height: 20px;
  box-sizing: border-box;
}

.jp-Placeholder-content .jp-MoreHorizIcon {
  width: 32px;
  height: 16px;
  border: 1px solid transparent;
  border-radius: var(--jp-border-radius);
}

.jp-Placeholder-content .jp-MoreHorizIcon:hover {
  border: 1px solid var(--jp-border-color1);
  box-shadow: 0px 0px 2px 0px rgba(0, 0, 0, 0.25);
  background-color: var(--jp-layout-color0);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-cell-scrolling-output-offset: 5px;
}

/*-----------------------------------------------------------------------------
| Cell
|----------------------------------------------------------------------------*/

.jp-Cell {
  padding: var(--jp-cell-padding);
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Common input/output
|----------------------------------------------------------------------------*/

.jp-Cell-inputWrapper,
.jp-Cell-outputWrapper {
  display: flex;
  flex-direction: row;
  padding: 0px;
  margin: 0px;
  /* Added to reveal the box-shadow on the input and output collapsers. */
  overflow: visible;
}

/* Only input/output areas inside cells */
.jp-Cell-inputArea,
.jp-Cell-outputArea {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Collapser
|----------------------------------------------------------------------------*/

/* Make the output collapser disappear when there is not output, but do so
 * in a manner that leaves it in the layout and preserves its width.
 */
.jp-Cell.jp-mod-noOutputs .jp-Cell-outputCollapser {
  border: none !important;
  background: transparent !important;
}

.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputCollapser {
  min-height: var(--jp-cell-collapser-min-height);
}

/*-----------------------------------------------------------------------------
| Output
|----------------------------------------------------------------------------*/

/* Put a space between input and output when there IS output */
.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputWrapper {
  margin-top: 5px;
}

/* Text output with the Out[] prompt needs a top padding to match the
 * alignment of the Out[] prompt itself.
 */
.jp-OutputArea-executeResult .jp-RenderedText.jp-OutputArea-output {
  padding-top: var(--jp-code-padding);
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea {
  overflow-y: auto;
  max-height: 200px;
  box-shadow: inset 0 0 6px 2px rgba(0, 0, 0, 0.3);
  margin-left: var(--jp-private-cell-scrolling-output-offset);
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-prompt {
  flex: 0 0
    calc(
      var(--jp-cell-prompt-width) -
        var(--jp-private-cell-scrolling-output-offset)
    );
}

/*-----------------------------------------------------------------------------
| CodeCell
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| MarkdownCell
|----------------------------------------------------------------------------*/

.jp-MarkdownOutput {
  flex: 1 1 auto;
  margin-top: 0;
  margin-bottom: 0;
  padding-left: var(--jp-code-padding);
}

.jp-MarkdownOutput.jp-RenderedHTMLCommon {
  overflow: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-NotebookPanel-toolbar {
  padding: 2px;
}

.jp-Toolbar-item.jp-Notebook-toolbarCellType .jp-select-wrapper.jp-mod-focused {
  border: none;
  box-shadow: none;
}

.jp-Notebook-toolbarCellTypeDropdown select {
  height: 24px;
  font-size: var(--jp-ui-font-size1);
  line-height: 14px;
  border-radius: 0;
  display: block;
}

.jp-Notebook-toolbarCellTypeDropdown span {
  top: 5px !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-notebook-dragImage-width: 304px;
  --jp-private-notebook-dragImage-height: 36px;
  --jp-private-notebook-selected-color: var(--md-blue-400);
  --jp-private-notebook-active-color: var(--md-green-400);
}

/*-----------------------------------------------------------------------------
| Imports
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Notebook
|----------------------------------------------------------------------------*/

.jp-NotebookPanel {
  display: block;
  height: 100%;
}

.jp-NotebookPanel.jp-Document {
  min-width: 240px;
  min-height: 120px;
}

.jp-Notebook {
  padding: var(--jp-notebook-padding);
  outline: none;
  overflow: auto;
  background: var(--jp-layout-color0);
}

.jp-Notebook.jp-mod-scrollPastEnd::after {
  display: block;
  content: '';
  min-height: var(--jp-notebook-scroll-padding);
}

.jp-Notebook .jp-Cell {
  overflow: visible;
}

.jp-Notebook .jp-Cell .jp-InputPrompt {
  cursor: move;
}

/*-----------------------------------------------------------------------------
| Notebook state related styling
|
| The notebook and cells each have states, here are the possibilities:
|
| - Notebook
|   - Command
|   - Edit
| - Cell
|   - None
|   - Active (only one can be active)
|   - Selected (the cells actions are applied to)
|   - Multiselected (when multiple selected, the cursor)
|   - No outputs
|----------------------------------------------------------------------------*/

/* Command or edit modes */

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-InputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-OutputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

/* cell is active */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser {
  background: var(--jp-brand-color1);
}

/* collapser is hovered */
.jp-Notebook .jp-Cell .jp-Collapser:hover {
  box-shadow: var(--jp-elevation-z2);
  background: var(--jp-brand-color1);
  opacity: var(--jp-cell-collapser-not-active-hover-opacity);
}

/* cell is active and collapser is hovered */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser:hover {
  background: var(--jp-brand-color0);
  opacity: 1;
}

/* Command mode */

.jp-Notebook.jp-mod-commandMode .jp-Cell.jp-mod-selected {
  background: var(--jp-notebook-multiselected-color);
}

.jp-Notebook.jp-mod-commandMode
  .jp-Cell.jp-mod-active.jp-mod-selected:not(.jp-mod-multiSelected) {
  background: transparent;
}

/* Edit mode */

.jp-Notebook.jp-mod-editMode .jp-Cell.jp-mod-active .jp-InputArea-editor {
  border: var(--jp-border-width) solid var(--jp-cell-editor-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-cell-editor-active-background);
}

/*-----------------------------------------------------------------------------
| Notebook drag and drop
|----------------------------------------------------------------------------*/

.jp-Notebook-cell.jp-mod-dropSource {
  opacity: 0.5;
}

.jp-Notebook-cell.jp-mod-dropTarget,
.jp-Notebook.jp-mod-commandMode
  .jp-Notebook-cell.jp-mod-active.jp-mod-selected.jp-mod-dropTarget {
  border-top-color: var(--jp-private-notebook-selected-color);
  border-top-style: solid;
  border-top-width: 2px;
}

.jp-dragImage {
  display: flex;
  flex-direction: row;
  width: var(--jp-private-notebook-dragImage-width);
  height: var(--jp-private-notebook-dragImage-height);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background);
  overflow: visible;
}

.jp-dragImage-singlePrompt {
  box-shadow: 2px 2px 4px 0px rgba(0, 0, 0, 0.12);
}

.jp-dragImage .jp-dragImage-content {
  flex: 1 1 auto;
  z-index: 2;
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  line-height: var(--jp-code-line-height);
  padding: var(--jp-code-padding);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background-color);
  color: var(--jp-content-font-color3);
  text-align: left;
  margin: 4px 4px 4px 0px;
}

.jp-dragImage .jp-dragImage-prompt {
  flex: 0 0 auto;
  min-width: 36px;
  color: var(--jp-cell-inprompt-font-color);
  padding: var(--jp-code-padding);
  padding-left: 12px;
  font-family: var(--jp-cell-prompt-font-family);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: 1.9;
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
}

.jp-dragImage-multipleBack {
  z-index: -1;
  position: absolute;
  height: 32px;
  width: 300px;
  top: 8px;
  left: 8px;
  background: var(--jp-layout-color2);
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  box-shadow: 2px 2px 4px 0px rgba(0, 0, 0, 0.12);
}

/*-----------------------------------------------------------------------------
| Cell toolbar
|----------------------------------------------------------------------------*/

.jp-NotebookTools {
  display: block;
  min-width: var(--jp-sidebar-min-width);
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
    * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  overflow: auto;
}

.jp-NotebookTools-tool {
  padding: 0px 12px 0 12px;
}

.jp-ActiveCellTool {
  padding: 12px;
  background-color: var(--jp-layout-color1);
  border-top: none !important;
}

.jp-ActiveCellTool .jp-InputArea-prompt {
  flex: 0 0 auto;
  padding-left: 0px;
}

.jp-ActiveCellTool .jp-InputArea-editor {
  flex: 1 1 auto;
  background: var(--jp-cell-editor-background);
  border-color: var(--jp-cell-editor-border-color);
}

.jp-ActiveCellTool .jp-InputArea-editor .CodeMirror {
  background: transparent;
}

.jp-MetadataEditorTool {
  flex-direction: column;
  padding: 12px 0px 12px 0px;
}

.jp-RankedPanel > :not(:first-child) {
  margin-top: 12px;
}

.jp-KeySelector select.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: var(--jp-border-width) solid var(--jp-border-color1);
}

.jp-KeySelector label,
.jp-MetadataEditorTool label {
  line-height: 1.4;
}

/*-----------------------------------------------------------------------------
| Presentation Mode (.jp-mod-presentationMode)
|----------------------------------------------------------------------------*/

.jp-mod-presentationMode .jp-Notebook {
  --jp-content-font-size1: var(--jp-content-presentation-font-size1);
  --jp-code-font-size: var(--jp-code-presentation-font-size);
}

.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-InputPrompt,
.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-OutputPrompt {
  flex: 0 0 110px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

</style>

    <style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
The following CSS variables define the main, public API for styling JupyterLab.
These variables should be used by all plugins wherever possible. In other
words, plugins should not define custom colors, sizes, etc unless absolutely
necessary. This enables users to change the visual theme of JupyterLab
by changing these variables.

Many variables appear in an ordered sequence (0,1,2,3). These sequences
are designed to work well together, so for example, `--jp-border-color1` should
be used with `--jp-layout-color1`. The numbers have the following meanings:

* 0: super-primary, reserved for special emphasis
* 1: primary, most important under normal situations
* 2: secondary, next most important under normal situations
* 3: tertiary, next most important under normal situations

Throughout JupyterLab, we are mostly following principles from Google's
Material Design when selecting colors. We are not, however, following
all of MD as it is not optimized for dense, information rich UIs.
*/

:root {
  /* Elevation
   *
   * We style box-shadows using Material Design's idea of elevation. These particular numbers are taken from here:
   *
   * https://github.com/material-components/material-components-web
   * https://material-components-web.appspot.com/elevation.html
   */

  --jp-shadow-base-lightness: 0;
  --jp-shadow-umbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.2
  );
  --jp-shadow-penumbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.14
  );
  --jp-shadow-ambient-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.12
  );
  --jp-elevation-z0: none;
  --jp-elevation-z1: 0px 2px 1px -1px var(--jp-shadow-umbra-color),
    0px 1px 1px 0px var(--jp-shadow-penumbra-color),
    0px 1px 3px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z2: 0px 3px 1px -2px var(--jp-shadow-umbra-color),
    0px 2px 2px 0px var(--jp-shadow-penumbra-color),
    0px 1px 5px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z4: 0px 2px 4px -1px var(--jp-shadow-umbra-color),
    0px 4px 5px 0px var(--jp-shadow-penumbra-color),
    0px 1px 10px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z6: 0px 3px 5px -1px var(--jp-shadow-umbra-color),
    0px 6px 10px 0px var(--jp-shadow-penumbra-color),
    0px 1px 18px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z8: 0px 5px 5px -3px var(--jp-shadow-umbra-color),
    0px 8px 10px 1px var(--jp-shadow-penumbra-color),
    0px 3px 14px 2px var(--jp-shadow-ambient-color);
  --jp-elevation-z12: 0px 7px 8px -4px var(--jp-shadow-umbra-color),
    0px 12px 17px 2px var(--jp-shadow-penumbra-color),
    0px 5px 22px 4px var(--jp-shadow-ambient-color);
  --jp-elevation-z16: 0px 8px 10px -5px var(--jp-shadow-umbra-color),
    0px 16px 24px 2px var(--jp-shadow-penumbra-color),
    0px 6px 30px 5px var(--jp-shadow-ambient-color);
  --jp-elevation-z20: 0px 10px 13px -6px var(--jp-shadow-umbra-color),
    0px 20px 31px 3px var(--jp-shadow-penumbra-color),
    0px 8px 38px 7px var(--jp-shadow-ambient-color);
  --jp-elevation-z24: 0px 11px 15px -7px var(--jp-shadow-umbra-color),
    0px 24px 38px 3px var(--jp-shadow-penumbra-color),
    0px 9px 46px 8px var(--jp-shadow-ambient-color);

  /* Borders
   *
   * The following variables, specify the visual styling of borders in JupyterLab.
   */

  --jp-border-width: 1px;
  --jp-border-color0: var(--md-grey-400);
  --jp-border-color1: var(--md-grey-400);
  --jp-border-color2: var(--md-grey-300);
  --jp-border-color3: var(--md-grey-200);
  --jp-border-radius: 2px;

  /* UI Fonts
   *
   * The UI font CSS variables are used for the typography all of the JupyterLab
   * user interface elements that are not directly user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-ui-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-ui-font-scale-factor: 1.2;
  --jp-ui-font-size0: 0.83333em;
  --jp-ui-font-size1: 13px; /* Base font size */
  --jp-ui-font-size2: 1.2em;
  --jp-ui-font-size3: 1.44em;

  --jp-ui-font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica,
    Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol';

  /*
   * Use these font colors against the corresponding main layout colors.
   * In a light theme, these go from dark to light.
   */

  /* Defaults use Material Design specification */
  --jp-ui-font-color0: rgba(0, 0, 0, 1);
  --jp-ui-font-color1: rgba(0, 0, 0, 0.87);
  --jp-ui-font-color2: rgba(0, 0, 0, 0.54);
  --jp-ui-font-color3: rgba(0, 0, 0, 0.38);

  /*
   * Use these against the brand/accent/warn/error colors.
   * These will typically go from light to darker, in both a dark and light theme.
   */

  --jp-ui-inverse-font-color0: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color1: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color2: rgba(255, 255, 255, 0.7);
  --jp-ui-inverse-font-color3: rgba(255, 255, 255, 0.5);

  /* Content Fonts
   *
   * Content font variables are used for typography of user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-content-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-content-line-height: 1.6;
  --jp-content-font-scale-factor: 1.2;
  --jp-content-font-size0: 0.83333em;
  --jp-content-font-size1: 14px; /* Base font size */
  --jp-content-font-size2: 1.2em;
  --jp-content-font-size3: 1.44em;
  --jp-content-font-size4: 1.728em;
  --jp-content-font-size5: 2.0736em;

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-content-presentation-font-size1: 17px;

  --jp-content-heading-line-height: 1;
  --jp-content-heading-margin-top: 1.2em;
  --jp-content-heading-margin-bottom: 0.8em;
  --jp-content-heading-font-weight: 500;

  /* Defaults use Material Design specification */
  --jp-content-font-color0: rgba(0, 0, 0, 1);
  --jp-content-font-color1: rgba(0, 0, 0, 0.87);
  --jp-content-font-color2: rgba(0, 0, 0, 0.54);
  --jp-content-font-color3: rgba(0, 0, 0, 0.38);

  --jp-content-link-color: var(--md-blue-700);

  --jp-content-font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji',
    'Segoe UI Symbol';

  /*
   * Code Fonts
   *
   * Code font variables are used for typography of code and other monospaces content.
   */

  --jp-code-font-size: 13px;
  --jp-code-line-height: 1.3077; /* 17px for 13px base */
  --jp-code-padding: 5px; /* 5px for 13px base, codemirror highlighting needs integer px value */
  --jp-code-font-family-default: Menlo, Consolas, 'DejaVu Sans Mono', monospace;
  --jp-code-font-family: var(--jp-code-font-family-default);

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-code-presentation-font-size: 16px;

  /* may need to tweak cursor width if you change font size */
  --jp-code-cursor-width0: 1.4px;
  --jp-code-cursor-width1: 2px;
  --jp-code-cursor-width2: 4px;

  /* Layout
   *
   * The following are the main layout colors use in JupyterLab. In a light
   * theme these would go from light to dark.
   */

  --jp-layout-color0: white;
  --jp-layout-color1: white;
  --jp-layout-color2: var(--md-grey-200);
  --jp-layout-color3: var(--md-grey-400);
  --jp-layout-color4: var(--md-grey-600);

  /* Inverse Layout
   *
   * The following are the inverse layout colors use in JupyterLab. In a light
   * theme these would go from dark to light.
   */

  --jp-inverse-layout-color0: #111111;
  --jp-inverse-layout-color1: var(--md-grey-900);
  --jp-inverse-layout-color2: var(--md-grey-800);
  --jp-inverse-layout-color3: var(--md-grey-700);
  --jp-inverse-layout-color4: var(--md-grey-600);

  /* Brand/accent */

  --jp-brand-color0: var(--md-blue-700);
  --jp-brand-color1: var(--md-blue-500);
  --jp-brand-color2: var(--md-blue-300);
  --jp-brand-color3: var(--md-blue-100);
  --jp-brand-color4: var(--md-blue-50);

  --jp-accent-color0: var(--md-green-700);
  --jp-accent-color1: var(--md-green-500);
  --jp-accent-color2: var(--md-green-300);
  --jp-accent-color3: var(--md-green-100);

  /* State colors (warn, error, success, info) */

  --jp-warn-color0: var(--md-orange-700);
  --jp-warn-color1: var(--md-orange-500);
  --jp-warn-color2: var(--md-orange-300);
  --jp-warn-color3: var(--md-orange-100);

  --jp-error-color0: var(--md-red-700);
  --jp-error-color1: var(--md-red-500);
  --jp-error-color2: var(--md-red-300);
  --jp-error-color3: var(--md-red-100);

  --jp-success-color0: var(--md-green-700);
  --jp-success-color1: var(--md-green-500);
  --jp-success-color2: var(--md-green-300);
  --jp-success-color3: var(--md-green-100);

  --jp-info-color0: var(--md-cyan-700);
  --jp-info-color1: var(--md-cyan-500);
  --jp-info-color2: var(--md-cyan-300);
  --jp-info-color3: var(--md-cyan-100);

  /* Cell specific styles */

  --jp-cell-padding: 5px;

  --jp-cell-collapser-width: 8px;
  --jp-cell-collapser-min-height: 20px;
  --jp-cell-collapser-not-active-hover-opacity: 0.6;

  --jp-cell-editor-background: var(--md-grey-100);
  --jp-cell-editor-border-color: var(--md-grey-300);
  --jp-cell-editor-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-cell-editor-active-background: var(--jp-layout-color0);
  --jp-cell-editor-active-border-color: var(--jp-brand-color1);

  --jp-cell-prompt-width: 64px;
  --jp-cell-prompt-font-family: 'Source Code Pro', monospace;
  --jp-cell-prompt-letter-spacing: 0px;
  --jp-cell-prompt-opacity: 1;
  --jp-cell-prompt-not-active-opacity: 0.5;
  --jp-cell-prompt-not-active-font-color: var(--md-grey-700);
  /* A custom blend of MD grey and blue 600
   * See https://meyerweb.com/eric/tools/color-blend/#546E7A:1E88E5:5:hex */
  --jp-cell-inprompt-font-color: #307fc1;
  /* A custom blend of MD grey and orange 600
   * https://meyerweb.com/eric/tools/color-blend/#546E7A:F4511E:5:hex */
  --jp-cell-outprompt-font-color: #bf5b3d;

  /* Notebook specific styles */

  --jp-notebook-padding: 10px;
  --jp-notebook-select-background: var(--jp-layout-color1);
  --jp-notebook-multiselected-color: var(--md-blue-50);

  /* The scroll padding is calculated to fill enough space at the bottom of the
  notebook to show one single-line cell (with appropriate padding) at the top
  when the notebook is scrolled all the way to the bottom. We also subtract one
  pixel so that no scrollbar appears if we have just one single-line cell in the
  notebook. This padding is to enable a 'scroll past end' feature in a notebook.
  */
  --jp-notebook-scroll-padding: calc(
    100% - var(--jp-code-font-size) * var(--jp-code-line-height) -
      var(--jp-code-padding) - var(--jp-cell-padding) - 1px
  );

  /* Rendermime styles */

  --jp-rendermime-error-background: #fdd;
  --jp-rendermime-table-row-background: var(--md-grey-100);
  --jp-rendermime-table-row-hover-background: var(--md-light-blue-50);

  /* Dialog specific styles */

  --jp-dialog-background: rgba(0, 0, 0, 0.25);

  /* Console specific styles */

  --jp-console-padding: 10px;

  /* Toolbar specific styles */

  --jp-toolbar-border-color: var(--jp-border-color1);
  --jp-toolbar-micro-height: 8px;
  --jp-toolbar-background: var(--jp-layout-color1);
  --jp-toolbar-box-shadow: 0px 0px 2px 0px rgba(0, 0, 0, 0.24);
  --jp-toolbar-header-margin: 4px 4px 0px 4px;
  --jp-toolbar-active-background: var(--md-grey-300);

  /* Input field styles */

  --jp-input-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-input-active-background: var(--jp-layout-color1);
  --jp-input-hover-background: var(--jp-layout-color1);
  --jp-input-background: var(--md-grey-100);
  --jp-input-border-color: var(--jp-border-color1);
  --jp-input-active-border-color: var(--jp-brand-color1);
  --jp-input-active-box-shadow-color: rgba(19, 124, 189, 0.3);

  /* General editor styles */

  --jp-editor-selected-background: #d9d9d9;
  --jp-editor-selected-focused-background: #d7d4f0;
  --jp-editor-cursor-color: var(--jp-ui-font-color0);

  /* Code mirror specific styles */

  --jp-mirror-editor-keyword-color: #008000;
  --jp-mirror-editor-atom-color: #88f;
  --jp-mirror-editor-number-color: #080;
  --jp-mirror-editor-def-color: #00f;
  --jp-mirror-editor-variable-color: var(--md-grey-900);
  --jp-mirror-editor-variable-2-color: #05a;
  --jp-mirror-editor-variable-3-color: #085;
  --jp-mirror-editor-punctuation-color: #05a;
  --jp-mirror-editor-property-color: #05a;
  --jp-mirror-editor-operator-color: #aa22ff;
  --jp-mirror-editor-comment-color: #408080;
  --jp-mirror-editor-string-color: #ba2121;
  --jp-mirror-editor-string-2-color: #708;
  --jp-mirror-editor-meta-color: #aa22ff;
  --jp-mirror-editor-qualifier-color: #555;
  --jp-mirror-editor-builtin-color: #008000;
  --jp-mirror-editor-bracket-color: #997;
  --jp-mirror-editor-tag-color: #170;
  --jp-mirror-editor-attribute-color: #00c;
  --jp-mirror-editor-header-color: blue;
  --jp-mirror-editor-quote-color: #090;
  --jp-mirror-editor-link-color: #00c;
  --jp-mirror-editor-error-color: #f00;
  --jp-mirror-editor-hr-color: #999;

  /* Vega extension styles */

  --jp-vega-background: white;

  /* Sidebar-related styles */

  --jp-sidebar-min-width: 180px;

  /* Search-related styles */

  --jp-search-toggle-off-opacity: 0.5;
  --jp-search-toggle-hover-opacity: 0.8;
  --jp-search-toggle-on-opacity: 1;
  --jp-search-selected-match-background-color: rgb(245, 200, 0);
  --jp-search-selected-match-color: black;
  --jp-search-unselected-match-background-color: var(
    --jp-inverse-layout-color0
  );
  --jp-search-unselected-match-color: var(--jp-ui-inverse-font-color0);

  /* Icon colors that work well with light or dark backgrounds */
  --jp-icon-contrast-color0: var(--md-purple-600);
  --jp-icon-contrast-color1: var(--md-green-600);
  --jp-icon-contrast-color2: var(--md-pink-600);
  --jp-icon-contrast-color3: var(--md-blue-600);
}
</style>

<style type="text/css">
a.anchor-link {
   display: none;
}
.highlight  {
    margin: 0.4em;
}

/* Input area styling */
.jp-InputArea {
    overflow: hidden;
}

.jp-InputArea-editor {
    overflow: hidden;
}

@media print {
  body {
    margin: 0;
  }
}
</style>



<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/latest.js?config=TeX-MML-AM_CHTML-full,Safe"> </script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    init_mathjax = function() {
        if (window.MathJax) {
        // MathJax loaded
            MathJax.Hub.Config({
                TeX: {
                    equationNumbers: {
                    autoNumber: "AMS",
                    useLabelIds: true
                    }
                },
                tex2jax: {
                    inlineMath: [ ['$','$'], ["\\(","\\)"] ],
                    displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
                    processEscapes: true,
                    processEnvironments: true
                },
                displayAlign: 'center',
                CommonHTML: {
                    linebreaks: { 
                    automatic: true 
                    }
                },
                "HTML-CSS": {
                    linebreaks: { 
                    automatic: true 
                    }
                }
            });
        
            MathJax.Hub.Queue(["Typeset", MathJax.Hub]);
        }
    }
    init_mathjax();
    </script>
    <!-- End of mathjax configuration --></head>
<body class="jp-Notebook" data-jp-theme-light="true" data-jp-theme-name="JupyterLab Light">

<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>In my last blog I discussed xxx in Python Pandas. Today I am going to looking at visualisations in Pandas.</p>
<p>I will focus on using Pandas to create visualisations but will also touch on other libraries.</p>
<p>Visualising your date is key as it is hard to get meaning from a table of data. As they say "a picture is worth a thousand words."</p>
<p>Also once your dataset gets big there is really no other way to get a true sense of the data without aggregation, which loses detail.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Lets-make-some-data">Lets make some data<a class="anchor-link" href="#Lets-make-some-data">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="n">df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">random</span><span class="o">.</span><span class="n">randint</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">100</span><span class="p">,</span><span class="n">size</span><span class="o">=</span><span class="p">(</span><span class="mi">100</span><span class="p">,</span> <span class="mi">3</span><span class="p">)),</span> <span class="n">columns</span><span class="o">=</span><span class="nb">list</span><span class="p">(</span><span class="s1">&#39;ABC&#39;</span><span class="p">))</span>
<span class="n">df2</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">random</span><span class="o">.</span><span class="n">choice</span><span class="p">(</span><span class="n">a</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;A&#39;</span><span class="p">,</span> <span class="s1">&#39;B&#39;</span><span class="p">,</span> <span class="s1">&#39;C&#39;</span><span class="p">,</span> <span class="s1">&#39;D&#39;</span><span class="p">],</span><span class="n">size</span><span class="o">=</span><span class="p">(</span><span class="mi">100</span><span class="p">,</span><span class="mi">2</span><span class="p">)),</span> <span class="n">columns</span><span class="o">=</span><span class="nb">list</span><span class="p">(</span><span class="s1">&#39;DE&#39;</span><span class="p">))</span>
<span class="c1"># join df and df2</span>
<span class="n">df3</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">concat</span><span class="p">([</span><span class="n">df</span><span class="p">,</span><span class="n">df2</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">df3</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
      <th>E</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>21</td>
      <td>46</td>
      <td>37</td>
      <td>A</td>
      <td>D</td>
    </tr>
    <tr>
      <th>1</th>
      <td>31</td>
      <td>15</td>
      <td>7</td>
      <td>D</td>
      <td>C</td>
    </tr>
    <tr>
      <th>2</th>
      <td>29</td>
      <td>60</td>
      <td>4</td>
      <td>B</td>
      <td>A</td>
    </tr>
    <tr>
      <th>3</th>
      <td>74</td>
      <td>68</td>
      <td>7</td>
      <td>C</td>
      <td>D</td>
    </tr>
    <tr>
      <th>4</th>
      <td>30</td>
      <td>76</td>
      <td>63</td>
      <td>D</td>
      <td>A</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>95</th>
      <td>35</td>
      <td>72</td>
      <td>17</td>
      <td>B</td>
      <td>B</td>
    </tr>
    <tr>
      <th>96</th>
      <td>6</td>
      <td>0</td>
      <td>30</td>
      <td>C</td>
      <td>A</td>
    </tr>
    <tr>
      <th>97</th>
      <td>92</td>
      <td>85</td>
      <td>8</td>
      <td>C</td>
      <td>D</td>
    </tr>
    <tr>
      <th>98</th>
      <td>80</td>
      <td>77</td>
      <td>47</td>
      <td>C</td>
      <td>A</td>
    </tr>
    <tr>
      <th>99</th>
      <td>72</td>
      <td>98</td>
      <td>54</td>
      <td>C</td>
      <td>C</td>
    </tr>
  </tbody>
</table>
<p>100 rows × 5 columns</p>
</div>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="df.plot">df.plot<a class="anchor-link" href="#df.plot">&#182;</a></h3>
</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>The most basic plot, using the plot() method with no parameters, in pandas gives you a line chart, using all continuous data series in the dataframe.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df3</span><span class="o">.</span><span class="n">plot</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;AxesSubplot:&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>We can use some parameters to change things up</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h4 id="Selecting-the-type-of-chart-using-kind=">Selecting the type of chart using kind=<a class="anchor-link" href="#Selecting-the-type-of-chart-using-kind=">&#182;</a></h4><p>Options include:-</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>‘line’ : line plot (default)</p>
<p>‘bar’ : vertical bar plot</p>
<p>‘barh’ : horizontal bar plot</p>
<p>‘hist’ : histogram</p>
<p>‘box’ : boxplot</p>
<p>‘kde’ : Kernel Density Estimation plot</p>
<p>‘density’ : same as ‘kde’</p>
<p>‘area’ : area plot</p>
<p>‘pie’ : pie plot</p>
<p>‘scatter’ : scatter plot (DataFrame only)</p>
<p>‘hexbin’ : hexbin plot (DataFrame only)</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Scatter">Scatter<a class="anchor-link" href="#Scatter">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df3</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;scatter&#39;</span><span class="p">,</span> <span class="n">x</span><span class="o">=</span><span class="s1">&#39;A&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;B&#39;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;AxesSubplot:xlabel=&#39;A&#39;, ylabel=&#39;B&#39;&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Bar-chart">Bar chart<a class="anchor-link" href="#Bar-chart">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df3</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;bar&#39;</span><span class="p">,</span> <span class="n">x</span><span class="o">=</span><span class="s1">&#39;D&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;A&#39;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;AxesSubplot:xlabel=&#39;D&#39;&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Histogram">Histogram<a class="anchor-link" href="#Histogram">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df3</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;hist&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;A&#39;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;AxesSubplot:ylabel=&#39;Frequency&#39;&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Box-plot">Box plot<a class="anchor-link" href="#Box-plot">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df3</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;box&#39;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;AxesSubplot:&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Other attributes of the plot() function that will be useful include:-</p>
<ul>
<li>title</li>
<li>figsize</li>
<li>xticks / yticks</li>
</ul>
<p>There are many many more which are powered by Matplotlib.</p>
<h4 id="Lets-try-figsize,-but-we-will-sort-the-data-by-column-A-first.">Lets try figsize, but we will sort the data by column A first.<a class="anchor-link" href="#Lets-try-figsize,-but-we-will-sort-the-data-by-column-A-first.">&#182;</a></h4>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df4</span> <span class="o">=</span> <span class="n">df3</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="s1">&#39;A&#39;</span><span class="p">,</span> <span class="n">ascending</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
<span class="n">df4</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;bar&#39;</span><span class="p">,</span> <span class="n">use_index</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;A&#39;</span><span class="p">,</span> <span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">20</span><span class="p">,</span><span class="mi">8</span><span class="p">))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;AxesSubplot:&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABIQAAAHVCAYAAACAOCDDAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjQuMywgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/MnkTPAAAACXBIWXMAAAsTAAALEwEAmpwYAAAu/ElEQVR4nO3de9hlWV0f+O+Camha7kUFCU3ztgISTIJip8GAIwHj01qGi6BBHWwYnM5EpE10EsokMwxOkikvA9HHxGdaLkKUBmwNTSy8IJcgmYh00w0NNghCAcVwaZu7ygi45o+9azh96rxv7XUu9Z6q9fk8z3nec/ZZZ5/fWWvtvdf5vfusXWqtAQAAAKAft9vvAAAAAAA4sySEAAAAADojIQQAAADQGQkhAAAAgM5ICAEAAAB0RkIIAAAAoDMH9juAJLnXve5Vd3Z29jsMAAAAgHPG9ddf/6e11kOLntuKhNDOzk6uu+66/Q4DAAAA4JxRSvngbs/5yRgAAABAZySEAAAAADojIQQAAADQma2YQwgAAABg23zxi1/MiRMn8oUvfGG/Q9nT+eefnwsvvDDnnXfe5NdICAEAAAAscOLEidzlLnfJzs5OSin7Hc5CtdbceuutOXHiRC6++OLJr/OTMQAAAIAFvvCFL+TgwYNbmwxKklJKDh482HwWk4QQAAAAwC62ORl00jIxSggBAAAAbLFXvepVKaXk3e9+99rWaQ4hAAAAgAl2jhxb6/qOHz08qdzVV1+dRz3qUbn66qvz3Oc+dy3v7QwhAAAAgC31+c9/Pm9+85vzwhe+MC9/+cvXtl4JIQAAAIAtde211+ayyy7Lgx70oBw8eDDXX3/9WtZ72oRQKeVFpZRPlFLeObPsnqWU15ZS3jv+vce4vJRSfr6U8r5SyjtKKQ9bS5QAAAAAHbr66qvzlKc8JUnylKc8JVdfffVa1jtlDqFfTvILSV46s+xIktfVWo+WUo6Mj5+d5DuSPHC8PTzJL45/AQAAAGjwyU9+Mq9//etz0003pZSSL3/5yyml5Gd+5mdWvvrZac8QqrW+Kckn5xY/PslLxvsvSfKEmeUvrYM/SHL3Usp9VooQAAAAoEPXXHNNnvrUp+aDH/xgjh8/ng9/+MO5+OKL8/u///srr3vZOYTuXWv96Hj/Y0nuPd6/b5IPz5Q7MS4DAAAAoMHVV1+dJz7xibdZ9qQnPWktPxtb+bLztdZaSqmtryulXJHkiiS56KKLVg0DAAAAYKOmXiZ+Xd7whjecsuzKK69cy7qXPUPo4yd/Cjb+/cS4/CNJ7jdT7sJx2SlqrVfVWi+ptV5y6NChJcMAAAAAoNWyCaFXJ7l8vH95kmtnlv/geLWxRyT5zMxPywAAAADYAqf9yVgp5eokj05yr1LKiSTPSXI0yStLKc9I8sEk3zsWf02S70zyviR/nuTpG4gZAAAAgBWcNiFUa/2+XZ567IKyNckzVwlo58ixU5ad6d/oAQAAACRJrXXlS7xv2pCOabPsT8YAAAAAzmnnn39+br311qUSLmdKrTW33nprzj///KbXrXyVMQAAAIBz0YUXXpgTJ07klltu2e9Q9nT++efnwgsvbHqNhBAAAADAAuedd14uvvji/Q5jI87qhNCi+YaSxXMOtZQFAAAAOJeZQwgAAACgMxJCAAAAAJ2REAIAAADozFk9h9CmtM43tKi8uYkAAACAbeUMIQAAAIDOSAgBAAAAdEZCCAAAAKAz5hA6w8w3BAAAAOw3ZwgBAAAAdEZCCAAAAKAzEkIAAAAAnZEQAgAAAOiMhBAAAABAZySEAAAAADojIQQAAADQGQkhAAAAgM5ICAEAAAB0RkIIAAAAoDMSQgAAAACdkRACAAAA6MyB/Q6A3e0cOXbKsuNHD+9DJAAAAMC5xBlCAAAAAJ2REAIAAADojIQQAAAAQGfMIXSOWDTfULJ4zqGWsgAAAMC5xxlCAAAAAJ2REAIAAADojIQQAAAAQGfMIcSezE0EAAAA5x5nCAEAAAB0RkIIAAAAoDMSQgAAAACdkRACAAAA6IxJpdk3iyahNgE1AAAAbJ4zhAAAAAA6IyEEAAAA0BkJIQAAAIDOmEOIs0LLfEOLyu5VHgAAAHrjDCEAAACAzkgIAQAAAHRGQggAAACgMxJCAAAAAJ2REAIAAADojIQQAAAAQGckhAAAAAA6IyEEAAAA0BkJIQAAAIDOSAgBAAAAdEZCCAAAAKAzB/Y7ANhPO0eOLVx+/OjhM1YWAAAAzjRnCAEAAAB0RkIIAAAAoDMSQgAAAACdkRACAAAA6IyEEAAAAEBnJIQAAAAAOiMhBAAAANAZCSEAAACAzhzY7wCAZOfIsVOWHT96eOWyAAAAsIgzhAAAAAA6IyEEAAAA0BkJIQAAAIDOSAgBAAAAdEZCCAAAAKAzEkIAAAAAnZEQAgAAAOiMhBAAAABAZySEAAAAADojIQQAAADQGQkhAAAAgM6slBAqpfzTUsq7SinvLKVcXUo5v5RycSnlLaWU95VSXlFKucO6ggUAAABgdUsnhEop901yZZJLaq1/M8ntkzwlyU8leX6t9QFJPpXkGesIFAAAAID1WPUnYweS3KmUciDJBUk+muQxSa4Zn39Jkies+B4AAAAArNHSCaFa60eS/GySD2VIBH0myfVJPl1r/dJY7ESS+64aJAAAAADrc2DZF5ZS7pHk8UkuTvLpJL+W5LKG11+R5Iokueiii5YNA9jDzpFjpyw7fvTwPkQCAADANlnlJ2PfluQDtdZbaq1fTPIbSR6Z5O7jT8iS5MIkH1n04lrrVbXWS2qtlxw6dGiFMAAAAABosUpC6ENJHlFKuaCUUpI8NskfJXlDkiePZS5Pcu1qIQIAAACwTqvMIfSWDJNHvy3JTeO6rkry7CQ/Vkp5X5KDSV64hjgBAAAAWJOl5xBKklrrc5I8Z27x+5Ncusp6AQAAANiclRJCwLlj0QTUiUmoAQAAzkWrzCEEAAAAwFlIQggAAACgMxJCAAAAAJ0xhxDQzHxDAAAAZzdnCAEAAAB0RkIIAAAAoDMSQgAAAACdkRACAAAA6IyEEAAAAEBnJIQAAAAAOiMhBAAAANCZA/sdAHBu2zlybOHy40cPn+FIAAAAOMkZQgAAAACdkRACAAAA6IyEEAAAAEBnzCEEbJVFcw6ZbwgAAGC9nCEEAAAA0BkJIQAAAIDOSAgBAAAAdMYcQsBZq2W+oVXL7lUeAADgbOMMIQAAAIDOSAgBAAAAdEZCCAAAAKAzEkIAAAAAnZEQAgAAAOiMhBAAAABAZySEAAAAADojIQQAAADQmQP7HQDA2WznyLGFy48fPbxSWQAAgE1yhhAAAABAZySEAAAAADojIQQAAADQGXMIAWypRXMOmW8IAABYB2cIAQAAAHRGQggAAACgMxJCAAAAAJ0xhxDAOaBlviFzEwEAAM4QAgAAAOiMhBAAAABAZySEAAAAADpjDiEAdrVovqHEnEMAAHC2c4YQAAAAQGckhAAAAAA6IyEEAAAA0BkJIQAAAIDOmFQagLVomYDaZNUAALC/nCEEAAAA0BkJIQAAAIDOSAgBAAAAdMYcQgBsNfMNAQDA+jlDCAAAAKAzEkIAAAAAnZEQAgAAAOiMOYQAOKcsmnNot/mGWsoCAMC5xBlCAAAAAJ2REAIAAADojIQQAAAAQGckhAAAAAA6IyEEAAAA0BkJIQAAAIDOSAgBAAAAdEZCCAAAAKAzEkIAAAAAnZEQAgAAAOiMhBAAAABAZySEAAAAADojIQQAAADQGQkhAAAAgM5ICAEAAAB0RkIIAAAAoDMH9jsAADgb7Bw5tnD58aOHz3AkAACwOmcIAQAAAHRGQggAAACgMxJCAAAAAJ1ZKSFUSrl7KeWaUsq7Syk3l1K+uZRyz1LKa0sp7x3/3mNdwQIAAACwulXPEPq5JL9da31wkocmuTnJkSSvq7U+MMnrxscAAAAAbImlE0KllLsl+e+SvDBJaq1/WWv9dJLHJ3nJWOwlSZ6wWogAAAAArNMqZwhdnOSWJC8updxQSnlBKeWrkty71vrRsczHktx71SABAAAAWJ9VEkIHkjwsyS/WWr8xyZ9l7udhtdaapC56cSnlilLKdaWU62655ZYVwgAAAACgxSoJoRNJTtRa3zI+viZDgujjpZT7JMn49xOLXlxrvarWekmt9ZJDhw6tEAYAAAAALZZOCNVaP5bkw6WUrxsXPTbJHyV5dZLLx2WXJ7l2pQgBAAAAWKsDK77+WUl+tZRyhyTvT/L0DEmmV5ZSnpHkg0m+d8X3AAAAAGCNVkoI1VpvTHLJgqceu8p6AQAAANicVeYQAgAAAOAsJCEEAAAA0BkJIQAAAIDOrDqpNAAwZ+fIsYXLjx89vFJZAABYF2cIAQAAAHRGQggAAACgMxJCAAAAAJ2REAIAAADojEmlAeAsYQJqAADWxRlCAAAAAJ2REAIAAADojIQQAAAAQGfMIQQA56hFcw6ZbwgAgMQZQgAAAADdkRACAAAA6IyEEAAAAEBnzCEEAJhvCACgM84QAgAAAOiMhBAAAABAZySEAAAAADojIQQAAADQGQkhAAAAgM5ICAEAAAB0RkIIAAAAoDMSQgAAAACdkRACAAAA6IyEEAAAAEBnJIQAAAAAOiMhBAAAANCZA/sdAABwdtk5cuyUZcePHt6HSAAAWJYzhAAAAAA6IyEEAAAA0BkJIQAAAIDOSAgBAAAAdEZCCAAAAKAzEkIAAAAAnZEQAgAAAOiMhBAAAABAZySEAAAAADojIQQAAADQGQkhAAAAgM5ICAEAAAB0RkIIAAAAoDMSQgAAAACdkRACAAAA6MyB/Q4AADh37Rw5tnD58aOHz3AkAADMcoYQAAAAQGckhAAAAAA6IyEEAAAA0BlzCAEAW6FlvqHWuYkWlTePEQDQM2cIAQAAAHRGQggAAACgMxJCAAAAAJ2REAIAAADojEmlAQBmtExAbbJqAOBs5QwhAAAAgM5ICAEAAAB0RkIIAAAAoDPmEAIAOAMWzTeUmHMIANgfzhACAAAA6IyEEAAAAEBnJIQAAAAAOmMOIQCALWO+IQBg05whBAAAANAZCSEAAACAzkgIAQAAAHTGHEIAAGex1vmGFpVfR1kA4OziDCEAAACAzkgIAQAAAHRGQggAAACgM+YQAgBgZeYbAoCzizOEAAAAADojIQQAAADQGQkhAAAAgM5ICAEAAAB0ZuVJpUspt09yXZKP1Fq/q5RycZKXJzmY5PokT621/uWq7wMAwLlh0QTUyeJJqFvKAgDTreMMoR9NcvPM459K8vxa6wOSfCrJM9bwHgAAAACsyUoJoVLKhUkOJ3nB+LgkeUySa8YiL0nyhFXeAwAAAID1WvUMoX+X5J8n+avx8cEkn661fml8fCLJfVd8DwAAAADWaOk5hEop35XkE7XW60spj17i9VckuSJJLrroomXDAACAJOYbAoAWq5wh9MgkjyulHM8wifRjkvxckruXUk4mmi5M8pFFL661XlVrvaTWesmhQ4dWCAMAAACAFksnhGqtP1FrvbDWupPkKUleX2v9gSRvSPLksdjlSa5dOUoAAAAA1mYdVxmb9+wkP1ZKeV+GOYVeuIH3AAAAAGBJS88hNKvW+sYkbxzvvz/JpetYLwAAAADrt4kzhAAAAADYYhJCAAAAAJ2REAIAAADozFrmEAIAgLPJzpFjC5cfP3r4DEcCAPvDGUIAAAAAnZEQAgAAAOiMhBAAAABAZySEAAAAADojIQQAAADQGQkhAAAAgM5ICAEAAAB0RkIIAAAAoDMSQgAAAACdkRACAAAA6IyEEAAAAEBnJIQAAAAAOnNgvwMAAIBtt3Pk2CnLjh89vHJZANgvzhACAAAA6IyEEAAAAEBnJIQAAAAAOmMOIQAA2CeL5htKFs851FIWAE7HGUIAAAAAnZEQAgAAAOiMhBAAAABAZ8whBAAA5xjzDQFwOs4QAgAAAOiMhBAAAABAZySEAAAAADpjDiEAAOiY+YYA+uQMIQAAAIDOSAgBAAAAdEZCCAAAAKAz5hACAAAmWzTnkPmGAM4+zhACAAAA6IyEEAAAAEBnJIQAAAAAOiMhBAAAANAZk0oDAAAb0TIB9apl9yoPwKmcIQQAAADQGQkhAAAAgM5ICAEAAAB0xhxCAADAOct8QwCLOUMIAAAAoDMSQgAAAACdkRACAAAA6IyEEAAAAEBnJIQAAAAAOiMhBAAAANAZCSEAAACAzkgIAQAAAHRGQggAAACgMxJCAAAAAJ2REAIAAADozIH9DgAAAGAb7Bw5tnD58aOHJ5ffrSzAtnGGEAAAAEBnJIQAAAAAOiMhBAAAANAZcwgBAABsmPmGgG3jDCEAAACAzkgIAQAAAHRGQggAAACgMxJCAAAAAJ0xqTQAAMAWaZmAelHZvcoDnOQMIQAAAIDOSAgBAAAAdEZCCAAAAKAz5hACAADoQMt8Q+YmgnOfM4QAAAAAOiMhBAAAANAZCSEAAACAzkgIAQAAAHRGQggAAACgMxJCAAAAAJ2REAIAAADozIFlX1hKuV+Slya5d5Ka5Kpa68+VUu6Z5BVJdpIcT/K9tdZPrR4qAAAA22jnyLFTlh0/enjlssDmrHKG0JeS/Hit9SFJHpHkmaWUhyQ5kuR1tdYHJnnd+BgAAACALbF0QqjW+tFa69vG+59LcnOS+yZ5fJKXjMVekuQJK8YIAAAAwBqtZQ6hUspOkm9M8pYk9661fnR86mMZflIGAAAAwJZYOSFUSrlzkl9P8k9qrZ+dfa7WWjPML7TodVeUUq4rpVx3yy23rBoGAAAAABOtlBAqpZyXIRn0q7XW3xgXf7yUcp/x+fsk+cSi19Zar6q1XlJrveTQoUOrhAEAAABAg6UTQqWUkuSFSW6utT5v5qlXJ7l8vH95kmuXDw8AAACAdVv6svNJHpnkqUluKqXcOC77F0mOJnllKeUZST6Y5HtXihAAAACAtVo6IVRrfXOSssvTj112vQAAAABs1ipnCAEAAMDG7Bw5dsqy40cP70MkcO5Zy2XnAQAAADh7SAgBAAAAdEZCCAAAAKAz5hACAADgrLdovqHEnEOwG2cIAQAAAHRGQggAAACgMxJCAAAAAJ0xhxAAAABdMd8QOEMIAAAAoDsSQgAAAACdkRACAAAA6Iw5hAAAAGAX5hviXOUMIQAAAIDOSAgBAAAAdEZCCAAAAKAzEkIAAAAAnZEQAgAAAOiMhBAAAABAZySEAAAAADpzYL8DAAAAgHPBzpFjC5cfP3r4DEcCp+cMIQAAAIDOSAgBAAAAdEZCCAAAAKAzEkIAAAAAnTGpNAAAAOyDRZNQ7zYB9apldytvIux+OUMIAAAAoDMSQgAAAACdkRACAAAA6Iw5hAAAAIDTMt/QucUZQgAAAACdkRACAAAA6IyEEAAAAEBnJIQAAAAAOiMhBAAAANAZCSEAAACAzkgIAQAAAHTmwH4HAAAAAJxbdo4cW7j8+NHDk8vvVpb1cIYQAAAAQGckhAAAAAA6IyEEAAAA0BlzCAEAAABnjZb5hsxNtDtnCAEAAAB0RkIIAAAAoDMSQgAAAACdkRACAAAA6IyEEAAAAEBnJIQAAAAAOiMhBAAAANAZCSEAAACAzkgIAQAAAHRGQggAAACgMxJCAAAAAJ2REAIAAADozIH9DgAAAABgv+0cObZw+fGjh1cqu62cIQQAAADQGQkhAAAAgM5ICAEAAAB0RkIIAAAAoDMSQgAAAACdkRACAAAA6IyEEAAAAEBnDux3AAAAAADnqp0jxxYuP3708BmO5LacIQQAAADQGQkhAAAAgM5ICAEAAAB0RkIIAAAAoDMSQgAAAACdkRACAAAA6IyEEAAAAEBnJIQAAAAAOnNgvwMAAAAAYLBz5Ngpy44fPbz293GGEAAAAEBnJIQAAAAAOiMhBAAAANCZjSSESimXlVLeU0p5XynlyCbeAwAAAIDlrD0hVEq5fZJ/n+Q7kjwkyfeVUh6y7vcBAAAAYDmbOEPo0iTvq7W+v9b6l0lenuTxG3gfAAAAAJawiYTQfZN8eObxiXEZAAAAAFug1FrXu8JSnpzkslrrD42Pn5rk4bXWH5krd0WSK8aHX5fkPQtWd68kfzrxrc/lstsSxzaU3ZY4tqHstsRxtpXdlji2oey2xLENZbcljm0ouy1xnG1ltyWObSi7LXFsQ9ltiWMbym5LHGdb2W2JYxvKbksc21B2W+LYhrLbEsc2l71/rfXQwlfUWtd6S/LNSX5n5vFPJPmJJdd1nbLbE8c2lN2WOLah7LbEcbaV3ZY4tqHstsSxDWW3JY5tKLstcZxtZbcljm0ouy1xbEPZbYljG8puSxxnW9ltiWMbym5LHNtQdlvi2Iay2xLH2Vb25G0TPxl7a5IHllIuLqXcIclTkrx6A+8DAAAAwBIOrHuFtdYvlVJ+JMnvJLl9khfVWt+17vcBAAAAYDlrTwglSa31NUles4ZVXaXsVsWxDWW3JY5tKLstcZxtZbcljm0ouy1xbEPZbYljG8puSxxnW9ltiWMbym5LHNtQdlvi2Iay2xLH2VZ2W+LYhrLbEsc2lN2WOLah7LbEcbaVTbKBSaUBAAAA2G6bmEMIAAAAgC0mIQQAAADQmY3MIbRNZq509v/UWn+vlPL9Sf5ukpuTXFVr/eK+BghsVCnl0iS11vrWUspDklyW5N3jXGfQvVLK1yT57iT3S/LlJH+c5GW11s/ua2B0oZTyqCSXJnlnrfV39zsetkMp5aW11h9c07oenOS+Sd5Sa/38zPLLaq2/vY736N1Yx4/PUM9J8pEkr6613rx/UXEuKqU8PMnNtdbPllLulORIkocl+aMk/7bW+pkV1n1lkv9Ua/3weqI9O5zzcwiVUn41Q+LrgiSfTnLnJL+R5LEZPv/lp3n9wVrrrZuOk2m2pT1a4iil/LVa6yc2HROnKqU8J8l3ZNgHvDbJw5O8IcnfT/I7tdZ/s4/hnXW2ZftjfcbBz3cleVOS70xyQ4Zj5ROT/HCt9Y37FhznpFLKH9ZaLx3v/49JnpnkPyX59iT/udZ6dD/j209n83ihlPL0WuuLl3ztq+cXJfl7SV6fJLXWx60Q15UZ+tjNSb4hyY/WWq8dn3tbrfVhy657FWdzW88rpTw7yfcleXmSE+PiCzP8Q/7lPW/TrF8p5V1JHjpe2fyqJH+e5JoM3+0fWmv97hXW/Zkkf5bkT5JcneTXaq23NLx+I+Pklv3FUvuWWuu+3zJ8WftHSX47yTvG228l+Z+SnLeg/N2SHE3y7iSfTHJrhh390SR3nyv7jpn3+HiS24+Py8nnZsoeTXKv8f4lSd6f5H1JPpjkW+fKXjYXzwvHuF+W5N5zZX8jyX+f5M4T6uKuSf6PJP8xyffPPfcf5h7fLsn/kORYkrcneVuGnfGjd1n325L8qyRfOyGOr0nyoiT/OkMS7ZeSvDPJryXZaWjb31q2bGN7TK63cdlXJ/nFJP8+ycEk/1uSm5K8Msl9VojjnnO3g0mOJ7lHknvOlb1zkp9M8q4kn0lyS5I/SPK0FfvFJRmSHr+S4T/+rx3X/9Yk37hKH9ql3f54E2X3WEdL292U5PYZEsKfTXLXcfmdMrf9L7Hulu1pcluva3tadb2N/f5HZso+IENy4dNJ3pLkby0bR2N7tBwXWraRtbTdLp+3JY6/PXP/vLHvvTrJv01yQcN7XrVoGxnvX5DkjeP9i5LcsOLnm7SNpOEY2VpvjXUxuY5btv9N96OGz9tUz7us4+CCZU3jhdl+NbbZofH+VyW5aa7s7TOMD//3JI+ce+5fzT2+IMk/T/LPkpyf5Glj+/30/GdOw7gzbeO9yfvCNIwXZt57E/u4yes9Td/40Ar19rYx1kcn+dbx70fH+9+64L1a+sVNJ9s/yU6S6zIkhW7TF8fHLWOtlv7WMjacXG+7tMOu46zGNmnZH/5xFn9fu0OS907tQ6vc0jgOScP4t2UbSeOxYZfP8tcWLGvpmy1jp8nb0oS454+pLd9zWvbJN8/W99xzN849nrydjuVvGPvGt4/bxy1jTJcnuctc2ZZx8uTjZNr2F03HkV3b7kxspBM60NVjx31EhozyheP9X0zyigXlfyfJs5N89Vznf3aS350r+84MO6R7JPncycoZO8XNc2Vvmrn/hiR/Z7z/oCTXzZV928z9F4wNfP8k/zTJq+bKfiRD5vKTGTbGJya5wy518etjB3vC2GF/Pckdd+n0L86wkT8qyb/LsNH9/SS/l+RZC9b9gSQ/m+RDSf5wjPWv7xLHm5L84wyn4b0zyY9nGFQ8I8nr58o+bJfbNyX56AplW9pjcr2Ny347ybPGz/eOse/cb1x27Qpx/NVYz7O3L45/3z9X9toMO6YLk/xYkv8lyQOTvCTDKY/L9os/zHBWzPcl+XCSJ4/LH5vkv63Yhz6XIbHy2fH+5zL8xORzST67QtmWg21L292w6P74+MYFn69l3S3bU0tbT95GxvKTBglLrLel379r5v6xJE8c7z86yX9dYR/Q0h4tx4WWbWRy243lWwZALXHMHnP+zyS/nOHL0vOTvHSu7PwAYXagcGK+nfOVfck9Zts2w0945mNu+UIxaRtJwzFyiXprqYuWOp68/S+xD5g8mN/rllMTrK31PGmwm4bxwlj+7WNfO5hT9yU3zD1+wdi3/kmS65M8b1F7jY9fObbbf0jyuiS/kORbkvxMkv84V3byuDNt472WfeHk8cJYflP7uJb1vmOX201J/t8V6u124/LXJvmGcdkpdbBkv3jX3OM7Zzi2PC+nfnlsGWu19LeWsWFLvU0eZy2x7pb94buT3H/B+90/yXsWxZHp/1CblNxMw7Y3Lp88/k3bNtJ6bJj0hb6xb7aMnSZvS7vEu9cxteW417JP/rUkT59px0vG+w9K8tZlt9Nd6vK8JI8b47tl7rmWcXLL9+qW/UXTcWTXfji14CZv2TubfcpzWbBz2e25DBvi+zMMYK4cO8MvZTh4PWeu7M1JDoz3/2C3Rp/vMDn1gDL/+Ibx712TPDXJazJ8SXhxkm8/zWv/ZZL/Om5o8510/gynPxj/3jFzya4FMX/LuHF8bOzEVyyKebw//1+fG+YefznDab1vWHD7ixXKtrTH5Hqb8Pnm19USx49n2BH/rZllH9ilr7597vFbx7+3yzDHzbL9oqXtWvvQzyd5aWa++O3x+VrKthxsW9ruLRn/k5XkdjPL77aGftGyPbW09eRtZCw/aZCwxHpb+v175j/bHn2sZR/Q0h4tx4WWbWRy243LWwZALXHMlr0x43/Msvhs1y9nOO59YOZ28vFfzpX90QwDxl/KMKg/Ocg6lORNCz7fsl8odt1G0nCMXKLeWuqipY4nb/+t/Shtg/mWBGtrPU8a7La0x7js+EwbvD9jkivDF/X57fodM/cPJLkqw5lOd1zQ1jfOtNfH8pVpERa13+RxZ9rGey37wsnjhfl1n+65ljZpXO/HM/zs6v5zt50Mc3UuVW8zyy/M8GXvF+bjXqFfvD5jkmnuNS9N8uXTtOdeY62W/tYyNmzpb5PHWUuse7YP3Zi994eXZUgW/9bYFleNn/d9mfknwmyMmf4PtUnJzTRse4uWZY/xb+M20npsmPSFvrFvzrbd6cZOk7elsUzLMbXluNeyT75bhgTln2QY539xjOG/ZPjJ2FLb6XzdLXhu/sy4lnHyXm1yw9zjlv1F03Fk18/W+oJN3DL89/R7ctsvbLdL8g8zTAA3X/53M5z+NbsDvHeGQdPvLSj/1zPuaJLcPcmTk1y6oNyzxnU/JkPW+OcyZMOfm1Oz/ScyDPZ/fOyEZea5XQeOM8sOZjgNbj4rePNsPYzLnpbhv80fnFt+fcbseoYB4JtmnvujBe+5KI7bZ9iRv3jBuh+UYaLHP81Xsq8PXPD53pnkgbu07YdXKNvSHpPrbXzu7TP3//Xcc/Ofb3IcY/mTA5rnJblLdsnQJvm/kzxqvP+4DHPanHxu/gDT0i/+W4ZTHb8nQyL0CePyb82pGeumPjQu/6YMA6wrM2yne/0Xb1LZ+c+713ONbXfHXdZ5ryw+hbhl3Tc0bE+zbf3407T15G1kXHbj3OOFg4Ql1tuy/f2bDAfnr0nyLzL8p+n+SZ6e5DeX/XyN7TH5uNC4jUzeTudjHh/vNQBqieP9Gc7oeFJOHazOv+d7k1zU0NZfn+G4+OBFr5kru9QXir22kTQcI5eot8l1Mdbxd0+s48nH09Z+lLbBfEuCtbWeJw12s/t44QFZMODeo29dkOTiuWWLkq7PybCPe+/c8htn7r/oNO03edyZtvHe5H3hWP7keOH52WO8MJbd1D6uZb0vPNmPF8T3smXrbcG6DmfBGZhL9osLM/PPprnn5n8i0zLWmtzf5tr6dGPDpnpL25ispS9P3h/ObD+PGMs/abx/+13iWPs/qNO+7U0e/zZuI63Hhklf6Bv75l5jp/lExeRtaXyu5ZjactxrygWMz981yUPHbWDhzynTvp0+aLftZ0HZlnHyyePk38mE42Qm7i9ay+66jtYXbOKW4T8Lr0jyiQy/Q/3j8f4rMjc4GMvfI8lPZfhv5qcynP5887hs8u/ldonl0eP73pDhLKLXJLkip/5+8Tlzt5O/gf/qnHoq5Sn/Zd3j/X86ybctWH7Z/IY5dsAPjRvnB5I8fFx+KMlPL1jHyxvieGyS94z1+qgMZx28d2yXx8+VfXKSr9tlPU9Ytmxje0yut3H5T2bxb0cfkOSaZeOYe83jMuzgPrbL8w/N8J+PTyV5c8ad0Nh+V67QLx6a4Yyb30ry4Aw7qE9lOGjMD35O9qH3jX3oEXv1oZnX3S7D4OP3M/dfwWXKpu1g29R2LbeWdTduTy1t3bqNTBoktK53XP73pvb78T3fkuFA97mMV3tIcrdlP19je0w+LmT4D/fUbeRvT227cXnLAKhlW/3lDGdynLzde1z+1UleN1f2mZn7L9nMc6f8FLRxG2n5QjFpG0nDMXKPevv0WG9/d9m6mKvf09Xx5O1/rh99+nT9KG2D+ZYEa2s9TxrspmG8sER/+5UsPsPgh5J8cW7ZC7J4f/G1Sd48t2wnw77tlgxjzpPxnjLuzG3Hev9r9hjvjcuflgn7wrnX7DleGMuc3MfdnGH/ttc+rmUb2ciYOg3j5E32i8b1toy1Jve3lrZept4ycUzWsu4M+8AXZcL+cIl6bvkHdUty8+lTt700fIdq2UbSeGwYX3PaL/SNfbNl7NS0LaXtmPrQ3Hb89HUzdTx/3NtJQy6goW6X2k4b1v/oMca35Svj5H+UU7+n7nWcfMIe6z/tsWGZsqe8dtWKWMctwxw/l2f47ebBJD+QIVv8zPkK3eX135JhcHrKKc9LxPLgsdHmJ4S7bO7xlUnuN3Gdd0zygyc35CTfn+F02IWfL0N2+3/OcAB/Xob/3t11l3p7epLvmbLeJdZ9+UzMe7ZJQ709PLed2Pcnk/znDDvVu+1R9oKx7G/uUfZuU9bbWhct/W2+X4yx/M2J/eRRGb5onXa9E9b1tRkmUDv52f7xbp8tw2mT95p5vOdALcN/gU/+dOBbMgyQv3OXPjTb75+a4QvkD8/3odz2YDs/0L3HafrQc0/X1sveTtMmk/vyXJv8fGN/2zWG8flJg4Ql+lBr+dl+8fXjNnJKvxifn7ofatnPzu4D9txfLHjtXtv0/Hr37G9pSCBl8X5rUszja3b7ctB0zGncJlq+UDT1oSmfbeb5v5EJx5zWdY9tcrIfP2Tc9nbrx5OOe0v05ZbBfGsC+dKpn28s8+gsTgof2KPevj7D9r3rehv6wV59edf5j+bbOjOJywVlDo63X9mjzPwxda+x02y8P5BhLqgp473/K0MSbtfjQm57HHn+HnG09Lelt9PGttzzWLbE+pr68iZi3iWGw/P9LaeOZ386w1w1ux1HJu9b5p6/T5Jb93h+0XFytzH4HXPb7wHrPI60/kNtUnJzwWtPOYt/7vlvntqHxvf+tiXaZHK/z+mThbv1i+9YVx8ay7R8Dzhdvf2NqfU29s9LM+yPH5k1HEeywfHQuL6vyYR98i6v/c3M/UN3l3LfkmHOrd32Q/9/W2fme+eUtj5524rLzs9cGv5OGSYK+6oMlyB9bBZcGn7ukqU/lKFRX5UVL1nacmnKlsvSzXy+CzLsxO6c4feZp3y+lksAn2a9qbU+bcHna133aduksd4mXypwQdk/y5BRnVJ2z0sQNtbF5P62oF+8stb6p1lgwXp/JLtcerexv7V8tlcvWMVjssulXhdcxv3SJG/Mgsu4L+ife27Xu5m/lO2GLzc5+XLIjX152f620iWZZ+uu9VKac+VfNpbfrS+39IuWumjp9y37i/k6/uHsvk2vrb9N6Mt7xTx5W2055qzTgs83qf1aLzk99qEfzpBA/obsfcyZvO7GfvysDPvs0x73FtTFyzIkdiZfynZmPZMv7b2gPeY/38Mz/ETjlM/Xsu6WemvVMs5pbOuW7WmVcdnpxk7/IMO8F3uud4k4Wvadk/f1LVrGOEuse219eY+YTzcGmBxD475+8r5liTFcy7il6TvGuiy7j9vweLble85KY7hSyp0y/JTtnXOfr6VfrNKHTnf8ben3LcfqjRxHNtmPSyk/miEBvNbvW41j1Ml9c091xczYOm5puDT8uPyGmft7XrK0MY6bMv3SlDdk+mXpJn++NFwCeIl628i6G+ut5VKBGym7RF1M7m+N/WJT6236bGm71OtNmXgZ99b+ucd2Of+b8aa2brk1tklL/9xIf2upu5Y+tGyfm9gvWvvn1Bha2mMj7bzJvpyGbTVr2vaW2H5Omd9hSvu1fLaZPtRyrJ5ab639eFIMy2x/U+u4sT0mf76Wda9zvQvep2Us0tLWb2vtF+P9dY+dJq13iTiaxiLr6JuL+vzM/bWN1TfZ51pibokh7eOFqfu3yf14iTi24jgytewSdbGR/f06+31O3c9OjWEjx8gN19umtumN9eNs6PtWSx9qqeO9bgeyHW5XSrlDhg96QYbZwz+Z4TSv83Ypf48MB7BSx/961Fr/rJTypVXiqLV+flzX8VLKo5NcU0q5f4aOM6vWWv8qw+/rf7eUcl6+Mgv+z2b4ecCyn+9Ahoki75ghk5la64fG97hNvI3r3dS6W+ptNuP99lLKJbXW60opD8owS/yZKLtMXUztb639YhPrbfls35ThKkP/Msk/q7XeWEr5i1rrf9mlzr5Ua/1ykj8vpfxJrfWz47r/opTyVwvqbVIfKqW8Y5f3KxnmEpq1TFtP1dImrXFsor+11F1rH2op39IvWuqiJYaW9thYO2+wL7dsq8scGyZp/HxT2691P9RyzGlZd9P+rSGGlrpoquPG9mjaThvW3br9t2jpyy1tfUlD2WRz47Kp620t37LvbD02TLWpsXqyuT7XEnNLDE3Hp4Z9S2s/bj1O7vtxpKFsa11san+/qTFcUwwbOkYmm6u3TW7TG+nHo01832rpQ61jkcXqCpmxdd3ScGn4sfzxTLxkaWMcr8/0S1PesMd65i9LN/nzpeESwEvU20bW3Vhvd8v0SwVupOwSdTG5vzX2i02td/Jnm3nN1Eu9Tr6Me2MfarmUbVNbt9wa26Slf26kv7XUXUsfWqLPtfSLlrpoiaGlPTbSzmeiL2fCtprGY0PjNtLy+Vr73NT90ORjTmO9tfTjphga+3JLHbeUnfz5Wtbdut7G/tbcl6f2o4Z+0bLP2sh4b4k4Wvrb5LKNbXc8Gxirb7LPtcTcEkPajk8b2b8tEce2HEcml22si43s71v7/dTP1xjDJvvQpuptU9v0Jvtx0z58aj239KFl2nrhe65SEeu8ZeKl4U+zjlMuWdr4+pZLU06+LF3r50vbJYCb6m0T626pt5nld81pLhV4BspOroup/a21X2xqvct+tpz+Uq+tl3Gf2ocmX8p2mbbeRJu0xrGJ/tZSd0v0oZZLb7b2i0l1scz2tEq/WFM7n5G+PGFbXfmYuurnW3Z/OOGzNR9zpqy7pR+3xtC4PbXUcUvZ1u106r6lab1L9Iel+vLp+lFjn9vIuKxlvS3lG/vbyuOWxvZcaax+JvrclJiXiWHKvn5T+7fWOMZy23AcaT6mTqmLlvZbpU326kMtn68lhk32oU3V2ya36U3143F9G/m+NbUPraNv1rolk0oDAAAAcObcbr8DAAAAAODMkhACAAAA6IyEEAAAAEBnJIQAAAAAOiMhBAAAANCZ/w//NNp1WuS+lQAAAABJRU5ErkJggg=="
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Lets-add-a-title">Lets add a title<a class="anchor-link" href="#Lets-add-a-title">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df4</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;bar&#39;</span><span class="p">,</span> <span class="n">use_index</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;A&#39;</span><span class="p">,</span> <span class="n">title</span><span class="o">=</span><span class="s1">&#39;Some random data&#39;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;AxesSubplot:title={&#39;center&#39;:&#39;Some random data&#39;}&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Getting-correlations-for-a-datasets">Getting correlations for a datasets<a class="anchor-link" href="#Getting-correlations-for-a-datasets">&#182;</a></h3><p>It can be helpful to look at what what correlation you have within a dataset, this can be done with using a little Matplotlib.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>

<span class="n">plt</span><span class="o">.</span><span class="n">matshow</span><span class="p">(</span><span class="n">df4</span><span class="o">.</span><span class="n">corr</span><span class="p">())</span>
<span class="n">cb</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">colorbar</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Change-visualisation-engine-backend-in-Pandas">Change visualisation engine backend in Pandas<a class="anchor-link" href="#Change-visualisation-engine-backend-in-Pandas">&#182;</a></h1>
</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>So the standard visualisation engine in Pandas is powered by Matplotlib, it does the job but there are better plotting engines these days. One options that has been in Pandas since v0.25 is the ability to change the engine.</p>
<p>You can set the backend for the whole session as follows:</p>
<p><strong>pd.options.plotting.backend = 'plotly'</strong></p>
<p>Or for just one plot like this:</p>
<p><strong>df.plot(backend='plotly')</strong></p>
<p>These are the available plotting backends that I know of:</p>
<ul>
<li>matplotlib</li>
<li>hvplot &gt;= 0.5.1</li>
<li>holoviews</li>
<li>pandas_bokeh</li>
<li>plotly &gt;= 4.8</li>
<li>altair</li>
</ul>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Lets try using the plotly library as the engine</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df3</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">backend</span><span class="o">=</span><span class="s1">&#39;plotly&#39;</span><span class="p">,</span> <span class="n">kind</span><span class="o">=</span><span class="s1">&#39;hist&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;A&#39;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


    
        <div class="jp-RenderedImage jp-OutputArea-output ">
        <img src="newplot8.png">
        </div>
    
    
    



</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Other-visualisations-library's">Other visualisations library's<a class="anchor-link" href="#Other-visualisations-library's">&#182;</a></h1>
</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>A few years ago there were limited options for visualisations in Python really Matplotlib was your only option. Matplotlib dates back to 2003 and was designed to be similar to MatLab a scientific platform.</p>
<p>R and ggplot set a standard the Matplotlib struggled to compete. ggplot used the so called Grammar of Graphics and offered animation and less verbose syntax.</p>
<p>All that has changed now and there are a number of great libraries that outperform Matplotlib. Some of these new libraries offer interactivity.</p>
<p>Each library has its own syntax which you need to learn, but it should not take long as many are designed to be easy to pickup.</p>
<p>Lets have a quick look at plotly my current favourite.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Bar-plot-in-plotly">Bar plot in plotly<a class="anchor-link" href="#Bar-plot-in-plotly">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">plotly.express</span> <span class="k">as</span> <span class="nn">px</span>
<span class="n">fig</span> <span class="o">=</span> <span class="n">px</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="p">[</span><span class="s2">&quot;a&quot;</span><span class="p">,</span> <span class="s2">&quot;b&quot;</span><span class="p">,</span> <span class="s2">&quot;c&quot;</span><span class="p">],</span> <span class="n">y</span><span class="o">=</span><span class="p">[</span><span class="mi">1</span><span class="p">,</span> <span class="mi">3</span><span class="p">,</span> <span class="mi">2</span><span class="p">])</span> <span class="c1"># x=df3[&#39;D&#39;], y=df3[&#39;A&#39;])</span>
<span class="n">fig</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>





</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Scatter-plot-in-plotly">Scatter plot in plotly<a class="anchor-link" href="#Scatter-plot-in-plotly">&#182;</a></h3>
</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Lets use the data from the df3 dataframe.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">fig</span> <span class="o">=</span> <span class="n">px</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="n">df3</span><span class="p">[</span><span class="s1">&#39;A&#39;</span><span class="p">],</span> <span class="n">y</span><span class="o">=</span><span class="n">df3</span><span class="p">[</span><span class="s1">&#39;B&#39;</span><span class="p">])</span>
<span class="n">fig</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>





</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Boxplot-in-plotly">Boxplot in plotly<a class="anchor-link" href="#Boxplot-in-plotly">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">fig</span> <span class="o">=</span> <span class="n">px</span><span class="o">.</span><span class="n">box</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="n">df3</span><span class="p">[</span><span class="s1">&#39;A&#39;</span><span class="p">],</span> <span class="n">y</span><span class="o">=</span><span class="n">df3</span><span class="p">[</span><span class="s1">&#39;E&#39;</span><span class="p">])</span>
<span class="n">fig</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>





</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Correlations-matrix">Correlations matrix<a class="anchor-link" href="#Correlations-matrix">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">data</span> <span class="o">=</span> <span class="p">[[</span><span class="mi">1</span><span class="p">,</span> <span class="mi">20</span><span class="p">,</span> <span class="mi">30</span><span class="p">],</span> <span class="p">[</span><span class="mi">20</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">60</span><span class="p">],</span> <span class="p">[</span><span class="mi">30</span><span class="p">,</span> <span class="mi">60</span><span class="p">,</span> <span class="mi">1</span><span class="p">]]</span>

<span class="n">px</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">data</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>





</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Right that is all for today. If you want to learn more about plotly this is a good starting point <a href="https://plotly.com/python/basic-charts/">https://plotly.com/python/basic-charts/</a></p>
<p>Other Python visulations libraries that are worth looking at:</p>
<ul>
<li>Seaborn</li>
<li>Plotly</li>
<li>Geoplotlib</li>
<li>Gleam</li>
<li>Plotnine(ggplot)</li>
<li>Bokeh</li>
<li>Missingo</li>
<li>Altair</li>
<li>Folium</li>
<li>Leather</li>
<li>pygal</li>
<li>Folium</li>
</ul>
<p>You can read other posts in this series on Pandas via my blog.</p>

</div>
</div>
</body>







</html>
