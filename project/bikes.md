
<html lang="en">
<head><meta charset="utf-8"/>
<meta content="width=device-width, initial-scale=1.0" name="viewport"/>
<title>Individual Assignment - Bikes Analysis</title><script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<style type="text/css">
    pre { line-height: 125%; }
td.linenos .normal { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
span.linenos { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
td.linenos .special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
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
.highlight .pm { color: var(--jp-mirror-editor-punctuation-color) } /* Punctuation.Marker */
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

/* tiny scrollbar */

.jp-scrollbar-tiny {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
  scrollbar-width: thin;
}

/* tiny scrollbar */

.jp-scrollbar-tiny::-webkit-scrollbar,
.jp-scrollbar-tiny::-webkit-scrollbar-corner {
  background-color: transparent;
  height: 4px;
  width: 4px;
}

.jp-scrollbar-tiny::-webkit-scrollbar-thumb {
  background: rgba(var(--jp-scrollbar-thumb-color), 0.5);
}

.jp-scrollbar-tiny::-webkit-scrollbar-track:horizontal {
  border-left: 0 solid transparent;
  border-right: 0 solid transparent;
}

.jp-scrollbar-tiny::-webkit-scrollbar-track:vertical {
  border-top: 0 solid transparent;
  border-bottom: 0 solid transparent;
}

/*
 * Lumino
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

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-Widget {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
}

.lm-Widget.lm-mod-hidden {
  display: none !important;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.lm-AccordionPanel[data-orientation='horizontal'] > .lm-AccordionPanel-title {
  /* Title is rotated for horizontal accordion panel using CSS */
  display: block;
  transform-origin: top left;
  transform: rotate(-90deg) translate(-100%);
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-CommandPalette {
  display: flex;
  flex-direction: column;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-CommandPalette-search {
  flex: 0 0 auto;
}

.lm-CommandPalette-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  min-height: 0;
  overflow: auto;
  list-style-type: none;
}

.lm-CommandPalette-header {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.lm-CommandPalette-item {
  display: flex;
  flex-direction: row;
}

.lm-CommandPalette-itemIcon {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemContent {
  flex: 1 1 auto;
  overflow: hidden;
}

.lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemLabel {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.lm-close-icon {
  border: 1px solid transparent;
  background-color: transparent;
  position: absolute;
  z-index: 1;
  right: 3%;
  top: 0;
  bottom: 0;
  margin: auto;
  padding: 7px 0;
  display: none;
  vertical-align: middle;
  outline: 0;
  cursor: pointer;
}
.lm-close-icon:after {
  content: 'X';
  display: block;
  width: 15px;
  height: 15px;
  text-align: center;
  color: #000;
  font-weight: normal;
  font-size: 12px;
  cursor: pointer;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-DockPanel {
  z-index: 0;
}

.lm-DockPanel-widget {
  z-index: 0;
}

.lm-DockPanel-tabBar {
  z-index: 1;
}

.lm-DockPanel-handle {
  z-index: 2;
}

.lm-DockPanel-handle.lm-mod-hidden {
  display: none !important;
}

.lm-DockPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}

.lm-DockPanel-handle[data-orientation='horizontal'] {
  cursor: ew-resize;
}

.lm-DockPanel-handle[data-orientation='vertical'] {
  cursor: ns-resize;
}

.lm-DockPanel-handle[data-orientation='horizontal']:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}

.lm-DockPanel-handle[data-orientation='vertical']:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}

.lm-DockPanel-overlay {
  z-index: 3;
  box-sizing: border-box;
  pointer-events: none;
}

.lm-DockPanel-overlay.lm-mod-hidden {
  display: none !important;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

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

.lm-Menu-content {
  margin: 0;
  padding: 0;
  display: table;
  list-style-type: none;
}

.lm-Menu-item {
  display: table-row;
}

.lm-Menu-item.lm-mod-hidden,
.lm-Menu-item.lm-mod-collapsed {
  display: none !important;
}

.lm-Menu-itemIcon,
.lm-Menu-itemSubmenuIcon {
  display: table-cell;
  text-align: center;
}

.lm-Menu-itemLabel {
  display: table-cell;
  text-align: left;
}

.lm-Menu-itemShortcut {
  display: table-cell;
  text-align: right;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-MenuBar {
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-MenuBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: row;
  list-style-type: none;
}

.lm-MenuBar-item {
  box-sizing: border-box;
}

.lm-MenuBar-itemIcon,
.lm-MenuBar-itemLabel {
  display: inline-block;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-ScrollBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-ScrollBar[data-orientation='horizontal'] {
  flex-direction: row;
}

.lm-ScrollBar[data-orientation='vertical'] {
  flex-direction: column;
}

.lm-ScrollBar-button {
  box-sizing: border-box;
  flex: 0 0 auto;
}

.lm-ScrollBar-track {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  flex: 1 1 auto;
}

.lm-ScrollBar-thumb {
  box-sizing: border-box;
  position: absolute;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-SplitPanel-child {
  z-index: 0;
}

.lm-SplitPanel-handle {
  z-index: 1;
}

.lm-SplitPanel-handle.lm-mod-hidden {
  display: none !important;
}

.lm-SplitPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}

.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle {
  cursor: ew-resize;
}

.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle {
  cursor: ns-resize;
}

.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}

.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-TabBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.lm-TabBar[data-orientation='horizontal'] {
  flex-direction: row;
  align-items: flex-end;
}

.lm-TabBar[data-orientation='vertical'] {
  flex-direction: column;
  align-items: flex-end;
}

.lm-TabBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex: 1 1 auto;
  list-style-type: none;
}

.lm-TabBar[data-orientation='horizontal'] > .lm-TabBar-content {
  flex-direction: row;
}

.lm-TabBar[data-orientation='vertical'] > .lm-TabBar-content {
  flex-direction: column;
}

.lm-TabBar-tab {
  display: flex;
  flex-direction: row;
  box-sizing: border-box;
  overflow: hidden;
  touch-action: none; /* Disable native Drag/Drop */
}

.lm-TabBar-tabIcon,
.lm-TabBar-tabCloseIcon {
  flex: 0 0 auto;
}

.lm-TabBar-tabLabel {
  flex: 1 1 auto;
  overflow: hidden;
  white-space: nowrap;
}

.lm-TabBar-tabInput {
  user-select: all;
  width: 100%;
  box-sizing: border-box;
}

.lm-TabBar-tab.lm-mod-hidden {
  display: none !important;
}

.lm-TabBar-addButton.lm-mod-hidden {
  display: none !important;
}

.lm-TabBar.lm-mod-dragging .lm-TabBar-tab {
  position: relative;
}

.lm-TabBar.lm-mod-dragging[data-orientation='horizontal'] .lm-TabBar-tab {
  left: 0;
  transition: left 150ms ease;
}

.lm-TabBar.lm-mod-dragging[data-orientation='vertical'] .lm-TabBar-tab {
  top: 0;
  transition: top 150ms ease;
}

.lm-TabBar.lm-mod-dragging .lm-TabBar-tab.lm-mod-dragging {
  transition: none;
}

.lm-TabBar-tabLabel .lm-TabBar-tabInput {
  user-select: all;
  width: 100%;
  box-sizing: border-box;
  background: inherit;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-TabPanel-tabBar {
  z-index: 1;
}

.lm-TabPanel-stackedPanel {
  z-index: 0;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapse {
  display: flex;
  flex-direction: column;
  align-items: stretch;
}

.jp-Collapse-header {
  padding: 1px 12px;
  background-color: var(--jp-layout-color1);
  border-bottom: solid var(--jp-border-width) var(--jp-border-color2);
  color: var(--jp-ui-font-color1);
  cursor: pointer;
  display: flex;
  align-items: center;
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  text-transform: uppercase;
  user-select: none;
}

.jp-Collapser-icon {
  height: 16px;
}

.jp-Collapse-header-collapsed .jp-Collapser-icon {
  transform: rotate(-90deg);
  margin: auto 0;
}

.jp-Collapser-title {
  line-height: 25px;
}

.jp-Collapse-contents {
  padding: 0 12px;
  background-color: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  overflow: auto;
}

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
  --jp-icon-add-above: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPGcgY2xpcC1wYXRoPSJ1cmwoI2NsaXAwXzEzN18xOTQ5MikiPgo8cGF0aCBjbGFzcz0ianAtaWNvbjMiIGQ9Ik00Ljc1IDQuOTMwNjZINi42MjVWNi44MDU2NkM2LjYyNSA3LjAxMTkxIDYuNzkzNzUgNy4xODA2NiA3IDcuMTgwNjZDNy4yMDYyNSA3LjE4MDY2IDcuMzc1IDcuMDExOTEgNy4zNzUgNi44MDU2NlY0LjkzMDY2SDkuMjVDOS40NTYyNSA0LjkzMDY2IDkuNjI1IDQuNzYxOTEgOS42MjUgNC41NTU2NkM5LjYyNSA0LjM0OTQxIDkuNDU2MjUgNC4xODA2NiA5LjI1IDQuMTgwNjZINy4zNzVWMi4zMDU2NkM3LjM3NSAyLjA5OTQxIDcuMjA2MjUgMS45MzA2NiA3IDEuOTMwNjZDNi43OTM3NSAxLjkzMDY2IDYuNjI1IDIuMDk5NDEgNi42MjUgMi4zMDU2NlY0LjE4MDY2SDQuNzVDNC41NDM3NSA0LjE4MDY2IDQuMzc1IDQuMzQ5NDEgNC4zNzUgNC41NTU2NkM0LjM3NSA0Ljc2MTkxIDQuNTQzNzUgNC45MzA2NiA0Ljc1IDQuOTMwNjZaIiBmaWxsPSIjNjE2MTYxIiBzdHJva2U9IiM2MTYxNjEiIHN0cm9rZS13aWR0aD0iMC43Ii8+CjwvZz4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiIGNsaXAtcnVsZT0iZXZlbm9kZCIgZD0iTTExLjUgOS41VjExLjVMMi41IDExLjVWOS41TDExLjUgOS41Wk0xMiA4QzEyLjU1MjMgOCAxMyA4LjQ0NzcyIDEzIDlWMTJDMTMgMTIuNTUyMyAxMi41NTIzIDEzIDEyIDEzTDIgMTNDMS40NDc3MiAxMyAxIDEyLjU1MjMgMSAxMlY5QzEgOC40NDc3MiAxLjQ0NzcxIDggMiA4TDEyIDhaIiBmaWxsPSIjNjE2MTYxIi8+CjxkZWZzPgo8Y2xpcFBhdGggaWQ9ImNsaXAwXzEzN18xOTQ5MiI+CjxyZWN0IGNsYXNzPSJqcC1pY29uMyIgd2lkdGg9IjYiIGhlaWdodD0iNiIgZmlsbD0id2hpdGUiIHRyYW5zZm9ybT0ibWF0cml4KC0xIDAgMCAxIDEwIDEuNTU1NjYpIi8+CjwvY2xpcFBhdGg+CjwvZGVmcz4KPC9zdmc+Cg==);
  --jp-icon-add-below: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPGcgY2xpcC1wYXRoPSJ1cmwoI2NsaXAwXzEzN18xOTQ5OCkiPgo8cGF0aCBjbGFzcz0ianAtaWNvbjMiIGQ9Ik05LjI1IDEwLjA2OTNMNy4zNzUgMTAuMDY5M0w3LjM3NSA4LjE5NDM0QzcuMzc1IDcuOTg4MDkgNy4yMDYyNSA3LjgxOTM0IDcgNy44MTkzNEM2Ljc5Mzc1IDcuODE5MzQgNi42MjUgNy45ODgwOSA2LjYyNSA4LjE5NDM0TDYuNjI1IDEwLjA2OTNMNC43NSAxMC4wNjkzQzQuNTQzNzUgMTAuMDY5MyA0LjM3NSAxMC4yMzgxIDQuMzc1IDEwLjQ0NDNDNC4zNzUgMTAuNjUwNiA0LjU0Mzc1IDEwLjgxOTMgNC43NSAxMC44MTkzTDYuNjI1IDEwLjgxOTNMNi42MjUgMTIuNjk0M0M2LjYyNSAxMi45MDA2IDYuNzkzNzUgMTMuMDY5MyA3IDEzLjA2OTNDNy4yMDYyNSAxMy4wNjkzIDcuMzc1IDEyLjkwMDYgNy4zNzUgMTIuNjk0M0w3LjM3NSAxMC44MTkzTDkuMjUgMTAuODE5M0M5LjQ1NjI1IDEwLjgxOTMgOS42MjUgMTAuNjUwNiA5LjYyNSAxMC40NDQzQzkuNjI1IDEwLjIzODEgOS40NTYyNSAxMC4wNjkzIDkuMjUgMTAuMDY5M1oiIGZpbGw9IiM2MTYxNjEiIHN0cm9rZT0iIzYxNjE2MSIgc3Ryb2tlLXdpZHRoPSIwLjciLz4KPC9nPgo8cGF0aCBjbGFzcz0ianAtaWNvbjMiIGZpbGwtcnVsZT0iZXZlbm9kZCIgY2xpcC1ydWxlPSJldmVub2RkIiBkPSJNMi41IDUuNUwyLjUgMy41TDExLjUgMy41TDExLjUgNS41TDIuNSA1LjVaTTIgN0MxLjQ0NzcyIDcgMSA2LjU1MjI4IDEgNkwxIDNDMSAyLjQ0NzcyIDEuNDQ3NzIgMiAyIDJMMTIgMkMxMi41NTIzIDIgMTMgMi40NDc3MiAxMyAzTDEzIDZDMTMgNi41NTIyOSAxMi41NTIzIDcgMTIgN0wyIDdaIiBmaWxsPSIjNjE2MTYxIi8+CjxkZWZzPgo8Y2xpcFBhdGggaWQ9ImNsaXAwXzEzN18xOTQ5OCI+CjxyZWN0IGNsYXNzPSJqcC1pY29uMyIgd2lkdGg9IjYiIGhlaWdodD0iNiIgZmlsbD0id2hpdGUiIHRyYW5zZm9ybT0ibWF0cml4KDEgMS43NDg0NmUtMDcgMS43NDg0NmUtMDcgLTEgNCAxMy40NDQzKSIvPgo8L2NsaXBQYXRoPgo8L2RlZnM+Cjwvc3ZnPgo=);
  --jp-icon-add: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDEzaC02djZoLTJ2LTZINXYtMmg2VjVoMnY2aDZ2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-bell: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE2IDE2IiB2ZXJzaW9uPSIxLjEiPgogICA8cGF0aCBjbGFzcz0ianAtaWNvbjIganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMzMzMzMzIgogICAgICBkPSJtOCAwLjI5Yy0xLjQgMC0yLjcgMC43My0zLjYgMS44LTEuMiAxLjUtMS40IDMuNC0xLjUgNS4yLTAuMTggMi4yLTAuNDQgNC0yLjMgNS4zbDAuMjggMS4zaDVjMC4wMjYgMC42NiAwLjMyIDEuMSAwLjcxIDEuNSAwLjg0IDAuNjEgMiAwLjYxIDIuOCAwIDAuNTItMC40IDAuNi0xIDAuNzEtMS41aDVsMC4yOC0xLjNjLTEuOS0wLjk3LTIuMi0zLjMtMi4zLTUuMy0wLjEzLTEuOC0wLjI2LTMuNy0xLjUtNS4yLTAuODUtMS0yLjItMS44LTMuNi0xLjh6bTAgMS40YzAuODggMCAxLjkgMC41NSAyLjUgMS4zIDAuODggMS4xIDEuMSAyLjcgMS4yIDQuNCAwLjEzIDEuNyAwLjIzIDMuNiAxLjMgNS4yaC0xMGMxLjEtMS42IDEuMi0zLjQgMS4zLTUuMiAwLjEzLTEuNyAwLjMtMy4zIDEuMi00LjQgMC41OS0wLjcyIDEuNi0xLjMgMi41LTEuM3ptLTAuNzQgMTJoMS41Yy0wLjAwMTUgMC4yOCAwLjAxNSAwLjc5LTAuNzQgMC43OS0wLjczIDAuMDAxNi0wLjcyLTAuNTMtMC43NC0wLjc5eiIgLz4KPC9zdmc+Cg==);
  --jp-icon-bug-dot: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiPgogICAgICAgIDxwYXRoIGZpbGwtcnVsZT0iZXZlbm9kZCIgY2xpcC1ydWxlPSJldmVub2RkIiBkPSJNMTcuMTkgOEgyMFYxMEgxNy45MUMxNy45NiAxMC4zMyAxOCAxMC42NiAxOCAxMVYxMkgyMFYxNEgxOC41SDE4VjE0LjAyNzVDMTUuNzUgMTQuMjc2MiAxNCAxNi4xODM3IDE0IDE4LjVDMTQgMTkuMjA4IDE0LjE2MzUgMTkuODc3OSAxNC40NTQ5IDIwLjQ3MzlDMTMuNzA2MyAyMC44MTE3IDEyLjg3NTcgMjEgMTIgMjFDOS43OCAyMSA3Ljg1IDE5Ljc5IDYuODEgMThINFYxNkg2LjA5QzYuMDQgMTUuNjcgNiAxNS4zNCA2IDE1VjE0SDRWMTJINlYxMUM2IDEwLjY2IDYuMDQgMTAuMzMgNi4wOSAxMEg0VjhINi44MUM3LjI2IDcuMjIgNy44OCA2LjU1IDguNjIgNi4wNEw3IDQuNDFMOC40MSAzTDEwLjU5IDUuMTdDMTEuMDQgNS4wNiAxMS41MSA1IDEyIDVDMTIuNDkgNSAxMi45NiA1LjA2IDEzLjQyIDUuMTdMMTUuNTkgM0wxNyA0LjQxTDE1LjM3IDYuMDRDMTYuMTIgNi41NSAxNi43NCA3LjIyIDE3LjE5IDhaTTEwIDE2SDE0VjE0SDEwVjE2Wk0xMCAxMkgxNFYxMEgxMFYxMloiIGZpbGw9IiM2MTYxNjEiLz4KICAgICAgICA8cGF0aCBkPSJNMjIgMTguNUMyMiAyMC40MzMgMjAuNDMzIDIyIDE4LjUgMjJDMTYuNTY3IDIyIDE1IDIwLjQzMyAxNSAxOC41QzE1IDE2LjU2NyAxNi41NjcgMTUgMTguNSAxNUMyMC40MzMgMTUgMjIgMTYuNTY3IDIyIDE4LjVaIiBmaWxsPSIjNjE2MTYxIi8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-bug: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0yMCA4aC0yLjgxYy0uNDUtLjc4LTEuMDctMS40NS0xLjgyLTEuOTZMMTcgNC40MSAxNS41OSAzbC0yLjE3IDIuMTdDMTIuOTYgNS4wNiAxMi40OSA1IDEyIDVjLS40OSAwLS45Ni4wNi0xLjQxLjE3TDguNDEgMyA3IDQuNDFsMS42MiAxLjYzQzcuODggNi41NSA3LjI2IDcuMjIgNi44MSA4SDR2MmgyLjA5Yy0uMDUuMzMtLjA5LjY2LS4wOSAxdjFINHYyaDJ2MWMwIC4zNC4wNC42Ny4wOSAxSDR2MmgyLjgxYzEuMDQgMS43OSAyLjk3IDMgNS4xOSAzczQuMTUtMS4yMSA1LjE5LTNIMjB2LTJoLTIuMDljLjA1LS4zMy4wOS0uNjYuMDktMXYtMWgydi0yaC0ydi0xYzAtLjM0LS4wNC0uNjctLjA5LTFIMjBWOHptLTYgOGgtNHYtMmg0djJ6bTAtNGgtNHYtMmg0djJ6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-build: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE0LjkgMTcuNDVDMTYuMjUgMTcuNDUgMTcuMzUgMTYuMzUgMTcuMzUgMTVDMTcuMzUgMTMuNjUgMTYuMjUgMTIuNTUgMTQuOSAxMi41NUMxMy41NCAxMi41NSAxMi40NSAxMy42NSAxMi40NSAxNUMxMi40NSAxNi4zNSAxMy41NCAxNy40NSAxNC45IDE3LjQ1Wk0yMC4xIDE1LjY4TDIxLjU4IDE2Ljg0QzIxLjcxIDE2Ljk1IDIxLjc1IDE3LjEzIDIxLjY2IDE3LjI5TDIwLjI2IDE5LjcxQzIwLjE3IDE5Ljg2IDIwIDE5LjkyIDE5LjgzIDE5Ljg2TDE4LjA5IDE5LjE2QzE3LjczIDE5LjQ0IDE3LjMzIDE5LjY3IDE2LjkxIDE5Ljg1TDE2LjY0IDIxLjdDMTYuNjIgMjEuODcgMTYuNDcgMjIgMTYuMyAyMkgxMy41QzEzLjMyIDIyIDEzLjE4IDIxLjg3IDEzLjE1IDIxLjdMMTIuODkgMTkuODVDMTIuNDYgMTkuNjcgMTIuMDcgMTkuNDQgMTEuNzEgMTkuMTZMOS45NjAwMiAxOS44NkM5LjgxMDAyIDE5LjkyIDkuNjIwMDIgMTkuODYgOS41NDAwMiAxOS43MUw4LjE0MDAyIDE3LjI5QzguMDUwMDIgMTcuMTMgOC4wOTAwMiAxNi45NSA4LjIyMDAyIDE2Ljg0TDkuNzAwMDIgMTUuNjhMOS42NTAwMSAxNUw5LjcwMDAyIDE0LjMxTDguMjIwMDIgMTMuMTZDOC4wOTAwMiAxMy4wNSA4LjA1MDAyIDEyLjg2IDguMTQwMDIgMTIuNzFMOS41NDAwMiAxMC4yOUM5LjYyMDAyIDEwLjEzIDkuODEwMDIgMTAuMDcgOS45NjAwMiAxMC4xM0wxMS43MSAxMC44NEMxMi4wNyAxMC41NiAxMi40NiAxMC4zMiAxMi44OSAxMC4xNUwxMy4xNSA4LjI4OTk4QzEzLjE4IDguMTI5OTggMTMuMzIgNy45OTk5OCAxMy41IDcuOTk5OThIMTYuM0MxNi40NyA3Ljk5OTk4IDE2LjYyIDguMTI5OTggMTYuNjQgOC4yODk5OEwxNi45MSAxMC4xNUMxNy4zMyAxMC4zMiAxNy43MyAxMC41NiAxOC4wOSAxMC44NEwxOS44MyAxMC4xM0MyMCAxMC4wNyAyMC4xNyAxMC4xMyAyMC4yNiAxMC4yOUwyMS42NiAxMi43MUMyMS43NSAxMi44NiAyMS43MSAxMy4wNSAyMS41OCAxMy4xNkwyMC4xIDE0LjMxTDIwLjE1IDE1TDIwLjEgMTUuNjhaIi8+CiAgICA8cGF0aCBkPSJNNy4zMjk2NiA3LjQ0NDU0QzguMDgzMSA3LjAwOTU0IDguMzM5MzIgNi4wNTMzMiA3LjkwNDMyIDUuMjk5ODhDNy40NjkzMiA0LjU0NjQzIDYuNTA4MSA0LjI4MTU2IDUuNzU0NjYgNC43MTY1NkM1LjM5MTc2IDQuOTI2MDggNS4xMjY5NSA1LjI3MTE4IDUuMDE4NDkgNS42NzU5NEM0LjkxMDA0IDYuMDgwNzEgNC45NjY4MiA2LjUxMTk4IDUuMTc2MzQgNi44NzQ4OEM1LjYxMTM0IDcuNjI4MzIgNi41NzYyMiA3Ljg3OTU0IDcuMzI5NjYgNy40NDQ1NFpNOS42NTcxOCA0Ljc5NTkzTDEwLjg2NzIgNC45NTE3OUMxMC45NjI4IDQuOTc3NDEgMTEuMDQwMiA1LjA3MTMzIDExLjAzODIgNS4xODc5M0wxMS4wMzg4IDYuOTg4OTNDMTEuMDQ1NSA3LjEwMDU0IDEwLjk2MTYgNy4xOTUxOCAxMC44NTUgNy4yMTA1NEw5LjY2MDAxIDcuMzgwODNMOS4yMzkxNSA4LjEzMTg4TDkuNjY5NjEgOS4yNTc0NUM5LjcwNzI5IDkuMzYyNzEgOS42NjkzNCA5LjQ3Njk5IDkuNTc0MDggOS41MzE5OUw4LjAxNTIzIDEwLjQzMkM3LjkxMTMxIDEwLjQ5MiA3Ljc5MzM3IDEwLjQ2NzcgNy43MjEwNSAxMC4zODI0TDYuOTg3NDggOS40MzE4OEw2LjEwOTMxIDkuNDMwODNMNS4zNDcwNCAxMC4zOTA1QzUuMjg5MDkgMTAuNDcwMiA1LjE3MzgzIDEwLjQ5MDUgNS4wNzE4NyAxMC40MzM5TDMuNTEyNDUgOS41MzI5M0MzLjQxMDQ5IDkuNDc2MzMgMy4zNzY0NyA5LjM1NzQxIDMuNDEwNzUgOS4yNTY3OUwzLjg2MzQ3IDguMTQwOTNMMy42MTc0OSA3Ljc3NDg4TDMuNDIzNDcgNy4zNzg4M0wyLjIzMDc1IDcuMjEyOTdDMi4xMjY0NyA3LjE5MjM1IDIuMDQwNDkgNy4xMDM0MiAyLjA0MjQ1IDYuOTg2ODJMMi4wNDE4NyA1LjE4NTgyQzIuMDQzODMgNS4wNjkyMiAyLjExOTA5IDQuOTc5NTggMi4yMTcwNCA0Ljk2OTIyTDMuNDIwNjUgNC43OTM5M0wzLjg2NzQ5IDQuMDI3ODhMMy40MTEwNSAyLjkxNzMxQzMuMzczMzcgMi44MTIwNCAzLjQxMTMxIDIuNjk3NzYgMy41MTUyMyAyLjYzNzc2TDUuMDc0MDggMS43Mzc3NkM1LjE2OTM0IDEuNjgyNzYgNS4yODcyOSAxLjcwNzA0IDUuMzU5NjEgMS43OTIzMUw2LjExOTE1IDIuNzI3ODhMNi45ODAwMSAyLjczODkzTDcuNzI0OTYgMS43ODkyMkM3Ljc5MTU2IDEuNzA0NTggNy45MTU0OCAxLjY3OTIyIDguMDA4NzkgMS43NDA4Mkw5LjU2ODIxIDIuNjQxODJDOS42NzAxNyAyLjY5ODQyIDkuNzEyODUgMi44MTIzNCA5LjY4NzIzIDIuOTA3OTdMOS4yMTcxOCA0LjAzMzgzTDkuNDYzMTYgNC4zOTk4OEw5LjY1NzE4IDQuNzk1OTNaIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iOS45LDEzLjYgMy42LDcuNCA0LjQsNi42IDkuOSwxMi4yIDE1LjQsNi43IDE2LjEsNy40ICIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNS45TDksOS43bDMuOC0zLjhsMS4yLDEuMmwtNC45LDVsLTQuOS01TDUuMiw1Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNy41TDksMTEuMmwzLjgtMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-left: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik0xMC44LDEyLjhMNy4xLDlsMy44LTMuOGwwLDcuNkgxMC44eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-right: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik03LjIsNS4yTDEwLjksOWwtMy44LDMuOFY1LjJINy4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-up-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iMTUuNCwxMy4zIDkuOSw3LjcgNC40LDEzLjIgMy42LDEyLjUgOS45LDYuMyAxNi4xLDEyLjYgIi8+Cgk8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-up: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik01LjIsMTAuNUw5LDYuOGwzLjgsMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-case-sensitive: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgogIDxnIGNsYXNzPSJqcC1pY29uLWFjY2VudDIiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTcuNiw4aDAuOWwzLjUsOGgtMS4xTDEwLDE0SDZsLTAuOSwySDRMNy42LDh6IE04LDkuMUw2LjQsMTNoMy4yTDgsOS4xeiIvPgogICAgPHBhdGggZD0iTTE2LjYsOS44Yy0wLjIsMC4xLTAuNCwwLjEtMC43LDAuMWMtMC4yLDAtMC40LTAuMS0wLjYtMC4yYy0wLjEtMC4xLTAuMi0wLjQtMC4yLTAuNyBjLTAuMywwLjMtMC42LDAuNS0wLjksMC43Yy0wLjMsMC4xLTAuNywwLjItMS4xLDAuMmMtMC4zLDAtMC41LDAtMC43LTAuMWMtMC4yLTAuMS0wLjQtMC4yLTAuNi0wLjNjLTAuMi0wLjEtMC4zLTAuMy0wLjQtMC41IGMtMC4xLTAuMi0wLjEtMC40LTAuMS0wLjdjMC0wLjMsMC4xLTAuNiwwLjItMC44YzAuMS0wLjIsMC4zLTAuNCwwLjQtMC41QzEyLDcsMTIuMiw2LjksMTIuNSw2LjhjMC4yLTAuMSwwLjUtMC4xLDAuNy0wLjIgYzAuMy0wLjEsMC41LTAuMSwwLjctMC4xYzAuMiwwLDAuNC0wLjEsMC42LTAuMWMwLjIsMCwwLjMtMC4xLDAuNC0wLjJjMC4xLTAuMSwwLjItMC4yLDAuMi0wLjRjMC0xLTEuMS0xLTEuMy0xIGMtMC40LDAtMS40LDAtMS40LDEuMmgtMC45YzAtMC40LDAuMS0wLjcsMC4yLTFjMC4xLTAuMiwwLjMtMC40LDAuNS0wLjZjMC4yLTAuMiwwLjUtMC4zLDAuOC0wLjNDMTMuMyw0LDEzLjYsNCwxMy45LDQgYzAuMywwLDAuNSwwLDAuOCwwLjFjMC4zLDAsMC41LDAuMSwwLjcsMC4yYzAuMiwwLjEsMC40LDAuMywwLjUsMC41QzE2LDUsMTYsNS4yLDE2LDUuNnYyLjljMCwwLjIsMCwwLjQsMCwwLjUgYzAsMC4xLDAuMSwwLjIsMC4zLDAuMmMwLjEsMCwwLjIsMCwwLjMsMFY5Ljh6IE0xNS4yLDYuOWMtMS4yLDAuNi0zLjEsMC4yLTMuMSwxLjRjMCwxLjQsMy4xLDEsMy4xLTAuNVY2Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-check: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik05IDE2LjE3TDQuODMgMTJsLTEuNDIgMS40MUw5IDE5IDIxIDdsLTEuNDEtMS40MXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-circle-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDJDNi40NyAyIDIgNi40NyAyIDEyczQuNDcgMTAgMTAgMTAgMTAtNC40NyAxMC0xMFMxNy41MyAyIDEyIDJ6bTAgMThjLTQuNDEgMC04LTMuNTktOC04czMuNTktOCA4LTggOCAzLjU5IDggOC0zLjU5IDgtOCA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iOSIgY3k9IjkiIHI9IjgiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-clear: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8bWFzayBpZD0iZG9udXRIb2xlIj4KICAgIDxyZWN0IHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgZmlsbD0id2hpdGUiIC8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSI4IiBmaWxsPSJibGFjayIvPgogIDwvbWFzaz4KCiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxyZWN0IGhlaWdodD0iMTgiIHdpZHRoPSIyIiB4PSIxMSIgeT0iMyIgdHJhbnNmb3JtPSJyb3RhdGUoMzE1LCAxMiwgMTIpIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCIgbWFzaz0idXJsKCNkb251dEhvbGUpIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-close: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1ub25lIGpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIGpwLWljb24zLWhvdmVyIiBmaWxsPSJub25lIj4KICAgIDxjaXJjbGUgY3g9IjEyIiBjeT0iMTIiIHI9IjExIi8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIGpwLWljb24tYWNjZW50Mi1ob3ZlciIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMTkgNi40MUwxNy41OSA1IDEyIDEwLjU5IDYuNDEgNSA1IDYuNDEgMTAuNTkgMTIgNSAxNy41OSA2LjQxIDE5IDEyIDEzLjQxIDE3LjU5IDE5IDE5IDE3LjU5IDEzLjQxIDEyeiIvPgogIDwvZz4KCiAgPGcgY2xhc3M9ImpwLWljb24tbm9uZSBqcC1pY29uLWJ1c3kiIGZpbGw9Im5vbmUiPgogICAgPGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-code-check: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBzaGFwZS1yZW5kZXJpbmc9Imdlb21ldHJpY1ByZWNpc2lvbiI+CiAgICA8cGF0aCBkPSJNNi41OSwzLjQxTDIsOEw2LjU5LDEyLjZMOCwxMS4xOEw0LjgyLDhMOCw0LjgyTDYuNTksMy40MU0xMi40MSwzLjQxTDExLDQuODJMMTQuMTgsOEwxMSwxMS4xOEwxMi40MSwxMi42TDE3LDhMMTIuNDEsMy40MU0yMS41OSwxMS41OUwxMy41LDE5LjY4TDkuODMsMTZMOC40MiwxNy40MUwxMy41LDIyLjVMMjMsMTNMMjEuNTksMTEuNTlaIiAvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-code: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyOCAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTExLjQgMTguNkw2LjggMTRMMTEuNCA5LjRMMTAgOEw0IDE0TDEwIDIwTDExLjQgMTguNlpNMTYuNiAxOC42TDIxLjIgMTRMMTYuNiA5LjRMMTggOEwyNCAxNEwxOCAyMEwxNi42IDE4LjZWMTguNloiLz4KCTwvZz4KPC9zdmc+Cg==);
  --jp-icon-collapse-all: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGgKICAgICAgICAgICAgZD0iTTggMmMxIDAgMTEgMCAxMiAwczIgMSAyIDJjMCAxIDAgMTEgMCAxMnMwIDItMiAyQzIwIDE0IDIwIDQgMjAgNFMxMCA0IDYgNGMwLTIgMS0yIDItMnoiIC8+CiAgICAgICAgPHBhdGgKICAgICAgICAgICAgZD0iTTE4IDhjMC0xLTEtMi0yLTJTNSA2IDQgNnMtMiAxLTIgMmMwIDEgMCAxMSAwIDEyczEgMiAyIDJjMSAwIDExIDAgMTIgMHMyLTEgMi0yYzAtMSAwLTExIDAtMTJ6bS0yIDB2MTJINFY4eiIgLz4KICAgICAgICA8cGF0aCBkPSJNNiAxM3YyaDh2LTJ6IiAvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-console: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwMCAyMDAiPgogIDxnIGNsYXNzPSJqcC1jb25zb2xlLWljb24tYmFja2dyb3VuZC1jb2xvciBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMjg4RDEiPgogICAgPHBhdGggZD0iTTIwIDE5LjhoMTYwdjE1OS45SDIweiIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtY29uc29sZS1pY29uLWNvbG9yIGpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIiBmaWxsPSIjZmZmIj4KICAgIDxwYXRoIGQ9Ik0xMDUgMTI3LjNoNDB2MTIuOGgtNDB6TTUxLjEgNzdMNzQgOTkuOWwtMjMuMyAyMy4zIDEwLjUgMTAuNSAyMy4zLTIzLjNMOTUgOTkuOSA4NC41IDg5LjQgNjEuNiA2Ni41eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-copy: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTExLjksMUgzLjJDMi40LDEsMS43LDEuNywxLjcsMi41djEwLjJoMS41VjIuNWg4LjdWMXogTTE0LjEsMy45aC04Yy0wLjgsMC0xLjUsMC43LTEuNSwxLjV2MTAuMmMwLDAuOCwwLjcsMS41LDEuNSwxLjVoOCBjMC44LDAsMS41LTAuNywxLjUtMS41VjUuNEMxNS41LDQuNiwxNC45LDMuOSwxNC4xLDMuOXogTTE0LjEsMTUuNWgtOFY1LjRoOFYxNS41eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-copyright: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGVuYWJsZS1iYWNrZ3JvdW5kPSJuZXcgMCAwIDI0IDI0IiBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCI+CiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0xMS44OCw5LjE0YzEuMjgsMC4wNiwxLjYxLDEuMTUsMS42MywxLjY2aDEuNzljLTAuMDgtMS45OC0xLjQ5LTMuMTktMy40NS0zLjE5QzkuNjQsNy42MSw4LDksOCwxMi4xNCBjMCwxLjk0LDAuOTMsNC4yNCwzLjg0LDQuMjRjMi4yMiwwLDMuNDEtMS42NSwzLjQ0LTIuOTVoLTEuNzljLTAuMDMsMC41OS0wLjQ1LDEuMzgtMS42MywxLjQ0QzEwLjU1LDE0LjgzLDEwLDEzLjgxLDEwLDEyLjE0IEMxMCw5LjI1LDExLjI4LDkuMTYsMTEuODgsOS4xNHogTTEyLDJDNi40OCwyLDIsNi40OCwyLDEyczQuNDgsMTAsMTAsMTBzMTAtNC40OCwxMC0xMFMxNy41MiwyLDEyLDJ6IE0xMiwyMGMtNC40MSwwLTgtMy41OS04LTggczMuNTktOCw4LThzOCwzLjU5LDgsOFMxNi40MSwyMCwxMiwyMHoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-cut: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkuNjQgNy42NGMuMjMtLjUuMzYtMS4wNS4zNi0xLjY0IDAtMi4yMS0xLjc5LTQtNC00UzIgMy43OSAyIDZzMS43OSA0IDQgNGMuNTkgMCAxLjE0LS4xMyAxLjY0LS4zNkwxMCAxMmwtMi4zNiAyLjM2QzcuMTQgMTQuMTMgNi41OSAxNCA2IDE0Yy0yLjIxIDAtNCAxLjc5LTQgNHMxLjc5IDQgNCA0IDQtMS43OSA0LTRjMC0uNTktLjEzLTEuMTQtLjM2LTEuNjRMMTIgMTRsNyA3aDN2LTFMOS42NCA3LjY0ek02IDhjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTAgMTJjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTYtNy41Yy0uMjggMC0uNS0uMjItLjUtLjVzLjIyLS41LjUtLjUuNS4yMi41LjUtLjIyLjUtLjUuNXpNMTkgM2wtNiA2IDIgMiA3LTdWM3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-delete: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2cHgiIGhlaWdodD0iMTZweCI+CiAgICA8cGF0aCBkPSJNMCAwaDI0djI0SDB6IiBmaWxsPSJub25lIiAvPgogICAgPHBhdGggY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjI2MjYyIiBkPSJNNiAxOWMwIDEuMS45IDIgMiAyaDhjMS4xIDAgMi0uOSAyLTJWN0g2djEyek0xOSA0aC0zLjVsLTEtMWgtNWwtMSAxSDV2MmgxNFY0eiIgLz4KPC9zdmc+Cg==);
  --jp-icon-download: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDloLTRWM0g5djZINWw3IDcgNy03ek01IDE4djJoMTR2LTJINXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-duplicate: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiIGNsaXAtcnVsZT0iZXZlbm9kZCIgZD0iTTIuNzk5OTggMC44NzVIOC44OTU4MkM5LjIwMDYxIDAuODc1IDkuNDQ5OTggMS4xMzkxNCA5LjQ0OTk4IDEuNDYxOThDOS40NDk5OCAxLjc4NDgyIDkuMjAwNjEgMi4wNDg5NiA4Ljg5NTgyIDIuMDQ4OTZIMy4zNTQxNUMzLjA0OTM2IDIuMDQ4OTYgMi43OTk5OCAyLjMxMzEgMi43OTk5OCAyLjYzNTk0VjkuNjc5NjlDMi43OTk5OCAxMC4wMDI1IDIuNTUwNjEgMTAuMjY2NyAyLjI0NTgyIDEwLjI2NjdDMS45NDEwMyAxMC4yNjY3IDEuNjkxNjUgMTAuMDAyNSAxLjY5MTY1IDkuNjc5NjlWMi4wNDg5NkMxLjY5MTY1IDEuNDAzMjggMi4xOTA0IDAuODc1IDIuNzk5OTggMC44NzVaTTUuMzY2NjUgMTEuOVY0LjU1SDExLjA4MzNWMTEuOUg1LjM2NjY1Wk00LjE0MTY1IDQuMTQxNjdDNC4xNDE2NSAzLjY5MDYzIDQuNTA3MjggMy4zMjUgNC45NTgzMiAzLjMyNUgxMS40OTE3QzExLjk0MjcgMy4zMjUgMTIuMzA4MyAzLjY5MDYzIDEyLjMwODMgNC4xNDE2N1YxMi4zMDgzQzEyLjMwODMgMTIuNzU5NCAxMS45NDI3IDEzLjEyNSAxMS40OTE3IDEzLjEyNUg0Ljk1ODMyQzQuNTA3MjggMTMuMTI1IDQuMTQxNjUgMTIuNzU5NCA0LjE0MTY1IDEyLjMwODNWNC4xNDE2N1oiIGZpbGw9IiM2MTYxNjEiLz4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBkPSJNOS40MzU3NCA4LjI2NTA3SDguMzY0MzFWOS4zMzY1QzguMzY0MzEgOS40NTQzNSA4LjI2Nzg4IDkuNTUwNzggOC4xNTAwMiA5LjU1MDc4QzguMDMyMTcgOS41NTA3OCA3LjkzNTc0IDkuNDU0MzUgNy45MzU3NCA5LjMzNjVWOC4yNjUwN0g2Ljg2NDMxQzYuNzQ2NDUgOC4yNjUwNyA2LjY1MDAyIDguMTY4NjQgNi42NTAwMiA4LjA1MDc4QzYuNjUwMDIgNy45MzI5MiA2Ljc0NjQ1IDcuODM2NSA2Ljg2NDMxIDcuODM2NUg3LjkzNTc0VjYuNzY1MDdDNy45MzU3NCA2LjY0NzIxIDguMDMyMTcgNi41NTA3OCA4LjE1MDAyIDYuNTUwNzhDOC4yNjc4OCA2LjU1MDc4IDguMzY0MzEgNi42NDcyMSA4LjM2NDMxIDYuNzY1MDdWNy44MzY1SDkuNDM1NzRDOS41NTM2IDcuODM2NSA5LjY1MDAyIDcuOTMyOTIgOS42NTAwMiA4LjA1MDc4QzkuNjUwMDIgOC4xNjg2NCA5LjU1MzYgOC4yNjUwNyA5LjQzNTc0IDguMjY1MDdaIiBmaWxsPSIjNjE2MTYxIiBzdHJva2U9IiM2MTYxNjEiIHN0cm9rZS13aWR0aD0iMC41Ii8+Cjwvc3ZnPgo=);
  --jp-icon-edit: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMgMTcuMjVWMjFoMy43NUwxNy44MSA5Ljk0bC0zLjc1LTMuNzVMMyAxNy4yNXpNMjAuNzEgNy4wNGMuMzktLjM5LjM5LTEuMDIgMC0xLjQxbC0yLjM0LTIuMzRjLS4zOS0uMzktMS4wMi0uMzktMS40MSAwbC0xLjgzIDEuODMgMy43NSAzLjc1IDEuODMtMS44M3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-ellipses: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iNSIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxOSIgY3k9IjEyIiByPSIyIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-error: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj48Y2lyY2xlIGN4PSIxMiIgY3k9IjE5IiByPSIyIi8+PHBhdGggZD0iTTEwIDNoNHYxMmgtNHoiLz48L2c+CjxwYXRoIGZpbGw9Im5vbmUiIGQ9Ik0wIDBoMjR2MjRIMHoiLz4KPC9zdmc+Cg==);
  --jp-icon-expand-all: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGgKICAgICAgICAgICAgZD0iTTggMmMxIDAgMTEgMCAxMiAwczIgMSAyIDJjMCAxIDAgMTEgMCAxMnMwIDItMiAyQzIwIDE0IDIwIDQgMjAgNFMxMCA0IDYgNGMwLTIgMS0yIDItMnoiIC8+CiAgICAgICAgPHBhdGgKICAgICAgICAgICAgZD0iTTE4IDhjMC0xLTEtMi0yLTJTNSA2IDQgNnMtMiAxLTIgMmMwIDEgMCAxMSAwIDEyczEgMiAyIDJjMSAwIDExIDAgMTIgMHMyLTEgMi0yYzAtMSAwLTExIDAtMTJ6bS0yIDB2MTJINFY4eiIgLz4KICAgICAgICA8cGF0aCBkPSJNMTEgMTBIOXYzSDZ2MmgzdjNoMnYtM2gzdi0yaC0zeiIgLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-extension: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwLjUgMTFIMTlWN2MwLTEuMS0uOS0yLTItMmgtNFYzLjVDMTMgMi4xMiAxMS44OCAxIDEwLjUgMVM4IDIuMTIgOCAzLjVWNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAydjMuOEgzLjVjMS40OSAwIDIuNyAxLjIxIDIuNyAyLjdzLTEuMjEgMi43LTIuNyAyLjdIMlYyMGMwIDEuMS45IDIgMiAyaDMuOHYtMS41YzAtMS40OSAxLjIxLTIuNyAyLjctMi43IDEuNDkgMCAyLjcgMS4yMSAyLjcgMi43VjIySDE3YzEuMSAwIDItLjkgMi0ydi00aDEuNWMxLjM4IDAgMi41LTEuMTIgMi41LTIuNVMyMS44OCAxMSAyMC41IDExeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-fast-forward: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTQgMThsOC41LTZMNCA2djEyem05LTEydjEybDguNS02TDEzIDZ6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-file-upload: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkgMTZoNnYtNmg0bC03LTctNyA3aDR6bS00IDJoMTR2Mkg1eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-file: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuMyA4LjJsLTUuNS01LjVjLS4zLS4zLS43LS41LTEuMi0uNUgzLjljLS44LjEtMS42LjktMS42IDEuOHYxNC4xYzAgLjkuNyAxLjYgMS42IDEuNmgxNC4yYy45IDAgMS42LS43IDEuNi0xLjZWOS40Yy4xLS41LS4xLS45LS40LTEuMnptLTUuOC0zLjNsMy40IDMuNmgtMy40VjQuOXptMy45IDEyLjdINC43Yy0uMSAwLS4yIDAtLjItLjJWNC43YzAtLjIuMS0uMy4yLS4zaDcuMnY0LjRzMCAuOC4zIDEuMWMuMy4zIDEuMS4zIDEuMS4zaDQuM3Y3LjJzLS4xLjItLjIuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-filter-dot: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTE0LDEyVjE5Ljg4QzE0LjA0LDIwLjE4IDEzLjk0LDIwLjUgMTMuNzEsMjAuNzFDMTMuMzIsMjEuMSAxMi42OSwyMS4xIDEyLjMsMjAuNzFMMTAuMjksMTguN0MxMC4wNiwxOC40NyA5Ljk2LDE4LjE2IDEwLDE3Ljg3VjEySDkuOTdMNC4yMSw0LjYyQzMuODcsNC4xOSAzLjk1LDMuNTYgNC4zOCwzLjIyQzQuNTcsMy4wOCA0Ljc4LDMgNSwzVjNIMTlWM0MxOS4yMiwzIDE5LjQzLDMuMDggMTkuNjIsMy4yMkMyMC4wNSwzLjU2IDIwLjEzLDQuMTkgMTkuNzksNC42MkwxNC4wMywxMkgxNFoiIC8+CiAgPC9nPgogIDxnIGNsYXNzPSJqcC1pY29uLWRvdCIgZmlsbD0iI0ZGRiI+CiAgICA8Y2lyY2xlIGN4PSIxOCIgY3k9IjE3IiByPSIzIj48L2NpcmNsZT4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-filter-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEwIDE4aDR2LTJoLTR2MnpNMyA2djJoMThWNkgzem0zIDdoMTJ2LTJINnYyeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-filter: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTE0LDEyVjE5Ljg4QzE0LjA0LDIwLjE4IDEzLjk0LDIwLjUgMTMuNzEsMjAuNzFDMTMuMzIsMjEuMSAxMi42OSwyMS4xIDEyLjMsMjAuNzFMMTAuMjksMTguN0MxMC4wNiwxOC40NyA5Ljk2LDE4LjE2IDEwLDE3Ljg3VjEySDkuOTdMNC4yMSw0LjYyQzMuODcsNC4xOSAzLjk1LDMuNTYgNC4zOCwzLjIyQzQuNTcsMy4wOCA0Ljc4LDMgNSwzVjNIMTlWM0MxOS4yMiwzIDE5LjQzLDMuMDggMTkuNjIsMy4yMkMyMC4wNSwzLjU2IDIwLjEzLDQuMTkgMTkuNzksNC42MkwxNC4wMywxMkgxNFoiIC8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-folder-favorite: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMjRweCIgdmlld0JveD0iMCAwIDI0IDI0IiB3aWR0aD0iMjRweCIgZmlsbD0iIzAwMDAwMCI+CiAgPHBhdGggZD0iTTAgMGgyNHYyNEgwVjB6IiBmaWxsPSJub25lIi8+PHBhdGggY2xhc3M9ImpwLWljb24zIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzYxNjE2MSIgZD0iTTIwIDZoLThsLTItMkg0Yy0xLjEgMC0yIC45LTIgMnYxMmMwIDEuMS45IDIgMiAyaDE2YzEuMSAwIDItLjkgMi0yVjhjMC0xLjEtLjktMi0yLTJ6bS0yLjA2IDExTDE1IDE1LjI4IDEyLjA2IDE3bC43OC0zLjMzLTIuNTktMi4yNCAzLjQxLS4yOUwxNSA4bDEuMzQgMy4xNCAzLjQxLjI5LTIuNTkgMi4yNC43OCAzLjMzeiIvPgo8L3N2Zz4K);
  --jp-icon-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY4YzAtMS4xLS45LTItMi0yaC04bC0yLTJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-home: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMjRweCIgdmlld0JveD0iMCAwIDI0IDI0IiB3aWR0aD0iMjRweCIgZmlsbD0iIzAwMDAwMCI+CiAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPjxwYXRoIGNsYXNzPSJqcC1pY29uMyBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xMCAyMHYtNmg0djZoNXYtOGgzTDEyIDMgMiAxMmgzdjh6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-html5: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMDAiIGQ9Ik0xMDguNCAwaDIzdjIyLjhoMjEuMlYwaDIzdjY5aC0yM1Y0NmgtMjF2MjNoLTIzLjJNMjA2IDIzaC0yMC4zVjBoNjMuN3YyM0gyMjl2NDZoLTIzbTUzLjUtNjloMjQuMWwxNC44IDI0LjNMMzEzLjIgMGgyNC4xdjY5aC0yM1YzNC44bC0xNi4xIDI0LjgtMTYuMS0yNC44VjY5aC0yMi42bTg5LjItNjloMjN2NDYuMmgzMi42VjY5aC01NS42Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI2U0NGQyNiIgZD0iTTEwNy42IDQ3MWwtMzMtMzcwLjRoMzYyLjhsLTMzIDM3MC4yTDI1NS43IDUxMiIvPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNmMTY1MjkiIGQ9Ik0yNTYgNDgwLjVWMTMxaDE0OC4zTDM3NiA0NDciLz4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNlYmViZWIiIGQ9Ik0xNDIgMTc2LjNoMTE0djQ1LjRoLTY0LjJsNC4yIDQ2LjVoNjB2NDUuM0gxNTQuNG0yIDIyLjhIMjAybDMuMiAzNi4zIDUwLjggMTMuNnY0Ny40bC05My4yLTI2Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIiBmaWxsPSIjZmZmIiBkPSJNMzY5LjYgMTc2LjNIMjU1Ljh2NDUuNGgxMDkuNm0tNC4xIDQ2LjVIMjU1Ljh2NDUuNGg1NmwtNS4zIDU5LTUwLjcgMTMuNnY0Ny4ybDkzLTI1LjgiLz4KPC9zdmc+Cg==);
  --jp-icon-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1icmFuZDQganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNGRkYiIGQ9Ik0yLjIgMi4yaDE3LjV2MTcuNUgyLjJ6Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzNGNTFCNSIgZD0iTTIuMiAyLjJ2MTcuNWgxNy41bC4xLTE3LjVIMi4yem0xMi4xIDIuMmMxLjIgMCAyLjIgMSAyLjIgMi4ycy0xIDIuMi0yLjIgMi4yLTIuMi0xLTIuMi0yLjIgMS0yLjIgMi4yLTIuMnpNNC40IDE3LjZsMy4zLTguOCAzLjMgNi42IDIuMi0zLjIgNC40IDUuNEg0LjR6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-info: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUwLjk3OCA1MC45NzgiPgoJPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KCQk8cGF0aCBkPSJNNDMuNTIsNy40NThDMzguNzExLDIuNjQ4LDMyLjMwNywwLDI1LjQ4OSwwQzE4LjY3LDAsMTIuMjY2LDIuNjQ4LDcuNDU4LDcuNDU4CgkJCWMtOS45NDMsOS45NDEtOS45NDMsMjYuMTE5LDAsMzYuMDYyYzQuODA5LDQuODA5LDExLjIxMiw3LjQ1NiwxOC4wMzEsNy40NThjMCwwLDAuMDAxLDAsMC4wMDIsMAoJCQljNi44MTYsMCwxMy4yMjEtMi42NDgsMTguMDI5LTcuNDU4YzQuODA5LTQuODA5LDcuNDU3LTExLjIxMiw3LjQ1Ny0xOC4wM0M1MC45NzcsMTguNjcsNDguMzI4LDEyLjI2Niw0My41Miw3LjQ1OHoKCQkJIE00Mi4xMDYsNDIuMTA1Yy00LjQzMiw0LjQzMS0xMC4zMzIsNi44NzItMTYuNjE1LDYuODcyaC0wLjAwMmMtNi4yODUtMC4wMDEtMTIuMTg3LTIuNDQxLTE2LjYxNy02Ljg3MgoJCQljLTkuMTYyLTkuMTYzLTkuMTYyLTI0LjA3MSwwLTMzLjIzM0MxMy4zMDMsNC40NCwxOS4yMDQsMiwyNS40ODksMmM2LjI4NCwwLDEyLjE4NiwyLjQ0LDE2LjYxNyw2Ljg3MgoJCQljNC40MzEsNC40MzEsNi44NzEsMTAuMzMyLDYuODcxLDE2LjYxN0M0OC45NzcsMzEuNzcyLDQ2LjUzNiwzNy42NzUsNDIuMTA2LDQyLjEwNXoiLz4KCQk8cGF0aCBkPSJNMjMuNTc4LDMyLjIxOGMtMC4wMjMtMS43MzQsMC4xNDMtMy4wNTksMC40OTYtMy45NzJjMC4zNTMtMC45MTMsMS4xMS0xLjk5NywyLjI3Mi0zLjI1MwoJCQljMC40NjgtMC41MzYsMC45MjMtMS4wNjIsMS4zNjctMS41NzVjMC42MjYtMC43NTMsMS4xMDQtMS40NzgsMS40MzYtMi4xNzVjMC4zMzEtMC43MDcsMC40OTUtMS41NDEsMC40OTUtMi41CgkJCWMwLTEuMDk2LTAuMjYtMi4wODgtMC43NzktMi45NzljLTAuNTY1LTAuODc5LTEuNTAxLTEuMzM2LTIuODA2LTEuMzY5Yy0xLjgwMiwwLjA1Ny0yLjk4NSwwLjY2Ny0zLjU1LDEuODMyCgkJCWMtMC4zMDEsMC41MzUtMC41MDMsMS4xNDEtMC42MDcsMS44MTRjLTAuMTM5LDAuNzA3LTAuMjA3LDEuNDMyLTAuMjA3LDIuMTc0aC0yLjkzN2MtMC4wOTEtMi4yMDgsMC40MDctNC4xMTQsMS40OTMtNS43MTkKCQkJYzEuMDYyLTEuNjQsMi44NTUtMi40ODEsNS4zNzgtMi41MjdjMi4xNiwwLjAyMywzLjg3NCwwLjYwOCw1LjE0MSwxLjc1OGMxLjI3OCwxLjE2LDEuOTI5LDIuNzY0LDEuOTUsNC44MTEKCQkJYzAsMS4xNDItMC4xMzcsMi4xMTEtMC40MSwyLjkxMWMtMC4zMDksMC44NDUtMC43MzEsMS41OTMtMS4yNjgsMi4yNDNjLTAuNDkyLDAuNjUtMS4wNjgsMS4zMTgtMS43MywyLjAwMgoJCQljLTAuNjUsMC42OTctMS4zMTMsMS40NzktMS45ODcsMi4zNDZjLTAuMjM5LDAuMzc3LTAuNDI5LDAuNzc3LTAuNTY1LDEuMTk5Yy0wLjE2LDAuOTU5LTAuMjE3LDEuOTUxLTAuMTcxLDIuOTc5CgkJCUMyNi41ODksMzIuMjE4LDIzLjU3OCwzMi4yMTgsMjMuNTc4LDMyLjIxOHogTTIzLjU3OCwzOC4yMnYtMy40ODRoMy4wNzZ2My40ODRIMjMuNTc4eiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-inspector: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaW5zcGVjdG9yLWljb24tY29sb3IganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY2YzAtMS4xLS45LTItMi0yem0tNSAxNEg0di00aDExdjR6bTAtNUg0VjloMTF2NHptNSA1aC00VjloNHY5eiIvPgo8L3N2Zz4K);
  --jp-icon-json: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtanNvbi1pY29uLWNvbG9yIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI0Y5QTgyNSI+CiAgICA8cGF0aCBkPSJNMjAuMiAxMS44Yy0xLjYgMC0xLjcuNS0xLjcgMSAwIC40LjEuOS4xIDEuMy4xLjUuMS45LjEgMS4zIDAgMS43LTEuNCAyLjMtMy41IDIuM2gtLjl2LTEuOWguNWMxLjEgMCAxLjQgMCAxLjQtLjggMC0uMyAwLS42LS4xLTEgMC0uNC0uMS0uOC0uMS0xLjIgMC0xLjMgMC0xLjggMS4zLTItMS4zLS4yLTEuMy0uNy0xLjMtMiAwLS40LjEtLjguMS0xLjIuMS0uNC4xLS43LjEtMSAwLS44LS40LS43LTEuNC0uOGgtLjVWNC4xaC45YzIuMiAwIDMuNS43IDMuNSAyLjMgMCAuNC0uMS45LS4xIDEuMy0uMS41LS4xLjktLjEgMS4zIDAgLjUuMiAxIDEuNyAxdjEuOHpNMS44IDEwLjFjMS42IDAgMS43LS41IDEuNy0xIDAtLjQtLjEtLjktLjEtMS4zLS4xLS41LS4xLS45LS4xLTEuMyAwLTEuNiAxLjQtMi4zIDMuNS0yLjNoLjl2MS45aC0uNWMtMSAwLTEuNCAwLTEuNC44IDAgLjMgMCAuNi4xIDEgMCAuMi4xLjYuMSAxIDAgMS4zIDAgMS44LTEuMyAyQzYgMTEuMiA2IDExLjcgNiAxM2MwIC40LS4xLjgtLjEgMS4yLS4xLjMtLjEuNy0uMSAxIDAgLjguMy44IDEuNC44aC41djEuOWgtLjljLTIuMSAwLTMuNS0uNi0zLjUtMi4zIDAtLjQuMS0uOS4xLTEuMy4xLS41LjEtLjkuMS0xLjMgMC0uNS0uMi0xLTEuNy0xdi0xLjl6Ii8+CiAgICA8Y2lyY2xlIGN4PSIxMSIgY3k9IjEzLjgiIHI9IjIuMSIvPgogICAgPGNpcmNsZSBjeD0iMTEiIGN5PSI4LjIiIHI9IjIuMSIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-julia: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDMyNSAzMDAiPgogIDxnIGNsYXNzPSJqcC1icmFuZDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjY2IzYzMzIj4KICAgIDxwYXRoIGQ9Ik0gMTUwLjg5ODQzOCAyMjUgQyAxNTAuODk4NDM4IDI2Ni40MjE4NzUgMTE3LjMyMDMxMiAzMDAgNzUuODk4NDM4IDMwMCBDIDM0LjQ3NjU2MiAzMDAgMC44OTg0MzggMjY2LjQyMTg3NSAwLjg5ODQzOCAyMjUgQyAwLjg5ODQzOCAxODMuNTc4MTI1IDM0LjQ3NjU2MiAxNTAgNzUuODk4NDM4IDE1MCBDIDExNy4zMjAzMTIgMTUwIDE1MC44OTg0MzggMTgzLjU3ODEyNSAxNTAuODk4NDM4IDIyNSIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzM4OTgyNiI+CiAgICA8cGF0aCBkPSJNIDIzNy41IDc1IEMgMjM3LjUgMTE2LjQyMTg3NSAyMDMuOTIxODc1IDE1MCAxNjIuNSAxNTAgQyAxMjEuMDc4MTI1IDE1MCA4Ny41IDExNi40MjE4NzUgODcuNSA3NSBDIDg3LjUgMzMuNTc4MTI1IDEyMS4wNzgxMjUgMCAxNjIuNSAwIEMgMjAzLjkyMTg3NSAwIDIzNy41IDMzLjU3ODEyNSAyMzcuNSA3NSIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzk1NThiMiI+CiAgICA8cGF0aCBkPSJNIDMyNC4xMDE1NjIgMjI1IEMgMzI0LjEwMTU2MiAyNjYuNDIxODc1IDI5MC41MjM0MzggMzAwIDI0OS4xMDE1NjIgMzAwIEMgMjA3LjY3OTY4OCAzMDAgMTc0LjEwMTU2MiAyNjYuNDIxODc1IDE3NC4xMDE1NjIgMjI1IEMgMTc0LjEwMTU2MiAxODMuNTc4MTI1IDIwNy42Nzk2ODggMTUwIDI0OS4xMDE1NjIgMTUwIEMgMjkwLjUyMzQzOCAxNTAgMzI0LjEwMTU2MiAxODMuNTc4MTI1IDMyNC4xMDE1NjIgMjI1Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-jupyter-favicon: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTUyIiBoZWlnaHQ9IjE2NSIgdmlld0JveD0iMCAwIDE1MiAxNjUiIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgPGcgY2xhc3M9ImpwLWp1cHl0ZXItaWNvbi1jb2xvciIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA3ODk0NywgMTEwLjU4MjkyNykiIGQ9Ik03NS45NDIyODQyLDI5LjU4MDQ1NjEgQzQzLjMwMjM5NDcsMjkuNTgwNDU2MSAxNC43OTY3ODMyLDE3LjY1MzQ2MzQgMCwwIEM1LjUxMDgzMjExLDE1Ljg0MDY4MjkgMTUuNzgxNTM4OSwyOS41NjY3NzMyIDI5LjM5MDQ5NDcsMzkuMjc4NDE3MSBDNDIuOTk5Nyw0OC45ODk4NTM3IDU5LjI3MzcsNTQuMjA2NzgwNSA3NS45NjA1Nzg5LDU0LjIwNjc4MDUgQzkyLjY0NzQ1NzksNTQuMjA2NzgwNSAxMDguOTIxNDU4LDQ4Ljk4OTg1MzcgMTIyLjUzMDY2MywzOS4yNzg0MTcxIEMxMzYuMTM5NDUzLDI5LjU2Njc3MzIgMTQ2LjQxMDI4NCwxNS44NDA2ODI5IDE1MS45MjExNTgsMCBDMTM3LjA4Nzg2OCwxNy42NTM0NjM0IDEwOC41ODI1ODksMjkuNTgwNDU2MSA3NS45NDIyODQyLDI5LjU4MDQ1NjEgTDc1Ljk0MjI4NDIsMjkuNTgwNDU2MSBaIiAvPgogICAgPHBhdGggdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMzczNjgsIDAuNzA0ODc4KSIgZD0iTTc1Ljk3ODQ1NzksMjQuNjI2NDA3MyBDMTA4LjYxODc2MywyNC42MjY0MDczIDEzNy4xMjQ0NTgsMzYuNTUzNDQxNSAxNTEuOTIxMTU4LDU0LjIwNjc4MDUgQzE0Ni40MTAyODQsMzguMzY2MjIyIDEzNi4xMzk0NTMsMjQuNjQwMTMxNyAxMjIuNTMwNjYzLDE0LjkyODQ4NzggQzEwOC45MjE0NTgsNS4yMTY4NDM5IDkyLjY0NzQ1NzksMCA3NS45NjA1Nzg5LDAgQzU5LjI3MzcsMCA0Mi45OTk3LDUuMjE2ODQzOSAyOS4zOTA0OTQ3LDE0LjkyODQ4NzggQzE1Ljc4MTUzODksMjQuNjQwMTMxNyA1LjUxMDgzMjExLDM4LjM2NjIyMiAwLDU0LjIwNjc4MDUgQzE0LjgzMzA4MTYsMzYuNTg5OTI5MyA0My4zMzg1Njg0LDI0LjYyNjQwNzMgNzUuOTc4NDU3OSwyNC42MjY0MDczIEw3NS45Nzg0NTc5LDI0LjYyNjQwNzMgWiIgLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzkiIGhlaWdodD0iNTEiIHZpZXdCb3g9IjAgMCAzOSA1MSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMTYzOCAtMjI4MSkiPgogICAgIDxnIGNsYXNzPSJqcC1qdXB5dGVyLWljb24tY29sb3IiIGZpbGw9IiNGMzc3MjYiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5Ljc0IDIzMTEuOTgpIiBkPSJNIDE4LjI2NDYgNy4xMzQxMUMgMTAuNDE0NSA3LjEzNDExIDMuNTU4NzIgNC4yNTc2IDAgMEMgMS4zMjUzOSAzLjgyMDQgMy43OTU1NiA3LjEzMDgxIDcuMDY4NiA5LjQ3MzAzQyAxMC4zNDE3IDExLjgxNTIgMTQuMjU1NyAxMy4wNzM0IDE4LjI2OSAxMy4wNzM0QyAyMi4yODIzIDEzLjA3MzQgMjYuMTk2MyAxMS44MTUyIDI5LjQ2OTQgOS40NzMwM0MgMzIuNzQyNCA3LjEzMDgxIDM1LjIxMjYgMy44MjA0IDM2LjUzOCAwQyAzMi45NzA1IDQuMjU3NiAyNi4xMTQ4IDcuMTM0MTEgMTguMjY0NiA3LjEzNDExWiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5LjczIDIyODUuNDgpIiBkPSJNIDE4LjI3MzMgNS45MzkzMUMgMjYuMTIzNSA1LjkzOTMxIDMyLjk3OTMgOC44MTU4MyAzNi41MzggMTMuMDczNEMgMzUuMjEyNiA5LjI1MzAzIDMyLjc0MjQgNS45NDI2MiAyOS40Njk0IDMuNjAwNEMgMjYuMTk2MyAxLjI1ODE4IDIyLjI4MjMgMCAxOC4yNjkgMEMgMTQuMjU1NyAwIDEwLjM0MTcgMS4yNTgxOCA3LjA2ODYgMy42MDA0QyAzLjc5NTU2IDUuOTQyNjIgMS4zMjUzOSA5LjI1MzAzIDAgMTMuMDczNEMgMy41Njc0NSA4LjgyNDYzIDEwLjQyMzIgNS45MzkzMSAxOC4yNzMzIDUuOTM5MzFaIi8+CiAgICA8L2c+CiAgICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjY5LjMgMjI4MS4zMSkiIGQ9Ik0gNS44OTM1MyAyLjg0NEMgNS45MTg4OSAzLjQzMTY1IDUuNzcwODUgNC4wMTM2NyA1LjQ2ODE1IDQuNTE2NDVDIDUuMTY1NDUgNS4wMTkyMiA0LjcyMTY4IDUuNDIwMTUgNC4xOTI5OSA1LjY2ODUxQyAzLjY2NDMgNS45MTY4OCAzLjA3NDQ0IDYuMDAxNTEgMi40OTgwNSA1LjkxMTcxQyAxLjkyMTY2IDUuODIxOSAxLjM4NDYzIDUuNTYxNyAwLjk1NDg5OCA1LjE2NDAxQyAwLjUyNTE3IDQuNzY2MzMgMC4yMjIwNTYgNC4yNDkwMyAwLjA4MzkwMzcgMy42Nzc1N0MgLTAuMDU0MjQ4MyAzLjEwNjExIC0wLjAyMTIzIDIuNTA2MTcgMC4xNzg3ODEgMS45NTM2NEMgMC4zNzg3OTMgMS40MDExIDAuNzM2ODA5IDAuOTIwODE3IDEuMjA3NTQgMC41NzM1MzhDIDEuNjc4MjYgMC4yMjYyNTkgMi4yNDA1NSAwLjAyNzU5MTkgMi44MjMyNiAwLjAwMjY3MjI5QyAzLjYwMzg5IC0wLjAzMDcxMTUgNC4zNjU3MyAwLjI0OTc4OSA0Ljk0MTQyIDAuNzgyNTUxQyA1LjUxNzExIDEuMzE1MzEgNS44NTk1NiAyLjA1Njc2IDUuODkzNTMgMi44NDRaIi8+CiAgICAgIDxwYXRoIHRyYW5zZm9ybT0idHJhbnNsYXRlKDE2MzkuOCAyMzIzLjgxKSIgZD0iTSA3LjQyNzg5IDMuNTgzMzhDIDcuNDYwMDggNC4zMjQzIDcuMjczNTUgNS4wNTgxOSA2Ljg5MTkzIDUuNjkyMTNDIDYuNTEwMzEgNi4zMjYwNyA1Ljk1MDc1IDYuODMxNTYgNS4yODQxMSA3LjE0NDZDIDQuNjE3NDcgNy40NTc2MyAzLjg3MzcxIDcuNTY0MTQgMy4xNDcwMiA3LjQ1MDYzQyAyLjQyMDMyIDcuMzM3MTIgMS43NDMzNiA3LjAwODcgMS4yMDE4NCA2LjUwNjk1QyAwLjY2MDMyOCA2LjAwNTIgMC4yNzg2MSA1LjM1MjY4IDAuMTA1MDE3IDQuNjMyMDJDIC0wLjA2ODU3NTcgMy45MTEzNSAtMC4wMjYyMzYxIDMuMTU0OTQgMC4yMjY2NzUgMi40NTg1NkMgMC40Nzk1ODcgMS43NjIxNyAwLjkzMTY5NyAxLjE1NzEzIDEuNTI1NzYgMC43MjAwMzNDIDIuMTE5ODMgMC4yODI5MzUgMi44MjkxNCAwLjAzMzQzOTUgMy41NjM4OSAwLjAwMzEzMzQ0QyA0LjU0NjY3IC0wLjAzNzQwMzMgNS41MDUyOSAwLjMxNjcwNiA2LjIyOTYxIDAuOTg3ODM1QyA2Ljk1MzkzIDEuNjU4OTYgNy4zODQ4NCAyLjU5MjM1IDcuNDI3ODkgMy41ODMzOEwgNy40Mjc4OSAzLjU4MzM4WiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM4LjM2IDIyODYuMDYpIiBkPSJNIDIuMjc0NzEgNC4zOTYyOUMgMS44NDM2MyA0LjQxNTA4IDEuNDE2NzEgNC4zMDQ0NSAxLjA0Nzk5IDQuMDc4NDNDIDAuNjc5MjY4IDMuODUyNCAwLjM4NTMyOCAzLjUyMTE0IDAuMjAzMzcxIDMuMTI2NTZDIDAuMDIxNDEzNiAyLjczMTk4IC0wLjA0MDM3OTggMi4yOTE4MyAwLjAyNTgxMTYgMS44NjE4MUMgMC4wOTIwMDMxIDEuNDMxOCAwLjI4MzIwNCAxLjAzMTI2IDAuNTc1MjEzIDAuNzEwODgzQyAwLjg2NzIyMiAwLjM5MDUxIDEuMjQ2OTEgMC4xNjQ3MDggMS42NjYyMiAwLjA2MjA1OTJDIDIuMDg1NTMgLTAuMDQwNTg5NyAyLjUyNTYxIC0wLjAxNTQ3MTQgMi45MzA3NiAwLjEzNDIzNUMgMy4zMzU5MSAwLjI4Mzk0MSAzLjY4NzkyIDAuNTUxNTA1IDMuOTQyMjIgMC45MDMwNkMgNC4xOTY1MiAxLjI1NDYyIDQuMzQxNjkgMS42NzQzNiA0LjM1OTM1IDIuMTA5MTZDIDQuMzgyOTkgMi42OTEwNyA0LjE3Njc4IDMuMjU4NjkgMy43ODU5NyAzLjY4NzQ2QyAzLjM5NTE2IDQuMTE2MjQgMi44NTE2NiA0LjM3MTE2IDIuMjc0NzEgNC4zOTYyOUwgMi4yNzQ3MSA0LjM5NjI5WiIvPgogICAgPC9nPgogIDwvZz4+Cjwvc3ZnPgo=);
  --jp-icon-jupyterlab-wordmark: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyMDAiIHZpZXdCb3g9IjAgMCAxODYwLjggNDc1Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0RTRFNEUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDQ4MC4xMzY0MDEsIDY0LjI3MTQ5MykiPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMDAwMDAsIDU4Ljg3NTU2NikiPgogICAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA4NzYwMywgMC4xNDAyOTQpIj4KICAgICAgICA8cGF0aCBkPSJNLTQyNi45LDE2OS44YzAsNDguNy0zLjcsNjQuNy0xMy42LDc2LjRjLTEwLjgsMTAtMjUsMTUuNS0zOS43LDE1LjVsMy43LDI5IGMyMi44LDAuMyw0NC44LTcuOSw2MS45LTIzLjFjMTcuOC0xOC41LDI0LTQ0LjEsMjQtODMuM1YwSC00Mjd2MTcwLjFMLTQyNi45LDE2OS44TC00MjYuOSwxNjkuOHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTU1LjA0NTI5NiwgNTYuODM3MTA0KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuNTYyNDUzLCAxLjc5OTg0MikiPgogICAgICAgIDxwYXRoIGQ9Ik0tMzEyLDE0OGMwLDIxLDAsMzkuNSwxLjcsNTUuNGgtMzEuOGwtMi4xLTMzLjNoLTAuOGMtNi43LDExLjYtMTYuNCwyMS4zLTI4LDI3LjkgYy0xMS42LDYuNi0yNC44LDEwLTM4LjIsOS44Yy0zMS40LDAtNjktMTcuNy02OS04OVYwaDM2LjR2MTEyLjdjMCwzOC43LDExLjYsNjQuNyw0NC42LDY0LjdjMTAuMy0wLjIsMjAuNC0zLjUsMjguOS05LjQgYzguNS01LjksMTUuMS0xNC4zLDE4LjktMjMuOWMyLjItNi4xLDMuMy0xMi41LDMuMy0xOC45VjAuMmgzNi40VjE0OEgtMzEyTC0zMTIsMTQ4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzOTAuMDEzMzIyLCA1My40Nzk2MzgpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS43MDY0NTgsIDAuMjMxNDI1KSI+CiAgICAgICAgPHBhdGggZD0iTS00NzguNiw3MS40YzAtMjYtMC44LTQ3LTEuNy02Ni43aDMyLjdsMS43LDM0LjhoMC44YzcuMS0xMi41LDE3LjUtMjIuOCwzMC4xLTI5LjcgYzEyLjUtNywyNi43LTEwLjMsNDEtOS44YzQ4LjMsMCw4NC43LDQxLjcsODQuNywxMDMuM2MwLDczLjEtNDMuNywxMDkuMi05MSwxMDkuMmMtMTIuMSwwLjUtMjQuMi0yLjItMzUtNy44IGMtMTAuOC01LjYtMTkuOS0xMy45LTI2LjYtMjQuMmgtMC44VjI5MWgtMzZ2LTIyMEwtNDc4LjYsNzEuNEwtNDc4LjYsNzEuNHogTS00NDIuNiwxMjUuNmMwLjEsNS4xLDAuNiwxMC4xLDEuNywxNS4xIGMzLDEyLjMsOS45LDIzLjMsMTkuOCwzMS4xYzkuOSw3LjgsMjIuMSwxMi4xLDM0LjcsMTIuMWMzOC41LDAsNjAuNy0zMS45LDYwLjctNzguNWMwLTQwLjctMjEuMS03NS42LTU5LjUtNzUuNiBjLTEyLjksMC40LTI1LjMsNS4xLTM1LjMsMTMuNGMtOS45LDguMy0xNi45LDE5LjctMTkuNiwzMi40Yy0xLjUsNC45LTIuMywxMC0yLjUsMTUuMVYxMjUuNkwtNDQyLjYsMTI1LjZMLTQ0Mi42LDEyNS42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2MDYuNzQwNzI2LCA1Ni44MzcxMDQpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC43NTEyMjYsIDEuOTg5Mjk5KSI+CiAgICAgICAgPHBhdGggZD0iTS00NDAuOCwwbDQzLjcsMTIwLjFjNC41LDEzLjQsOS41LDI5LjQsMTIuOCw0MS43aDAuOGMzLjctMTIuMiw3LjktMjcuNywxMi44LTQyLjQgbDM5LjctMTE5LjJoMzguNUwtMzQ2LjksMTQ1Yy0yNiw2OS43LTQzLjcsMTA1LjQtNjguNiwxMjcuMmMtMTIuNSwxMS43LTI3LjksMjAtNDQuNiwyMy45bC05LjEtMzEuMSBjMTEuNy0zLjksMjIuNS0xMC4xLDMxLjgtMTguMWMxMy4yLTExLjEsMjMuNy0yNS4yLDMwLjYtNDEuMmMxLjUtMi44LDIuNS01LjcsMi45LTguOGMtMC4zLTMuMy0xLjItNi42LTIuNS05LjdMLTQ4MC4yLDAuMSBoMzkuN0wtNDQwLjgsMEwtNDQwLjgsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoODIyLjc0ODEwNCwgMC4wMDAwMDApIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS40NjQwNTAsIDAuMzc4OTE0KSI+CiAgICAgICAgPHBhdGggZD0iTS00MTMuNywwdjU4LjNoNTJ2MjguMmgtNTJWMTk2YzAsMjUsNywzOS41LDI3LjMsMzkuNWM3LjEsMC4xLDE0LjItMC43LDIxLjEtMi41IGwxLjcsMjcuN2MtMTAuMywzLjctMjEuMyw1LjQtMzIuMiw1Yy03LjMsMC40LTE0LjYtMC43LTIxLjMtMy40Yy02LjgtMi43LTEyLjktNi44LTE3LjktMTIuMWMtMTAuMy0xMC45LTE0LjEtMjktMTQuMS01Mi45IFY4Ni41aC0zMVY1OC4zaDMxVjkuNkwtNDEzLjcsMEwtNDEzLjcsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOTc0LjQzMzI4NiwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDAuOTkwMDM0LCAwLjYxMDMzOSkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDQ1LjgsMTEzYzAuOCw1MCwzMi4yLDcwLjYsNjguNiw3MC42YzE5LDAuNiwzNy45LTMsNTUuMy0xMC41bDYuMiwyNi40IGMtMjAuOSw4LjktNDMuNSwxMy4xLTY2LjIsMTIuNmMtNjEuNSwwLTk4LjMtNDEuMi05OC4zLTEwMi41Qy00ODAuMiw0OC4yLTQ0NC43LDAtMzg2LjUsMGM2NS4yLDAsODIuNyw1OC4zLDgyLjcsOTUuNyBjLTAuMSw1LjgtMC41LDExLjUtMS4yLDE3LjJoLTE0MC42SC00NDUuOEwtNDQ1LjgsMTEzeiBNLTMzOS4yLDg2LjZjMC40LTIzLjUtOS41LTYwLjEtNTAuNC02MC4xIGMtMzYuOCwwLTUyLjgsMzQuNC01NS43LDYwLjFILTMzOS4yTC0zMzkuMiw4Ni42TC0zMzkuMiw4Ni42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMjAxLjk2MTA1OCwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuMTc5NjQwLCAwLjcwNTA2OCkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDc4LjYsNjhjMC0yMy45LTAuNC00NC41LTEuNy02My40aDMxLjhsMS4yLDM5LjloMS43YzkuMS0yNy4zLDMxLTQ0LjUsNTUuMy00NC41IGMzLjUtMC4xLDcsMC40LDEwLjMsMS4ydjM0LjhjLTQuMS0wLjktOC4yLTEuMy0xMi40LTEuMmMtMjUuNiwwLTQzLjcsMTkuNy00OC43LDQ3LjRjLTEsNS43LTEuNiwxMS41LTEuNywxNy4ydjEwOC4zaC0zNlY2OCBMLTQ3OC42LDY4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCBkPSJNMTM1Mi4zLDMyNi4yaDM3VjI4aC0zN1YzMjYuMnogTTE2MDQuOCwzMjYuMmMtMi41LTEzLjktMy40LTMxLjEtMy40LTQ4Ljd2LTc2IGMwLTQwLjctMTUuMS04My4xLTc3LjMtODMuMWMtMjUuNiwwLTUwLDcuMS02Ni44LDE4LjFsOC40LDI0LjRjMTQuMy05LjIsMzQtMTUuMSw1My0xNS4xYzQxLjYsMCw0Ni4yLDMwLjIsNDYuMiw0N3Y0LjIgYy03OC42LTAuNC0xMjIuMywyNi41LTEyMi4zLDc1LjZjMCwyOS40LDIxLDU4LjQsNjIuMiw1OC40YzI5LDAsNTAuOS0xNC4zLDYyLjItMzAuMmgxLjNsMi45LDI1LjZIMTYwNC44eiBNMTU2NS43LDI1Ny43IGMwLDMuOC0wLjgsOC0yLjEsMTEuOGMtNS45LDE3LjItMjIuNywzNC00OS4yLDM0Yy0xOC45LDAtMzQuOS0xMS4zLTM0LjktMzUuM2MwLTM5LjUsNDUuOC00Ni42LDg2LjItNDUuOFYyNTcuN3ogTTE2OTguNSwzMjYuMiBsMS43LTMzLjZoMS4zYzE1LjEsMjYuOSwzOC43LDM4LjIsNjguMSwzOC4yYzQ1LjQsMCw5MS4yLTM2LjEsOTEuMi0xMDguOGMwLjQtNjEuNy0zNS4zLTEwMy43LTg1LjctMTAzLjcgYy0zMi44LDAtNTYuMywxNC43LTY5LjMsMzcuNGgtMC44VjI4aC0zNi42djI0NS43YzAsMTguMS0wLjgsMzguNi0xLjcsNTIuNUgxNjk4LjV6IE0xNzA0LjgsMjA4LjJjMC01LjksMS4zLTEwLjksMi4xLTE1LjEgYzcuNi0yOC4xLDMxLjEtNDUuNCw1Ni4zLTQ1LjRjMzkuNSwwLDYwLjUsMzQuOSw2MC41LDc1LjZjMCw0Ni42LTIzLjEsNzguMS02MS44LDc4LjFjLTI2LjksMC00OC4zLTE3LjYtNTUuNS00My4zIGMtMC44LTQuMi0xLjctOC44LTEuNy0xMy40VjIwOC4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgZmlsbD0iIzYxNjE2MSIgZD0iTTE1IDlIOXY2aDZWOXptLTIgNGgtMnYtMmgydjJ6bTgtMlY5aC0yVjdjMC0xLjEtLjktMi0yLTJoLTJWM2gtMnYyaC0yVjNIOXYySDdjLTEuMSAwLTIgLjktMiAydjJIM3YyaDJ2MkgzdjJoMnYyYzAgMS4xLjkgMiAyIDJoMnYyaDJ2LTJoMnYyaDJ2LTJoMmMxLjEgMCAyLS45IDItMnYtMmgydi0yaC0ydi0yaDJ6bS00IDZIN1Y3aDEwdjEweiIvPgo8L3N2Zz4K);
  --jp-icon-keyboard: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMTdjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY3YzAtMS4xLS45LTItMi0yem0tOSAzaDJ2MmgtMlY4em0wIDNoMnYyaC0ydi0yek04IDhoMnYySDhWOHptMCAzaDJ2Mkg4di0yem0tMSAySDV2LTJoMnYyem0wLTNINVY4aDJ2MnptOSA3SDh2LTJoOHYyem0wLTRoLTJ2LTJoMnYyem0wLTNoLTJWOGgydjJ6bTMgM2gtMnYtMmgydjJ6bTAtM2gtMlY4aDJ2MnoiLz4KPC9zdmc+Cg==);
  --jp-icon-launch: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMzIgMzIiIHdpZHRoPSIzMiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0yNiwyOEg2YTIuMDAyNywyLjAwMjcsMCwwLDEtMi0yVjZBMi4wMDI3LDIuMDAyNywwLDAsMSw2LDRIMTZWNkg2VjI2SDI2VjE2aDJWMjZBMi4wMDI3LDIuMDAyNywwLDAsMSwyNiwyOFoiLz4KICAgIDxwb2x5Z29uIHBvaW50cz0iMjAgMiAyMCA0IDI2LjU4NiA0IDE4IDEyLjU4NiAxOS40MTQgMTQgMjggNS40MTQgMjggMTIgMzAgMTIgMzAgMiAyMCAyIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-launcher: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkgMTlINVY1aDdWM0g1YTIgMiAwIDAwLTIgMnYxNGEyIDIgMCAwMDIgMmgxNGMxLjEgMCAyLS45IDItMnYtN2gtMnY3ek0xNCAzdjJoMy41OWwtOS44MyA5LjgzIDEuNDEgMS40MUwxOSA2LjQxVjEwaDJWM2gtN3oiLz4KPC9zdmc+Cg==);
  --jp-icon-line-form: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGZpbGw9IndoaXRlIiBkPSJNNS44OCA0LjEyTDEzLjc2IDEybC03Ljg4IDcuODhMOCAyMmwxMC0xMEw4IDJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-link: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMuOSAxMmMwLTEuNzEgMS4zOS0zLjEgMy4xLTMuMWg0VjdIN2MtMi43NiAwLTUgMi4yNC01IDVzMi4yNCA1IDUgNWg0di0xLjlIN2MtMS43MSAwLTMuMS0xLjM5LTMuMS0zLjF6TTggMTNoOHYtMkg4djJ6bTktNmgtNHYxLjloNGMxLjcxIDAgMy4xIDEuMzkgMy4xIDMuMXMtMS4zOSAzLjEtMy4xIDMuMWgtNFYxN2g0YzIuNzYgMCA1LTIuMjQgNS01cy0yLjI0LTUtNS01eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xOSA1djE0SDVWNWgxNG0xLjEtMkgzLjljLS41IDAtLjkuNC0uOS45djE2LjJjMCAuNC40LjkuOS45aDE2LjJjLjQgMCAuOS0uNS45LS45VjMuOWMwLS41LS41LS45LS45LS45ek0xMSA3aDZ2MmgtNlY3em0wIDRoNnYyaC02di0yem0wIDRoNnYyaC02ek03IDdoMnYySDd6bTAgNGgydjJIN3ptMCA0aDJ2Mkg3eiIvPgo8L3N2Zz4K);
  --jp-icon-markdown: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjN0IxRkEyIiBkPSJNNSAxNC45aDEybC02LjEgNnptOS40LTYuOGMwLTEuMy0uMS0yLjktLjEtNC41LS40IDEuNC0uOSAyLjktMS4zIDQuM2wtMS4zIDQuM2gtMkw4LjUgNy45Yy0uNC0xLjMtLjctMi45LTEtNC4zLS4xIDEuNi0uMSAzLjItLjIgNC42TDcgMTIuNEg0LjhsLjctMTFoMy4zTDEwIDVjLjQgMS4yLjcgMi43IDEgMy45LjMtMS4yLjctMi42IDEtMy45bDEuMi0zLjdoMy4zbC42IDExaC0yLjRsLS4zLTQuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-move-down: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBkPSJNMTIuNDcxIDcuNTI4OTlDMTIuNzYzMiA3LjIzNjg0IDEyLjc2MzIgNi43NjMxNiAxMi40NzEgNi40NzEwMVY2LjQ3MTAxQzEyLjE3OSA2LjE3OTA1IDExLjcwNTcgNi4xNzg4NCAxMS40MTM1IDYuNDcwNTRMNy43NSAxMC4xMjc1VjEuNzVDNy43NSAxLjMzNTc5IDcuNDE0MjEgMSA3IDFWMUM2LjU4NTc5IDEgNi4yNSAxLjMzNTc5IDYuMjUgMS43NVYxMC4xMjc1TDIuNTk3MjYgNi40NjgyMkMyLjMwMzM4IDYuMTczODEgMS44MjY0MSA2LjE3MzU5IDEuNTMyMjYgNi40Njc3NFY2LjQ2Nzc0QzEuMjM4MyA2Ljc2MTcgMS4yMzgzIDcuMjM4MyAxLjUzMjI2IDcuNTMyMjZMNi4yOTI4OSAxMi4yOTI5QzYuNjgzNDIgMTIuNjgzNCA3LjMxNjU4IDEyLjY4MzQgNy43MDcxMSAxMi4yOTI5TDEyLjQ3MSA3LjUyODk5WiIgZmlsbD0iIzYxNjE2MSIvPgo8L3N2Zz4K);
  --jp-icon-move-up: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTQiIGhlaWdodD0iMTQiIHZpZXdCb3g9IjAgMCAxNCAxNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggY2xhc3M9ImpwLWljb24zIiBkPSJNMS41Mjg5OSA2LjQ3MTAxQzEuMjM2ODQgNi43NjMxNiAxLjIzNjg0IDcuMjM2ODQgMS41Mjg5OSA3LjUyODk5VjcuNTI4OTlDMS44MjA5NSA3LjgyMDk1IDIuMjk0MjYgNy44MjExNiAyLjU4NjQ5IDcuNTI5NDZMNi4yNSAzLjg3MjVWMTIuMjVDNi4yNSAxMi42NjQyIDYuNTg1NzkgMTMgNyAxM1YxM0M3LjQxNDIxIDEzIDcuNzUgMTIuNjY0MiA3Ljc1IDEyLjI1VjMuODcyNUwxMS40MDI3IDcuNTMxNzhDMTEuNjk2NiA3LjgyNjE5IDEyLjE3MzYgNy44MjY0MSAxMi40Njc3IDcuNTMyMjZWNy41MzIyNkMxMi43NjE3IDcuMjM4MyAxMi43NjE3IDYuNzYxNyAxMi40Njc3IDYuNDY3NzRMNy43MDcxMSAxLjcwNzExQzcuMzE2NTggMS4zMTY1OCA2LjY4MzQyIDEuMzE2NTggNi4yOTI4OSAxLjcwNzExTDEuNTI4OTkgNi40NzEwMVoiIGZpbGw9IiM2MTYxNjEiLz4KPC9zdmc+Cg==);
  --jp-icon-new-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDZoLThsLTItMkg0Yy0xLjExIDAtMS45OS44OS0xLjk5IDJMMiAxOGMwIDEuMTEuODkgMiAyIDJoMTZjMS4xMSAwIDItLjg5IDItMlY4YzAtMS4xMS0uODktMi0yLTJ6bS0xIDhoLTN2M2gtMnYtM2gtM3YtMmgzVjloMnYzaDN2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-not-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI1IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDMgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMTkgMTcuMTg0NCAyLjk2OTY4IDE0LjMwMzIgMS44NjA5NCAxMS40NDA5WiIvPgogICAgPHBhdGggY2xhc3M9ImpwLWljb24yIiBzdHJva2U9IiMzMzMzMzMiIHN0cm9rZS13aWR0aD0iMiIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOS4zMTU5MiA5LjMyMDMxKSIgZD0iTTcuMzY4NDIgMEwwIDcuMzY0NzkiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDkuMzE1OTIgMTYuNjgzNikgc2NhbGUoMSAtMSkiIGQ9Ik03LjM2ODQyIDBMMCA3LjM2NDc5Ii8+Cjwvc3ZnPgo=);
  --jp-icon-notebook: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtbm90ZWJvb2staWNvbi1jb2xvciBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNFRjZDMDAiPgogICAgPHBhdGggZD0iTTE4LjcgMy4zdjE1LjRIMy4zVjMuM2gxNS40bTEuNS0xLjVIMS44djE4LjNoMTguM2wuMS0xOC4zeiIvPgogICAgPHBhdGggZD0iTTE2LjUgMTYuNWwtNS40LTQuMy01LjYgNC4zdi0xMWgxMXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-numbering: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyOCAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTQgMTlINlYxOS41SDVWMjAuNUg2VjIxSDRWMjJIN1YxOEg0VjE5Wk01IDEwSDZWNkg0VjdINVYxMFpNNCAxM0g1LjhMNCAxNS4xVjE2SDdWMTVINS4yTDcgMTIuOVYxMkg0VjEzWk05IDdWOUgyM1Y3SDlaTTkgMjFIMjNWMTlIOVYyMVpNOSAxNUgyM1YxM0g5VjE1WiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-offline-bolt: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDIuMDJjLTUuNTEgMC05Ljk4IDQuNDctOS45OCA5Ljk4czQuNDcgOS45OCA5Ljk4IDkuOTggOS45OC00LjQ3IDkuOTgtOS45OFMxNy41MSAyLjAyIDEyIDIuMDJ6TTExLjQ4IDIwdi02LjI2SDhMMTMgNHY2LjI2aDMuMzVMMTEuNDggMjB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-palette: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE4IDEzVjIwSDRWNkg5LjAyQzkuMDcgNS4yOSA5LjI0IDQuNjIgOS41IDRINEMyLjkgNCAyIDQuOSAyIDZWMjBDMiAyMS4xIDIuOSAyMiA0IDIySDE4QzE5LjEgMjIgMjAgMjEuMSAyMCAyMFYxNUwxOCAxM1pNMTkuMyA4Ljg5QzE5Ljc0IDguMTkgMjAgNy4zOCAyMCA2LjVDMjAgNC4wMSAxNy45OSAyIDE1LjUgMkMxMy4wMSAyIDExIDQuMDEgMTEgNi41QzExIDguOTkgMTMuMDEgMTEgMTUuNDkgMTFDMTYuMzcgMTEgMTcuMTkgMTAuNzQgMTcuODggMTAuM0wyMSAxMy40MkwyMi40MiAxMkwxOS4zIDguODlaTTE1LjUgOUMxNC4xMiA5IDEzIDcuODggMTMgNi41QzEzIDUuMTIgMTQuMTIgNCAxNS41IDRDMTYuODggNCAxOCA1LjEyIDE4IDYuNUMxOCA3Ljg4IDE2Ljg4IDkgMTUuNSA5WiIvPgogICAgPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik00IDZIOS4wMTg5NEM5LjAwNjM5IDYuMTY1MDIgOSA2LjMzMTc2IDkgNi41QzkgOC44MTU3NyAxMC4yMTEgMTAuODQ4NyAxMi4wMzQzIDEySDlWMTRIMTZWMTIuOTgxMUMxNi41NzAzIDEyLjkzNzcgMTcuMTIgMTIuODIwNyAxNy42Mzk2IDEyLjYzOTZMMTggMTNWMjBINFY2Wk04IDhINlYxMEg4VjhaTTYgMTJIOFYxNEg2VjEyWk04IDE2SDZWMThIOFYxNlpNOSAxNkgxNlYxOEg5VjE2WiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-paste: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE5IDJoLTQuMThDMTQuNC44NCAxMy4zIDAgMTIgMGMtMS4zIDAtMi40Ljg0LTIuODIgMkg1Yy0xLjEgMC0yIC45LTIgMnYxNmMwIDEuMS45IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjRjMC0xLjEtLjktMi0yLTJ6bS03IDBjLjU1IDAgMSAuNDUgMSAxcy0uNDUgMS0xIDEtMS0uNDUtMS0xIC40NS0xIDEtMXptNyAxOEg1VjRoMnYzaDEwVjRoMnYxNnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-pdf: url(data:image/svg+xml;base64,PHN2ZwogICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyMiAyMiIgd2lkdGg9IjE2Ij4KICAgIDxwYXRoIHRyYW5zZm9ybT0icm90YXRlKDQ1KSIgY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI0ZGMkEyQSIKICAgICAgIGQ9Im0gMjIuMzQ0MzY5LC0zLjAxNjM2NDIgaCA1LjYzODYwNCB2IDEuNTc5MjQzMyBoIC0zLjU0OTIyNyB2IDEuNTA4NjkyOTkgaCAzLjMzNzU3NiBWIDEuNjUwODE1NCBoIC0zLjMzNzU3NiB2IDMuNDM1MjYxMyBoIC0yLjA4OTM3NyB6IG0gLTcuMTM2NDQ0LDEuNTc5MjQzMyB2IDQuOTQzOTU0MyBoIDAuNzQ4OTIgcSAxLjI4MDc2MSwwIDEuOTUzNzAzLC0wLjYzNDk1MzUgMC42NzgzNjksLTAuNjM0OTUzNSAwLjY3ODM2OSwtMS44NDUxNjQxIDAsLTEuMjA0NzgzNTUgLTAuNjcyOTQyLC0xLjgzNDMxMDExIC0wLjY3Mjk0MiwtMC42Mjk1MjY1OSAtMS45NTkxMywtMC42Mjk1MjY1OSB6IG0gLTIuMDg5Mzc3LC0xLjU3OTI0MzMgaCAyLjIwMzM0MyBxIDEuODQ1MTY0LDAgMi43NDYwMzksMC4yNjU5MjA3IDAuOTA2MzAxLDAuMjYwNDkzNyAxLjU1MjEwOCwwLjg5MDAyMDMgMC41Njk4MywwLjU0ODEyMjMgMC44NDY2MDUsMS4yNjQ0ODAwNiAwLjI3Njc3NCwwLjcxNjM1NzgxIDAuMjc2Nzc0LDEuNjIyNjU4OTQgMCwwLjkxNzE1NTEgLTAuMjc2Nzc0LDEuNjM4OTM5OSAtMC4yNzY3NzUsMC43MTYzNTc4IC0wLjg0NjYwNSwxLjI2NDQ4IC0wLjY1MTIzNCwwLjYyOTUyNjYgLTEuNTYyOTYyLDAuODk1NDQ3MyAtMC45MTE3MjgsMC4yNjA0OTM3IC0yLjczNTE4NSwwLjI2MDQ5MzcgaCAtMi4yMDMzNDMgeiBtIC04LjE0NTg1NjUsMCBoIDMuNDY3ODIzIHEgMS41NDY2ODE2LDAgMi4zNzE1Nzg1LDAuNjg5MjIzIDAuODMwMzI0LDAuNjgzNzk2MSAwLjgzMDMyNCwxLjk1MzcwMzE0IDAsMS4yNzUzMzM5NyAtMC44MzAzMjQsMS45NjQ1NTcwNiBRIDkuOTg3MTk2MSwyLjI3NDkxNSA4LjQ0MDUxNDUsMi4yNzQ5MTUgSCA3LjA2MjA2ODQgViA1LjA4NjA3NjcgSCA0Ljk3MjY5MTUgWiBtIDIuMDg5Mzc2OSwxLjUxNDExOTkgdiAyLjI2MzAzOTQzIGggMS4xNTU5NDEgcSAwLjYwNzgxODgsMCAwLjkzODg2MjksLTAuMjkzMDU1NDcgMC4zMzEwNDQxLC0wLjI5ODQ4MjQxIDAuMzMxMDQ0MSwtMC44NDExNzc3MiAwLC0wLjU0MjY5NTMxIC0wLjMzMTA0NDEsLTAuODM1NzUwNzQgLTAuMzMxMDQ0MSwtMC4yOTMwNTU1IC0wLjkzODg2MjksLTAuMjkzMDU1NSB6IgovPgo8L3N2Zz4K);
  --jp-icon-python: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iLTEwIC0xMCAxMzEuMTYxMzYxNjk0MzM1OTQgMTMyLjM4ODk5OTkzODk2NDg0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMzA2OTk4IiBkPSJNIDU0LjkxODc4NSw5LjE5Mjc0MjFlLTQgQyA1MC4zMzUxMzIsMC4wMjIyMTcyNyA0NS45NTc4NDYsMC40MTMxMzY5NyA0Mi4xMDYyODUsMS4wOTQ2NjkzIDMwLjc2MDA2OSwzLjA5OTE3MzEgMjguNzAwMDM2LDcuMjk0NzcxNCAyOC43MDAwMzUsMTUuMDMyMTY5IHYgMTAuMjE4NzUgaCAyNi44MTI1IHYgMy40MDYyNSBoIC0yNi44MTI1IC0xMC4wNjI1IGMgLTcuNzkyNDU5LDAgLTE0LjYxNTc1ODgsNC42ODM3MTcgLTE2Ljc0OTk5OTgsMTMuNTkzNzUgLTIuNDYxODE5OTgsMTAuMjEyOTY2IC0yLjU3MTAxNTA4LDE2LjU4NjAyMyAwLDI3LjI1IDEuOTA1OTI4Myw3LjkzNzg1MiA2LjQ1NzU0MzIsMTMuNTkzNzQ4IDE0LjI0OTk5OTgsMTMuNTkzNzUgaCA5LjIxODc1IHYgLTEyLjI1IGMgMCwtOC44NDk5MDIgNy42NTcxNDQsLTE2LjY1NjI0OCAxNi43NSwtMTYuNjU2MjUgaCAyNi43ODEyNSBjIDcuNDU0OTUxLDAgMTMuNDA2MjUzLC02LjEzODE2NCAxMy40MDYyNSwtMTMuNjI1IHYgLTI1LjUzMTI1IGMgMCwtNy4yNjYzMzg2IC02LjEyOTk4LC0xMi43MjQ3NzcxIC0xMy40MDYyNSwtMTMuOTM3NDk5NyBDIDY0LjI4MTU0OCwwLjMyNzk0Mzk3IDU5LjUwMjQzOCwtMC4wMjAzNzkwMyA1NC45MTg3ODUsOS4xOTI3NDIxZS00IFogbSAtMTQuNSw4LjIxODc1MDEyNTc5IGMgMi43Njk1NDcsMCA1LjAzMTI1LDIuMjk4NjQ1NiA1LjAzMTI1LDUuMTI0OTk5NiAtMmUtNiwyLjgxNjMzNiAtMi4yNjE3MDMsNS4wOTM3NSAtNS4wMzEyNSw1LjA5Mzc1IC0yLjc3OTQ3NiwtMWUtNiAtNS4wMzEyNSwtMi4yNzc0MTUgLTUuMDMxMjUsLTUuMDkzNzUgLTEwZS03LC0yLjgyNjM1MyAyLjI1MTc3NCwtNS4xMjQ5OTk2IDUuMDMxMjUsLTUuMTI0OTk5NiB6Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI2ZmZDQzYiIgZD0ibSA4NS42Mzc1MzUsMjguNjU3MTY5IHYgMTEuOTA2MjUgYyAwLDkuMjMwNzU1IC03LjgyNTg5NSwxNi45OTk5OTkgLTE2Ljc1LDE3IGggLTI2Ljc4MTI1IGMgLTcuMzM1ODMzLDAgLTEzLjQwNjI0OSw2LjI3ODQ4MyAtMTMuNDA2MjUsMTMuNjI1IHYgMjUuNTMxMjQ3IGMgMCw3LjI2NjM0NCA2LjMxODU4OCwxMS41NDAzMjQgMTMuNDA2MjUsMTMuNjI1MDA0IDguNDg3MzMxLDIuNDk1NjEgMTYuNjI2MjM3LDIuOTQ2NjMgMjYuNzgxMjUsMCA2Ljc1MDE1NSwtMS45NTQzOSAxMy40MDYyNTMsLTUuODg3NjEgMTMuNDA2MjUsLTEzLjYyNTAwNCBWIDg2LjUwMDkxOSBoIC0yNi43ODEyNSB2IC0zLjQwNjI1IGggMjYuNzgxMjUgMTMuNDA2MjU0IGMgNy43OTI0NjEsMCAxMC42OTYyNTEsLTUuNDM1NDA4IDEzLjQwNjI0MSwtMTMuNTkzNzUgMi43OTkzMywtOC4zOTg4ODYgMi42ODAyMiwtMTYuNDc1Nzc2IDAsLTI3LjI1IC0xLjkyNTc4LC03Ljc1NzQ0MSAtNS42MDM4NywtMTMuNTkzNzUgLTEzLjQwNjI0MSwtMTMuNTkzNzUgeiBtIC0xNS4wNjI1LDY0LjY1NjI1IGMgMi43Nzk0NzgsM2UtNiA1LjAzMTI1LDIuMjc3NDE3IDUuMDMxMjUsNS4wOTM3NDcgLTJlLTYsMi44MjYzNTQgLTIuMjUxNzc1LDUuMTI1MDA0IC01LjAzMTI1LDUuMTI1MDA0IC0yLjc2OTU1LDAgLTUuMDMxMjUsLTIuMjk4NjUgLTUuMDMxMjUsLTUuMTI1MDA0IDJlLTYsLTIuODE2MzMgMi4yNjE2OTcsLTUuMDkzNzQ3IDUuMDMxMjUsLTUuMDkzNzQ3IHoiLz4KPC9zdmc+Cg==);
  --jp-icon-r-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjE5NkYzIiBkPSJNNC40IDIuNWMxLjItLjEgMi45LS4zIDQuOS0uMyAyLjUgMCA0LjEuNCA1LjIgMS4zIDEgLjcgMS41IDEuOSAxLjUgMy41IDAgMi0xLjQgMy41LTIuOSA0LjEgMS4yLjQgMS43IDEuNiAyLjIgMyAuNiAxLjkgMSAzLjkgMS4zIDQuNmgtMy44Yy0uMy0uNC0uOC0xLjctMS4yLTMuN3MtMS4yLTIuNi0yLjYtMi42aC0uOXY2LjRINC40VjIuNXptMy43IDYuOWgxLjRjMS45IDAgMi45LS45IDIuOS0yLjNzLTEtMi4zLTIuOC0yLjNjLS43IDAtMS4zIDAtMS42LjJ2NC41aC4xdi0uMXoiLz4KPC9zdmc+Cg==);
  --jp-icon-react: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMTUwIDE1MCA1NDEuOSAyOTUuMyI+CiAgPGcgY2xhc3M9ImpwLWljb24tYnJhbmQyIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzYxREFGQiI+CiAgICA8cGF0aCBkPSJNNjY2LjMgMjk2LjVjMC0zMi41LTQwLjctNjMuMy0xMDMuMS04Mi40IDE0LjQtNjMuNiA4LTExNC4yLTIwLjItMTMwLjQtNi41LTMuOC0xNC4xLTUuNi0yMi40LTUuNnYyMi4zYzQuNiAwIDguMy45IDExLjQgMi42IDEzLjYgNy44IDE5LjUgMzcuNSAxNC45IDc1LjctMS4xIDkuNC0yLjkgMTkuMy01LjEgMjkuNC0xOS42LTQuOC00MS04LjUtNjMuNS0xMC45LTEzLjUtMTguNS0yNy41LTM1LjMtNDEuNi01MCAzMi42LTMwLjMgNjMuMi00Ni45IDg0LTQ2LjlWNzhjLTI3LjUgMC02My41IDE5LjYtOTkuOSA1My42LTM2LjQtMzMuOC03Mi40LTUzLjItOTkuOS01My4ydjIyLjNjMjAuNyAwIDUxLjQgMTYuNSA4NCA0Ni42LTE0IDE0LjctMjggMzEuNC00MS4zIDQ5LjktMjIuNiAyLjQtNDQgNi4xLTYzLjYgMTEtMi4zLTEwLTQtMTkuNy01LjItMjktNC43LTM4LjIgMS4xLTY3LjkgMTQuNi03NS44IDMtMS44IDYuOS0yLjYgMTEuNS0yLjZWNzguNWMtOC40IDAtMTYgMS44LTIyLjYgNS42LTI4LjEgMTYuMi0zNC40IDY2LjctMTkuOSAxMzAuMS02Mi4yIDE5LjItMTAyLjcgNDkuOS0xMDIuNyA4Mi4zIDAgMzIuNSA0MC43IDYzLjMgMTAzLjEgODIuNC0xNC40IDYzLjYtOCAxMTQuMiAyMC4yIDEzMC40IDYuNSAzLjggMTQuMSA1LjYgMjIuNSA1LjYgMjcuNSAwIDYzLjUtMTkuNiA5OS45LTUzLjYgMzYuNCAzMy44IDcyLjQgNTMuMiA5OS45IDUzLjIgOC40IDAgMTYtMS44IDIyLjYtNS42IDI4LjEtMTYuMiAzNC40LTY2LjcgMTkuOS0xMzAuMSA2Mi0xOS4xIDEwMi41LTQ5LjkgMTAyLjUtODIuM3ptLTEzMC4yLTY2LjdjLTMuNyAxMi45LTguMyAyNi4yLTEzLjUgMzkuNS00LjEtOC04LjQtMTYtMTMuMS0yNC00LjYtOC05LjUtMTUuOC0xNC40LTIzLjQgMTQuMiAyLjEgMjcuOSA0LjcgNDEgNy45em0tNDUuOCAxMDYuNWMtNy44IDEzLjUtMTUuOCAyNi4zLTI0LjEgMzguMi0xNC45IDEuMy0zMCAyLTQ1LjIgMi0xNS4xIDAtMzAuMi0uNy00NS0xLjktOC4zLTExLjktMTYuNC0yNC42LTI0LjItMzgtNy42LTEzLjEtMTQuNS0yNi40LTIwLjgtMzkuOCA2LjItMTMuNCAxMy4yLTI2LjggMjAuNy0zOS45IDcuOC0xMy41IDE1LjgtMjYuMyAyNC4xLTM4LjIgMTQuOS0xLjMgMzAtMiA0NS4yLTIgMTUuMSAwIDMwLjIuNyA0NSAxLjkgOC4zIDExLjkgMTYuNCAyNC42IDI0LjIgMzggNy42IDEzLjEgMTQuNSAyNi40IDIwLjggMzkuOC02LjMgMTMuNC0xMy4yIDI2LjgtMjAuNyAzOS45em0zMi4zLTEzYzUuNCAxMy40IDEwIDI2LjggMTMuOCAzOS44LTEzLjEgMy4yLTI2LjkgNS45LTQxLjIgOCA0LjktNy43IDkuOC0xNS42IDE0LjQtMjMuNyA0LjYtOCA4LjktMTYuMSAxMy0yNC4xek00MjEuMiA0MzBjLTkuMy05LjYtMTguNi0yMC4zLTI3LjgtMzIgOSAuNCAxOC4yLjcgMjcuNS43IDkuNCAwIDE4LjctLjIgMjcuOC0uNy05IDExLjctMTguMyAyMi40LTI3LjUgMzJ6bS03NC40LTU4LjljLTE0LjItMi4xLTI3LjktNC43LTQxLTcuOSAzLjctMTIuOSA4LjMtMjYuMiAxMy41LTM5LjUgNC4xIDggOC40IDE2IDEzLjEgMjQgNC43IDggOS41IDE1LjggMTQuNCAyMy40ek00MjAuNyAxNjNjOS4zIDkuNiAxOC42IDIwLjMgMjcuOCAzMi05LS40LTE4LjItLjctMjcuNS0uNy05LjQgMC0xOC43LjItMjcuOC43IDktMTEuNyAxOC4zLTIyLjQgMjcuNS0zMnptLTc0IDU4LjljLTQuOSA3LjctOS44IDE1LjYtMTQuNCAyMy43LTQuNiA4LTguOSAxNi0xMyAyNC01LjQtMTMuNC0xMC0yNi44LTEzLjgtMzkuOCAxMy4xLTMuMSAyNi45LTUuOCA0MS4yLTcuOXptLTkwLjUgMTI1LjJjLTM1LjQtMTUuMS01OC4zLTM0LjktNTguMy01MC42IDAtMTUuNyAyMi45LTM1LjYgNTguMy01MC42IDguNi0zLjcgMTgtNyAyNy43LTEwLjEgNS43IDE5LjYgMTMuMiA0MCAyMi41IDYwLjktOS4yIDIwLjgtMTYuNiA0MS4xLTIyLjIgNjAuNi05LjktMy4xLTE5LjMtNi41LTI4LTEwLjJ6TTMxMCA0OTBjLTEzLjYtNy44LTE5LjUtMzcuNS0xNC45LTc1LjcgMS4xLTkuNCAyLjktMTkuMyA1LjEtMjkuNCAxOS42IDQuOCA0MSA4LjUgNjMuNSAxMC45IDEzLjUgMTguNSAyNy41IDM1LjMgNDEuNiA1MC0zMi42IDMwLjMtNjMuMiA0Ni45LTg0IDQ2LjktNC41LS4xLTguMy0xLTExLjMtMi43em0yMzcuMi03Ni4yYzQuNyAzOC4yLTEuMSA2Ny45LTE0LjYgNzUuOC0zIDEuOC02LjkgMi42LTExLjUgMi42LTIwLjcgMC01MS40LTE2LjUtODQtNDYuNiAxNC0xNC43IDI4LTMxLjQgNDEuMy00OS45IDIyLjYtMi40IDQ0LTYuMSA2My42LTExIDIuMyAxMC4xIDQuMSAxOS44IDUuMiAyOS4xem0zOC41LTY2LjdjLTguNiAzLjctMTggNy0yNy43IDEwLjEtNS43LTE5LjYtMTMuMi00MC0yMi41LTYwLjkgOS4yLTIwLjggMTYuNi00MS4xIDIyLjItNjAuNiA5LjkgMy4xIDE5LjMgNi41IDI4LjEgMTAuMiAzNS40IDE1LjEgNTguMyAzNC45IDU4LjMgNTAuNi0uMSAxNS43LTIzIDM1LjYtNTguNCA1MC42ek0zMjAuOCA3OC40eiIvPgogICAgPGNpcmNsZSBjeD0iNDIwLjkiIGN5PSIyOTYuNSIgcj0iNDUuNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-redo: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCBkPSJNMCAwaDI0djI0SDB6IiBmaWxsPSJub25lIi8+PHBhdGggZD0iTTE4LjQgMTAuNkMxNi41NSA4Ljk5IDE0LjE1IDggMTEuNSA4Yy00LjY1IDAtOC41OCAzLjAzLTkuOTYgNy4yMkwzLjkgMTZjMS4wNS0zLjE5IDQuMDUtNS41IDcuNi01LjUgMS45NSAwIDMuNzMuNzIgNS4xMiAxLjg4TDEzIDE2aDlWN2wtMy42IDMuNnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-refresh: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTkgMTMuNWMtMi40OSAwLTQuNS0yLjAxLTQuNS00LjVTNi41MSA0LjUgOSA0LjVjMS4yNCAwIDIuMzYuNTIgMy4xNyAxLjMzTDEwIDhoNVYzbC0xLjc2IDEuNzZDMTIuMTUgMy42OCAxMC42NiAzIDkgMyA1LjY5IDMgMy4wMSA1LjY5IDMuMDEgOVM1LjY5IDE1IDkgMTVjMi45NyAwIDUuNDMtMi4xNiA1LjktNWgtMS41MmMtLjQ2IDItMi4yNCAzLjUtNC4zOCAzLjV6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-regex: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi1hY2NlbnQyIiBmaWxsPSIjRkZGIj4KICAgIDxjaXJjbGUgY2xhc3M9InN0MiIgY3g9IjUuNSIgY3k9IjE0LjUiIHI9IjEuNSIvPgogICAgPHJlY3QgeD0iMTIiIHk9IjQiIGNsYXNzPSJzdDIiIHdpZHRoPSIxIiBoZWlnaHQ9IjgiLz4KICAgIDxyZWN0IHg9IjguNSIgeT0iNy41IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjg2NiAtMC41IDAuNSAwLjg2NiAtMi4zMjU1IDcuMzIxOSkiIGNsYXNzPSJzdDIiIHdpZHRoPSI4IiBoZWlnaHQ9IjEiLz4KICAgIDxyZWN0IHg9IjEyIiB5PSI0IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjUgLTAuODY2IDAuODY2IDAuNSAtMC42Nzc5IDE0LjgyNTIpIiBjbGFzcz0ic3QyIiB3aWR0aD0iMSIgaGVpZ2h0PSI4Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-run: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTggNXYxNGwxMS03eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-running: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMjU2IDhDMTE5IDggOCAxMTkgOCAyNTZzMTExIDI0OCAyNDggMjQ4IDI0OC0xMTEgMjQ4LTI0OFMzOTMgOCAyNTYgOHptOTYgMzI4YzAgOC44LTcuMiAxNi0xNiAxNkgxNzZjLTguOCAwLTE2LTcuMi0xNi0xNlYxNzZjMC04LjggNy4yLTE2IDE2LTE2aDE2MGM4LjggMCAxNiA3LjIgMTYgMTZ2MTYweiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-save: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE3IDNINWMtMS4xMSAwLTIgLjktMiAydjE0YzAgMS4xLjg5IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjdsLTQtNHptLTUgMTZjLTEuNjYgMC0zLTEuMzQtMy0zczEuMzQtMyAzLTMgMyAxLjM0IDMgMy0xLjM0IDMtMyAzem0zLTEwSDVWNWgxMHY0eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-search: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjEsMTAuOWgtMC43bC0wLjItMC4yYzAuOC0wLjksMS4zLTIuMiwxLjMtMy41YzAtMy0yLjQtNS40LTUuNC01LjRTMS44LDQuMiwxLjgsNy4xczIuNCw1LjQsNS40LDUuNCBjMS4zLDAsMi41LTAuNSwzLjUtMS4zbDAuMiwwLjJ2MC43bDQuMSw0LjFsMS4yLTEuMkwxMi4xLDEwLjl6IE03LjEsMTAuOWMtMi4xLDAtMy43LTEuNy0zLjctMy43czEuNy0zLjcsMy43LTMuN3MzLjcsMS43LDMuNywzLjcgUzkuMiwxMC45LDcuMSwxMC45eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-settings: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuNDMgMTIuOThjLjA0LS4zMi4wNy0uNjQuMDctLjk4cy0uMDMtLjY2LS4wNy0uOThsMi4xMS0xLjY1Yy4xOS0uMTUuMjQtLjQyLjEyLS42NGwtMi0zLjQ2Yy0uMTItLjIyLS4zOS0uMy0uNjEtLjIybC0yLjQ5IDFjLS41Mi0uNC0xLjA4LS43My0xLjY5LS45OGwtLjM4LTIuNjVBLjQ4OC40ODggMCAwMDE0IDJoLTRjLS4yNSAwLS40Ni4xOC0uNDkuNDJsLS4zOCAyLjY1Yy0uNjEuMjUtMS4xNy41OS0xLjY5Ljk4bC0yLjQ5LTFjLS4yMy0uMDktLjQ5IDAtLjYxLjIybC0yIDMuNDZjLS4xMy4yMi0uMDcuNDkuMTIuNjRsMi4xMSAxLjY1Yy0uMDQuMzItLjA3LjY1LS4wNy45OHMuMDMuNjYuMDcuOThsLTIuMTEgMS42NWMtLjE5LjE1LS4yNC40Mi0uMTIuNjRsMiAzLjQ2Yy4xMi4yMi4zOS4zLjYxLjIybDIuNDktMWMuNTIuNCAxLjA4LjczIDEuNjkuOThsLjM4IDIuNjVjLjAzLjI0LjI0LjQyLjQ5LjQyaDRjLjI1IDAgLjQ2LS4xOC40OS0uNDJsLjM4LTIuNjVjLjYxLS4yNSAxLjE3LS41OSAxLjY5LS45OGwyLjQ5IDFjLjIzLjA5LjQ5IDAgLjYxLS4yMmwyLTMuNDZjLjEyLS4yMi4wNy0uNDktLjEyLS42NGwtMi4xMS0xLjY1ek0xMiAxNS41Yy0xLjkzIDAtMy41LTEuNTctMy41LTMuNXMxLjU3LTMuNSAzLjUtMy41IDMuNSAxLjU3IDMuNSAzLjUtMS41NyAzLjUtMy41IDMuNXoiLz4KPC9zdmc+Cg==);
  --jp-icon-share: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTSAxOCAyIEMgMTYuMzU0OTkgMiAxNSAzLjM1NDk5MDQgMTUgNSBDIDE1IDUuMTkwOTUyOSAxNS4wMjE3OTEgNS4zNzcxMjI0IDE1LjA1NjY0MSA1LjU1ODU5MzggTCA3LjkyMTg3NSA5LjcyMDcwMzEgQyA3LjM5ODUzOTkgOS4yNzc4NTM5IDYuNzMyMDc3MSA5IDYgOSBDIDQuMzU0OTkwNCA5IDMgMTAuMzU0OTkgMyAxMiBDIDMgMTMuNjQ1MDEgNC4zNTQ5OTA0IDE1IDYgMTUgQyA2LjczMjA3NzEgMTUgNy4zOTg1Mzk5IDE0LjcyMjE0NiA3LjkyMTg3NSAxNC4yNzkyOTcgTCAxNS4wNTY2NDEgMTguNDM5NDUzIEMgMTUuMDIxNTU1IDE4LjYyMTUxNCAxNSAxOC44MDgzODYgMTUgMTkgQyAxNSAyMC42NDUwMSAxNi4zNTQ5OSAyMiAxOCAyMiBDIDE5LjY0NTAxIDIyIDIxIDIwLjY0NTAxIDIxIDE5IEMgMjEgMTcuMzU0OTkgMTkuNjQ1MDEgMTYgMTggMTYgQyAxNy4yNjc0OCAxNiAxNi42MDE1OTMgMTYuMjc5MzI4IDE2LjA3ODEyNSAxNi43MjI2NTYgTCA4Ljk0MzM1OTQgMTIuNTU4NTk0IEMgOC45NzgyMDk1IDEyLjM3NzEyMiA5IDEyLjE5MDk1MyA5IDEyIEMgOSAxMS44MDkwNDcgOC45NzgyMDk1IDExLjYyMjg3OCA4Ljk0MzM1OTQgMTEuNDQxNDA2IEwgMTYuMDc4MTI1IDcuMjc5Mjk2OSBDIDE2LjYwMTQ2IDcuNzIyMTQ2MSAxNy4yNjc5MjMgOCAxOCA4IEMgMTkuNjQ1MDEgOCAyMSA2LjY0NTAwOTYgMjEgNSBDIDIxIDMuMzU0OTkwNCAxOS42NDUwMSAyIDE4IDIgeiBNIDE4IDQgQyAxOC41NjQxMjkgNCAxOSA0LjQzNTg3MDYgMTkgNSBDIDE5IDUuNTY0MTI5NCAxOC41NjQxMjkgNiAxOCA2IEMgMTcuNDM1ODcxIDYgMTcgNS41NjQxMjk0IDE3IDUgQyAxNyA0LjQzNTg3MDYgMTcuNDM1ODcxIDQgMTggNCB6IE0gNiAxMSBDIDYuNTY0MTI5NCAxMSA3IDExLjQzNTg3MSA3IDEyIEMgNyAxMi41NjQxMjkgNi41NjQxMjk0IDEzIDYgMTMgQyA1LjQzNTg3MDYgMTMgNSAxMi41NjQxMjkgNSAxMiBDIDUgMTEuNDM1ODcxIDUuNDM1ODcwNiAxMSA2IDExIHogTSAxOCAxOCBDIDE4LjU2NDEyOSAxOCAxOSAxOC40MzU4NzEgMTkgMTkgQyAxOSAxOS41NjQxMjkgMTguNTY0MTI5IDIwIDE4IDIwIEMgMTcuNDM1ODcxIDIwIDE3IDE5LjU2NDEyOSAxNyAxOSBDIDE3IDE4LjQzNTg3MSAxNy40MzU4NzEgMTggMTggMTggeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-spreadsheet: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNENBRjUwIiBkPSJNMi4yIDIuMnYxNy42aDE3LjZWMi4ySDIuMnptMTUuNCA3LjdoLTUuNVY0LjRoNS41djUuNXpNOS45IDQuNHY1LjVINC40VjQuNGg1LjV6bS01LjUgNy43aDUuNXY1LjVINC40di01LjV6bTcuNyA1LjV2LTUuNWg1LjV2NS41aC01LjV6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-stop: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik02IDZoMTJ2MTJINnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tab: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIxIDNIM2MtMS4xIDAtMiAuOS0yIDJ2MTRjMCAxLjEuOSAyIDIgMmgxOGMxLjEgMCAyLS45IDItMlY1YzAtMS4xLS45LTItMi0yem0wIDE2SDNWNWgxMHY0aDh2MTB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-table-rows: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik0yMSw4SDNWNGgxOFY4eiBNMjEsMTBIM3Y0aDE4VjEweiBNMjEsMTZIM3Y0aDE4VjE2eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-tag: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjgiIGhlaWdodD0iMjgiIHZpZXdCb3g9IjAgMCA0MyAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTI4LjgzMzIgMTIuMzM0TDMyLjk5OTggMTYuNTAwN0wzNy4xNjY1IDEyLjMzNEgyOC44MzMyWiIvPgoJCTxwYXRoIGQ9Ik0xNi4yMDk1IDIxLjYxMDRDMTUuNjg3MyAyMi4xMjk5IDE0Ljg0NDMgMjIuMTI5OSAxNC4zMjQ4IDIxLjYxMDRMNi45ODI5IDE0LjcyNDVDNi41NzI0IDE0LjMzOTQgNi4wODMxMyAxMy42MDk4IDYuMDQ3ODYgMTMuMDQ4MkM1Ljk1MzQ3IDExLjUyODggNi4wMjAwMiA4LjYxOTQ0IDYuMDY2MjEgNy4wNzY5NUM2LjA4MjgxIDYuNTE0NzcgNi41NTU0OCA2LjA0MzQ3IDcuMTE4MDQgNi4wMzA1NUM5LjA4ODYzIDUuOTg0NzMgMTMuMjYzOCA1LjkzNTc5IDEzLjY1MTggNi4zMjQyNUwyMS43MzY5IDEzLjYzOUMyMi4yNTYgMTQuMTU4NSAyMS43ODUxIDE1LjQ3MjQgMjEuMjYyIDE1Ljk5NDZMMTYuMjA5NSAyMS42MTA0Wk05Ljc3NTg1IDguMjY1QzkuMzM1NTEgNy44MjU2NiA4LjYyMzUxIDcuODI1NjYgOC4xODI4IDguMjY1QzcuNzQzNDYgOC43MDU3MSA3Ljc0MzQ2IDkuNDE3MzMgOC4xODI4IDkuODU2NjdDOC42MjM4MiAxMC4yOTY0IDkuMzM1ODIgMTAuMjk2NCA5Ljc3NTg1IDkuODU2NjdDMTAuMjE1NiA5LjQxNzMzIDEwLjIxNTYgOC43MDUzMyA5Ljc3NTg1IDguMjY1WiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-terminal: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0IiA+CiAgICA8cmVjdCBjbGFzcz0ianAtdGVybWluYWwtaWNvbi1iYWNrZ3JvdW5kLWNvbG9yIGpwLWljb24tc2VsZWN0YWJsZSIgd2lkdGg9IjIwIiBoZWlnaHQ9IjIwIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSgyIDIpIiBmaWxsPSIjMzMzMzMzIi8+CiAgICA8cGF0aCBjbGFzcz0ianAtdGVybWluYWwtaWNvbi1jb2xvciBqcC1pY29uLXNlbGVjdGFibGUtaW52ZXJzZSIgZD0iTTUuMDU2NjQgOC43NjE3MkM1LjA1NjY0IDguNTk3NjYgNS4wMzEyNSA4LjQ1MzEyIDQuOTgwNDcgOC4zMjgxMkM0LjkzMzU5IDguMTk5MjIgNC44NTU0NyA4LjA4MjAzIDQuNzQ2MDkgNy45NzY1NkM0LjY0MDYyIDcuODcxMDkgNC41IDcuNzc1MzkgNC4zMjQyMiA3LjY4OTQ1QzQuMTUyMzQgNy41OTk2MSAzLjk0MzM2IDcuNTExNzIgMy42OTcyNyA3LjQyNTc4QzMuMzAyNzMgNy4yODUxNiAyLjk0MzM2IDcuMTM2NzIgMi42MTkxNCA2Ljk4MDQ3QzIuMjk0OTIgNi44MjQyMiAyLjAxNzU4IDYuNjQyNTggMS43ODcxMSA2LjQzNTU1QzEuNTYwNTUgNi4yMjg1MiAxLjM4NDc3IDUuOTg4MjggMS4yNTk3NyA1LjcxNDg0QzEuMTM0NzcgNS40Mzc1IDEuMDcyMjcgNS4xMDkzOCAxLjA3MjI3IDQuNzMwNDdDMS4wNzIyNyA0LjM5ODQ0IDEuMTI4OTEgNC4wOTU3IDEuMjQyMTkgMy44MjIyN0MxLjM1NTQ3IDMuNTQ0OTIgMS41MTU2MiAzLjMwNDY5IDEuNzIyNjYgMy4xMDE1NkMxLjkyOTY5IDIuODk4NDQgMi4xNzk2OSAyLjczNDM3IDIuNDcyNjYgMi42MDkzOEMyLjc2NTYyIDIuNDg0MzggMy4wOTE4IDIuNDA0MyAzLjQ1MTE3IDIuMzY5MTRWMS4xMDkzOEg0LjM4ODY3VjIuMzgwODZDNC43NDAyMyAyLjQyNzczIDUuMDU2NjQgMi41MjM0NCA1LjMzNzg5IDIuNjY3OTdDNS42MTkxNCAyLjgxMjUgNS44NTc0MiAzLjAwMTk1IDYuMDUyNzMgMy4yMzYzM0M2LjI1MTk1IDMuNDY2OCA2LjQwNDMgMy43NDAyMyA2LjUwOTc3IDQuMDU2NjRDNi42MTkxNCA0LjM2OTE0IDYuNjczODMgNC43MjA3IDYuNjczODMgNS4xMTEzM0g1LjA0NDkyQzUuMDQ0OTIgNC42Mzg2NyA0LjkzNzUgNC4yODEyNSA0LjcyMjY2IDQuMDM5MDZDNC41MDc4MSAzLjc5Mjk3IDQuMjE2OCAzLjY2OTkyIDMuODQ5NjEgMy42Njk5MkMzLjY1MDM5IDMuNjY5OTIgMy40NzY1NiAzLjY5NzI3IDMuMzI4MTIgMy43NTE5NUMzLjE4MzU5IDMuODAyNzMgMy4wNjQ0NSAzLjg3Njk1IDIuOTcwNyAzLjk3NDYxQzIuODc2OTUgNC4wNjgzNiAyLjgwNjY0IDQuMTc5NjkgMi43NTk3NyA0LjMwODU5QzIuNzE2OCA0LjQzNzUgMi42OTUzMSA0LjU3ODEyIDIuNjk1MzEgNC43MzA0N0MyLjY5NTMxIDQuODgyODEgMi43MTY4IDUuMDE5NTMgMi43NTk3NyA1LjE0MDYyQzIuODA2NjQgNS4yNTc4MSAyLjg4MjgxIDUuMzY3MTkgMi45ODgyOCA1LjQ2ODc1QzMuMDk3NjYgNS41NzAzMSAzLjI0MDIzIDUuNjY3OTcgMy40MTYwMiA1Ljc2MTcyQzMuNTkxOCA1Ljg1MTU2IDMuODEwNTUgNS45NDMzNiA0LjA3MjI3IDYuMDM3MTFDNC40NjY4IDYuMTg1NTUgNC44MjQyMiA2LjMzOTg0IDUuMTQ0NTMgNi41QzUuNDY0ODQgNi42NTYyNSA1LjczODI4IDYuODM5ODQgNS45NjQ4NCA3LjA1MDc4QzYuMTk1MzEgNy4yNTc4MSA2LjM3MTA5IDcuNSA2LjQ5MjE5IDcuNzc3MzRDNi42MTcxOSA4LjA1MDc4IDYuNjc5NjkgOC4zNzUgNi42Nzk2OSA4Ljc1QzYuNjc5NjkgOS4wOTM3NSA2LjYyMzA1IDkuNDA0MyA2LjUwOTc3IDkuNjgxNjRDNi4zOTY0OCA5Ljk1NTA4IDYuMjM0MzggMTAuMTkxNCA2LjAyMzQ0IDEwLjM5MDZDNS44MTI1IDEwLjU4OTggNS41NTg1OSAxMC43NSA1LjI2MTcyIDEwLjg3MTFDNC45NjQ4NCAxMC45ODgzIDQuNjMyODEgMTEuMDY0NSA0LjI2NTYyIDExLjA5OTZWMTIuMjQ4SDMuMzMzOThWMTEuMDk5NkMzLjAwMTk1IDExLjA2ODQgMi42Nzk2OSAxMC45OTYxIDIuMzY3MTkgMTAuODgyOEMyLjA1NDY5IDEwLjc2NTYgMS43NzczNCAxMC41OTc3IDEuNTM1MTYgMTAuMzc4OUMxLjI5Njg4IDEwLjE2MDIgMS4xMDU0NyA5Ljg4NDc3IDAuOTYwOTM4IDkuNTUyNzNDMC44MTY0MDYgOS4yMTY4IDAuNzQ0MTQxIDguODE0NDUgMC43NDQxNDEgOC4zNDU3SDIuMzc4OTFDMi4zNzg5MSA4LjYyNjk1IDIuNDE5OTIgOC44NjMyOCAyLjUwMTk1IDkuMDU0NjlDMi41ODM5OCA5LjI0MjE5IDIuNjg5NDUgOS4zOTI1OCAyLjgxODM2IDkuNTA1ODZDMi45NTExNyA5LjYxNTIzIDMuMTAxNTYgOS42OTMzNiAzLjI2OTUzIDkuNzQwMjNDMy40Mzc1IDkuNzg3MTEgMy42MDkzOCA5LjgxMDU1IDMuNzg1MTYgOS44MTA1NUM0LjIwMzEyIDkuODEwNTUgNC41MTk1MyA5LjcxMjg5IDQuNzM0MzggOS41MTc1OEM0Ljk0OTIyIDkuMzIyMjcgNS4wNTY2NCA5LjA3MDMxIDUuMDU2NjQgOC43NjE3MlpNMTMuNDE4IDEyLjI3MTVIOC4wNzQyMlYxMUgxMy40MThWMTIuMjcxNVoiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDMuOTUyNjQgNikiIGZpbGw9IndoaXRlIi8+Cjwvc3ZnPgo=);
  --jp-icon-text-editor: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtdGV4dC1lZGl0b3ItaWNvbi1jb2xvciBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xNSAxNUgzdjJoMTJ2LTJ6bTAtOEgzdjJoMTJWN3pNMyAxM2gxOHYtMkgzdjJ6bTAgOGgxOHYtMkgzdjJ6TTMgM3YyaDE4VjNIM3oiLz4KPC9zdmc+Cg==);
  --jp-icon-toc: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik03LDVIMjFWN0g3VjVNNywxM1YxMUgyMVYxM0g3TTQsNC41QTEuNSwxLjUgMCAwLDEgNS41LDZBMS41LDEuNSAwIDAsMSA0LDcuNUExLjUsMS41IDAgMCwxIDIuNSw2QTEuNSwxLjUgMCAwLDEgNCw0LjVNNCwxMC41QTEuNSwxLjUgMCAwLDEgNS41LDEyQTEuNSwxLjUgMCAwLDEgNCwxMy41QTEuNSwxLjUgMCAwLDEgMi41LDEyQTEuNSwxLjUgMCAwLDEgNCwxMC41TTcsMTlWMTdIMjFWMTlIN000LDE2LjVBMS41LDEuNSAwIDAsMSA1LjUsMThBMS41LDEuNSAwIDAsMSA0LDE5LjVBMS41LDEuNSAwIDAsMSAyLjUsMThBMS41LDEuNSAwIDAsMSA0LDE2LjVaIiAvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tree-view: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik0yMiAxMVYzaC03djNIOVYzSDJ2OGg3VjhoMnYxMGg0djNoN3YtOGgtN3YzaC0yVjhoMnYzeiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMiAxNy4xODQ0IDIuOTY5NjggMTQuMzAzMiAxLjg2MDk0IDExLjQ0MDlaIi8+CiAgICA8cGF0aCBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiMzMzMzMzMiIHN0cm9rZT0iIzMzMzMzMyIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOCA5Ljg2NzE5KSIgZD0iTTIuODYwMTUgNC44NjUzNUwwLjcyNjU0OSAyLjk5OTU5TDAgMy42MzA0NUwyLjg2MDE1IDYuMTMxNTdMOCAwLjYzMDg3Mkw3LjI3ODU3IDBMMi44NjAxNSA0Ljg2NTM1WiIvPgo8L3N2Zz4K);
  --jp-icon-undo: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjUgOGMtMi42NSAwLTUuMDUuOTktNi45IDIuNkwyIDd2OWg5bC0zLjYyLTMuNjJjMS4zOS0xLjE2IDMuMTYtMS44OCA1LjEyLTEuODggMy41NCAwIDYuNTUgMi4zMSA3LjYgNS41bDIuMzctLjc4QzIxLjA4IDExLjAzIDE3LjE1IDggMTIuNSA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-user: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE2IDdhNCA0IDAgMTEtOCAwIDQgNCAwIDAxOCAwek0xMiAxNGE3IDcgMCAwMC03IDdoMTRhNyA3IDAgMDAtNy03eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-users: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZlcnNpb249IjEuMSIgdmlld0JveD0iMCAwIDM2IDI0IiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPgogPGcgY2xhc3M9ImpwLWljb24zIiB0cmFuc2Zvcm09Im1hdHJpeCgxLjczMjcgMCAwIDEuNzMyNyAtMy42MjgyIC4wOTk1NzcpIiBmaWxsPSIjNjE2MTYxIj4KICA8cGF0aCB0cmFuc2Zvcm09Im1hdHJpeCgxLjUsMCwwLDEuNSwwLC02KSIgZD0ibTEyLjE4NiA3LjUwOThjLTEuMDUzNSAwLTEuOTc1NyAwLjU2NjUtMi40Nzg1IDEuNDEwMiAwLjc1MDYxIDAuMzEyNzcgMS4zOTc0IDAuODI2NDggMS44NzMgMS40NzI3aDMuNDg2M2MwLTEuNTkyLTEuMjg4OS0yLjg4MjgtMi44ODA5LTIuODgyOHoiLz4KICA8cGF0aCBkPSJtMjAuNDY1IDIuMzg5NWEyLjE4ODUgMi4xODg1IDAgMCAxLTIuMTg4NCAyLjE4ODUgMi4xODg1IDIuMTg4NSAwIDAgMS0yLjE4ODUtMi4xODg1IDIuMTg4NSAyLjE4ODUgMCAwIDEgMi4xODg1LTIuMTg4NSAyLjE4ODUgMi4xODg1IDAgMCAxIDIuMTg4NCAyLjE4ODV6Ii8+CiAgPHBhdGggdHJhbnNmb3JtPSJtYXRyaXgoMS41LDAsMCwxLjUsMCwtNikiIGQ9Im0zLjU4OTggOC40MjE5Yy0xLjExMjYgMC0yLjAxMzcgMC45MDExMS0yLjAxMzcgMi4wMTM3aDIuODE0NWMwLjI2Nzk3LTAuMzczMDkgMC41OTA3LTAuNzA0MzUgMC45NTg5OC0wLjk3ODUyLTAuMzQ0MzMtMC42MTY4OC0xLjAwMzEtMS4wMzUyLTEuNzU5OC0xLjAzNTJ6Ii8+CiAgPHBhdGggZD0ibTYuOTE1NCA0LjYyM2ExLjUyOTQgMS41Mjk0IDAgMCAxLTEuNTI5NCAxLjUyOTQgMS41Mjk0IDEuNTI5NCAwIDAgMS0xLjUyOTQtMS41Mjk0IDEuNTI5NCAxLjUyOTQgMCAwIDEgMS41Mjk0LTEuNTI5NCAxLjUyOTQgMS41Mjk0IDAgMCAxIDEuNTI5NCAxLjUyOTR6Ii8+CiAgPHBhdGggZD0ibTYuMTM1IDEzLjUzNWMwLTMuMjM5MiAyLjYyNTktNS44NjUgNS44NjUtNS44NjUgMy4yMzkyIDAgNS44NjUgMi42MjU5IDUuODY1IDUuODY1eiIvPgogIDxjaXJjbGUgY3g9IjEyIiBjeT0iMy43Njg1IiByPSIyLjk2ODUiLz4KIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-vega: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbjEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjEyMTIxIj4KICAgIDxwYXRoIGQ9Ik0xMC42IDUuNGwyLjItMy4ySDIuMnY3LjNsNC02LjZ6Ii8+CiAgICA8cGF0aCBkPSJNMTUuOCAyLjJsLTQuNCA2LjZMNyA2LjNsLTQuOCA4djUuNWgxNy42VjIuMmgtNHptLTcgMTUuNEg1LjV2LTQuNGgzLjN2NC40em00LjQgMEg5LjhWOS44aDMuNHY3Ljh6bTQuNCAwaC0zLjRWNi41aDMuNHYxMS4xeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-word: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KIDxnIGNsYXNzPSJqcC1pY29uMiIgZmlsbD0iIzQxNDE0MSI+CiAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiA8L2c+CiA8ZyBjbGFzcz0ianAtaWNvbi1hY2NlbnQyIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSguNDMgLjA0MDEpIiBmaWxsPSIjZmZmIj4KICA8cGF0aCBkPSJtNC4xNCA4Ljc2cTAuMDY4Mi0xLjg5IDIuNDItMS44OSAxLjE2IDAgMS42OCAwLjQyIDAuNTY3IDAuNDEgMC41NjcgMS4xNnYzLjQ3cTAgMC40NjIgMC41MTQgMC40NjIgMC4xMDMgMCAwLjItMC4wMjMxdjAuNzE0cS0wLjM5OSAwLjEwMy0wLjY1MSAwLjEwMy0wLjQ1MiAwLTAuNjkzLTAuMjItMC4yMzEtMC4yLTAuMjg0LTAuNjYyLTAuOTU2IDAuODcyLTIgMC44NzItMC45MDMgMC0xLjQ3LTAuNDcyLTAuNTI1LTAuNDcyLTAuNTI1LTEuMjYgMC0wLjI2MiAwLjA0NTItMC40NzIgMC4wNTY3LTAuMjIgMC4xMTYtMC4zNzggMC4wNjgyLTAuMTY4IDAuMjMxLTAuMzA0IDAuMTU4LTAuMTQ3IDAuMjYyLTAuMjQyIDAuMTE2LTAuMDkxNCAwLjM2OC0wLjE2OCAwLjI2Mi0wLjA5MTQgMC4zOTktMC4xMjYgMC4xMzYtMC4wNDUyIDAuNDcyLTAuMTAzIDAuMzM2LTAuMDU3OCAwLjUwNC0wLjA3OTggMC4xNTgtMC4wMjMxIDAuNTY3LTAuMDc5OCAwLjU1Ni0wLjA2ODIgMC43NzctMC4yMjEgMC4yMi0wLjE1MiAwLjIyLTAuNDQxdi0wLjI1MnEwLTAuNDMtMC4zNTctMC42NjItMC4zMzYtMC4yMzEtMC45NzYtMC4yMzEtMC42NjIgMC0wLjk5OCAwLjI2Mi0wLjMzNiAwLjI1Mi0wLjM5OSAwLjc5OHptMS44OSAzLjY4cTAuNzg4IDAgMS4yNi0wLjQxIDAuNTA0LTAuNDIgMC41MDQtMC45MDN2LTEuMDVxLTAuMjg0IDAuMTM2LTAuODYxIDAuMjMxLTAuNTY3IDAuMDkxNC0wLjk4NyAwLjE1OC0wLjQyIDAuMDY4Mi0wLjc2NiAwLjMyNi0wLjMzNiAwLjI1Mi0wLjMzNiAwLjcwNHQwLjMwNCAwLjcwNCAwLjg2MSAwLjI1MnoiIHN0cm9rZS13aWR0aD0iMS4wNSIvPgogIDxwYXRoIGQ9Im0xMCA0LjU2aDAuOTQ1djMuMTVxMC42NTEtMC45NzYgMS44OS0wLjk3NiAxLjE2IDAgMS44OSAwLjg0IDAuNjgyIDAuODQgMC42ODIgMi4zMSAwIDEuNDctMC43MDQgMi40Mi0wLjcwNCAwLjg4Mi0xLjg5IDAuODgyLTEuMjYgMC0xLjg5LTEuMDJ2MC43NjZoLTAuODV6bTIuNjIgMy4wNHEtMC43NDYgMC0xLjE2IDAuNjQtMC40NTIgMC42My0wLjQ1MiAxLjY4IDAgMS4wNSAwLjQ1MiAxLjY4dDEuMTYgMC42M3EwLjc3NyAwIDEuMjYtMC42MyAwLjQ5NC0wLjY0IDAuNDk0LTEuNjggMC0xLjA1LTAuNDcyLTEuNjgtMC40NjItMC42NC0xLjI2LTAuNjR6IiBzdHJva2Utd2lkdGg9IjEuMDUiLz4KICA8cGF0aCBkPSJtMi43MyAxNS44IDEzLjYgMC4wMDgxYzAuMDA2OSAwIDAtMi42IDAtMi42IDAtMC4wMDc4LTEuMTUgMC0xLjE1IDAtMC4wMDY5IDAtMC4wMDgzIDEuNS0wLjAwODMgMS41LTJlLTMgLTAuMDAxNC0xMS4zLTAuMDAxNC0xMS4zLTAuMDAxNGwtMC4wMDU5Mi0xLjVjMC0wLjAwNzgtMS4xNyAwLjAwMTMtMS4xNyAwLjAwMTN6IiBzdHJva2Utd2lkdGg9Ii45NzUiLz4KIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-yaml: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1jb250cmFzdDIganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjRDgxQjYwIj4KICAgIDxwYXRoIGQ9Ik03LjIgMTguNnYtNS40TDMgNS42aDMuM2wxLjQgMy4xYy4zLjkuNiAxLjYgMSAyLjUuMy0uOC42LTEuNiAxLTIuNWwxLjQtMy4xaDMuNGwtNC40IDcuNnY1LjVsLTIuOS0uMXoiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxNi41IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxMSIgcj0iMi4xIi8+CiAgPC9nPgo8L3N2Zz4K);
}

/* Icon CSS class declarations */

.jp-AddAboveIcon {
  background-image: var(--jp-icon-add-above);
}

.jp-AddBelowIcon {
  background-image: var(--jp-icon-add-below);
}

.jp-AddIcon {
  background-image: var(--jp-icon-add);
}

.jp-BellIcon {
  background-image: var(--jp-icon-bell);
}

.jp-BugDotIcon {
  background-image: var(--jp-icon-bug-dot);
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

.jp-CodeCheckIcon {
  background-image: var(--jp-icon-code-check);
}

.jp-CodeIcon {
  background-image: var(--jp-icon-code);
}

.jp-CollapseAllIcon {
  background-image: var(--jp-icon-collapse-all);
}

.jp-ConsoleIcon {
  background-image: var(--jp-icon-console);
}

.jp-CopyIcon {
  background-image: var(--jp-icon-copy);
}

.jp-CopyrightIcon {
  background-image: var(--jp-icon-copyright);
}

.jp-CutIcon {
  background-image: var(--jp-icon-cut);
}

.jp-DeleteIcon {
  background-image: var(--jp-icon-delete);
}

.jp-DownloadIcon {
  background-image: var(--jp-icon-download);
}

.jp-DuplicateIcon {
  background-image: var(--jp-icon-duplicate);
}

.jp-EditIcon {
  background-image: var(--jp-icon-edit);
}

.jp-EllipsesIcon {
  background-image: var(--jp-icon-ellipses);
}

.jp-ErrorIcon {
  background-image: var(--jp-icon-error);
}

.jp-ExpandAllIcon {
  background-image: var(--jp-icon-expand-all);
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

.jp-FilterDotIcon {
  background-image: var(--jp-icon-filter-dot);
}

.jp-FilterIcon {
  background-image: var(--jp-icon-filter);
}

.jp-FilterListIcon {
  background-image: var(--jp-icon-filter-list);
}

.jp-FolderFavoriteIcon {
  background-image: var(--jp-icon-folder-favorite);
}

.jp-FolderIcon {
  background-image: var(--jp-icon-folder);
}

.jp-HomeIcon {
  background-image: var(--jp-icon-home);
}

.jp-Html5Icon {
  background-image: var(--jp-icon-html5);
}

.jp-ImageIcon {
  background-image: var(--jp-icon-image);
}

.jp-InfoIcon {
  background-image: var(--jp-icon-info);
}

.jp-InspectorIcon {
  background-image: var(--jp-icon-inspector);
}

.jp-JsonIcon {
  background-image: var(--jp-icon-json);
}

.jp-JuliaIcon {
  background-image: var(--jp-icon-julia);
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

.jp-LaunchIcon {
  background-image: var(--jp-icon-launch);
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

.jp-MarkdownIcon {
  background-image: var(--jp-icon-markdown);
}

.jp-MoveDownIcon {
  background-image: var(--jp-icon-move-down);
}

.jp-MoveUpIcon {
  background-image: var(--jp-icon-move-up);
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

.jp-NumberingIcon {
  background-image: var(--jp-icon-numbering);
}

.jp-OfflineBoltIcon {
  background-image: var(--jp-icon-offline-bolt);
}

.jp-PaletteIcon {
  background-image: var(--jp-icon-palette);
}

.jp-PasteIcon {
  background-image: var(--jp-icon-paste);
}

.jp-PdfIcon {
  background-image: var(--jp-icon-pdf);
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

.jp-RedoIcon {
  background-image: var(--jp-icon-redo);
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

.jp-ShareIcon {
  background-image: var(--jp-icon-share);
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

.jp-TableRowsIcon {
  background-image: var(--jp-icon-table-rows);
}

.jp-TagIcon {
  background-image: var(--jp-icon-tag);
}

.jp-TerminalIcon {
  background-image: var(--jp-icon-terminal);
}

.jp-TextEditorIcon {
  background-image: var(--jp-icon-text-editor);
}

.jp-TocIcon {
  background-image: var(--jp-icon-toc);
}

.jp-TreeViewIcon {
  background-image: var(--jp-icon-tree-view);
}

.jp-TrustedIcon {
  background-image: var(--jp-icon-trusted);
}

.jp-UndoIcon {
  background-image: var(--jp-icon-undo);
}

.jp-UserIcon {
  background-image: var(--jp-icon-user);
}

.jp-UsersIcon {
  background-image: var(--jp-icon-users);
}

.jp-VegaIcon {
  background-image: var(--jp-icon-vega);
}

.jp-WordIcon {
  background-image: var(--jp-icon-word);
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

.lm-TabBar .lm-TabBar-addButton {
  align-items: center;
  display: flex;
  padding: 4px;
  padding-bottom: 5px;
  margin-right: 1px;
  background-color: var(--jp-layout-color2);
}

.lm-TabBar .lm-TabBar-addButton:hover {
  background-color: var(--jp-layout-color1);
}

.lm-DockPanel-tabBar .lm-TabBar-tab {
  width: var(--jp-private-horizontal-tab-width);
}

.lm-DockPanel-tabBar .lm-TabBar-content {
  flex: unset;
}

.lm-DockPanel-tabBar[data-orientation='horizontal'] {
  flex: 1 1 auto;
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

.jp-icon-dot[fill] {
  fill: var(--jp-warn-color0);
}

.jp-jupyter-icon-color[fill] {
  fill: var(--jp-jupyter-icon-color, var(--jp-warn-color0));
}

.jp-notebook-icon-color[fill] {
  fill: var(--jp-notebook-icon-color, var(--jp-warn-color0));
}

.jp-json-icon-color[fill] {
  fill: var(--jp-json-icon-color, var(--jp-warn-color1));
}

.jp-console-icon-color[fill] {
  fill: var(--jp-console-icon-color, white);
}

.jp-console-icon-background-color[fill] {
  fill: var(--jp-console-icon-background-color, var(--jp-brand-color1));
}

.jp-terminal-icon-color[fill] {
  fill: var(--jp-terminal-icon-color, var(--jp-layout-color2));
}

.jp-terminal-icon-background-color[fill] {
  fill: var(
    --jp-terminal-icon-background-color,
    var(--jp-inverse-layout-color2)
  );
}

.jp-text-editor-icon-color[fill] {
  fill: var(--jp-text-editor-icon-color, var(--jp-inverse-layout-color3));
}

.jp-inspector-icon-color[fill] {
  fill: var(--jp-inspector-icon-color, var(--jp-inverse-layout-color3));
}

/* CSS for icons in selected filebrowser listing items */
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}

.jp-DirListing-item.jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* stylelint-disable selector-max-class, selector-max-compound-selectors */

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

/* stylelint-enable selector-max-class, selector-max-compound-selectors */

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

.jp-icon-hoverShow:not(:hover) .jp-icon-hoverShow-content {
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

.jp-IFrame {
  width: 100%;
  height: 100%;
}

.jp-IFrame > iframe {
  border: none;
}

/*
When drag events occur, `lm-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-IFrame {
  position: relative;
}

body.lm-mod-override-cursor .jp-IFrame::before {
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

.jp-HoverBox {
  position: fixed;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-FormGroup-content fieldset {
  border: none;
  padding: 0;
  min-width: 0;
  width: 100%;
}

/* stylelint-disable selector-max-type */

.jp-FormGroup-content fieldset .jp-inputFieldWrapper input,
.jp-FormGroup-content fieldset .jp-inputFieldWrapper select,
.jp-FormGroup-content fieldset .jp-inputFieldWrapper textarea {
  font-size: var(--jp-content-font-size2);
  border-color: var(--jp-input-border-color);
  border-style: solid;
  border-radius: var(--jp-border-radius);
  border-width: 1px;
  padding: 6px 8px;
  background: none;
  color: var(--jp-ui-font-color0);
  height: inherit;
}

.jp-FormGroup-content fieldset input[type='checkbox'] {
  position: relative;
  top: 2px;
  margin-left: 0;
}

.jp-FormGroup-content button.jp-mod-styled {
  cursor: pointer;
}

.jp-FormGroup-content .checkbox label {
  cursor: pointer;
  font-size: var(--jp-content-font-size1);
}

.jp-FormGroup-content .jp-root > fieldset > legend {
  display: none;
}

.jp-FormGroup-content .jp-root > fieldset > p {
  display: none;
}

/** copy of `input.jp-mod-styled:focus` style */
.jp-FormGroup-content fieldset input:focus,
.jp-FormGroup-content fieldset select:focus {
  -moz-outline-radius: unset;
  outline: var(--jp-border-width) solid var(--md-blue-500);
  outline-offset: -1px;
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-FormGroup-content fieldset input:hover:not(:focus),
.jp-FormGroup-content fieldset select:hover:not(:focus) {
  background-color: var(--jp-border-color2);
}

/* stylelint-enable selector-max-type */

.jp-FormGroup-content .checkbox .field-description {
  /* Disable default description field for checkbox:
   because other widgets do not have description fields,
   we add descriptions to each widget on the field level.
  */
  display: none;
}

.jp-FormGroup-content #root__description {
  display: none;
}

.jp-FormGroup-content .jp-modifiedIndicator {
  width: 5px;
  background-color: var(--jp-brand-color2);
  margin-top: 0;
  margin-left: calc(var(--jp-private-settingeditor-modifier-indent) * -1);
  flex-shrink: 0;
}

.jp-FormGroup-content .jp-modifiedIndicator.jp-errorIndicator {
  background-color: var(--jp-error-color0);
  margin-right: 0.5em;
}

/* RJSF ARRAY style */

.jp-arrayFieldWrapper legend {
  font-size: var(--jp-content-font-size2);
  color: var(--jp-ui-font-color0);
  flex-basis: 100%;
  padding: 4px 0;
  font-weight: var(--jp-content-heading-font-weight);
  border-bottom: 1px solid var(--jp-border-color2);
}

.jp-arrayFieldWrapper .field-description {
  padding: 4px 0;
  white-space: pre-wrap;
}

.jp-arrayFieldWrapper .array-item {
  width: 100%;
  border: 1px solid var(--jp-border-color2);
  border-radius: 4px;
  margin: 4px;
}

.jp-ArrayOperations {
  display: flex;
  margin-left: 8px;
}

.jp-ArrayOperationsButton {
  margin: 2px;
}

.jp-ArrayOperationsButton .jp-icon3[fill] {
  fill: var(--jp-ui-font-color0);
}

button.jp-ArrayOperationsButton.jp-mod-styled:disabled {
  cursor: not-allowed;
  opacity: 0.5;
}

/* RJSF form validation error */

.jp-FormGroup-content .validationErrors {
  color: var(--jp-error-color0);
}

/* Hide panel level error as duplicated the field level error */
.jp-FormGroup-content .panel.errors {
  display: none;
}

/* RJSF normal content (settings-editor) */

.jp-FormGroup-contentNormal {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}

.jp-FormGroup-contentNormal .jp-FormGroup-contentItem {
  margin-left: 7px;
  color: var(--jp-ui-font-color0);
}

.jp-FormGroup-contentNormal .jp-FormGroup-description {
  flex-basis: 100%;
  padding: 4px 7px;
}

.jp-FormGroup-contentNormal .jp-FormGroup-default {
  flex-basis: 100%;
  padding: 4px 7px;
}

.jp-FormGroup-contentNormal .jp-FormGroup-fieldLabel {
  font-size: var(--jp-content-font-size1);
  font-weight: normal;
  min-width: 120px;
}

.jp-FormGroup-contentNormal fieldset:not(:first-child) {
  margin-left: 7px;
}

.jp-FormGroup-contentNormal .field-array-of-string .array-item {
  /* Display `jp-ArrayOperations` buttons side-by-side with content except
    for small screens where flex-wrap will place them one below the other.
  */
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}

.jp-FormGroup-contentNormal .jp-objectFieldWrapper .form-group {
  padding: 2px 8px 2px var(--jp-private-settingeditor-modifier-indent);
  margin-top: 2px;
}

/* RJSF compact content (metadata-form) */

.jp-FormGroup-content.jp-FormGroup-contentCompact {
  width: 100%;
}

.jp-FormGroup-contentCompact .form-group {
  display: flex;
  padding: 0.5em 0.2em 0.5em 0;
}

.jp-FormGroup-contentCompact
  .jp-FormGroup-compactTitle
  .jp-FormGroup-description {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color2);
}

.jp-FormGroup-contentCompact .jp-FormGroup-fieldLabel {
  padding-bottom: 0.3em;
}

.jp-FormGroup-contentCompact .jp-inputFieldWrapper .form-control {
  width: 100%;
  box-sizing: border-box;
}

.jp-FormGroup-contentCompact .jp-arrayFieldWrapper .jp-FormGroup-compactTitle {
  padding-bottom: 7px;
}

.jp-FormGroup-contentCompact
  .jp-objectFieldWrapper
  .jp-objectFieldWrapper
  .form-group {
  padding: 2px 8px 2px var(--jp-private-settingeditor-modifier-indent);
  margin-top: 2px;
}

.jp-FormGroup-contentCompact ul.error-detail {
  margin-block-start: 0.5em;
  margin-block-end: 0.5em;
  padding-inline-start: 1em;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-SidePanel {
  display: flex;
  flex-direction: column;
  min-width: var(--jp-sidebar-min-width);
  overflow-y: auto;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  font-size: var(--jp-ui-font-size1);
}

.jp-SidePanel-header {
  flex: 0 0 auto;
  display: flex;
  border-bottom: var(--jp-border-width) solid var(--jp-border-color2);
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  letter-spacing: 1px;
  margin: 0;
  padding: 2px;
  text-transform: uppercase;
}

.jp-SidePanel-toolbar {
  flex: 0 0 auto;
}

.jp-SidePanel-content {
  flex: 1 1 auto;
}

.jp-SidePanel-toolbar,
.jp-AccordionPanel-toolbar {
  height: var(--jp-private-toolbar-height);
}

.jp-SidePanel-toolbar.jp-Toolbar-micro {
  display: none;
}

.lm-AccordionPanel .jp-AccordionPanel-title {
  box-sizing: border-box;
  line-height: 25px;
  margin: 0;
  display: flex;
  align-items: center;
  background: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  font-size: var(--jp-ui-font-size0);
}

.jp-AccordionPanel-title {
  cursor: pointer;
  user-select: none;
  -moz-user-select: none;
  -webkit-user-select: none;
  text-transform: uppercase;
}

.lm-AccordionPanel[data-orientation='horizontal'] > .jp-AccordionPanel-title {
  /* Title is rotated for horizontal accordion panel using CSS */
  display: block;
  transform-origin: top left;
  transform: rotate(-90deg) translate(-100%);
}

.jp-AccordionPanel-title .lm-AccordionPanel-titleLabel {
  user-select: none;
  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
}

.jp-AccordionPanel-title .lm-AccordionPanel-titleCollapser {
  transform: rotate(-90deg);
  margin: auto 0;
  height: 16px;
}

.jp-AccordionPanel-title.lm-mod-expanded .lm-AccordionPanel-titleCollapser {
  transform: rotate(0deg);
}

.lm-AccordionPanel .jp-AccordionPanel-toolbar {
  background: none;
  box-shadow: none;
  border: none;
  margin-left: auto;
}

.lm-AccordionPanel .lm-SplitPanel-handle:hover {
  background: var(--jp-layout-color3);
}

.jp-text-truncated {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
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

.jp-SpinnerContent::before {
  width: 50%;
  height: 50%;
  background: #f37626;
  border-radius: 100% 0 0;
  position: absolute;
  top: 0;
  left: 0;
  content: '';
}

.jp-SpinnerContent::after {
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
  padding: 0 12px;
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

input[type='checkbox'].jp-mod-styled {
  appearance: checkbox;
  -webkit-appearance: checkbox;
  -moz-appearance: checkbox;
  height: auto;
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
  box-sizing: border-box;
  margin-bottom: 12px;
}

.jp-select-wrapper:not(.multiple) {
  height: 28px;
}

.jp-select-wrapper.jp-mod-focused select.jp-mod-styled {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-input-active-background);
}

select.jp-mod-styled:hover {
  cursor: pointer;
  color: var(--jp-ui-font-color0);
  background-color: var(--jp-input-hover-background);
  box-shadow: inset 0 0 1px rgba(0, 0, 0, 0.5);
}

select.jp-mod-styled {
  flex: 1 1 auto;
  width: 100%;
  font-size: var(--jp-ui-font-size2);
  background: var(--jp-input-background);
  color: var(--jp-ui-font-color0);
  padding: 0 25px 0 8px;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

select.jp-mod-styled:not([multiple]) {
  height: 32px;
}

select.jp-mod-styled[multiple] {
  max-height: 200px;
  overflow-y: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-switch {
  display: flex;
  align-items: center;
  padding-left: 4px;
  padding-right: 4px;
  font-size: var(--jp-ui-font-size1);
  background-color: transparent;
  color: var(--jp-ui-font-color1);
  border: none;
  height: 20px;
}

.jp-switch:hover {
  background-color: var(--jp-layout-color2);
}

.jp-switch-label {
  margin-right: 5px;
  font-family: var(--jp-ui-font-family);
}

.jp-switch-track {
  cursor: pointer;
  background-color: var(--jp-switch-color, var(--jp-border-color1));
  -webkit-transition: 0.4s;
  transition: 0.4s;
  border-radius: 34px;
  height: 16px;
  width: 35px;
  position: relative;
}

.jp-switch-track::before {
  content: '';
  position: absolute;
  height: 10px;
  width: 10px;
  margin: 3px;
  left: 0;
  background-color: var(--jp-ui-inverse-font-color1);
  -webkit-transition: 0.4s;
  transition: 0.4s;
  border-radius: 50%;
}

.jp-switch[aria-checked='true'] .jp-switch-track {
  background-color: var(--jp-switch-true-position-color, var(--jp-warn-color0));
}

.jp-switch[aria-checked='true'] .jp-switch-track::before {
  /* track width (35) - margins (3 + 3) - thumb width (10) */
  left: 19px;
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
  z-index: 8;
  overflow-x: hidden;
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
  padding: 0;
  margin: 0;
}

button.jp-ToolbarButtonComponent {
  background: var(--jp-layout-color1);
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0 6px;
  margin: 0;
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

button.jp-ToolbarButtonComponent > span {
  padding: 0;
  flex: 0 0 auto;
}

button.jp-ToolbarButtonComponent .jp-ToolbarButtonComponent-label {
  font-size: var(--jp-ui-font-size1);
  line-height: 100%;
  padding-left: 2px;
  color: var(--jp-ui-font-color1);
  font-family: var(--jp-ui-font-family);
}

#jp-main-dock-panel[data-mode='single-document']
  .jp-MainAreaWidget
  > .jp-Toolbar.jp-Toolbar-micro {
  padding: 0;
  min-height: 0;
}

#jp-main-dock-panel[data-mode='single-document']
  .jp-MainAreaWidget
  > .jp-Toolbar {
  border: none;
  box-shadow: none;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-WindowedPanel-outer {
  position: relative;
  overflow-y: auto;
}

.jp-WindowedPanel-inner {
  position: relative;
}

.jp-WindowedPanel-window {
  position: absolute;
  left: 0;
  right: 0;
  overflow: visible;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* Sibling imports */

body {
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
}

/* Disable native link decoration styles everywhere outside of dialog boxes */
a {
  text-decoration: unset;
  color: unset;
}

a:hover {
  text-decoration: unset;
  color: unset;
}

/* Accessibility for links inside dialog box text */
.jp-Dialog-content a {
  text-decoration: revert;
  color: var(--jp-content-link-color);
}

.jp-Dialog-content a:hover {
  text-decoration: revert;
}

/* Styles for ui-components */
.jp-Button {
  color: var(--jp-ui-font-color2);
  border-radius: var(--jp-border-radius);
  padding: 0 12px;
  font-size: var(--jp-ui-font-size1);

  /* Copy from blueprint 3 */
  display: inline-flex;
  flex-direction: row;
  border: none;
  cursor: pointer;
  align-items: center;
  justify-content: center;
  text-align: left;
  vertical-align: middle;
  min-height: 30px;
  min-width: 30px;
}

.jp-Button:disabled {
  cursor: not-allowed;
}

.jp-Button:empty {
  padding: 0 !important;
}

.jp-Button.jp-mod-small {
  min-height: 24px;
  min-width: 24px;
  font-size: 12px;
  padding: 0 7px;
}

/* Use our own theme for hover styles */
.jp-Button.jp-mod-minimal:hover {
  background-color: var(--jp-layout-color2);
}

.jp-Button.jp-mod-minimal {
  background: none;
}

.jp-InputGroup {
  display: block;
  position: relative;
}

.jp-InputGroup input {
  box-sizing: border-box;
  border: none;
  border-radius: 0;
  background-color: transparent;
  color: var(--jp-ui-font-color0);
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
  padding-bottom: 0;
  padding-top: 0;
  padding-left: 10px;
  padding-right: 28px;
  position: relative;
  width: 100%;
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  font-size: 14px;
  font-weight: 400;
  height: 30px;
  line-height: 30px;
  outline: none;
  vertical-align: middle;
}

.jp-InputGroup input:focus {
  box-shadow: inset 0 0 0 var(--jp-border-width)
      var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-InputGroup input:disabled {
  cursor: not-allowed;
  resize: block;
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color2);
}

.jp-InputGroup input:disabled ~ span {
  cursor: not-allowed;
  color: var(--jp-ui-font-color2);
}

.jp-InputGroup input::placeholder,
input::placeholder {
  color: var(--jp-ui-font-color2);
}

.jp-InputGroupAction {
  position: absolute;
  bottom: 1px;
  right: 0;
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
  font-family: var(--jp-ui-font-family);
  height: 24px;
  line-height: 14px;
  padding: 0 25px 0 10px;
  text-align: left;
  -moz-appearance: none;
  -webkit-appearance: none;
}

.jp-HTMLSelect.jp-DefaultStyle select:disabled {
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color2);
  cursor: not-allowed;
  resize: block;
}

.jp-HTMLSelect.jp-DefaultStyle select:disabled ~ span {
  cursor: not-allowed;
}

/* Use our own theme for hover and option styles */
/* stylelint-disable-next-line selector-max-type */
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

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-StatusBar-Widget {
  display: flex;
  align-items: center;
  background: var(--jp-layout-color2);
  min-height: var(--jp-statusbar-height);
  justify-content: space-between;
  padding: 0 10px;
}

.jp-StatusBar-Left {
  display: flex;
  align-items: center;
  flex-direction: row;
}

.jp-StatusBar-Middle {
  display: flex;
  align-items: center;
}

.jp-StatusBar-Right {
  display: flex;
  align-items: center;
  flex-direction: row-reverse;
}

.jp-StatusBar-Item {
  max-height: var(--jp-statusbar-height);
  margin: 0 2px;
  height: var(--jp-statusbar-height);
  white-space: nowrap;
  text-overflow: ellipsis;
  color: var(--jp-ui-font-color1);
  padding: 0 6px;
}

.jp-mod-highlighted:hover {
  background-color: var(--jp-layout-color3);
}

.jp-mod-clicked {
  background-color: var(--jp-brand-color1);
}

.jp-mod-clicked:hover {
  background-color: var(--jp-brand-color0);
}

.jp-mod-clicked .jp-StatusBar-TextItem {
  color: var(--jp-ui-inverse-font-color1);
}

.jp-StatusBar-HoverItem {
  box-shadow: '0px 4px 4px rgba(0, 0, 0, 0.25)';
}

.jp-StatusBar-TextItem {
  font-size: var(--jp-ui-font-size1);
  font-family: var(--jp-ui-font-family);
  line-height: 24px;
  color: var(--jp-ui-font-color1);
}

.jp-StatusBar-GroupItem {
  display: flex;
  align-items: center;
  flex-direction: row;
}

.jp-Statusbar-ProgressCircle svg {
  display: block;
  margin: 0 auto;
  width: 16px;
  height: 24px;
  align-self: normal;
}

.jp-Statusbar-ProgressCircle path {
  fill: var(--jp-inverse-layout-color3);
}

.jp-Statusbar-ProgressBar-progress-bar {
  height: 10px;
  width: 100px;
  border: solid 0.25px var(--jp-brand-color2);
  border-radius: 3px;
  overflow: hidden;
  align-self: center;
}

.jp-Statusbar-ProgressBar-progress-bar > div {
  background-color: var(--jp-brand-color2);
  background-image: linear-gradient(
    -45deg,
    rgba(255, 255, 255, 0.2) 25%,
    transparent 25%,
    transparent 50%,
    rgba(255, 255, 255, 0.2) 50%,
    rgba(255, 255, 255, 0.2) 75%,
    transparent 75%,
    transparent
  );
  background-size: 40px 40px;
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 14px;
  color: #fff;
  text-align: center;
  animation: jp-Statusbar-ExecutionTime-progress-bar 2s linear infinite;
}

.jp-Statusbar-ProgressBar-progress-bar p {
  color: var(--jp-ui-font-color1);
  font-family: var(--jp-ui-font-family);
  font-size: var(--jp-ui-font-size1);
  line-height: 10px;
  width: 100px;
}

@keyframes jp-Statusbar-ExecutionTime-progress-bar {
  0% {
    background-position: 0 0;
  }

  100% {
    background-position: 40px 40px;
  }
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
  padding-bottom: 0;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);

  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Modal variant
|----------------------------------------------------------------------------*/

.jp-ModalCommandPalette {
  position: absolute;
  z-index: 10000;
  top: 38px;
  left: 30%;
  margin: 0;
  padding: 4px;
  width: 40%;
  box-shadow: var(--jp-elevation-z4);
  border-radius: 4px;
  background: var(--jp-layout-color0);
}

.jp-ModalCommandPalette .lm-CommandPalette {
  max-height: 40vh;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-close-icon::after {
  display: none;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-CommandPalette-header {
  display: none;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-CommandPalette-item {
  margin-left: 4px;
  margin-right: 4px;
}

.jp-ModalCommandPalette
  .lm-CommandPalette
  .lm-CommandPalette-item.lm-mod-disabled {
  display: none;
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
  padding: 0 9px;
  background-color: var(--jp-input-active-background);
  height: 30px;
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.lm-CommandPalette.lm-mod-focused .lm-CommandPalette-wrapper {
  box-shadow: inset 0 0 0 1px var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-SearchIconGroup {
  color: white;
  background-color: var(--jp-brand-color1);
  position: absolute;
  top: 4px;
  right: 4px;
  padding: 5px 5px 1px;
}

.jp-SearchIconGroup svg {
  height: 20px;
  width: 20px;
}

.jp-SearchIconGroup .jp-icon3[fill] {
  fill: var(--jp-layout-color0);
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
  color: var(--jp-ui-font-color2);
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Results
|----------------------------------------------------------------------------*/

.lm-CommandPalette-header:first-child {
  margin-top: 0;
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
  color: var(--jp-ui-font-color2);
}

.lm-CommandPalette-item.lm-mod-active {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.lm-CommandPalette-item.lm-mod-active .lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-inverse-font-color0);
}

.lm-CommandPalette-item.lm-mod-active .jp-icon-selectable[fill] {
  fill: var(--jp-layout-color0);
}

.lm-CommandPalette-item.lm-mod-active:hover:not(.lm-mod-disabled) {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
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
  color: var(--jp-ui-font-color2);
}

.lm-CommandPalette-item .lm-CommandPalette-itemIcon {
  margin: 0 4px 0 0;
  position: relative;
  width: 16px;
  top: 2px;
  flex: 0 0 auto;
}

.lm-CommandPalette-item.lm-mod-disabled .lm-CommandPalette-itemIcon {
  opacity: 0.6;
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

.lm-CommandPalette-content:empty::after {
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
  padding: 0 8px;
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
  top: 0;
  left: 0;
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
  padding: 24px 24px 12px;
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
  resize: both;
}

.jp-Dialog-content.jp-Dialog-content-small {
  max-width: 500px;
}

.jp-Dialog-button {
  overflow: visible;
}

button.jp-Dialog-button:focus {
  outline: 1px solid var(--jp-brand-color1);
  outline-offset: 4px;
  -moz-outline-radius: 0;
}

button.jp-Dialog-button:focus::-moz-focus-inner {
  border: 0;
}

button.jp-Dialog-button.jp-mod-styled.jp-mod-accept:focus,
button.jp-Dialog-button.jp-mod-styled.jp-mod-warn:focus,
button.jp-Dialog-button.jp-mod-styled.jp-mod-reject:focus {
  outline-offset: 4px;
  -moz-outline-radius: 0;
}

button.jp-Dialog-button.jp-mod-styled.jp-mod-accept:focus {
  outline: 1px solid var(--jp-accept-color-normal, var(--jp-brand-color1));
}

button.jp-Dialog-button.jp-mod-styled.jp-mod-warn:focus {
  outline: 1px solid var(--jp-warn-color-normal, var(--jp-error-color1));
}

button.jp-Dialog-button.jp-mod-styled.jp-mod-reject:focus {
  outline: 1px solid var(--jp-reject-color-normal, var(--md-grey-600));
}

button.jp-Dialog-close-button {
  padding: 0;
  height: 100%;
  min-width: unset;
  min-height: unset;
}

.jp-Dialog-header {
  display: flex;
  justify-content: space-between;
  flex: 0 0 auto;
  padding-bottom: 12px;
  font-size: var(--jp-ui-font-size3);
  font-weight: 400;
  color: var(--jp-ui-font-color1);
}

.jp-Dialog-body {
  display: flex;
  flex-direction: column;
  flex: 1 1 auto;
  font-size: var(--jp-ui-font-size1);
  background: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  overflow: auto;
}

.jp-Dialog-footer {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  align-items: center;
  flex: 0 0 auto;
  margin-left: -12px;
  margin-right: -12px;
  padding: 12px;
}

.jp-Dialog-checkbox {
  padding-right: 5px;
}

.jp-Dialog-checkbox > input:focus-visible {
  outline: 1px solid var(--jp-input-active-border-color);
  outline-offset: 1px;
}

.jp-Dialog-spacer {
  flex: 1 1 auto;
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
  padding: 0 16px;
}

.jp-Dialog-body > label {
  line-height: 1.4;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-button.jp-mod-styled:not(:last-child) {
  margin-right: 12px;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-Input-Boolean-Dialog {
  flex-direction: row-reverse;
  align-items: end;
  width: 100%;
}

.jp-Input-Boolean-Dialog > label {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MainAreaWidget > :focus {
  outline: none;
}

.jp-MainAreaWidget .jp-MainAreaWidget-error {
  padding: 6px;
}

.jp-MainAreaWidget .jp-MainAreaWidget-error > pre {
  width: auto;
  padding: 10px;
  background: var(--jp-error-color3);
  border: var(--jp-border-width) solid var(--jp-error-color1);
  border-radius: var(--jp-border-radius);
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  white-space: pre-wrap;
  word-wrap: break-word;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

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
  --md-purple-A700: #a0f;
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
  --md-yellow-A200: #ff0;
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
  --md-grey-200: #eee;
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
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| RenderedText
|----------------------------------------------------------------------------*/

:root {
  /* This is the padding value to fill the gaps between lines containing spans with background color. */
  --jp-private-code-span-padding: calc(
    (var(--jp-code-line-height) - 1) * var(--jp-code-font-size) / 2
  );
}

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
  margin: 0;
  padding: 0;
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
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-red-bg {
  background-color: #e75c58;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-green-bg {
  background-color: #00a250;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-yellow-bg {
  background-color: #ddb62b;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-blue-bg {
  background-color: #208ffb;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-magenta-bg {
  background-color: #d160c4;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-cyan-bg {
  background-color: #60c6c8;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-white-bg {
  background-color: #c5c1b4;
  padding: var(--jp-private-code-span-padding) 0;
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
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-red-intense-bg {
  background-color: #b22b31;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-green-intense-bg {
  background-color: #007427;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-yellow-intense-bg {
  background-color: #b27d12;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-blue-intense-bg {
  background-color: #0065ca;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-magenta-intense-bg {
  background-color: #a03196;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-cyan-intense-bg {
  background-color: #258f8f;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-white-intense-bg {
  background-color: #a1a6b2;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-default-inverse-fg {
  color: var(--jp-ui-inverse-font-color0);
}

.jp-RenderedText pre .ansi-default-inverse-bg {
  background-color: var(--jp-inverse-layout-color0);
  padding: var(--jp-private-code-span-padding) 0;
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

/* stylelint-disable selector-max-type, selector-max-compound-selectors */

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
  margin-bottom: 0;
}

/* stylelint-enable selector-max-type, selector-max-compound-selectors */

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
  font-size: var(--jp-ui-font-size1);
  table-layout: fixed;
  margin-left: auto;
  margin-bottom: 1em;
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
  padding: 0.5em;
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

.jp-RenderedHTMLCommon p {
  text-align: left;
  margin: 0;
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
  font-size: var(--jp-ui-font-size0);
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

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

.lm-cursor-backdrop {
  position: fixed;
  width: 200px;
  height: 200px;
  margin-top: -100px;
  margin-left: -100px;
  will-change: transform;
  z-index: 100;
}

.lm-mod-drag-image {
  will-change: transform;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-lineFormSearch {
  padding: 4px 12px;
  background-color: var(--jp-layout-color2);
  box-shadow: var(--jp-toolbar-box-shadow);
  z-index: 2;
  font-size: var(--jp-ui-font-size1);
}

.jp-lineFormCaption {
  font-size: var(--jp-ui-font-size0);
  line-height: var(--jp-ui-font-size1);
  margin-top: 4px;
  color: var(--jp-ui-font-color0);
}

.jp-baseLineForm {
  border: none;
  border-radius: 0;
  position: absolute;
  background-size: 16px;
  background-repeat: no-repeat;
  background-position: center;
  outline: none;
}

.jp-lineFormButtonContainer {
  top: 4px;
  right: 8px;
  height: 24px;
  padding: 0 12px;
  width: 12px;
}

.jp-lineFormButtonIcon {
  top: 0;
  right: 0;
  background-color: var(--jp-brand-color1);
  height: 100%;
  width: 100%;
  box-sizing: border-box;
  padding: 4px 6px;
}

.jp-lineFormButton {
  top: 0;
  right: 0;
  background-color: transparent;
  height: 100%;
  width: 100%;
  box-sizing: border-box;
}

.jp-lineFormWrapper {
  overflow: hidden;
  padding: 0 8px;
  border: 1px solid var(--jp-border-color0);
  background-color: var(--jp-input-active-background);
  height: 22px;
}

.jp-lineFormWrapperFocusWithin {
  border: var(--jp-border-width) solid var(--md-blue-500);
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-lineFormInput {
  background: transparent;
  width: 200px;
  height: 100%;
  border: none;
  outline: none;
  color: var(--jp-ui-font-color0);
  line-height: 28px;
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
  border-radius: 0;
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
.jp-DocumentSearch-input {
  border: none;
  outline: none;
  color: var(--jp-ui-font-color0);
  font-size: var(--jp-ui-font-size1);
  background-color: var(--jp-layout-color0);
  font-family: var(--jp-ui-font-family);
  padding: 2px 1px;
  resize: none;
}

.jp-DocumentSearch-overlay {
  position: absolute;
  background-color: var(--jp-toolbar-background);
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  border-left: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  top: 0;
  right: 0;
  z-index: 7;
  min-width: 405px;
  padding: 2px;
  font-size: var(--jp-ui-font-size1);

  --jp-private-document-search-button-height: 20px;
}

.jp-DocumentSearch-overlay button {
  background-color: var(--jp-toolbar-background);
  outline: 0;
}

.jp-DocumentSearch-overlay button:hover {
  background-color: var(--jp-layout-color2);
}

.jp-DocumentSearch-overlay button:active {
  background-color: var(--jp-layout-color3);
}

.jp-DocumentSearch-overlay-row {
  display: flex;
  align-items: center;
  margin-bottom: 2px;
}

.jp-DocumentSearch-button-content {
  display: inline-block;
  cursor: pointer;
  box-sizing: border-box;
  width: 100%;
  height: 100%;
}

.jp-DocumentSearch-button-content svg {
  width: 100%;
  height: 100%;
}

.jp-DocumentSearch-input-wrapper {
  border: var(--jp-border-width) solid var(--jp-border-color0);
  display: flex;
  background-color: var(--jp-layout-color0);
  margin: 2px;
}

.jp-DocumentSearch-input-wrapper:focus-within {
  border-color: var(--jp-cell-editor-active-border-color);
}

.jp-DocumentSearch-toggle-wrapper,
.jp-DocumentSearch-button-wrapper {
  all: initial;
  overflow: hidden;
  display: inline-block;
  border: none;
  box-sizing: border-box;
}

.jp-DocumentSearch-toggle-wrapper {
  width: 14px;
  height: 14px;
}

.jp-DocumentSearch-button-wrapper {
  width: var(--jp-private-document-search-button-height);
  height: var(--jp-private-document-search-button-height);
}

.jp-DocumentSearch-toggle-wrapper:focus,
.jp-DocumentSearch-button-wrapper:focus {
  outline: var(--jp-border-width) solid
    var(--jp-cell-editor-active-border-color);
  outline-offset: -1px;
}

.jp-DocumentSearch-toggle-wrapper,
.jp-DocumentSearch-button-wrapper,
.jp-DocumentSearch-button-content:focus {
  outline: none;
}

.jp-DocumentSearch-toggle-placeholder {
  width: 5px;
}

.jp-DocumentSearch-input-button::before {
  display: block;
  padding-top: 100%;
}

.jp-DocumentSearch-input-button-off {
  opacity: var(--jp-search-toggle-off-opacity);
}

.jp-DocumentSearch-input-button-off:hover {
  opacity: var(--jp-search-toggle-hover-opacity);
}

.jp-DocumentSearch-input-button-on {
  opacity: var(--jp-search-toggle-on-opacity);
}

.jp-DocumentSearch-index-counter {
  padding-left: 10px;
  padding-right: 10px;
  user-select: none;
  min-width: 35px;
  display: inline-block;
}

.jp-DocumentSearch-up-down-wrapper {
  display: inline-block;
  padding-right: 2px;
  margin-left: auto;
  white-space: nowrap;
}

.jp-DocumentSearch-spacer {
  margin-left: auto;
}

.jp-DocumentSearch-up-down-wrapper button {
  outline: 0;
  border: none;
  width: var(--jp-private-document-search-button-height);
  height: var(--jp-private-document-search-button-height);
  vertical-align: middle;
  margin: 1px 5px 2px;
}

.jp-DocumentSearch-up-down-button:hover {
  background-color: var(--jp-layout-color2);
}

.jp-DocumentSearch-up-down-button:active {
  background-color: var(--jp-layout-color3);
}

.jp-DocumentSearch-filter-button {
  border-radius: var(--jp-border-radius);
}

.jp-DocumentSearch-filter-button:hover {
  background-color: var(--jp-layout-color2);
}

.jp-DocumentSearch-filter-button-enabled {
  background-color: var(--jp-layout-color2);
}

.jp-DocumentSearch-filter-button-enabled:hover {
  background-color: var(--jp-layout-color3);
}

.jp-DocumentSearch-search-options {
  padding: 0 8px;
  margin-left: 3px;
  width: 100%;
  display: grid;
  justify-content: start;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  justify-items: stretch;
}

.jp-DocumentSearch-search-filter-disabled {
  color: var(--jp-ui-font-color2);
}

.jp-DocumentSearch-search-filter {
  display: flex;
  align-items: center;
  user-select: none;
}

.jp-DocumentSearch-regex-error {
  color: var(--jp-error-color0);
}

.jp-DocumentSearch-replace-button-wrapper {
  overflow: hidden;
  display: inline-block;
  box-sizing: border-box;
  border: var(--jp-border-width) solid var(--jp-border-color0);
  margin: auto 2px;
  padding: 1px 4px;
  height: calc(var(--jp-private-document-search-button-height) + 2px);
}

.jp-DocumentSearch-replace-button-wrapper:focus {
  border: var(--jp-border-width) solid var(--jp-cell-editor-active-border-color);
}

.jp-DocumentSearch-replace-button {
  display: inline-block;
  text-align: center;
  cursor: pointer;
  box-sizing: border-box;
  color: var(--jp-ui-font-color1);

  /* height - 2 * (padding of wrapper) */
  line-height: calc(var(--jp-private-document-search-button-height) - 2px);
  width: 100%;
  height: 100%;
}

.jp-DocumentSearch-replace-button:focus {
  outline: none;
}

.jp-DocumentSearch-replace-wrapper-class {
  margin-left: 14px;
  display: flex;
}

.jp-DocumentSearch-replace-toggle {
  border: none;
  background-color: var(--jp-toolbar-background);
  border-radius: var(--jp-border-radius);
}

.jp-DocumentSearch-replace-toggle:hover {
  background-color: var(--jp-layout-color2);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.cm-editor {
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  border: 0;
  border-radius: 0;
  height: auto;

  /* Changed to auto to autogrow */
}

.cm-editor pre {
  padding: 0 var(--jp-code-padding);
}

.jp-CodeMirrorEditor[data-type='inline'] .cm-dialog {
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

.jp-CodeMirrorEditor {
  cursor: text;
}

/* When zoomed out 67% and 33% on a screen of 1440 width x 900 height */
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .jp-CodeMirrorEditor[data-type='inline'] .cm-cursor {
    border-left: var(--jp-code-cursor-width1) solid
      var(--jp-editor-cursor-color);
  }
}

/* When zoomed out less than 33% */
@media screen and (min-width: 4320px) {
  .jp-CodeMirrorEditor[data-type='inline'] .cm-cursor {
    border-left: var(--jp-code-cursor-width2) solid
      var(--jp-editor-cursor-color);
  }
}

.cm-editor.jp-mod-readOnly .cm-cursor {
  display: none;
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

.cm-searching,
.cm-searching span {
  /* `.cm-searching span`: we need to override syntax highlighting */
  background-color: var(--jp-search-unselected-match-background-color);
  color: var(--jp-search-unselected-match-color);
}

.cm-searching::selection,
.cm-searching span::selection {
  background-color: var(--jp-search-unselected-match-background-color);
  color: var(--jp-search-unselected-match-color);
}

.jp-current-match > .cm-searching,
.jp-current-match > .cm-searching span,
.cm-searching > .jp-current-match,
.cm-searching > .jp-current-match span {
  background-color: var(--jp-search-selected-match-background-color);
  color: var(--jp-search-selected-match-color);
}

.jp-current-match > .cm-searching::selection,
.cm-searching > .jp-current-match::selection,
.jp-current-match > .cm-searching span::selection {
  background-color: var(--jp-search-selected-match-background-color);
  color: var(--jp-search-selected-match-color);
}

.cm-trailingspace {
  background-image: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAgAAAAFCAYAAAB4ka1VAAAAsElEQVQIHQGlAFr/AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA7+r3zKmT0/+pk9P/7+r3zAAAAAAAAAAABAAAAAAAAAAA6OPzM+/q9wAAAAAA6OPzMwAAAAAAAAAAAgAAAAAAAAAAGR8NiRQaCgAZIA0AGR8NiQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQyoYJ/SY80UAAAAASUVORK5CYII=);
  background-position: center left;
  background-repeat: repeat-x;
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

/* Styles for shared cursors (remote cursor locations and selected ranges) */
.jp-CodeMirrorEditor .cm-ySelectionCaret {
  position: relative;
  border-left: 1px solid black;
  margin-left: -1px;
  margin-right: -1px;
  box-sizing: border-box;
}

.jp-CodeMirrorEditor .cm-ySelectionCaret > .cm-ySelectionInfo {
  white-space: nowrap;
  position: absolute;
  top: -1.15em;
  padding-bottom: 0.05em;
  left: -1px;
  font-size: 0.95em;
  font-family: var(--jp-ui-font-family);
  font-weight: bold;
  line-height: normal;
  user-select: none;
  color: white;
  padding-left: 2px;
  padding-right: 2px;
  z-index: 101;
  transition: opacity 0.3s ease-in-out;
}

.jp-CodeMirrorEditor .cm-ySelectionInfo {
  transition-delay: 0.7s;
  opacity: 0;
}

.jp-CodeMirrorEditor .cm-ySelectionCaret:hover > .cm-ySelectionInfo {
  opacity: 1;
  transition-delay: 0s;
}

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

.jp-FileBrowser .jp-SidePanel-content {
  display: flex;
  flex-direction: column;
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  flex-wrap: wrap;
  row-gap: 12px;
  border-bottom: none;
  height: auto;
  margin: 8px 12px 0;
  box-shadow: none;
  padding: 0;
  justify-content: flex-start;
}

.jp-FileBrowser-Panel {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
}

.jp-BreadCrumbs {
  flex: 0 0 auto;
  margin: 8px 12px;
}

.jp-BreadCrumbs-item {
  margin: 0 2px;
  padding: 0 2px;
  border-radius: var(--jp-border-radius);
  cursor: pointer;
}

.jp-BreadCrumbs-item:hover {
  background-color: var(--jp-layout-color2);
}

.jp-BreadCrumbs-item:first-child {
  margin-left: 0;
}

.jp-BreadCrumbs-item.jp-mod-dropTarget {
  background-color: var(--jp-brand-color2);
  opacity: 0.7;
}

/*-----------------------------------------------------------------------------
| Buttons
|----------------------------------------------------------------------------*/

.jp-FileBrowser-toolbar > .jp-Toolbar-item {
  flex: 0 0 auto;
  padding-left: 0;
  padding-right: 2px;
  align-items: center;
  height: unset;
}

.jp-FileBrowser-toolbar > .jp-Toolbar-item .jp-ToolbarButtonComponent {
  width: 40px;
}

/*-----------------------------------------------------------------------------
| Other styles
|----------------------------------------------------------------------------*/

.jp-FileDialog.jp-mod-conflict input {
  color: var(--jp-error-color1);
}

.jp-FileDialog .jp-new-name-title {
  margin-top: 12px;
}

.jp-LastModified-hidden {
  display: none;
}

.jp-FileSize-hidden {
  display: none;
}

.jp-FileBrowser .lm-AccordionPanel > h3:first-child {
  display: none;
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
  align-items: center;
  overflow: hidden;
  border-top: var(--jp-border-width) solid var(--jp-border-color2);
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  box-shadow: var(--jp-toolbar-box-shadow);
  z-index: 2;
}

.jp-DirListing-headerItem {
  padding: 4px 12px 2px;
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

.jp-DirListing-headerItem.jp-id-filesize {
  flex: 0 0 75px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
}

.jp-id-narrow {
  display: none;
  flex: 0 0 5px;
  padding: 4px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
  color: var(--jp-border-color2);
}

.jp-DirListing-narrow .jp-id-narrow {
  display: block;
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

.jp-DirListing-content mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.jp-DirListing-content .jp-DirListing-item.jp-mod-selected mark {
  color: var(--jp-ui-inverse-font-color0);
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
  align-items: center;
  padding: 4px 12px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-DirListing-checkboxWrapper {
  /* Increases hit area of checkbox. */
  padding: 4px;
}

.jp-DirListing-header
  .jp-DirListing-checkboxWrapper
  + .jp-DirListing-headerItem {
  padding-left: 4px;
}

.jp-DirListing-content .jp-DirListing-checkboxWrapper {
  position: relative;
  left: -4px;
  margin: -4px 0 -4px -8px;
}

.jp-DirListing-checkboxWrapper.jp-mod-visible {
  visibility: visible;
}

/* For devices that support hovering, hide checkboxes until hovered, selected...
*/
@media (hover: hover) {
  .jp-DirListing-checkboxWrapper {
    visibility: hidden;
  }

  .jp-DirListing-item:hover .jp-DirListing-checkboxWrapper,
  .jp-DirListing-item.jp-mod-selected .jp-DirListing-checkboxWrapper {
    visibility: visible;
  }
}

.jp-DirListing-item[data-is-dot] {
  opacity: 75%;
}

.jp-DirListing-item.jp-mod-selected {
  color: var(--jp-ui-inverse-font-color1);
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

.jp-DirListing-itemText:focus {
  outline-width: 2px;
  outline-color: var(--jp-inverse-layout-color1);
  outline-style: solid;
  outline-offset: 1px;
}

.jp-DirListing-item.jp-mod-selected .jp-DirListing-itemText:focus {
  outline-color: var(--jp-layout-color1);
}

.jp-DirListing-itemModified {
  flex: 0 0 125px;
  text-align: right;
}

.jp-DirListing-itemFileSize {
  flex: 0 0 90px;
  text-align: right;
}

.jp-DirListing-editor {
  flex: 1 0 64px;
  outline: none;
  border: none;
  color: var(--jp-ui-font-color1);
  background-color: var(--jp-layout-color1);
}

.jp-DirListing-item.jp-mod-running .jp-DirListing-itemIcon::before {
  color: var(--jp-success-color1);
  content: '\25CF';
  font-size: 8px;
  position: absolute;
  left: -8px;
}

.jp-DirListing-item.jp-mod-running.jp-mod-selected
  .jp-DirListing-itemIcon::before {
  color: var(--jp-ui-inverse-font-color1);
}

.jp-DirListing-item.lm-mod-drag-image,
.jp-DirListing-item.jp-mod-selected.lm-mod-drag-image {
  font-size: var(--jp-ui-font-size1);
  padding-left: 4px;
  margin-left: 4px;
  width: 160px;
  background-color: var(--jp-ui-inverse-font-color2);
  box-shadow: var(--jp-elevation-z2);
  border-radius: 0;
  color: var(--jp-ui-font-color1);
  transform: translateX(-40%) translateY(-58%);
}

.jp-Document {
  min-width: 120px;
  min-height: 120px;
  outline: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Main OutputArea
| OutputArea has a list of Outputs
|----------------------------------------------------------------------------*/

.jp-OutputArea {
  overflow-y: auto;
}

.jp-OutputArea-child {
  display: table;
  table-layout: fixed;
  width: 100%;
  overflow: hidden;
}

.jp-OutputPrompt {
  width: var(--jp-cell-prompt-width);
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

.jp-OutputArea-prompt {
  display: table-cell;
  vertical-align: top;
}

.jp-OutputArea-output {
  display: table-cell;
  width: 100%;
  height: auto;
  overflow: auto;
  user-select: text;
  -moz-user-select: text;
  -webkit-user-select: text;
  -ms-user-select: text;
}

.jp-OutputArea .jp-RenderedText {
  padding-left: 1ch;
}

/**
 * Prompt overlay.
 */

.jp-OutputArea-promptOverlay {
  position: absolute;
  top: 0;
  width: var(--jp-cell-prompt-width);
  height: 100%;
  opacity: 0.5;
}

.jp-OutputArea-promptOverlay:hover {
  background: var(--jp-layout-color2);
  box-shadow: inset 0 0 1px var(--jp-inverse-layout-color0);
  cursor: zoom-out;
}

.jp-mod-outputsScrolled .jp-OutputArea-promptOverlay:hover {
  cursor: zoom-in;
}

/**
 * Isolated output.
 */
.jp-OutputArea-output.jp-mod-isolated {
  width: 100%;
  display: block;
}

/*
When drag events occur, `lm-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated {
  position: relative;
}

body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated::before {
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
  margin: 0;
  padding: 0;
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

.jp-TrimmedOutputs pre {
  background: var(--jp-layout-color3);
  font-size: calc(var(--jp-code-font-size) * 1.4);
  text-align: center;
  text-transform: uppercase;
}

/* Hide the gutter in case of
 *  - nested output areas (e.g. in the case of output widgets)
 *  - mirrored output areas
 */
.jp-OutputArea .jp-OutputArea .jp-OutputArea-prompt {
  display: none;
}

/* Hide empty lines in the output area, for instance due to cleared widgets */
.jp-OutputArea-prompt:empty {
  padding: 0;
  border: 0;
}

/*-----------------------------------------------------------------------------
| executeResult is added to any Output-result for the display of the object
| returned by a cell
|----------------------------------------------------------------------------*/

.jp-OutputArea-output.jp-OutputArea-executeResult {
  margin-left: 0;
  width: 100%;
}

/* Text output with the Out[] prompt needs a top padding to match the
 * alignment of the Out[] prompt itself.
 */
.jp-OutputArea-executeResult .jp-RenderedText.jp-OutputArea-output {
  padding-top: var(--jp-code-padding);
  border-top: var(--jp-border-width) solid transparent;
}

/*-----------------------------------------------------------------------------
| The Stdin output
|----------------------------------------------------------------------------*/

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
  padding: 0 0.25em;
  margin: 0 0.25em;
  flex: 0 0 70%;
}

.jp-Stdin-input::placeholder {
  opacity: 0;
}

.jp-Stdin-input:focus {
  box-shadow: none;
}

.jp-Stdin-input:focus::placeholder {
  opacity: 1;
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
| Printing
|----------------------------------------------------------------------------*/

@media print {
  .jp-OutputArea-child {
    break-inside: avoid-page;
  }
}

/*-----------------------------------------------------------------------------
| Mobile
|----------------------------------------------------------------------------*/
@media only screen and (max-width: 760px) {
  .jp-OutputPrompt {
    display: table-row;
    text-align: left;
  }

  .jp-OutputArea-child .jp-OutputArea-output {
    display: table-row;
    margin-left: var(--jp-notebook-padding);
  }
}

/* Trimmed outputs warning */
.jp-TrimmedOutputs > a {
  margin: 10px;
  text-decoration: none;
  cursor: pointer;
}

.jp-TrimmedOutputs > a:hover {
  text-decoration: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Table of Contents
|----------------------------------------------------------------------------*/

:root {
  --jp-private-toc-active-width: 4px;
}

.jp-TableOfContents {
  display: flex;
  flex-direction: column;
  background: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  height: 100%;
}

.jp-TableOfContents-placeholder {
  text-align: center;
}

.jp-TableOfContents-placeholderContent {
  color: var(--jp-content-font-color2);
  padding: 8px;
}

.jp-TableOfContents-placeholderContent > h3 {
  margin-bottom: var(--jp-content-heading-margin-bottom);
}

.jp-TableOfContents .jp-SidePanel-content {
  overflow-y: auto;
}

.jp-TableOfContents-tree {
  margin: 4px;
}

.jp-TableOfContents ol {
  list-style-type: none;
}

/* stylelint-disable-next-line selector-max-type */
.jp-TableOfContents li > ol {
  /* Align left border with triangle icon center */
  padding-left: 11px;
}

.jp-TableOfContents-content {
  /* left margin for the active heading indicator */
  margin: 0 0 0 var(--jp-private-toc-active-width);
  padding: 0;
  background-color: var(--jp-layout-color1);
}

.jp-tocItem {
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-tocItem-heading {
  display: flex;
  cursor: pointer;
}

.jp-tocItem-heading:hover {
  background-color: var(--jp-layout-color2);
}

.jp-tocItem-content {
  display: block;
  padding: 4px 0;
  white-space: nowrap;
  text-overflow: ellipsis;
  overflow-x: hidden;
}

.jp-tocItem-collapser {
  height: 20px;
  margin: 2px 2px 0;
  padding: 0;
  background: none;
  border: none;
  cursor: pointer;
}

.jp-tocItem-collapser:hover {
  background-color: var(--jp-layout-color3);
}

/* Active heading indicator */

.jp-tocItem-heading::before {
  content: ' ';
  background: transparent;
  width: var(--jp-private-toc-active-width);
  height: 24px;
  position: absolute;
  left: 0;
  border-radius: var(--jp-border-radius);
}

.jp-tocItem-heading.jp-tocItem-active::before {
  background-color: var(--jp-brand-color1);
}

.jp-tocItem-heading:hover.jp-tocItem-active::before {
  background: var(--jp-brand-color0);
  opacity: 1;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapser {
  flex: 0 0 var(--jp-cell-collapser-width);
  padding: 0;
  margin: 0;
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
  top: 0;
  bottom: 0;
}

/*-----------------------------------------------------------------------------
| Printing
|----------------------------------------------------------------------------*/

/*
Hiding collapsers in print mode.

Note: input and output wrappers have "display: block" propery in print mode.
*/

@media print {
  .jp-Collapser {
    display: none;
  }
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
  height: 0;
  width: 100%;
  padding: 0;
  margin: 0;
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
  display: table;
  table-layout: fixed;
  width: 100%;
  overflow: hidden;
}

.jp-InputArea-editor {
  display: table-cell;
  overflow: hidden;
  vertical-align: top;

  /* This is the non-active, default styling */
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  border-radius: 0;
  background: var(--jp-cell-editor-background);
}

.jp-InputPrompt {
  display: table-cell;
  vertical-align: top;
  width: var(--jp-cell-prompt-width);
  color: var(--jp-cell-inprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  opacity: var(--jp-cell-prompt-opacity);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;

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
| Mobile
|----------------------------------------------------------------------------*/
@media only screen and (max-width: 760px) {
  .jp-InputArea-editor {
    display: table-row;
    margin-left: var(--jp-notebook-padding);
  }

  .jp-InputPrompt {
    display: table-row;
    text-align: left;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Placeholder {
  display: table;
  table-layout: fixed;
  width: 100%;
}

.jp-Placeholder-prompt {
  display: table-cell;
  box-sizing: border-box;
}

.jp-Placeholder-content {
  display: table-cell;
  padding: 4px 6px;
  border: 1px solid transparent;
  border-radius: 0;
  background: none;
  box-sizing: border-box;
  cursor: pointer;
}

.jp-Placeholder-contentContainer {
  display: flex;
}

.jp-Placeholder-content:hover,
.jp-InputPlaceholder > .jp-Placeholder-content:hover {
  border-color: var(--jp-layout-color3);
}

.jp-Placeholder-content .jp-MoreHorizIcon {
  width: 32px;
  height: 16px;
  border: 1px solid transparent;
  border-radius: var(--jp-border-radius);
}

.jp-Placeholder-content .jp-MoreHorizIcon:hover {
  border: 1px solid var(--jp-border-color1);
  box-shadow: 0 0 2px 0 rgba(0, 0, 0, 0.25);
  background-color: var(--jp-layout-color0);
}

.jp-PlaceholderText {
  white-space: nowrap;
  overflow-x: hidden;
  color: var(--jp-inverse-layout-color3);
  font-family: var(--jp-code-font-family);
}

.jp-InputPlaceholder > .jp-Placeholder-content {
  border-color: var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background);
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
  margin: 0;
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
  padding: 0;
  margin: 0;

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

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea {
  overflow-y: auto;
  max-height: 24em;
  margin-left: var(--jp-private-cell-scrolling-output-offset);
  resize: vertical;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea[style*='height'] {
  max-height: unset;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea::after {
  content: ' ';
  box-shadow: inset 0 0 6px 2px rgb(0 0 0 / 30%);
  width: 100%;
  height: 100%;
  position: sticky;
  bottom: 0;
  top: 0;
  margin-top: -50%;
  float: left;
  display: block;
  pointer-events: none;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-child {
  padding-top: 6px;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-prompt {
  width: calc(
    var(--jp-cell-prompt-width) - var(--jp-private-cell-scrolling-output-offset)
  );
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-promptOverlay {
  left: calc(-1 * var(--jp-private-cell-scrolling-output-offset));
}

/*-----------------------------------------------------------------------------
| CodeCell
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| MarkdownCell
|----------------------------------------------------------------------------*/

.jp-MarkdownOutput {
  display: table-cell;
  width: 100%;
  margin-top: 0;
  margin-bottom: 0;
  padding-left: var(--jp-code-padding);
}

.jp-MarkdownOutput.jp-RenderedHTMLCommon {
  overflow: auto;
}

/* collapseHeadingButton (show always if hiddenCellsButton is _not_ shown) */
.jp-collapseHeadingButton {
  display: flex;
  min-height: var(--jp-cell-collapser-min-height);
  font-size: var(--jp-code-font-size);
  position: absolute;
  background-color: transparent;
  background-size: 25px;
  background-repeat: no-repeat;
  background-position-x: center;
  background-position-y: top;
  background-image: var(--jp-icon-caret-down);
  right: 0;
  top: 0;
  bottom: 0;
}

.jp-collapseHeadingButton.jp-mod-collapsed {
  background-image: var(--jp-icon-caret-right);
}

/*
 set the container font size to match that of content
 so that the nested collapse buttons have the right size
*/
.jp-MarkdownCell .jp-InputPrompt {
  font-size: var(--jp-content-font-size1);
}

/*
  Align collapseHeadingButton with cell top header
  The font sizes are identical to the ones in packages/rendermime/style/base.css
*/
.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='1'] {
  font-size: var(--jp-content-font-size5);
  background-position-y: calc(0.3 * var(--jp-content-font-size5));
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='2'] {
  font-size: var(--jp-content-font-size4);
  background-position-y: calc(0.3 * var(--jp-content-font-size4));
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='3'] {
  font-size: var(--jp-content-font-size3);
  background-position-y: calc(0.3 * var(--jp-content-font-size3));
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='4'] {
  font-size: var(--jp-content-font-size2);
  background-position-y: calc(0.3 * var(--jp-content-font-size2));
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='5'] {
  font-size: var(--jp-content-font-size1);
  background-position-y: top;
}

.jp-mod-rendered .jp-collapseHeadingButton[data-heading-level='6'] {
  font-size: var(--jp-content-font-size0);
  background-position-y: top;
}

/* collapseHeadingButton (show only on (hover,active) if hiddenCellsButton is shown) */
.jp-Notebook.jp-mod-showHiddenCellsButton .jp-collapseHeadingButton {
  display: none;
}

.jp-Notebook.jp-mod-showHiddenCellsButton
  :is(.jp-MarkdownCell:hover, .jp-mod-active)
  .jp-collapseHeadingButton {
  display: flex;
}

/* showHiddenCellsButton (only show if jp-mod-showHiddenCellsButton is set, which
is a consequence of the showHiddenCellsButton option in Notebook Settings)*/
.jp-Notebook.jp-mod-showHiddenCellsButton .jp-showHiddenCellsButton {
  margin-left: calc(var(--jp-cell-prompt-width) + 2 * var(--jp-code-padding));
  margin-top: var(--jp-code-padding);
  border: 1px solid var(--jp-border-color2);
  background-color: var(--jp-border-color3) !important;
  color: var(--jp-content-font-color0) !important;
  display: flex;
}

.jp-Notebook.jp-mod-showHiddenCellsButton .jp-showHiddenCellsButton:hover {
  background-color: var(--jp-border-color2) !important;
}

.jp-showHiddenCellsButton {
  display: none;
}

/*-----------------------------------------------------------------------------
| Printing
|----------------------------------------------------------------------------*/

/*
Using block instead of flex to allow the use of the break-inside CSS property for
cell outputs.
*/

@media print {
  .jp-Cell-inputWrapper,
  .jp-Cell-outputWrapper {
    display: block;
  }
}

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
  --jp-notebook-toolbar-padding: 2px 5px 2px 2px;
}

/*-----------------------------------------------------------------------------

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-NotebookPanel-toolbar {
  padding: var(--jp-notebook-toolbar-padding);

  /* disable paint containment from lumino 2.0 default strict CSS containment */
  contain: style size !important;
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

.jp-Toolbar-responsive-popup {
  position: absolute;
  height: fit-content;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: flex-end;
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  background: var(--jp-toolbar-background);
  min-height: var(--jp-toolbar-micro-height);
  padding: var(--jp-notebook-toolbar-padding);
  z-index: 1;
  right: 0;
  top: 0;
}

.jp-Toolbar > .jp-Toolbar-responsive-opener {
  margin-left: auto;
}

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

.jp-Notebook-ExecutionIndicator {
  position: relative;
  display: inline-block;
  height: 100%;
  z-index: 9997;
}

.jp-Notebook-ExecutionIndicator-tooltip {
  visibility: hidden;
  height: auto;
  width: max-content;
  width: -moz-max-content;
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color1);
  text-align: justify;
  border-radius: 6px;
  padding: 0 5px;
  position: fixed;
  display: table;
}

.jp-Notebook-ExecutionIndicator-tooltip.up {
  transform: translateX(-50%) translateY(-100%) translateY(-32px);
}

.jp-Notebook-ExecutionIndicator-tooltip.down {
  transform: translateX(calc(-100% + 16px)) translateY(5px);
}

.jp-Notebook-ExecutionIndicator-tooltip.hidden {
  display: none;
}

.jp-Notebook-ExecutionIndicator:hover .jp-Notebook-ExecutionIndicator-tooltip {
  visibility: visible;
}

.jp-Notebook-ExecutionIndicator span {
  font-size: var(--jp-ui-font-size1);
  font-family: var(--jp-ui-font-family);
  color: var(--jp-ui-font-color1);
  line-height: 24px;
  display: block;
}

.jp-Notebook-ExecutionIndicator-progress-bar {
  display: flex;
  justify-content: center;
  height: 100%;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

/*
 * Execution indicator
 */
.jp-tocItem-content::after {
  content: '';

  /* Must be identical to form a circle */
  width: 12px;
  height: 12px;
  background: none;
  border: none;
  position: absolute;
  right: 0;
}

.jp-tocItem-content[data-running='0']::after {
  border-radius: 50%;
  border: var(--jp-border-width) solid var(--jp-inverse-layout-color3);
  background: none;
}

.jp-tocItem-content[data-running='1']::after {
  border-radius: 50%;
  border: var(--jp-border-width) solid var(--jp-inverse-layout-color3);
  background-color: var(--jp-inverse-layout-color3);
}

.jp-tocItem-content[data-running='0'],
.jp-tocItem-content[data-running='1'] {
  margin-right: 12px;
}

/*
 * Copyright (c) Jupyter Development Team.
 * Distributed under the terms of the Modified BSD License.
 */

.jp-Notebook-footer {
  height: 27px;
  margin-left: calc(
    var(--jp-cell-prompt-width) + var(--jp-cell-collapser-width) +
      var(--jp-cell-padding)
  );
  width: calc(
    100% -
      (
        var(--jp-cell-prompt-width) + var(--jp-cell-collapser-width) +
          var(--jp-cell-padding) + var(--jp-cell-padding)
      )
  );
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  color: var(--jp-ui-font-color3);
  margin-top: 6px;
  background: none;
  cursor: pointer;
}

.jp-Notebook-footer:focus {
  border-color: var(--jp-cell-editor-active-border-color);
}

/* For devices that support hovering, hide footer until hover */
@media (hover: hover) {
  .jp-Notebook-footer {
    opacity: 0;
  }

  .jp-Notebook-footer:focus,
  .jp-Notebook-footer:hover {
    opacity: 1;
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Imports
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-side-by-side-output-size: 1fr;
  --jp-side-by-side-resized-cell: var(--jp-side-by-side-output-size);
  --jp-private-notebook-dragImage-width: 304px;
  --jp-private-notebook-dragImage-height: 36px;
  --jp-private-notebook-selected-color: var(--md-blue-400);
  --jp-private-notebook-active-color: var(--md-green-400);
}

/*-----------------------------------------------------------------------------
| Notebook
|----------------------------------------------------------------------------*/

/* stylelint-disable selector-max-class */

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

.jp-MainAreaWidget-ContainStrict .jp-Notebook * {
  contain: strict;
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

/* cell is dirty */
.jp-Notebook .jp-Cell.jp-mod-dirty .jp-InputPrompt {
  color: var(--jp-warn-color1);
}

.jp-Notebook .jp-Cell.jp-mod-dirty .jp-InputPrompt::before {
  color: var(--jp-warn-color1);
  content: '•';
}

.jp-Notebook .jp-Cell.jp-mod-active.jp-mod-dirty .jp-Collapser {
  background: var(--jp-warn-color1);
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
  display: block;
  flex-direction: row;
  width: var(--jp-private-notebook-dragImage-width);
  height: var(--jp-private-notebook-dragImage-height);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background);
  overflow: visible;
}

.jp-dragImage-singlePrompt {
  box-shadow: 2px 2px 4px 0 rgba(0, 0, 0, 0.12);
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
  margin: 4px 4px 4px 0;
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
  box-shadow: 2px 2px 4px 0 rgba(0, 0, 0, 0.12);
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

.jp-ActiveCellTool {
  padding: 12px 0;
  display: flex;
}

.jp-ActiveCellTool-Content {
  flex: 1 1 auto;
}

.jp-ActiveCellTool .jp-ActiveCellTool-CellContent {
  background: var(--jp-cell-editor-background);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  border-radius: 0;
  min-height: 29px;
}

.jp-ActiveCellTool .jp-InputPrompt {
  min-width: calc(var(--jp-cell-prompt-width) * 0.75);
}

.jp-ActiveCellTool-CellContent > pre {
  padding: 5px 4px;
  margin: 0;
  white-space: normal;
}

.jp-MetadataEditorTool {
  flex-direction: column;
  padding: 12px 0;
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
.jp-MetadataEditorTool label,
.jp-NumberSetter label {
  line-height: 1.4;
}

.jp-NotebookTools .jp-select-wrapper {
  margin-top: 4px;
  margin-bottom: 0;
}

.jp-NumberSetter input {
  width: 100%;
  margin-top: 4px;
}

.jp-NotebookTools .jp-Collapse {
  margin-top: 16px;
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
| Side-by-side Mode (.jp-mod-sideBySide)
|----------------------------------------------------------------------------*/
.jp-mod-sideBySide.jp-Notebook .jp-Notebook-cell {
  margin-top: 3em;
  margin-bottom: 3em;
  margin-left: 5%;
  margin-right: 5%;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell {
  display: grid;
  grid-template-columns: minmax(0, 1fr) min-content minmax(
      0,
      var(--jp-side-by-side-output-size)
    );
  grid-template-rows: auto minmax(0, 1fr) auto;
  grid-template-areas:
    'header header header'
    'input handle output'
    'footer footer footer';
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell.jp-mod-resizedCell {
  grid-template-columns: minmax(0, 1fr) min-content minmax(
      0,
      var(--jp-side-by-side-resized-cell)
    );
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-CellHeader {
  grid-area: header;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-Cell-inputWrapper {
  grid-area: input;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-Cell-outputWrapper {
  /* overwrite the default margin (no vertical separation needed in side by side move */
  margin-top: 0;
  grid-area: output;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-CellFooter {
  grid-area: footer;
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-CellResizeHandle {
  grid-area: handle;
  user-select: none;
  display: block;
  height: 100%;
  cursor: ew-resize;
  padding: 0 var(--jp-cell-padding);
}

.jp-mod-sideBySide.jp-Notebook .jp-CodeCell .jp-CellResizeHandle::after {
  content: '';
  display: block;
  background: var(--jp-border-color2);
  height: 100%;
  width: 5px;
}

.jp-mod-sideBySide.jp-Notebook
  .jp-CodeCell.jp-mod-resizedCell
  .jp-CellResizeHandle::after {
  background: var(--jp-border-color0);
}

.jp-CellResizeHandle {
  display: none;
}

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Cell-Placeholder {
  padding-left: 55px;
}

.jp-Cell-Placeholder-wrapper {
  background: #fff;
  border: 1px solid;
  border-color: #e5e6e9 #dfe0e4 #d0d1d5;
  border-radius: 4px;
  -webkit-border-radius: 4px;
  margin: 10px 15px;
}

.jp-Cell-Placeholder-wrapper-inner {
  padding: 15px;
  position: relative;
}

.jp-Cell-Placeholder-wrapper-body {
  background-repeat: repeat;
  background-size: 50% auto;
}

.jp-Cell-Placeholder-wrapper-body div {
  background: #f6f7f8;
  background-image: -webkit-linear-gradient(
    left,
    #f6f7f8 0%,
    #edeef1 20%,
    #f6f7f8 40%,
    #f6f7f8 100%
  );
  background-repeat: no-repeat;
  background-size: 800px 104px;
  height: 104px;
  position: absolute;
  right: 15px;
  left: 15px;
  top: 15px;
}

div.jp-Cell-Placeholder-h1 {
  top: 20px;
  height: 20px;
  left: 15px;
  width: 150px;
}

div.jp-Cell-Placeholder-h2 {
  left: 15px;
  top: 50px;
  height: 10px;
  width: 100px;
}

div.jp-Cell-Placeholder-content-1,
div.jp-Cell-Placeholder-content-2,
div.jp-Cell-Placeholder-content-3 {
  left: 15px;
  right: 15px;
  height: 10px;
}

div.jp-Cell-Placeholder-content-1 {
  top: 100px;
}

div.jp-Cell-Placeholder-content-2 {
  top: 120px;
}

div.jp-Cell-Placeholder-content-3 {
  top: 140px;
}

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
  --jp-elevation-z1: 0 2px 1px -1px var(--jp-shadow-umbra-color),
    0 1px 1px 0 var(--jp-shadow-penumbra-color),
    0 1px 3px 0 var(--jp-shadow-ambient-color);
  --jp-elevation-z2: 0 3px 1px -2px var(--jp-shadow-umbra-color),
    0 2px 2px 0 var(--jp-shadow-penumbra-color),
    0 1px 5px 0 var(--jp-shadow-ambient-color);
  --jp-elevation-z4: 0 2px 4px -1px var(--jp-shadow-umbra-color),
    0 4px 5px 0 var(--jp-shadow-penumbra-color),
    0 1px 10px 0 var(--jp-shadow-ambient-color);
  --jp-elevation-z6: 0 3px 5px -1px var(--jp-shadow-umbra-color),
    0 6px 10px 0 var(--jp-shadow-penumbra-color),
    0 1px 18px 0 var(--jp-shadow-ambient-color);
  --jp-elevation-z8: 0 5px 5px -3px var(--jp-shadow-umbra-color),
    0 8px 10px 1px var(--jp-shadow-penumbra-color),
    0 3px 14px 2px var(--jp-shadow-ambient-color);
  --jp-elevation-z12: 0 7px 8px -4px var(--jp-shadow-umbra-color),
    0 12px 17px 2px var(--jp-shadow-penumbra-color),
    0 5px 22px 4px var(--jp-shadow-ambient-color);
  --jp-elevation-z16: 0 8px 10px -5px var(--jp-shadow-umbra-color),
    0 16px 24px 2px var(--jp-shadow-penumbra-color),
    0 6px 30px 5px var(--jp-shadow-ambient-color);
  --jp-elevation-z20: 0 10px 13px -6px var(--jp-shadow-umbra-color),
    0 20px 31px 3px var(--jp-shadow-penumbra-color),
    0 8px 38px 7px var(--jp-shadow-ambient-color);
  --jp-elevation-z24: 0 11px 15px -7px var(--jp-shadow-umbra-color),
    0 24px 38px 3px var(--jp-shadow-penumbra-color),
    0 9px 46px 8px var(--jp-shadow-ambient-color);

  /* Borders
   *
   * The following variables, specify the visual styling of borders in JupyterLab.
   */

  --jp-border-width: 1px;
  --jp-border-color0: var(--md-grey-400);
  --jp-border-color1: var(--md-grey-400);
  --jp-border-color2: var(--md-grey-300);
  --jp-border-color3: var(--md-grey-200);
  --jp-inverse-border-color: var(--md-grey-600);
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
  --jp-ui-font-family: system-ui, -apple-system, blinkmacsystemfont, 'Segoe UI',
    helvetica, arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji',
    'Segoe UI Symbol';

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
  --jp-content-link-color: var(--md-blue-900);
  --jp-content-font-family: system-ui, -apple-system, blinkmacsystemfont,
    'Segoe UI', helvetica, arial, sans-serif, 'Apple Color Emoji',
    'Segoe UI Emoji', 'Segoe UI Symbol';

  /*
   * Code Fonts
   *
   * Code font variables are used for typography of code and other monospaces content.
   */

  --jp-code-font-size: 13px;
  --jp-code-line-height: 1.3077; /* 17px for 13px base */
  --jp-code-padding: 5px; /* 5px for 13px base, codemirror highlighting needs integer px value */
  --jp-code-font-family-default: menlo, consolas, 'DejaVu Sans Mono', monospace;
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

  --jp-inverse-layout-color0: #111;
  --jp-inverse-layout-color1: var(--md-grey-900);
  --jp-inverse-layout-color2: var(--md-grey-800);
  --jp-inverse-layout-color3: var(--md-grey-700);
  --jp-inverse-layout-color4: var(--md-grey-600);

  /* Brand/accent */

  --jp-brand-color0: var(--md-blue-900);
  --jp-brand-color1: var(--md-blue-700);
  --jp-brand-color2: var(--md-blue-300);
  --jp-brand-color3: var(--md-blue-100);
  --jp-brand-color4: var(--md-blue-50);
  --jp-accent-color0: var(--md-green-900);
  --jp-accent-color1: var(--md-green-700);
  --jp-accent-color2: var(--md-green-300);
  --jp-accent-color3: var(--md-green-100);

  /* State colors (warn, error, success, info) */

  --jp-warn-color0: var(--md-orange-900);
  --jp-warn-color1: var(--md-orange-700);
  --jp-warn-color2: var(--md-orange-300);
  --jp-warn-color3: var(--md-orange-100);
  --jp-error-color0: var(--md-red-900);
  --jp-error-color1: var(--md-red-700);
  --jp-error-color2: var(--md-red-300);
  --jp-error-color3: var(--md-red-100);
  --jp-success-color0: var(--md-green-900);
  --jp-success-color1: var(--md-green-700);
  --jp-success-color2: var(--md-green-300);
  --jp-success-color3: var(--md-green-100);
  --jp-info-color0: var(--md-cyan-900);
  --jp-info-color1: var(--md-cyan-700);
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
  --jp-cell-prompt-font-family: var(--jp-code-font-family-default);
  --jp-cell-prompt-letter-spacing: 0;
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
  --jp-toolbar-box-shadow: 0 0 2px 0 rgba(0, 0, 0, 0.24);
  --jp-toolbar-header-margin: 4px 4px 0 4px;
  --jp-toolbar-active-background: var(--md-grey-300);

  /* Statusbar specific styles */

  --jp-statusbar-height: 24px;

  /* Input field styles */

  --jp-input-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-input-active-background: var(--jp-layout-color1);
  --jp-input-hover-background: var(--jp-layout-color1);
  --jp-input-background: var(--md-grey-100);
  --jp-input-border-color: var(--jp-inverse-border-color);
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
  --jp-mirror-editor-variable-2-color: rgb(0, 54, 109);
  --jp-mirror-editor-variable-3-color: #085;
  --jp-mirror-editor-punctuation-color: #05a;
  --jp-mirror-editor-property-color: #05a;
  --jp-mirror-editor-operator-color: #a2f;
  --jp-mirror-editor-comment-color: #408080;
  --jp-mirror-editor-string-color: #ba2121;
  --jp-mirror-editor-string-2-color: #708;
  --jp-mirror-editor-meta-color: #a2f;
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

  /*
    RTC user specific colors.
    These colors are used for the cursor, username in the editor,
    and the icon of the user.
  */

  --jp-collaborator-color1: #ffad8e;
  --jp-collaborator-color2: #dac83d;
  --jp-collaborator-color3: #72dd76;
  --jp-collaborator-color4: #00e4d0;
  --jp-collaborator-color5: #45d4ff;
  --jp-collaborator-color6: #e2b1ff;
  --jp-collaborator-color7: #ff9de6;

  /* Vega extension styles */

  --jp-vega-background: white;

  /* Sidebar-related styles */

  --jp-sidebar-min-width: 250px;

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

  /* Button colors */
  --jp-accept-color-normal: var(--md-blue-700);
  --jp-accept-color-hover: var(--md-blue-800);
  --jp-accept-color-active: var(--md-blue-900);
  --jp-warn-color-normal: var(--md-red-700);
  --jp-warn-color-hover: var(--md-red-800);
  --jp-warn-color-active: var(--md-red-900);
  --jp-reject-color-normal: var(--md-grey-600);
  --jp-reject-color-hover: var(--md-grey-700);
  --jp-reject-color-active: var(--md-grey-800);

  /* File or activity icons and switch semantic variables */
  --jp-jupyter-icon-color: #f37626;
  --jp-notebook-icon-color: #f37626;
  --jp-json-icon-color: var(--md-orange-700);
  --jp-console-icon-background-color: var(--md-blue-700);
  --jp-console-icon-color: white;
  --jp-terminal-icon-background-color: var(--md-grey-800);
  --jp-terminal-icon-color: var(--md-grey-200);
  --jp-text-editor-icon-color: var(--md-grey-700);
  --jp-inspector-icon-color: var(--md-grey-700);
  --jp-switch-color: var(--md-grey-400);
  --jp-switch-true-position-color: var(--md-orange-900);
}
</style>
<style type="text/css">
/* Force rendering true colors when outputing to pdf */
* {
  -webkit-print-color-adjust: exact;
}

/* Misc */
a.anchor-link {
  display: none;
}

/* Input area styling */
.jp-InputArea {
  overflow: hidden;
}

.jp-InputArea-editor {
  overflow: hidden;
}

.cm-editor.cm-s-jupyter .highlight pre {
/* weird, but --jp-code-padding defined to be 5px but 4px horizontal padding is hardcoded for pre.cm-line */
  padding: var(--jp-code-padding) 4px;
  margin: 0;

  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
  color: inherit;

}

.jp-OutputArea-output pre {
  line-height: inherit;
  font-family: inherit;
}

.jp-RenderedText pre {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-code-font-size);
}

/* Hiding the collapser by default */
.jp-Collapser {
  display: none;
}

@page {
    margin: 0.5in; /* Margin for each printed piece of paper */
}

@media print {
  .jp-Cell-inputWrapper,
  .jp-Cell-outputWrapper {
    display: block;
  }
}
</style>
<!-- Load mathjax -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/latest.js?config=TeX-AMS_CHTML-full,Safe"> </script>
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
                }
            });

            MathJax.Hub.Queue(["Typeset", MathJax.Hub]);
        }
    }
    init_mathjax();
    </script>
<!-- End of mathjax configuration --><script type="module">
  document.addEventListener("DOMContentLoaded", async () => {
    const diagrams = document.querySelectorAll(".jp-Mermaid > pre.mermaid");
    // do not load mermaidjs if not needed
    if (!diagrams.length) {
      return;
    }
    const mermaid = (await import("https://cdnjs.cloudflare.com/ajax/libs/mermaid/10.7.0/mermaid.esm.min.mjs")).default;
    const parser = new DOMParser();

    mermaid.initialize({
      maxTextSize: 100000,
      maxEdges: 100000,
      startOnLoad: false,
      fontFamily: window
        .getComputedStyle(document.body)
        .getPropertyValue("--jp-ui-font-family"),
      theme: document.querySelector("body[data-jp-theme-light='true']")
        ? "default"
        : "dark",
    });

    let _nextMermaidId = 0;

    function makeMermaidImage(svg) {
      const img = document.createElement("img");
      const doc = parser.parseFromString(svg, "image/svg+xml");
      const svgEl = doc.querySelector("svg");
      const { maxWidth } = svgEl?.style || {};
      const firstTitle = doc.querySelector("title");
      const firstDesc = doc.querySelector("desc");

      img.setAttribute("src", `data:image/svg+xml,${encodeURIComponent(svg)}`);
      if (maxWidth) {
        img.width = parseInt(maxWidth);
      }
      if (firstTitle) {
        img.setAttribute("alt", firstTitle.textContent);
      }
      if (firstDesc) {
        const caption = document.createElement("figcaption");
        caption.className = "sr-only";
        caption.textContent = firstDesc.textContent;
        return [img, caption];
      }
      return [img];
    }

    async function makeMermaidError(text) {
      let errorMessage = "";
      try {
        await mermaid.parse(text);
      } catch (err) {
        errorMessage = `${err}`;
      }

      const result = document.createElement("details");
      result.className = 'jp-RenderedMermaid-Details';
      const summary = document.createElement("summary");
      summary.className = 'jp-RenderedMermaid-Summary';
      const pre = document.createElement("pre");
      const code = document.createElement("code");
      code.innerText = text;
      pre.appendChild(code);
      summary.appendChild(pre);
      result.appendChild(summary);

      const warning = document.createElement("pre");
      warning.innerText = errorMessage;
      result.appendChild(warning);
      return [result];
    }

    async function renderOneMarmaid(src) {
      const id = `jp-mermaid-${_nextMermaidId++}`;
      const parent = src.parentNode;
      let raw = src.textContent.trim();
      const el = document.createElement("div");
      el.style.visibility = "hidden";
      document.body.appendChild(el);
      let results = null;
      let output = null;
      try {
        let { svg } = await mermaid.render(id, raw, el);
        svg = cleanMermaidSvg(svg);
        results = makeMermaidImage(svg);
        output = document.createElement("figure");
        results.map(output.appendChild, output);
      } catch (err) {
        parent.classList.add("jp-mod-warning");
        results = await makeMermaidError(raw);
        output = results[0];
      } finally {
        el.remove();
      }
      parent.classList.add("jp-RenderedMermaid");
      parent.appendChild(output);
    }


    /**
     * Post-process to ensure mermaid diagrams contain only valid SVG and XHTML.
     */
    function cleanMermaidSvg(svg) {
      return svg.replace(RE_VOID_ELEMENT, replaceVoidElement);
    }


    /**
     * A regular expression for all void elements, which may include attributes and
     * a slash.
     *
     * @see https://developer.mozilla.org/en-US/docs/Glossary/Void_element
     *
     * Of these, only `<br>` is generated by Mermaid in place of `\n`,
     * but _any_ "malformed" tag will break the SVG rendering entirely.
     */
    const RE_VOID_ELEMENT =
      /<\s*(area|base|br|col|embed|hr|img|input|link|meta|param|source|track|wbr)\s*([^>]*?)\s*>/gi;

    /**
     * Ensure a void element is closed with a slash, preserving any attributes.
     */
    function replaceVoidElement(match, tag, rest) {
      rest = rest.trim();
      if (!rest.endsWith('/')) {
        rest = `${rest} /`;
      }
      return `<${tag} ${rest}>`;
    }

    void Promise.all([...diagrams].map(renderOneMarmaid));
  });
</script>
<style>
  .jp-Mermaid:not(.jp-RenderedMermaid) {
    display: none;
  }

  .jp-RenderedMermaid {
    overflow: auto;
    display: flex;
  }

  .jp-RenderedMermaid.jp-mod-warning {
    width: auto;
    padding: 0.5em;
    margin-top: 0.5em;
    border: var(--jp-border-width) solid var(--jp-warn-color2);
    border-radius: var(--jp-border-radius);
    color: var(--jp-ui-font-color1);
    font-size: var(--jp-ui-font-size1);
    white-space: pre-wrap;
    word-wrap: break-word;
  }

  .jp-RenderedMermaid figure {
    margin: 0;
    overflow: auto;
    max-width: 100%;
  }

  .jp-RenderedMermaid img {
    max-width: 100%;
  }

  .jp-RenderedMermaid-Details > pre {
    margin-top: 1em;
  }

  .jp-RenderedMermaid-Summary {
    color: var(--jp-warn-color2);
  }

  .jp-RenderedMermaid:not(.jp-mod-warning) pre {
    display: none;
  }

  .jp-RenderedMermaid-Summary > pre {
    display: inline-block;
    white-space: normal;
  }
</style>
<!-- End of mermaid configuration --></head>
<body class="jp-Notebook" data-jp-theme-light="true" data-jp-theme-name="JupyterLab Light">
<main>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=0847671d">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<p><br/><br/></p>
<div style="font-size: 30px; font-weight: bold;">Exploring Bike Rental Trends</div>
<br/><div style="font-size: 17px"><em>A Python Analysis Project</em></div>
<br/>
<br/>Anna Carolina Corrêa
<br/>
<p>Prof. Chase Kusterer <br/>
Hult International Business School -  San Francisco <br/>
Introduction to Python <br/></p>
<br/>
<p>･<em>:.｡. .｡.:</em>･゜ﾟ･<em>☆･</em>:.｡. .｡.:<em>･゜ﾟ･</em>☆･<em>:.｡. .｡.:</em>･゜ﾟ･<em>☆･</em>:.｡. .｡.:<em>･゜ﾟ･</em>☆･<em>:.｡. .｡.:</em>･゜ﾟ･<em>☆･</em>:.｡. .｡.:<em>･゜ﾟ･</em>☆･<em>:.｡. .｡.:</em>･゜ﾟ･<em>☆･</em>:.｡. .｡.:<em>･゜ﾟ･</em>☆･<em>:.｡. .｡.:</em>･゜ﾟ･<em>☆･</em>:.｡. .｡.:<em>･゜ﾟ･</em>☆･<em>:.｡. .｡.:</em>･゜ﾟ･<em>☆･</em>:</p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=ff381d8d">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1>Introduction</h1><br/>
<p>In this project, we will analyze bicycle's rental demand to uncover which factors impact the customers' preference for using our service. We will compare temporal features, weather conditions, holidays indicators, and other relevant variables using diversified data visualizations and descriptive analytics. By employing boxplots, scatter plots, and heatmaps weaim to reveal key relationships and impact of those factors. These insights will lead us through the development of actionable recommendations to optimize operations and maximize rental results. When these key patterns are identified, it is possible to translate the extensive, complex figures into data-driven strategies that will enhance customer satisfaction.<br/></p>
<hr/>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=7d80d576">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1> Key Insights</h1>
<p>After analyzing the provided data, three key insights were uncovered:</p>
<p><b>1.</b> Users comfort  strongly impacts the motivation to rent and ride a bike, and temperature is a direct driver of comfort (Kane &amp; Kythreotis, 2023). Even during winter season, days that see comfortable Dew Point temperature have a significant jump in bike rentals, confirming that warmer days spark demand. Secondary weather factors like humidity, visibility, and Dew Point temperature boost these effects even more, providing stronger evidence that comfort affects motivation to ridership. Customers are more likely to utilize bikes during warmer days, with more humidity and better visibility, with Dew Point temperature around 5 to 20 degrees; in practice, this indicates that warmer, sunny days with comfortable humidity represent opportunity windows. <br/><br/>
<b>2.</b> 8 am and 6 pm register the highest rental volume, highlighting the importance of rental bikes as primary means of commute transportation. The peaks, that align with rush hour window time, reveal that convenience rentals are the main motivation for rentals, rather than leisure. Although commute stands out as the main trip purpose (Zhang et al., 2024), one of the hourly peaks, 9 pm, indicates interest for leisure usage, but in smaller demand. However, rush hour spikes account for majority of daily rentals, illustrating the predictability of demand cycle. With this data, the company is able to prepare for peak hours.<br/><br/>
<b>3.</b> Demand is extremely sensitive to seasons. In contrast to the first insight, winter season faces the lowest rental counts, while other seasons are affected during colder days (Dill &amp; Gliebe, 2008). Summer, for its warmth and humidity, has the highest rental counts and most popular months. For this reason, off-season promotions and marketing campaigns focused on commute benefits can avoid low rentals during winter and ensure more bicycles availability during higher demand periods.<br/></p>
<p>These findings can be confirmed by <span style="background-color: #dfc6f6">prior studies</span> that support the facts that:</p>
<ul>
<li>Bicycle users are sensitive to weather, and temperature is the strongest driver;</li>
<li>Bikes are commonly used during peak hours, especially to go to work, which is the second most frequent trip purpose after going back home.<br/><br/><br/></li>
</ul>
<hr/>
<h2>References:</h2>
<p>Dill, J., &amp; Gliebe, J. (2008). Understanding and measuring bicycling behavior: A focus on travel time and route choice (Final Report No. OTREC-RR-08-03). Oregon Transportation Research and Education Consortium. <a href="https://nacto.org/wp-content/uploads/Dill-and-Gliebe-2008.pdf">https://nacto.org/wp-content/uploads/Dill-and-Gliebe-2008.pdf</a></p>
<p>Kane, C., &amp; Kythreotis, S. (2023). Relationships between weather and cycling. Liikenne. Retrieved from <a href="https://www.researchgate.net/publication/378512994_Relationships_Between_Weather_and_Cycling">https://www.researchgate.net/publication/378512994_Relationships_Between_Weather_and_Cycling</a></p>
<p>Zhang, Y., Shao, J., Nelson, J. D., Kent, J. L., &amp; Vardoulakis, S. (2024, December 17). Gender, weather, and time of day: Active travel observations in Greater Sydney. Transport Findings. <a href="https://findingspress.org/article/127019-gender-weather-and-time-of-day-active-travel-observations-in-greater-sydney">https://findingspress.org/article/127019-gender-weather-and-time-of-day-active-travel-observations-in-greater-sydney</a></p>
<hr/>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=cb1fd9ba">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1>The answers you're looking for</h1>
<hr/>
<p><span style="font-size: 17px;"><b>1.</b> In your analytical opinion, why are the majority of users renting bicycles?</span><br/></p>
<blockquote>
<p>As previously stated, users are utilizing bicycles mainly for commuting purposes. This can be identified by the Hour of Day vs. Rentals visual and analysis, where peak usage times is during  morning and evening commute windows, with a stable growth from 6 am to 8 am, and second growth from 4 pm to 6 pm, where it reaches the highest peak. There is another peak at 9 pm, which indicates leisure usage. The present reliance on bikes for work-home trips urge for a marketing emphasis on reliability and speed over recreation. This understanding empowers the company to develop data-driven strategies to capture high loyalty customers that see the vehicle as a convenient form of commuting.</p>
</blockquote>
<p><span style="font-size: 17px;"><b>2.</b> Are there ideal weather conditions that create high bike rental demand? If so, what are they?</span></p>
<blockquote>
<p>Yes, there are ideal conditions for a high demand. First and most importantly, weather comfort is one of the main drivers of demand. Users have a strong preference for warmer and moderate humidity days, with temperature around 15 to 25 degrees, and 40% to 60% humidity, as conditions are not severe. They also prefer better visibility, over 1200, avoiding rainfalls and snowfalls for more comfort and satefy; this, combined with Dew Point temperature from 5 to 20 degrees, provide a pleasant amount of wind and moisture, which translates into more rentals.</p>
</blockquote>
<p><span style="font-size: 17px;"><b>3.</b> How should the company strategize based on your results? In other words, what actionable steps can the company take in order to take advantage of your insights.</span></p>
<p>Based on the findings above, there are a few adjustments that can be made to enhance rental demand and customer satisfaction:</p>
<blockquote>
<p>The companies in the rental business understand the importance of maintenance. The time for these adjustments should be schedule to fit low movement hours after 9 pm.<br/><br/></p>
</blockquote>
<p>During commute hours there is a higher demand for bike rentals, and by allocating a higher number of bikes for availability in high traffic areas can increase number of usage and, consequently, increase profit. Reallocation is also useful during summer time, while winter season can benefit from lower bicycle availability, allowing rotation during low season for better maintenance and lower erosion.<br/><br/>
The company's app can also benefit from notification alerts for clearer, warmer weathers (<s>in a Starbucks style</s>) to encourage customers to utilize the vehicle, which can be beneficial especially during winter.<br/><br/>
Users respond positively to promotions. Usage can be encourage during low hours with better pricing close to peak times. With  this strategy, it is possible to avoid congestion and lack of availability during rush hour, while also encouraging one-time users to include rental bikes in their commute routine. This type of promotions also work during low season, like Winter, or during excessive heat days during the summer.</p>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=1e7f9d8e">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h1>The code</h1>
<h2> Imports, loading file and initial peek.</h2>
<hr/>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=7d3f4e0d">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [2]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># imports</span>
<span class="kn">import</span> <span class="nn">pandas</span>             <span class="k">as</span> <span class="nn">pd</span> <span class="c1"># data science essentials</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span>  <span class="k">as</span> <span class="nn">plt</span> <span class="c1"># data visualization essentials</span>
<span class="kn">import</span> <span class="nn">seaborn</span>            <span class="k">as</span> <span class="nn">sns</span> <span class="c1"># enhanced data visualization</span>


<span class="c1"># suppressing user warnings</span>
<span class="kn">import</span> <span class="nn">warnings</span>
<span class="n">warnings</span><span class="o">.</span><span class="n">simplefilter</span><span class="p">(</span><span class="n">action</span><span class="o">=</span><span class="s1">'ignore'</span><span class="p">,</span> <span class="n">category</span><span class="o">=</span><span class="ne">UserWarning</span><span class="p">)</span>


<span class="c1"># specifying file name</span>
<span class="n">file</span> <span class="o">=</span> <span class="s2">"bikes_data.xlsx"</span>


<span class="c1"># reading the file into Python through pandas</span>
<span class="n">bikes_data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_excel</span><span class="p">(</span><span class="n">io</span>          <span class="o">=</span> <span class="n">file</span>        <span class="p">,</span>
                           <span class="n">sheet_name</span>  <span class="o">=</span> <span class="s1">'SU (2 + 3)'</span><span class="p">,</span>
                           <span class="n">header</span>      <span class="o">=</span> <span class="mi">0</span>           <span class="p">)</span>


<span class="c1">#checking results (first 10 rows of the dataset)</span>
<span class="n">bikes_data</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="n">n</span> <span class="o">=</span> <span class="mi">10</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[2]:</div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html" tabindex="0">
<div>
<style scoped="">
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
<th>ID</th>
<th>Month</th>
<th>Day of Week</th>
<th>Hour</th>
<th>Temperature</th>
<th>Humidity</th>
<th>Wind Speed</th>
<th>Visibility</th>
<th>Dew Point Temperature</th>
<th>UV Index</th>
<th>Rainfall</th>
<th>Snowfall</th>
<th>Season</th>
<th>Holiday</th>
<th>RENTALS</th>
</tr>
</thead>
<tbody>
<tr>
<th>0</th>
<td>1</td>
<td>Jan</td>
<td>Sunday</td>
<td>0</td>
<td>-3.2</td>
<td>40</td>
<td>0.5</td>
<td>1358</td>
<td>-14.9</td>
<td>0.00</td>
<td>0.0</td>
<td>0.0</td>
<td>Winter</td>
<td>Yes</td>
<td>221</td>
</tr>
<tr>
<th>1</th>
<td>2</td>
<td>Jan</td>
<td>Sunday</td>
<td>13</td>
<td>2.4</td>
<td>22</td>
<td>2.3</td>
<td>1921</td>
<td>-17.2</td>
<td>1.10</td>
<td>0.0</td>
<td>0.0</td>
<td>Winter</td>
<td>Yes</td>
<td>268</td>
</tr>
<tr>
<th>2</th>
<td>3</td>
<td>Jan</td>
<td>Sunday</td>
<td>16</td>
<td>3.0</td>
<td>28</td>
<td>2.5</td>
<td>1864</td>
<td>-13.7</td>
<td>0.51</td>
<td>0.0</td>
<td>0.0</td>
<td>Winter</td>
<td>Yes</td>
<td>335</td>
</tr>
<tr>
<th>3</th>
<td>4</td>
<td>Jan</td>
<td>Sunday</td>
<td>17</td>
<td>1.8</td>
<td>33</td>
<td>3.3</td>
<td>1913</td>
<td>-12.8</td>
<td>0.18</td>
<td>0.0</td>
<td>0.0</td>
<td>Winter</td>
<td>Yes</td>
<td>299</td>
</tr>
<tr>
<th>4</th>
<td>5</td>
<td>Jan</td>
<td>Sunday</td>
<td>20</td>
<td>-0.3</td>
<td>40</td>
<td>1.2</td>
<td>1936</td>
<td>-12.2</td>
<td>0.00</td>
<td>0.0</td>
<td>0.0</td>
<td>Winter</td>
<td>Yes</td>
<td>225</td>
</tr>
<tr>
<th>5</th>
<td>6</td>
<td>Jan</td>
<td>Monday</td>
<td>10</td>
<td>-1.4</td>
<td>50</td>
<td>1.9</td>
<td>1355</td>
<td>-10.5</td>
<td>0.38</td>
<td>0.0</td>
<td>0.0</td>
<td>Winter</td>
<td>No</td>
<td>221</td>
</tr>
<tr>
<th>6</th>
<td>7</td>
<td>Jan</td>
<td>Monday</td>
<td>18</td>
<td>-0.8</td>
<td>24</td>
<td>2.3</td>
<td>2000</td>
<td>-18.9</td>
<td>0.01</td>
<td>0.0</td>
<td>0.0</td>
<td>Winter</td>
<td>No</td>
<td>723</td>
</tr>
<tr>
<th>7</th>
<td>8</td>
<td>Jan</td>
<td>Tuesday</td>
<td>21</td>
<td>-4.3</td>
<td>47</td>
<td>2.8</td>
<td>1997</td>
<td>-13.9</td>
<td>0.00</td>
<td>0.0</td>
<td>0.0</td>
<td>Winter</td>
<td>No</td>
<td>352</td>
</tr>
<tr>
<th>8</th>
<td>9</td>
<td>Jan</td>
<td>Wednesday</td>
<td>3</td>
<td>-7.4</td>
<td>54</td>
<td>1.7</td>
<td>1968</td>
<td>-15.1</td>
<td>0.00</td>
<td>0.0</td>
<td>0.0</td>
<td>Winter</td>
<td>No</td>
<td>63</td>
</tr>
<tr>
<th>9</th>
<td>10</td>
<td>Jan</td>
<td>Wednesday</td>
<td>7</td>
<td>-8.1</td>
<td>51</td>
<td>0.5</td>
<td>1987</td>
<td>-16.4</td>
<td>0.00</td>
<td>0.0</td>
<td>0.0</td>
<td>Winter</td>
<td>No</td>
<td>324</td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=44698e47">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h2>Auditing data quality, type and fixing issues.

</h2></div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=332f43d3">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [3]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># analyzing info related to variables for quality check</span>
<span class="n">bikes_data</span><span class="o">.</span><span class="n">info</span><span class="p">(</span><span class="n">verbose</span> <span class="o">=</span> <span class="kc">True</span><span class="p">)</span>


<span class="c1"># remove ID, month, day of week and hour for relevant statistics results</span>
<span class="n">bikes_data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_excel</span><span class="p">(</span><span class="n">io</span>          <span class="o">=</span> <span class="n">file</span>        <span class="p">,</span>
                           <span class="n">sheet_name</span>  <span class="o">=</span> <span class="s1">'SU (2 + 3)'</span><span class="p">,</span>
                           <span class="n">header</span>      <span class="o">=</span> <span class="mi">0</span> <span class="p">,</span>
                           <span class="n">usecols</span>     <span class="o">=</span> <span class="nb">range</span><span class="p">(</span><span class="mi">4</span><span class="p">,</span> <span class="mi">15</span><span class="p">))</span>

    
<span class="c1"># transforming column headers into lowercase</span>
<span class="n">bikes_data</span><span class="o">.</span><span class="n">columns</span> <span class="o">=</span> <span class="n">bikes_data</span><span class="o">.</span><span class="n">columns</span><span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">title</span><span class="p">()</span>

<span class="c1"># overview of all columns and rows</span>

<span class="c1"># descriptive statistics results for initial analysis</span>
<span class="n">bikes_data</span><span class="o">.</span><span class="n">describe</span><span class="p">()</span><span class="o">.</span><span class="n">round</span><span class="p">(</span><span class="n">decimals</span> <span class="o">=</span> <span class="mi">2</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain" tabindex="0">
<pre>&lt;class 'pandas.core.frame.DataFrame'&gt;
RangeIndex: 1387 entries, 0 to 1386
Data columns (total 15 columns):
 #   Column                 Non-Null Count  Dtype  
---  ------                 --------------  -----  
 0   ID                     1387 non-null   int64  
 1   Month                  1387 non-null   object 
 2   Day of Week            1387 non-null   object 
 3   Hour                   1387 non-null   int64  
 4   Temperature            1387 non-null   float64
 5   Humidity               1387 non-null   int64  
 6   Wind Speed             1387 non-null   float64
 7   Visibility             1387 non-null   int64  
 8   Dew Point Temperature  1387 non-null   float64
 9   UV Index               1387 non-null   float64
 10  Rainfall               1387 non-null   float64
 11  Snowfall               1387 non-null   float64
 12  Season                 1387 non-null   object 
 13  Holiday                1387 non-null   object 
 14  RENTALS                1387 non-null   int64  
dtypes: float64(6), int64(5), object(4)
memory usage: 162.7+ KB
</pre>
</div>
</div>
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[3]:</div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html" tabindex="0">
<div>
<style scoped="">
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
<th>Temperature</th>
<th>Humidity</th>
<th>Wind Speed</th>
<th>Visibility</th>
<th>Dew Point Temperature</th>
<th>Uv Index</th>
<th>Rainfall</th>
<th>Snowfall</th>
<th>Rentals</th>
</tr>
</thead>
<tbody>
<tr>
<th>count</th>
<td>1387.00</td>
<td>1387.00</td>
<td>1387.00</td>
<td>1387.00</td>
<td>1387.00</td>
<td>1387.00</td>
<td>1387.00</td>
<td>1387.00</td>
<td>1387.00</td>
</tr>
<tr>
<th>mean</th>
<td>13.09</td>
<td>58.76</td>
<td>1.71</td>
<td>1434.42</td>
<td>4.37</td>
<td>0.57</td>
<td>0.14</td>
<td>0.08</td>
<td>810.02</td>
</tr>
<tr>
<th>std</th>
<td>11.90</td>
<td>20.56</td>
<td>1.02</td>
<td>618.09</td>
<td>13.10</td>
<td>0.87</td>
<td>1.26</td>
<td>0.44</td>
<td>694.72</td>
</tr>
<tr>
<th>min</th>
<td>-15.80</td>
<td>11.00</td>
<td>0.00</td>
<td>81.00</td>
<td>-30.50</td>
<td>0.00</td>
<td>0.00</td>
<td>0.00</td>
<td>5.00</td>
</tr>
<tr>
<th>25%</th>
<td>3.20</td>
<td>43.00</td>
<td>0.90</td>
<td>946.00</td>
<td>-4.40</td>
<td>0.00</td>
<td>0.00</td>
<td>0.00</td>
<td>250.50</td>
</tr>
<tr>
<th>50%</th>
<td>14.10</td>
<td>58.00</td>
<td>1.50</td>
<td>1718.00</td>
<td>5.20</td>
<td>0.01</td>
<td>0.00</td>
<td>0.00</td>
<td>626.00</td>
</tr>
<tr>
<th>75%</th>
<td>22.80</td>
<td>75.00</td>
<td>2.30</td>
<td>2000.00</td>
<td>15.60</td>
<td>0.98</td>
<td>0.00</td>
<td>0.00</td>
<td>1196.50</td>
</tr>
<tr>
<th>max</th>
<td>38.00</td>
<td>98.00</td>
<td>7.40</td>
<td>2000.00</td>
<td>26.60</td>
<td>3.45</td>
<td>35.00</td>
<td>7.00</td>
<td>3734.00</td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=c584ba0d">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h3>First results</h3><br/>
<p>After loading the file and obtaining a first output to visualize the records, the next step was to evaluate the information related to each variable and identify if there were any columns or items that required transformation. Considering that "Hour" does not have any numerical/statistical value for the current analysis, since it is purely a time label instead of a continuous measure, I used the <span style="background-color: #dfc6f6"><i> usecols = range(4, 15)</i></span> to exclude from the descriptive summary results.</p>
<p>At first glance, it is possible to observe that the <b>Rentals</b> standard deviation is 694.72, almost as high as the mean of 810.02. Such high dispersion indicates possible outliers; we can observe, for example, a maximum bike rentals of 3.734 in a single day. To understand the reason, it needs further investigation, but we can consider the likeliness of being driven due to seasonality, holidays, or weather.</p>
<p>Another distinct detail is that <b>Visibility</b> also has significant variations with possible outliers. The lowest visibility registered in the data is 81 m, and when comparing to the maximum (2000) and average (1434) we can observe that this number is very low number and rare, which may coincide with drops in demand.</p>
<p>To better understand how these and other factors truly affect bike rentals, we  will proceed with deeper statistical analysis and relevant visualization. This way, we can reveal the relationship between the variables and rental demand.</p>
<hr/>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs" id="cell-id=79fc3d75">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [14]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># remove ID, month, day of week and hour for relevant statistics results</span>
<span class="n">bikes_data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_excel</span><span class="p">(</span><span class="n">io</span>          <span class="o">=</span> <span class="n">file</span>        <span class="p">,</span>
                           <span class="n">sheet_name</span>  <span class="o">=</span> <span class="s1">'SU (2 + 3)'</span><span class="p">,</span>
                           <span class="n">header</span>      <span class="o">=</span> <span class="mi">0</span><span class="p">)</span>

<span class="c1"># replacing season names to numerical values</span>
<span class="n">bikes_data</span><span class="o">.</span><span class="n">replace</span><span class="p">({</span><span class="s1">'Winter'</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
                    <span class="s1">'Spring'</span><span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
                    <span class="s1">'Summer'</span><span class="p">:</span> <span class="mi">3</span><span class="p">,</span>
                    <span class="s1">'Autumn'</span><span class="p">:</span> <span class="mi">4</span><span class="p">},</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>

<span class="c1"># replacing day of the week to numerical values</span>
<span class="n">bikes_data</span><span class="o">.</span><span class="n">replace</span><span class="p">({</span><span class="s1">'Monday'</span>   <span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
                    <span class="s1">'Tuesday'</span>  <span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
                    <span class="s1">'Wednesday'</span><span class="p">:</span> <span class="mi">3</span><span class="p">,</span>
                    <span class="s1">'Thursday'</span> <span class="p">:</span> <span class="mi">4</span><span class="p">,</span>
                    <span class="s1">'Friday'</span>   <span class="p">:</span> <span class="mi">5</span><span class="p">,</span>
                    <span class="s1">'Saturday'</span> <span class="p">:</span> <span class="mi">6</span><span class="p">,</span>
                    <span class="s1">'Sunday'</span>   <span class="p">:</span> <span class="mi">7</span><span class="p">},</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>


<span class="c1"># replacing month (name) to month (number)</span>
<span class="c1"># dictionary for the numerical month</span>
<span class="n">month_num</span> <span class="o">=</span> <span class="p">{</span><span class="s1">'Jan'</span> <span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
             <span class="s1">'Feb'</span> <span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
             <span class="s1">'Mar'</span> <span class="p">:</span> <span class="mi">3</span><span class="p">,</span>
             <span class="s1">'Apr'</span> <span class="p">:</span> <span class="mi">4</span><span class="p">,</span>
             <span class="s1">'May'</span> <span class="p">:</span> <span class="mi">5</span><span class="p">,</span>
             <span class="s1">'June'</span><span class="p">:</span> <span class="mi">6</span><span class="p">,</span>
             <span class="s1">'July'</span><span class="p">:</span> <span class="mi">7</span><span class="p">,</span>
             <span class="s1">'Aug'</span> <span class="p">:</span> <span class="mi">8</span><span class="p">,</span>
             <span class="s1">'Sep'</span> <span class="p">:</span> <span class="mi">9</span><span class="p">,</span>
             <span class="s1">'Oct'</span> <span class="p">:</span> <span class="mi">10</span><span class="p">,</span>
             <span class="s1">'Nov'</span> <span class="p">:</span> <span class="mi">11</span><span class="p">,</span>
             <span class="s1">'Dec'</span> <span class="p">:</span> <span class="mi">12</span><span class="p">,}</span>

<span class="c1"># replacing the data in the file</span>
<span class="n">bikes_data</span><span class="p">[</span><span class="s1">'Month'</span><span class="p">]</span> <span class="o">=</span> <span class="n">bikes_data</span><span class="p">[</span><span class="s1">'Month'</span><span class="p">]</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="n">month_num</span><span class="p">)</span>
<span class="n">bikes_data</span><span class="p">[</span><span class="s1">'Month'</span><span class="p">]</span> <span class="o">=</span> <span class="n">bikes_data</span><span class="p">[</span><span class="s1">'Month'</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">int</span><span class="p">)</span>

<span class="c1"># replacing holiday into numerical data</span>
<span class="n">bikes_data</span><span class="o">.</span><span class="n">replace</span><span class="p">({</span><span class="s1">'No'</span>  <span class="p">:</span> <span class="mi">0</span><span class="p">,</span>
                    <span class="s1">'Yes'</span> <span class="p">:</span> <span class="mi">1</span><span class="p">},</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>

<span class="c1"># transforming column headers into lowercase</span>
<span class="n">bikes_data</span><span class="o">.</span><span class="n">columns</span> <span class="o">=</span> <span class="n">bikes_data</span><span class="o">.</span><span class="n">columns</span><span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">title</span><span class="p">()</span>

<span class="c1"># code gives future warning error</span>
<span class="c1"># suppressing future warnings</span>
<span class="kn">import</span> <span class="nn">warnings</span>
<span class="n">warnings</span><span class="o">.</span><span class="n">simplefilter</span><span class="p">(</span><span class="n">action</span><span class="o">=</span><span class="s1">'ignore'</span><span class="p">,</span> <span class="n">category</span><span class="o">=</span><span class="ne">FutureWarning</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=6e5a7f20">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h3>Explanation</h3><br/>
<p>Now that the strings are transformed into relevant numerical codes, we can ensure that each variable can be compared and correlated to the <b>rentals</b>, and understand its impact and relevance. The numbers and features were organized in the following format:<br/></p>
<p><span style="background-color: #dfc6f6">Seasons:<br/></span>
Winter = 1<br/>
Spring = 2<br/>
Summer = 3<br/>
Autumn = 4<br/></p>
<p><span style="background-color: #dfc6f6">Month:<br/></span>
From 1 to 12, following its respective order:<br/>
Jan = 1<br/>
Feb = 2<br/>
[...]<br/>
Dec = 12<br/></p>
<p><span style="background-color: #dfc6f6">Week of day:<br/></span>
From 1 to 7, starting on Monday:<br/>
Monday = 1<br/>
Tuesday = 2<br/>
[...]<br/>
Sunday = 7<br/></p>
<p><span style="background-color: #dfc6f6">Holidays:<br/></span>
No: 0<br/>
Yes: 1<br/></p>
<hr/>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=981766b2">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h2> Analysis </h2><br/>
<p>With the transformations done, we can now start our correlation analysis and produce clear, interpretable visualization to assess their influence in rental demand.</p>
<hr/>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=f2c5ed1d">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [6]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># pearson correlation to quantifying relationships</span>
<span class="n">bikes_data</span><span class="o">.</span><span class="n">iloc</span><span class="p">[</span> <span class="p">:</span> <span class="p">,</span> <span class="mi">1</span><span class="p">:</span> <span class="p">]</span><span class="o">.</span><span class="n">corr</span><span class="p">(</span><span class="n">method</span> <span class="o">=</span> <span class="s1">'pearson'</span><span class="p">,</span>
                         <span class="n">numeric_only</span> <span class="o">=</span> <span class="kc">True</span><span class="p">)</span><span class="o">.</span><span class="n">round</span><span class="p">(</span><span class="n">decimals</span> <span class="o">=</span> <span class="mi">2</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[6]:</div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html" tabindex="0">
<div>
<style scoped="">
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
<th>Month</th>
<th>Day Of Week</th>
<th>Hour</th>
<th>Temperature</th>
<th>Humidity</th>
<th>Wind Speed</th>
<th>Visibility</th>
<th>Dew Point Temperature</th>
<th>Uv Index</th>
<th>Rainfall</th>
<th>Snowfall</th>
<th>Season</th>
<th>Holiday</th>
<th>Rentals</th>
</tr>
</thead>
<tbody>
<tr>
<th>Month</th>
<td>1.00</td>
<td>0.04</td>
<td>0.04</td>
<td>0.24</td>
<td>0.11</td>
<td>-0.14</td>
<td>0.09</td>
<td>0.25</td>
<td>-0.03</td>
<td>-0.00</td>
<td>0.01</td>
<td>0.58</td>
<td>0.05</td>
<td>0.20</td>
</tr>
<tr>
<th>Day Of Week</th>
<td>0.04</td>
<td>1.00</td>
<td>0.04</td>
<td>0.04</td>
<td>-0.01</td>
<td>-0.06</td>
<td>-0.03</td>
<td>0.03</td>
<td>0.01</td>
<td>0.03</td>
<td>-0.07</td>
<td>0.02</td>
<td>-0.02</td>
<td>-0.06</td>
</tr>
<tr>
<th>Hour</th>
<td>0.04</td>
<td>0.04</td>
<td>1.00</td>
<td>0.11</td>
<td>-0.25</td>
<td>0.27</td>
<td>0.15</td>
<td>-0.01</td>
<td>0.14</td>
<td>0.02</td>
<td>-0.06</td>
<td>0.02</td>
<td>0.01</td>
<td>0.42</td>
</tr>
<tr>
<th>Temperature</th>
<td>0.24</td>
<td>0.04</td>
<td>0.11</td>
<td>1.00</td>
<td>0.17</td>
<td>-0.04</td>
<td>0.06</td>
<td>0.91</td>
<td>0.34</td>
<td>0.05</td>
<td>-0.25</td>
<td>0.60</td>
<td>-0.08</td>
<td>0.55</td>
</tr>
<tr>
<th>Humidity</th>
<td>0.11</td>
<td>-0.01</td>
<td>-0.25</td>
<td>0.17</td>
<td>1.00</td>
<td>-0.33</td>
<td>-0.54</td>
<td>0.55</td>
<td>-0.47</td>
<td>0.19</td>
<td>0.11</td>
<td>0.15</td>
<td>-0.07</td>
<td>-0.22</td>
</tr>
<tr>
<th>Wind Speed</th>
<td>-0.14</td>
<td>-0.06</td>
<td>0.27</td>
<td>-0.04</td>
<td>-0.33</td>
<td>1.00</td>
<td>0.17</td>
<td>-0.17</td>
<td>0.31</td>
<td>-0.02</td>
<td>-0.01</td>
<td>-0.16</td>
<td>0.02</td>
<td>0.12</td>
</tr>
<tr>
<th>Visibility</th>
<td>0.09</td>
<td>-0.03</td>
<td>0.15</td>
<td>0.06</td>
<td>-0.54</td>
<td>0.17</td>
<td>1.00</td>
<td>-0.16</td>
<td>0.17</td>
<td>-0.12</td>
<td>-0.08</td>
<td>0.16</td>
<td>0.03</td>
<td>0.24</td>
</tr>
<tr>
<th>Dew Point Temperature</th>
<td>0.25</td>
<td>0.03</td>
<td>-0.01</td>
<td>0.91</td>
<td>0.55</td>
<td>-0.17</td>
<td>-0.16</td>
<td>1.00</td>
<td>0.08</td>
<td>0.11</td>
<td>-0.17</td>
<td>0.58</td>
<td>-0.10</td>
<td>0.38</td>
</tr>
<tr>
<th>Uv Index</th>
<td>-0.03</td>
<td>0.01</td>
<td>0.14</td>
<td>0.34</td>
<td>-0.47</td>
<td>0.31</td>
<td>0.17</td>
<td>0.08</td>
<td>1.00</td>
<td>-0.06</td>
<td>-0.08</td>
<td>0.12</td>
<td>-0.03</td>
<td>0.25</td>
</tr>
<tr>
<th>Rainfall</th>
<td>-0.00</td>
<td>0.03</td>
<td>0.02</td>
<td>0.05</td>
<td>0.19</td>
<td>-0.02</td>
<td>-0.12</td>
<td>0.11</td>
<td>-0.06</td>
<td>1.00</td>
<td>0.00</td>
<td>0.02</td>
<td>-0.02</td>
<td>-0.11</td>
</tr>
<tr>
<th>Snowfall</th>
<td>0.01</td>
<td>-0.07</td>
<td>-0.06</td>
<td>-0.25</td>
<td>0.11</td>
<td>-0.01</td>
<td>-0.08</td>
<td>-0.17</td>
<td>-0.08</td>
<td>0.00</td>
<td>1.00</td>
<td>-0.18</td>
<td>-0.02</td>
<td>-0.16</td>
</tr>
<tr>
<th>Season</th>
<td>0.58</td>
<td>0.02</td>
<td>0.02</td>
<td>0.60</td>
<td>0.15</td>
<td>-0.16</td>
<td>0.16</td>
<td>0.58</td>
<td>0.12</td>
<td>0.02</td>
<td>-0.18</td>
<td>1.00</td>
<td>-0.10</td>
<td>0.44</td>
</tr>
<tr>
<th>Holiday</th>
<td>0.05</td>
<td>-0.02</td>
<td>0.01</td>
<td>-0.08</td>
<td>-0.07</td>
<td>0.02</td>
<td>0.03</td>
<td>-0.10</td>
<td>-0.03</td>
<td>-0.02</td>
<td>-0.02</td>
<td>-0.10</td>
<td>1.00</td>
<td>-0.08</td>
</tr>
<tr>
<th>Rentals</th>
<td>0.20</td>
<td>-0.06</td>
<td>0.42</td>
<td>0.55</td>
<td>-0.22</td>
<td>0.12</td>
<td>0.24</td>
<td>0.38</td>
<td>0.25</td>
<td>-0.11</td>
<td>-0.16</td>
<td>0.44</td>
<td>-0.08</td>
<td>1.00</td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=38e495f5">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h3>Pearson Correlation Results</h3>
<p>The Person Correlation Coefficient measures the strength of a relationship between variables with ranges from -1 to 1, with 0 indicating no correlation.</p>
<p>From this first output, we can gather some key points:</p>
<h4><span style="background-color: #dfc6f6">Strong Relationship:</span></h4><br/>
1. <b>Temperature</b>: The strongest relationship in the table is between Rentals &amp; Temperature, indicating that warmer days have more rentals.<br/>
2. <b>Season</b>: Although there is a strong connection between higher Rentals &amp; Season, we need further investigation to understand which seasons influence the demand positively and negatively.<br/>
3. <b> Hour of Day</b>: It is possible to see that Hour of Day &amp; Rentals are closely related, meaning that some times of the day will have more rentals, while others will have less.
<h4><span style="background-color: #dfc6f6">Moderate Relationship:</span></h4><br/>
While not as strong influences, these moderate impact variables should still be considered when developing strategies to maximize rental demand.<br/><br/>
1. <b>Dew Point Temperature</b>: More comfortable (warmer + moderate humidity) days result in higher rentals.<br/>
2. <b>UV Index</b>, <b>Visibility</b>, and <b>Humidity</b>: all these 3 factors have an impact in demand, meaning that sunnier, clearer and less muggy days results in more rentals.
<hr/>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=82d70933">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [7]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># boxplot comparing season and rentals</span>
<span class="n">sns</span><span class="o">.</span><span class="n">boxplot</span> <span class="p">(</span><span class="n">x</span> <span class="o">=</span> <span class="s1">'Season'</span><span class="p">,</span>
            <span class="n">y</span> <span class="o">=</span> <span class="s1">'Rentals'</span><span class="p">,</span>
            <span class="n">data</span> <span class="o">=</span> <span class="n">bikes_data</span><span class="p">,)</span>

<span class="c1"># customization of the boxplot</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="n">label</span> <span class="o">=</span> <span class="s2">"""</span>
<span class="s2">Bike Rentals Variation by Season</span>
<span class="s2">"""</span><span class="p">)</span>

<span class="c1"># displaying the visual</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">(</span><span class="n">block</span> <span class="o">=</span> <span class="kc">True</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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YTt79qzkz6bk5uYGa2vrJt9Pa8XP2/RkEYjKy8uRmZmJN998U7J85MiRSEtLq/U1RqMRRqNRfF5cXNykNTYEf4HkhZ+3vJw7dw7Tp09vln0tXbq0yfexfv16Tt1xF/y8TU8Wgeivv/5CZWVljTmBnJ2dodfra31NfHw84uLimqO8BuMvkLzw85YXNzc3rF+/3tRlNBo3NzdTl9Ci8fM2PVkEomoKhULyXBCEGsuqzZ8/H3PmzBGfFxcXw9XVtUnru1/8BZIXft7yYm1tzcAoI/y8TU8WgcjR0RHm5uY1zgZdunSpzpmklUollEplc5TXYPwFkhd+3kRETUcWo8ysrKzQr18/7N+/X7J8//79GDRokImqIiIiopZCFmeIAGDOnDmIiIhA//79odPpsH79epw7dw4vv/yyqUsjIiIiE5NNIJowYQKuXLmCxYsXIz8/H76+vti9e3ervoM7ERERNQ6FIAiCqYtoDYqLi6FSqWAwGODg4GDqcoiIiKge6vv9LYs+RERERER3w0BEREREssdARERERLLHQERERESyx0BEREREssdARERERLLHQERERESyx0BEREREssdARERERLInm1t3/F3VE3oXFxebuBIiIiKqr+rv7XvdmIOBqJ6uXbsGAHB1dTVxJURERHS/rl27BpVKVed63susnqqqqnDx4kXY29tDoVCYupxmU1xcDFdXV5w/f573cJMBft7yws9bXuT6eQuCgGvXrsHFxQVmZnX3FOIZonoyMzNDp06dTF2GyTg4OMjqF0ju+HnLCz9veZHj5323M0PV2KmaiIiIZI+BiIiIiGSPgYjuSqlUIiYmBkql0tSlUDPg5y0v/LzlhZ/33bFTNREREckezxARERGR7DEQERERkewxEBEREZHsMRBRrVJTUzFmzBi4uLhAoVBg+/btpi6Jmkh8fDwefvhh2Nvbw8nJCWPHjsXJkydNXRY1kcTERPj5+Ylz0eh0OuzZs8fUZVEziY+Ph0KhwOzZs01dSovDQES1KikpQa9evbBmzRpTl0JN7NChQ4iKikJGRgb279+PmzdvYuTIkSgpKTF1adQEOnXqhLfffhvHjh3DsWPHMHToUDz++OPIzc01dWnUxI4ePYr169fDz8/P1KW0SBxlRvekUCiwbds2jB071tSlUDO4fPkynJyccOjQIQQEBJi6HGoGarUa7777LqZOnWrqUqiJXL9+HX379kVCQgKWLFmC3r17Y9WqVaYuq0XhGSIikjAYDABufUlS21ZZWYktW7agpKQEOp3O1OVQE4qKisJjjz2G4cOHm7qUFov3MiMikSAImDNnDh555BH4+vqauhxqIjk5OdDpdCgrK0O7du2wbds2eHt7m7osaiJbtmzBTz/9hKNHj5q6lBaNgYiIRK+88gqys7Px448/mroUakJeXl7IyspCUVERvvrqK0yaNAmHDh1iKGqDzp8/j//5n//Bvn37YG1tbepyWjT2IaJ7Yh8ieZg5cya2b9+O1NRUeHh4mLocakbDhw9Hly5dsG7dOlOXQo1s+/bteOKJJ2Bubi4uq6yshEKhgJmZGYxGo2SdnPEMEZHMCYKAmTNnYtu2bTh48CDDkAwJggCj0WjqMqgJDBs2DDk5OZJlU6ZMQffu3fHGG28wDN2GgYhqdf36dfzxxx/i87y8PGRlZUGtVsPNzc2ElVFji4qKwqeffoodO3bA3t4eer0eAKBSqWBjY2Pi6qixLViwACEhIXB1dcW1a9ewZcsWHDx4ECkpKaYujZqAvb19jf6AdnZ26NixI/sJ3oGBiGp17NgxDBkyRHw+Z84cAMCkSZOQlJRkoqqoKSQmJgIAgoKCJMs3bNiAyZMnN39B1KQKCgoQERGB/Px8qFQq+Pn5ISUlBSNGjDB1aUQmxT5EREREJHuch4iIiIhkj4GIiIiIZI+BiIiIiGSPgYiIiIhkj4GIiIiIZI+BiIiIiGSPgYiIiIhkj4GIiIiIZI+BiIiIiGSPgYiIWo1Lly7hpZdegpubG5RKJTQaDYKDg5Genm7q0oioleO9zIio1Rg3bhwqKiqwceNGdO7cGQUFBfjuu+9w9epVU5dGRK0czxARUatQVFSEH3/8Ee+88w6GDBkCd3d3DBgwAPPnz8djjz0GADAYDJg+fTqcnJzg4OCAoUOH4pdffhG38eeff+Lxxx+Hs7Mz2rVrh4cffhgHDhyQ7CchIQGenp6wtraGs7MznnrqKXGd0WjErFmz4OTkBGtrazzyyCM4evSouP7gwYNQKBT47rvv0L9/f9ja2mLQoEE4efJkE787RPR3MRARUavQrl07tGvXDtu3b4fRaKyxXhAEPPbYY9Dr9di9ezcyMzPRt29fDBs2TDyDdP36dYwePRoHDhzAzz//jODgYIwZMwbnzp0DABw7dgyzZs3C4sWLcfLkSaSkpCAgIEDcx+uvv46vvvoKGzduxE8//YSuXbsiODi4xhmq6Oho/POf/8SxY8dgYWGBF154oQnfGSJqFAIRUSvx5ZdfCh06dBCsra2FQYMGCfPnzxd++eUXQRAE4bvvvhMcHByEsrIyyWu6dOkirFu3rs5tent7C6tXrxYEQRC++uorwcHBQSguLq7R7vr164KlpaWQnJwsLisvLxdcXFyE5cuXC4IgCD/88IMAQDhw4IDYZteuXQIAobS0tOEHTkRNjmeIiKjVGDduHC5evIidO3ciODgYBw8eRN++fZGUlITMzExcv34dHTt2FM8mtWvXDnl5efjzzz8BACUlJXj99dfh7e2N9u3bo127dvjtt9/EM0QjRoyAu7s7OnfujIiICCQnJ+PGjRsAbl1uq6iowODBg8V6LC0tMWDAAJw4cUJSp5+fn/izVqsFcKtDOBG1XOxUTUStirW1NUaMGIERI0bgrbfewosvvoiYmBhERkZCq9Xi4MGDNV7Tvn17AMBrr72GvXv34h//+Ae6du0KGxsbPPXUUygvLwcA2Nvb46effsLBgwexb98+vPXWW4iNjcXRo0chCAIAQKFQSLYtCEKNZZaWluLP1euqqqoa6y0goibAM0RE1Kp5e3ujpKQEffv2hV6vh4WFBbp27Sp5ODo6AgD+/e9/Y/LkyXjiiSfQs2dPaDQanDlzRrI9CwsLDB8+HMuXL0d2djbOnDmD77//Hl27doWVlRV+/PFHsW1FRQWOHTuGHj16NOchE1ET4BkiImoVrly5gqeffhovvPAC/Pz8YG9vj2PHjmH58uV4/PHHMXz4cOh0OowdOxbvvPMOvLy8cPHiRezevRtjx45F//790bVrV3z99dcYM2YMFAoFFi1aJDlz8+233+L06dMICAhAhw4dsHv3blRVVcHLywt2dnaYMWMGXnvtNajVari5uWH58uW4ceMGpk6dasJ3hogaAwMREbUK7dq1g7+/P1auXCn253F1dcW0adOwYMECKBQK7N69G9HR0XjhhRdw+fJlaDQaBAQEwNnZGQCwcuVKvPDCCxg0aBAcHR3xxhtvoLi4WNxH+/bt8fXXXyM2NhZlZWXw9PTEZ599Bh8fHwDA22+/jaqqKkRERODatWvo378/9u7diw4dOpjkPSGixqMQqi+MExEREckU+xARERGR7DEQERERkewxEBEREZHsMRARERGR7DEQERERkewxEBEREZHsMRARERGR7DEQERERkewxEBEREZHsMRARERGR7DEQERERkewxEBEREZHs/T9Ax02bIWCBCAAAAABJRU5ErkJggg=="/>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=6fa3818b">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h3>Season vs. Rentals Boxplot</h3>
<p>When comparing the distribution of rentals with season, we can see that <b>Winter</b> is in the bottom range, with a median of less than 500 rentals, around 200 to 300, with the interquartile range being narrow, indicating that demand is consistently low during Winter, with some extreme rentals days.</p>
<p><b>Spring</b> shows a drastic difference from the previous season, the median climbs to over 500 and has a greater variability, with some outliers hitting over 3000 rentals per day. This points out that users feel more comfortable using rental bikes during warmer periods.</p>
<p>The highest median and peaks happen during the <b>Summer</b>. With a median of around 1000 rentals and outliers that reach 3500+ rentals, this season shows consistent higher demand, with even its low days reaching above 500 rentals per day.</p>
<p>Finally, <b>Autumn</b> follows Summer's rental trends, with a median that is slightly above 1000 rentals and a high variability. This tells us that Autumn has a consistent high demand, but is more stable than Summer, with less rental peaks.</p>
<hr/>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=4ddc6dc5">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [8]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># defining filters</span>
<span class="n">winter_def</span>   <span class="o">=</span> <span class="p">(</span><span class="n">bikes_data</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span> <span class="p">:</span> <span class="p">,</span> <span class="s1">'Season'</span><span class="p">]</span>    <span class="o">==</span> <span class="mi">1</span><span class="p">)</span>
<span class="n">rental_def</span>   <span class="o">=</span> <span class="p">(</span><span class="n">bikes_data</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span> <span class="p">:</span> <span class="p">,</span> <span class="s1">'Rentals'</span><span class="p">]</span>   <span class="o">&gt;=</span> <span class="mi">700</span><span class="p">)</span>

<span class="c1"># printing out the results</span>
<span class="n">bikes_data</span><span class="p">[</span><span class="n">winter_def</span><span class="p">][</span><span class="n">rental_def</span><span class="p">]</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[8]:</div>
<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html" tabindex="0">
<div>
<style scoped="">
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
<th>Id</th>
<th>Month</th>
<th>Day Of Week</th>
<th>Hour</th>
<th>Temperature</th>
<th>Humidity</th>
<th>Wind Speed</th>
<th>Visibility</th>
<th>Dew Point Temperature</th>
<th>Uv Index</th>
<th>Rainfall</th>
<th>Snowfall</th>
<th>Season</th>
<th>Holiday</th>
<th>Rentals</th>
</tr>
</thead>
<tbody>
<tr>
<th>6</th>
<td>7</td>
<td>1</td>
<td>1</td>
<td>18</td>
<td>-0.8</td>
<td>24</td>
<td>2.3</td>
<td>2000</td>
<td>-18.9</td>
<td>0.01</td>
<td>0.0</td>
<td>0.0</td>
<td>1</td>
<td>0</td>
<td>723</td>
</tr>
<tr>
<th>156</th>
<td>157</td>
<td>2</td>
<td>4</td>
<td>18</td>
<td>4.1</td>
<td>40</td>
<td>2.1</td>
<td>1327</td>
<td>-8.3</td>
<td>0.10</td>
<td>0.0</td>
<td>0.0</td>
<td>1</td>
<td>0</td>
<td>712</td>
</tr>
<tr>
<th>199</th>
<td>200</td>
<td>2</td>
<td>1</td>
<td>8</td>
<td>-2.1</td>
<td>71</td>
<td>1.7</td>
<td>610</td>
<td>-6.6</td>
<td>0.06</td>
<td>0.0</td>
<td>0.0</td>
<td>1</td>
<td>0</td>
<td>764</td>
</tr>
<tr>
<th>208</th>
<td>209</td>
<td>2</td>
<td>3</td>
<td>18</td>
<td>3.9</td>
<td>56</td>
<td>4.0</td>
<td>1004</td>
<td>-4.0</td>
<td>0.18</td>
<td>0.0</td>
<td>0.0</td>
<td>1</td>
<td>0</td>
<td>767</td>
</tr>
<tr>
<th>216</th>
<td>217</td>
<td>2</td>
<td>6</td>
<td>16</td>
<td>7.6</td>
<td>18</td>
<td>3.2</td>
<td>1930</td>
<td>-15.2</td>
<td>1.73</td>
<td>0.0</td>
<td>0.0</td>
<td>1</td>
<td>0</td>
<td>730</td>
</tr>
<tr>
<th>217</th>
<td>218</td>
<td>2</td>
<td>7</td>
<td>8</td>
<td>-2.9</td>
<td>63</td>
<td>0.7</td>
<td>1386</td>
<td>-8.9</td>
<td>0.11</td>
<td>0.0</td>
<td>0.0</td>
<td>1</td>
<td>0</td>
<td>857</td>
</tr>
<tr>
<th>222</th>
<td>223</td>
<td>2</td>
<td>1</td>
<td>18</td>
<td>6.6</td>
<td>62</td>
<td>0.8</td>
<td>522</td>
<td>-0.1</td>
<td>0.05</td>
<td>0.0</td>
<td>0.0</td>
<td>1</td>
<td>0</td>
<td>969</td>
</tr>
<tr>
<th>223</th>
<td>224</td>
<td>2</td>
<td>2</td>
<td>8</td>
<td>5.7</td>
<td>57</td>
<td>2.5</td>
<td>458</td>
<td>-2.1</td>
<td>0.04</td>
<td>0.0</td>
<td>0.0</td>
<td>1</td>
<td>0</td>
<td>882</td>
</tr>
<tr>
<th>1288</th>
<td>1289</td>
<td>12</td>
<td>1</td>
<td>18</td>
<td>-2.1</td>
<td>29</td>
<td>3.9</td>
<td>2000</td>
<td>-17.7</td>
<td>0.00</td>
<td>0.0</td>
<td>0.0</td>
<td>1</td>
<td>0</td>
<td>864</td>
</tr>
<tr>
<th>1289</th>
<td>1290</td>
<td>12</td>
<td>2</td>
<td>8</td>
<td>-8.1</td>
<td>36</td>
<td>1.6</td>
<td>2000</td>
<td>-20.5</td>
<td>0.01</td>
<td>0.0</td>
<td>0.0</td>
<td>1</td>
<td>0</td>
<td>853</td>
</tr>
<tr>
<th>1349</th>
<td>1350</td>
<td>12</td>
<td>5</td>
<td>18</td>
<td>4.9</td>
<td>63</td>
<td>0.6</td>
<td>677</td>
<td>-1.5</td>
<td>0.00</td>
<td>0.0</td>
<td>0.0</td>
<td>1</td>
<td>1</td>
<td>725</td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=3337ea56">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h3>Winter Peak Days Analysis</h3><br/>
<p>Following the Rentals vs. Season boxplot, we can proceed to investigate the cause of the outliers on low demand seasons. When we isolate Winter season and high rentals, a pattern emerges:</p>
<ul>
<li>Most of the rentals in peak day happen during the morning and evening commute window, 8am and 6pm.</li>
<li>Renting bikes is also a viable option when days are clearer (visibility generally above 1000), and with dryer days (no rain or snowfall)</li>
</ul>
<p>Finally, although winter registers generally lower demand, these outliers demonstrate that users sees bike rentals as a convenient way of commuting during brighter and dryer days. The company should consider these for a dynamic fleet allocation and target more availability during weekdays and promotions for peak commute hours users.</p>
<hr/>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=4cfcbc78">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [9]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># instantiating a scatter plot for month, temperatyre and rentals</span>
<span class="n">sns</span><span class="o">.</span><span class="n">lmplot</span><span class="p">(</span><span class="n">x</span>          <span class="o">=</span> <span class="s1">'Rentals'</span>     <span class="p">,</span>
           <span class="n">y</span>          <span class="o">=</span> <span class="s1">'Temperature'</span> <span class="p">,</span>
           <span class="n">hue</span>        <span class="o">=</span> <span class="s1">'Month'</span>       <span class="p">,</span> 
           <span class="n">scatter</span>    <span class="o">=</span> <span class="kc">True</span>          <span class="p">,</span> 
           <span class="n">fit_reg</span>    <span class="o">=</span> <span class="kc">False</span>         <span class="p">,</span> 
           <span class="n">aspect</span>     <span class="o">=</span> <span class="mi">2</span>             <span class="p">,</span> 
           <span class="n">data</span>       <span class="o">=</span> <span class="n">bikes_data</span><span class="p">)</span>     


<span class="c1"># adding and personalizing reference lines</span>
<span class="n">plt</span><span class="o">.</span><span class="n">axvline</span><span class="p">(</span><span class="n">x</span> <span class="o">=</span> <span class="mi">1000</span><span class="p">,</span> <span class="n">color</span> <span class="o">=</span> <span class="s1">'purple'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">axvline</span><span class="p">(</span><span class="n">x</span> <span class="o">=</span> <span class="mi">2000</span><span class="p">,</span> <span class="n">color</span> <span class="o">=</span> <span class="s1">'purple'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">axvline</span><span class="p">(</span><span class="n">x</span> <span class="o">=</span> <span class="mi">3000</span><span class="p">,</span> <span class="n">color</span> <span class="o">=</span> <span class="s1">'purple'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[9]:</div>
<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain" tabindex="0">
<pre>&lt;matplotlib.lines.Line2D at 0x274cad87e60&gt;</pre>
</div>
</div>
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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"/>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=aa1344cd">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h3>Month &amp; Temperature vs.  Rentals (Part I)</h3><br/>
<p>As stated before, warmer temperature drives the outliers further to the right, meaning more rentals, and the scatter plot above reinforces this.</p>
<p>June and July, the peak summer months, consistently register the highest rental counts. In contrast, peak rental days in winter, autumn, and spring occur during periods when the temperature reaches above 10 degrees and around 20 degrees.</p>
<p>Colder days generally result in fewer rentals, which is highlighted by colder temperature markers being grouped mostly in the first segment of the plot. Here we can find December, January, and February (winter months), with no outliers moving after the first vertical demarcation.</p>
<p>Following the summer season, autumn experiences many days with comfortable temperatures, translating into higher rental volume when compared to other transitional seasons.</p>
<p>Although warmer days generally see more frequent rentals, the plot reveals that excessive heat often harms demand, since it impacts users' comfort and, consequently, their preference for utilizing the service. Days where the temperature hits above 30 degrees cluster in the first and second division lines (mid-demand), while Summer days that see peak rentals are usually around or below 30 degrees, but above 20 degrees.</p>
<hr/>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=21c2a1de">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [10]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># instantiating lineplot for month and rentals</span>
<span class="n">sns</span><span class="o">.</span><span class="n">lineplot</span><span class="p">(</span> <span class="n">x</span>     <span class="o">=</span> <span class="s1">'Month'</span>   <span class="p">,</span>
              <span class="n">y</span>     <span class="o">=</span> <span class="s1">'Rentals'</span> <span class="p">,</span>
              <span class="n">color</span> <span class="o">=</span> <span class="s1">'#d1a3fa'</span> <span class="p">,</span>
              <span class="n">data</span>  <span class="o">=</span> <span class="n">bikes_data</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[10]:</div>
<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain" tabindex="0">
<pre>&lt;Axes: xlabel='Month', ylabel='Rentals'&gt;</pre>
</div>
</div>
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAkQAAAGwCAYAAABIC3rIAAAAOnRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjEwLjAsIGh0dHBzOi8vbWF0cGxvdGxpYi5vcmcvlHJYcgAAAAlwSFlzAAAPYQAAD2EBqD+naQAAfURJREFUeJzt/Xl05HWdL/4/359P7ZWksnWSDp1uGmmQpRUGFGn4DXjYHEGOdxbQxhZHrqMXBFsWkXHmO+AZuwdmBO8MMygcx+aiDnPODCgzV1EUL0wPItBtKyCySNP0lk4vSSWp9bO8fn+8qz5JOpXUkkpqez7OyZGuVJJPYlL1qtf7tSgRERARERG1MKPWF0BERERUawyIiIiIqOUxICIiIqKWx4CIiIiIWh4DIiIiImp5DIiIiIio5TEgIiIiopbnq/UFNArXdbFv3z60t7dDKVXryyEiIqISiAgmJiYwODgIw5g7D8SAqET79u3D0NBQrS+DiIiIKrB7926sWLFizvczICpRe3s7AP0D7ejoqPHVEBERUSnGx8cxNDTkPY/PhQFRifLHZB0dHQyIiIiIGkyxchcWVRMREVHLY0BERERELY8BEREREbU8BkRERETU8hgQERERUctjQEREREQtjwERERERtTwGRERERNTyGBARERFRy2NARERERC2PARERERG1PAZERERE1PIYEBEREVHLY0BERA3HdQQiUuvLIKImwoCIiBqKuILUqMBK1vpKiKiZMCAioobiZAE7BVhJZomIqHoYEBFRQ8kmBOICTkYHR0RE1cCAiIgahpMV2GnAFwLEBewUM0REVB0MiIioYVgpgTiA4VMw/ICV0gXWREQLxYCIiBqC6+hCasOv/234AdcC7HRtr4uImgMDIiJqCHZaB0D5gEgpBWWwuJqIqoMBERHVPXEF2YRAmToQyjMCLK4moupgQEREdc/J6sDHDMy83TCVLq5OM0NERAvDgIiI6l42qQMeZahZ7zP8gJVkcTURLQwDIiKqa05WYKdmZ4fyWFxNRNXAgIiI6pqVnmq1L4TF1URUDQyIiKhuHd1qPxcWVxPRQjEgIqK6ZacBN1tCQMTiaiJaIAZERFSXRAq32s+FxdVEtBAMiIioLjmZwq32czH8gGPpjyEiKhcDIiKqS9Y8rfaF5IurswkWVxNR+RgQEVHdcbICa55W+7mYLK4mogoxICKiumOlBe48rfZzYXE1EVWKARER1ZV8q71ZpLNsLoYfsFIsriai8jAgIqK6Umqr/VwM/9TuMyKiUjEgIqK6ISKwkqW32hfCydVEVAkGRERUN8pttZ+LGchlmqzqXBcRNb+aBkRPP/00PvShD2FwcBBKKXzve9+b876f/vSnoZTC1772tRm3ZzIZXH/99ejt7UU0GsXll1+OPXv2zLjP6OgoNmzYgFgshlgshg0bNmBsbKz63xARLYiVEohbeqv9XPLF1VaKGSIiKk1NA6JEIoF3v/vduPfee+e93/e+9z384he/wODg4Kz3bdy4EY8++igefvhhbN26FZOTk7jsssvgOI53n/Xr12PHjh14/PHH8fjjj2PHjh3YsGFD1b8fIqqcY+WKqYPV+Xwsriaicvhq+cX/4A/+AH/wB38w73327t2Lz372s/jRj36ESy+9dMb74vE4vvnNb+Khhx7ChRdeCAD49re/jaGhIfzkJz/BJZdcgldeeQWPP/44nn32WZx11lkAgAceeABnn302Xn31VZx44okFv24mk0EmM1WVOT4+vpBvlYiKsFK61d4XWlh2KC+/ysPJAEakKp+SiJpYXdcQua6LDRs24JZbbsEpp5wy6/3btm2DZVm4+OKLvdsGBwdx6qmn4plnngEA/PznP0csFvOCIQB43/veh1gs5t2nkM2bN3tHbLFYDENDQ1X8zohouoW22hfC4moiKkddB0R33nknfD4fbrjhhoLvHx4eRiAQQFdX14zb+/v7MTw87N2nr69v1sf29fV59ynktttuQzwe99527969gO+EiOZjp3WrfKWt9nNhcTURlaqmR2bz2bZtG/73//7f2L59e9nttyIy42MKffzR9zlaMBhEMFilYgYimlO+1d4wKm+1n4thKjiuwEoLzEB1PzcRNZe6zRD913/9F0ZGRrBy5Ur4fD74fD7s2rULN910E4499lgAwMDAALLZLEZHR2d87MjICPr7+737HDhwYNbnP3jwoHcfIqqdarXazyVfS8TiaiKaT90GRBs2bMCvf/1r7Nixw3sbHBzELbfcgh/96EcAgDPOOAN+vx9PPPGE93H79+/HSy+9hHXr1gEAzj77bMTjcTz33HPefX7xi18gHo979yGi2vFa7c3FyeBwcjURlaKmR2aTk5N44403vH/v3LkTO3bsQHd3N1auXIme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HHP1Tx1zBaIKvpDuDGMwREREVFjDFFWLCG688Uace+65OPXUUwEAw8PDAID+/v4Z9+3v78euXbu8+wQCAXR1dc26T/7jC9m8eTPuuOOOan4L83IdwE4JXDe37FfpQmtl5rYA57I9XqbHzL2f84CIiIgWrGECos9+9rP49a9/ja1bt85639FBgYgUDRSK3ee2227DjTfe6P17fHwcQ0NDZV51aZQJ+AK5Iy4/YJg85iIiIlpKDREQXX/99Xjsscfw9NNPY8WKFd7tAwMDAHQWaPny5d7tIyMjXtZoYGAA2WwWo6OjM7JEIyMjWLdu3ZxfMxgMIhgMVvtbKSjUqQMeZnuIiIhqo65riEQEn/3sZ/HII4/gySefxOrVq2e8f/Xq1RgYGMATTzzh3ZbNZvHUU095wc4ZZ5wBv98/4z779+/HSy+9NG9AtJSU4ioMIiKiWqrrDNF1112H7373u/j+97+P9vZ2r+YnFoshHA5DKYWNGzdi06ZNWLNmDdasWYNNmzYhEolg/fr13n2vueYa3HTTTejp6UF3dzduvvlmrF27FhdeeGEtvz0iIiKqE3UdEN13330AgPPPP3/G7d/61rfwiU98AgDwhS98AalUCtdeey1GR0dx1lln4cc//jHa29u9+99zzz3w+Xy44oorkEqlcMEFF2DLli0wTXOpvhUiIiKqYw01h6iWFnMOERERES2OppxDRERERLQYGBARERFRy2NARERERC2PARERERG1PAZERERE1PIYEBEREVHLY0BERERELY8BEREREbU8BkRERETU8hgQERERUcur611m9SS/4WR8fLzGV0JERESlyj9vF9tUxoCoRBMTEwCAoaGhGl8JERERlWtiYgKxWGzO93O5a4lc18W+ffvQ3t4OpVStL2dJjY+PY2hoCLt37+Zi2wXgz7E6+HOsDv4cq4M/x+pYzJ+jiGBiYgKDg4MwjLkrhZghKpFhGFixYkWtL6OmOjo6+AdfBfw5Vgd/jtXBn2N18OdYHYv1c5wvM5THomoiIiJqeQyIiIiIqOUxIKKigsEg/uqv/grBYLDWl9LQ+HOsDv4cq4M/x+rgz7E66uHnyKJqIiIiannMEBEREVHLY0BERERELY8BEREREbU8BkRERETU8hgQ0Zw2b96M97znPWhvb0dfXx8+/OEP49VXX631ZTW8zZs3QymFjRs31vpSGs7evXvxsY99DD09PYhEIjjttNOwbdu2Wl9WQ7FtG3/xF3+B1atXIxwO47jjjsOXv/xluK5b60ura08//TQ+9KEPYXBwEEopfO9735vxfhHB7bffjsHBQYTDYZx//vl4+eWXa3OxdWy+n6NlWbj11luxdu1aRKNRDA4O4uMf/zj27du3JNfGgIjm9NRTT+G6667Ds88+iyeeeAK2bePiiy9GIpGo9aU1rOeffx73338/3vWud9X6UhrO6OgozjnnHPj9fvzwhz/Eb37zG3z1q19FZ2dnrS+todx55534+te/jnvvvRevvPIK7rrrLvzt3/4t/uEf/qHWl1bXEokE3v3ud+Pee+8t+P677roLd999N+699148//zzGBgYwEUXXeTtwSRtvp9jMpnE9u3b8Zd/+ZfYvn07HnnkEbz22mu4/PLLl+bihKhEIyMjAkCeeuqpWl9KQ5qYmJA1a9bIE088Ieedd5587nOfq/UlNZRbb71Vzj333FpfRsO79NJL5ZOf/OSM2/7wD/9QPvaxj9XoihoPAHn00Ue9f7uuKwMDA/I3f/M33m3pdFpisZh8/etfr8EVNoajf46FPPfccwJAdu3atejXwwwRlSwejwMAuru7a3wljem6667DpZdeigsvvLDWl9KQHnvsMZx55pn4kz/5E/T19eH000/HAw88UOvLajjnnnsufvrTn+K1114DAPzqV7/C1q1b8cEPfrDGV9a4du7cieHhYVx88cXebcFgEOeddx6eeeaZGl5Z44vH41BKLUkmmMtdqSQightvvBHnnnsuTj311FpfTsN5+OGHsX37djz//PO1vpSG9eabb+K+++7DjTfeiD//8z/Hc889hxtuuAHBYBAf//jHa315DePWW29FPB7HO9/5TpimCcdx8JWvfAUf/ehHa31pDWt4eBgA0N/fP+P2/v5+7Nq1qxaX1BTS6TS++MUvYv369UuyOJcBEZXks5/9LH79619j69attb6UhrN792587nOfw49//GOEQqFaX07Dcl0XZ555JjZt2gQAOP300/Hyyy/jvvvuY0BUhn/913/Ft7/9bXz3u9/FKaecgh07dmDjxo0YHBzE1VdfXevLa2hKqRn/FpFZt1FpLMvCRz7yEbiui3/6p39akq/JgIiKuv766/HYY4/h6aefxooVK2p9OQ1n27ZtGBkZwRlnnOHd5jgOnn76adx7773IZDIwTbOGV9gYli9fjpNPPnnGbSeddBL+/d//vUZX1JhuueUWfPGLX8RHPvIRAMDatWuxa9cubN68mQFRhQYGBgDoTNHy5cu920dGRmZljag4y7JwxRVXYOfOnXjyySeXJDsEsMuM5iEi+OxnP4tHHnkETz75JFavXl3rS2pIF1xwAV588UXs2LHDezvzzDNx1VVXYceOHQyGSnTOOefMGvvw2muvYdWqVTW6osaUTCZhGDMf+k3TZNv9AqxevRoDAwN44oknvNuy2SyeeuoprFu3roZX1njywdDrr7+On/zkJ+jp6Vmyr80MEc3puuuuw3e/+118//vfR3t7u3dOHovFEA6Ha3x1jaO9vX1W3VU0GkVPTw/rscrw+c9/HuvWrcOmTZtwxRVX4LnnnsP999+P+++/v9aX1lA+9KEP4Stf+QpWrlyJU045Bb/85S9x991345Of/GStL62uTU5O4o033vD+vXPnTuzYsQPd3d1YuXIlNm7ciE2bNmHNmjVYs2YNNm3ahEgkgvXr19fwquvPfD/HwcFB/PEf/zG2b9+O//zP/4TjON7zTnd3NwKBwOJe3KL3sVHDAlDw7Vvf+latL63hse2+Mv/xH/8hp556qgSDQXnnO98p999/f60vqeGMj4/L5z73OVm5cqWEQiE57rjj5Etf+pJkMplaX1pd+9nPflbw8fDqq68WEd16/1d/9VcyMDAgwWBQfv/3f19efPHF2l50HZrv57hz5845n3d+9rOfLfq1KRGRxQ25iIiIiOoba4iIiIio5TEgIiIiopbHgIiIiIhaHgMiIiIiankMiIiIiKjlMSAiIiKilseAiIiIiFoeAyIiIiJqeQyIiIgqpJTC9773vVpfBhFVAQMiImo4n/jEJ6CUwmc+85lZ77v22muhlMInPvGJqn2922+/HaeddlrVPh8R1R8GRETUkIaGhvDwww8jlUp5t6XTafzLv/wLVq5cWcMrI6JGxICIiBrS7/3e72HlypV45JFHvNseeeQRDA0N4fTTT/duy2QyuOGGG9DX14dQKIRzzz0Xzz//vPf+//f//h+UUvjpT3+KM888E5FIBOvWrcOrr74KANiyZQvuuOMO/OpXv4JSCkopbNmyxfv4Q4cO4X/8j/+BSCSCNWvW4LHHHlv8b56Iqo4BERE1rD/90z/Ft771Le/f//zP/4xPfvKTM+7zhS98Af/+7/+OBx98ENu3b8fxxx+PSy65BEeOHJlxvy996Uv46le/ihdeeAE+n8/7PFdeeSVuuukmnHLKKdi/fz/279+PK6+80vu4O+64A1dccQV+/etf44Mf/CCuuuqqWZ+biOofAyIialgbNmzA1q1b8dZbb2HXrl347//+b3zsYx/z3p9IJHDffffhb//2b/EHf/AHOPnkk/HAAw8gHA7jm9/85ozP9ZWvfAXnnXceTj75ZHzxi1/EM888g3Q6jXA4jLa2Nvh8PgwMDGBgYADhcNj7uE984hP46Ec/iuOPPx6bNm1CIpHAc889t2Q/AyKqDl+tL4CIqFK9vb249NJL8eCDD0JEcOmll6K3t9d7/+9+9ztYloVzzjnHu83v9+O9730vXnnllRmf613vepf338uXLwcAjIyMFK1Hmv5x0WgU7e3tGBkZWdD3RURLjwERETW0T37yk/jsZz8LAPjHf/zHGe8TEQC6Pf7o24++ze/3e/+df5/rukW//vSPy39sKR9HRPWFR2ZE1NA+8IEPIJvNIpvN4pJLLpnxvuOPPx6BQABbt271brMsCy+88AJOOumkkr9GIBCA4zhVu2Yiqj/MEBFRQzNN0zv+Mk1zxvui0Sj+1//6X7jlllvQ3d2NlStX4q677kIymcQ111xT8tc49thjsXPnTuzYsQMrVqxAe3s7gsFgVb8PIqotBkRE1PA6OjrmfN/f/M3fwHVdbNiwARMTEzjzzDPxox/9CF1dXSV//j/6oz/CI488gve///0YGxvDt771raoOfiSi2lOSP2QnIiIialGsISIiIqKWx4CIiIiIWh4DIiIiImp5DIiIiIio5TEgIiIiopbHgIiIiIhaHgMiIiIiankMiIiIiKjlMSAiIiKilseAiIiIiFoeAyIiIiJqef9/VjGKhKNi4VUAAAAASUVORK5CYII="/>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=1d371d21">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h3>Month &amp; Temperature vs.  Rentals (Part II)</h3><br/>
<p>Even though the previous scatter plot had a major role in informing how temperature affects rentals and, consequently, affects the months of most usage to less usage, the graph above is a cleaner visualization of bike rentals per month, reinforcing the periods of peak demand, them being June, the first and highest peak, with a stable demand until October, the second peak, during autumn season.</p>
<p>Additionally, it facilitates the view of the months where rental steeply decreases. This drastic drop remains constant for during November and December, and increases slowly throughout January and February. With adequate strategies, the abrupt drop can be softened with off-season promotions and targeted marketing during clearer days.</p>
<hr/>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=942dbe36">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [11]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># instantiating a pointplot for hour and rentals</span>
<span class="n">sns</span><span class="o">.</span><span class="n">pointplot</span><span class="p">(</span><span class="n">x</span>         <span class="o">=</span> <span class="s1">'Hour'</span>    <span class="p">,</span>
              <span class="n">y</span>         <span class="o">=</span> <span class="s1">'Rentals'</span> <span class="p">,</span>
              <span class="n">data</span>      <span class="o">=</span> <span class="n">bikes_data</span><span class="p">,</span>
              <span class="n">estimator</span> <span class="o">=</span> <span class="s2">"mean"</span>    <span class="p">,</span>
              <span class="n">color</span>     <span class="o">=</span> <span class="s1">'#d1a3fa'</span> <span class="p">,</span>
              <span class="n">markers</span>   <span class="o">=</span> <span class="s1">'s'</span>       <span class="p">,</span>
              <span class="n">scale</span>     <span class="o">=</span> <span class="mi">1</span>         <span class="p">,</span>          
              <span class="n">errwidth</span>  <span class="o">=</span> <span class="mf">1.7</span>       <span class="p">,</span>        
              <span class="n">capsize</span>   <span class="o">=</span> <span class="mf">0.05</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[11]:</div>
<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain" tabindex="0">
<pre>&lt;Axes: xlabel='Hour', ylabel='Rentals'&gt;</pre>
</div>
</div>
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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ITZs2ICtW7fi6aefxp49e3DVVVe5LvLdUVVVhbq6Ojz55JOYOXMmPv74Y9x00024+eabsW3btoDU9/XXX4der8fNN9/sVzl/+ctfMHz4cPTt2xdarRYzZ87ECy+8gCuuuKLbZV1yySXIzc3F8uXLYTab0dzcjCeffBKVlZVdPofa+v725/wJ5PWgO2V299zpqMxAnD9c7T7AWv+iF0L49Ss/WO655x78+9//9vtXPQAMHToUJSUlqK6uxj//+U/Mnz8f27Zt8ykoKi8vx3333YePP/64w3EE3VFYWOj6e9SoUZg0aRIGDhyI119/HUuXLvWpTFmWMX78eKxcuRIAMGbMGBw8eBAvvvgifvrTn/pV3zVr1qCwsLBLYz468tZbb2H9+vV48803MWLECJSUlGDJkiUwmUyYP3++z+WuW7cOd955J/r06QO1Wo2xY8di7ty52Ldvn1/1dYqUcwhwDBK97bbbIMsyXnjhBb/KmjZtGkpKSnD+/Hm88sormDNnDnbt2oXMzMxul7V37178+c9/xr59+wL63t16662uv0eOHInx48cjNzcXmzdv7nbQ4Rzcf8MNN+D+++8HAFx22WXYsWMH/va3v2HKlCl+1/fVV1/FHXfc4fd3yV/+8hfs3LkT7733HnJzc/H555/jV7/6FbKzs7vdih0XF4d//vOfuOuuu5CWlga1Wo3p06crvqc609H3ty/nTyCvB10t05dzp6MyA3H+sIUoQDIyMqBWq70i8aqqKq+IPdQWL16M9957D59++in69u3rd3larRaDBg3C+PHjsWrVKowePRp//vOffSpr7969qKqqwrhx46DRaKDRaLBt2zb85S9/gUajgd1u97u+SUlJGDVqVKezOjqSnZ3tFfANGzbM5wH0TidOnMCWLVvw85//3K9yAODBBx/Eb37zG9x2220YNWoU5s2bh/vvv9/vlreBAwdi27ZtqKurQ3l5OXbv3o2Wlhbk5eX5Va5z5l8knEOA4wt9zpw5KCsrQ3FxsV+tQ4Djczlo0CBMnDgRa9asgUajwZo1a3wq64svvkBVVRX69evnOo9OnDiBZcuWoX///n7V01N2djZyc3N9OpcyMjKg0WiCch4Bjvfg8OHDfp9LjY2NePjhh/HMM8/g+uuvx6WXXop77rkHt956K/77v//bpzLHjRvn+hFZUVGBoqIiXLhwoUvn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"/>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=50bcf3a1">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h3>Hour vs. Rentals</h3><br/>
<p>The continuous time plot showcases the rental variation during hourly periods, and because there is a lot of details to uncover, we'll explore through sections:</p>
<ul>
<li><b>Low movement </b><br/></li>
</ul>
<p>The overnight time faces a consistent drop on rentals starting from the evening peak at 9 pm, and only starts rising up again around 6 am.<br/><br/></p>
<ul>
<li><b>First peak</b><br/></li>
</ul>
<p>As movement starts to ramp up at 6 am, rentals see a steep growth until it reaches its first peak at 8 am, a common commute time morning window, indicating users' preference for rental bikes as a form of transportation to work.<br/><br/></p>
<ul>
<li><b>Mid-level traffic</b><br/></li>
</ul>
<p>After the 8 am peak, a constant mid-traffic level starts, maintaining a median of around 700 to 1200 during late-morning and afternoon hours.<br/><br/></p>
<ul>
<li><b>Rush hour</b><br/></li>
</ul>
<p>At 5 pm the rentals steeply grow, reaching the highest peak that occurs around 6 pm, another specific evening time commute window, reaching a median of almost 1750 rentals. This data reinforces what was previously concluded, that users see rental bikes as a convenient commute vehicle.<br/><br/></p>
<ul>
<li><b>Last peak</b><br/></li>
</ul>
<p>The last peak happens at 9 pm, indicating that users still utilize the services for personal leisure time, after that, the usage continuously drop until morning hours.<br/><br/></p>
<ul>
<li><b>Invisible details</b><br/></li>
</ul>
<p>The bars outside the squares indicate the variability inside each times, meaning that during overnight time there is last variability, it is constantly low volume of rentals, while during peak hours the variation is higher.</p>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=89669766">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [12]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># instantiating an lmplot for dew point and rentals</span>
<span class="n">sns</span><span class="o">.</span><span class="n">lmplot</span><span class="p">(</span><span class="n">x</span>       <span class="o">=</span> <span class="s1">'Dew Point Temperature'</span> <span class="p">,</span>
           <span class="n">y</span>       <span class="o">=</span> <span class="s1">'Rentals'</span>               <span class="p">,</span> 
           <span class="n">hue</span>     <span class="o">=</span> <span class="kc">None</span>                    <span class="p">,</span> 
           <span class="n">scatter</span> <span class="o">=</span> <span class="kc">True</span>                    <span class="p">,</span> 
           <span class="n">fit_reg</span> <span class="o">=</span> <span class="kc">True</span>                    <span class="p">,</span> 
           <span class="n">aspect</span>  <span class="o">=</span> <span class="mi">3</span>                       <span class="p">,</span> 
           <span class="n">data</span>    <span class="o">=</span> <span class="n">bikes_data</span><span class="p">)</span> 

<span class="c1"># colors and adjustments to plot</span>
<span class="n">sns</span><span class="o">.</span><span class="n">regplot</span><span class="p">(</span><span class="n">x</span>           <span class="o">=</span> <span class="s1">'Dew Point Temperature'</span>               <span class="p">,</span>
            <span class="n">y</span>           <span class="o">=</span> <span class="s1">'Rentals'</span>                             <span class="p">,</span>
            <span class="n">data</span>        <span class="o">=</span> <span class="n">bikes_data</span>                            <span class="p">,</span>
            <span class="n">scatter_kws</span> <span class="o">=</span> <span class="p">{</span><span class="s1">'s'</span><span class="p">:</span><span class="mi">40</span><span class="p">,</span> <span class="s1">'alpha'</span><span class="p">:</span><span class="mi">1</span><span class="p">,</span> <span class="s1">'color'</span><span class="p">:</span><span class="s1">'#ffd45a'</span><span class="p">},</span>
            <span class="n">line_kws</span>    <span class="o">=</span> <span class="p">{</span><span class="s1">'linewidth'</span><span class="p">:</span><span class="mi">3</span><span class="p">,</span> <span class="s1">'color'</span><span class="p">:</span><span class="s1">'#d1a3fa'</span><span class="p">})</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[12]:</div>
<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain" tabindex="0">
<pre>&lt;Axes: xlabel='Dew Point Temperature', ylabel='Rentals'&gt;</pre>
</div>
</div>
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABdEAAAHpCAYAAABtM3XZAAAAOnRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjEwLjAsIGh0dHBzOi8vbWF0cGxvdGxpYi5vcmcvlHJYcgAAAAlwSFlzAAAPYQAAD2EBqD+naQABAABJREFUeJzs/XuUXGWdL/6/n72r+kJIV6cv1d25DHAMkABBGJDQ4qgB5OLJ4Ihf0B/r5IjDAXMU/GHAmSNnzfrKrDkwoic4yyhxPB5dOs7EMzMwI4hZw4xBfkoCQyQjakdoTmDSSaqqk/Qll75U7ef5/VGXVHdX7Vvta/X7tVbEpHfvevbt2bU/z2d/HqGUUiAiIiIiIiIiIiIiogW0sBtARERERERERERERBRVDKITEREREREREREREdXBIDoRERERERERERERUR0MohMRERERERERERER1cEgOhERERERERERERFRHQyiExERERERERERERHVwSA6EREREREREREREVEdDKLbpJTC5OQklFJhN4WIiIiIiIiIiIiIAsIguk0nTpxAKpXCiRMnwm4KEREREREREREREQWEQXQiIiIiIiIiIiIiojoYRCciIiIiIiIiIiIiqoNBdCIiIiIiIiIiIiKiOhhEJyIiIiIiIiIiIiKqg0F0IiIiIiIiIiIiIqI6GEQnIiIiIiIiIiIiIqqDQXQiIiIiIiIiIiIiojoYRCciIiIiIiIiIiIiqoNBdCIiIiIiIiIiIiKiOhhEJyIiIiIiIiIiIiKqg0F0IiIiIiIiIiIiIqI6GEQnIiIiIiIiIiIiIqqDQXQiIiIiIiIiIiIiojoSYTeAiIiIiIiIiIiCI6ezyI3sgpEfh57sRHrlBmhtfWE3i4goshhEJyIiIiIiIiJaDFQBmf3b0WfsRq8SkBDQCgpi+Glk9EH0r9kMCIaKiIjmYzkXIiIiIiIiIqJFILN/O9LGbggB6JpCUpPQNQUhgLSxG5n928NuIhFRJDGITkRERERERETU5OR0Fn3Gbmii9s81AfQZuyGns8E2jIgoBhhEJyIiIiIiIiJqcrmRXZCqTgS9RCqB3MiugFpERBQfDKITERERERERETU5Iz8OCYsgOgSM/HgwDSIiihEG0YmIiIiIiIiImpye7IQGZbqMBgU92RlMg4iIYoRBdCIiIiIiIiKiJpdeuQGasAiiC4X0yg0BtYiIKD4YRCciIiIiIiIianJaWx+y+iBknTi6VEBWH4TW1hdsw4iIYoBBdCIiIiIiIiKiRaB/zWbk9EEoBRhSIC81GFJAKSCnD6J/zeawm0hEFElCKWX+Lg8BACYnJ5FKpTAxMYGOjo6wm0NERERERERE5IqcziI3sgtGfhx6srNY6sXDDHS/109EFDQG0W1iEJ2IiIiIiIiIyIQqILN/O/qM3ZBKQEJAg4ImFLLlTHeRCLuVRESOsZwLERERERERERE1LLN/O9LGbggB6JpCUpPQNQUhgLSxG5n928NuIhGRKwyiExERERERERFRQ+R0Fn3Gbmii9s81gWKG+nQ22IYREXmAQXQiIiIiIiIiImpIbmQXpKoTQS+RSiA3siugFhEReYdBdCIiIiIiIiIiaoiRH4eERRAdAkZ+PJgGERF5iEF0IiIiIiIiIiJqiJ7shAZluowGBT3ZGUyDiIg8xCA6ERERERERERE1JL1yAzRhEUQXCumVGwJqERGRdxhEJyIiIiIiIiKihmhtfcjqg5B14uhSAVl9EFpbX7ANIyLyAIPoRERERERERETUsP41m5HTB6EUYEiBvNRgSAGlgJw+iP41m8NuIhGRK0IpZf6uDQEAJicnkUqlMDExgY6OjrCbQ0REREREREQUSXI6i9zILhj5cejJzmKpF2agE1GMMYhuE4PoRERERERERERERIsPy7kQEREREREREREREdXBIDoRERERERERERERUR0MohMRERERERERERER1cEgOhERERERERERERFRHaEG0Z944glceuml6OjoQEdHBwYHB/HjH/+48vM777wTQog5f66++uo565iZmcF9992Hnp4eLFmyBLfccgtGRkbmLDM2NoZNmzYhlUohlUph06ZNGB8fD2ITiYiIiIiIiIiIiCjGQg2ir1y5En/+53+OV155Ba+88gquvfZafOhDH8Kvf/3ryjI33XQTjhw5Uvnz7LPPzlnH/fffj6eeego7duzAz372M5w8eRIbN26EYRiVZe644w7s27cPO3fuxM6dO7Fv3z5s2rQpsO0kIiIiIiIiIiIiongSSikVdiOqdXV14Utf+hLuuusu3HnnnRgfH8c//MM/1Fx2YmICvb29+N73voePfvSjAIDDhw9j1apVePbZZ3HjjTdiaGgIF110Efbs2YP169cDAPbs2YPBwUHs378fF154oa12TU5OIpVKYWJiAh0dHZ5sKxERERERERERERFFW2RqohuGgR07duDUqVMYHBys/Pvzzz+PdDqNCy64AHfffTdyuVzlZ3v37kU+n8cNN9xQ+bfly5fjkksuwYsvvggA2L17N1KpVCWADgBXX301UqlUZZlaZmZmMDk5OecPERERERERERERES0uibAb8Nprr2FwcBDT09M4++yz8dRTT+Giiy4CANx888247bbbcM455+DAgQP4kz/5E1x77bXYu3cvWltbkclk0NLSgmXLls1ZZ19fHzKZDAAgk8kgnU4v+Nx0Ol1ZppZHH30UDz/8sIdbSkRERERERERRI6ezyI3sgpEfh57sRHrlBmhtfWE3i4iIIiT0IPqFF16Iffv2YXx8HH//93+Pj3/84/jpT3+Kiy66qFKiBQAuueQSXHnllTjnnHPwox/9CLfeemvddSqlIISo/L36/9dbZr7Pf/7z2LJlS+Xvk5OTWLVqldPNIyIiIiIiIqIoUgVk9m9Hn7EbvUpAQkArKIjhp5HRB9G/ZjMgQg+bEBFRBIRezqWlpQWrV6/GlVdeiUcffRTvfOc78Rd/8Rc1lx0YGMA555yDN954AwDQ39+P2dlZjI2NzVkul8uhr6+vskw2m12wrtHR0coytbS2tqKjo2POHyIiIiIiIiJqDpn925E2dkMIQNcUkpqErikIAaSN3cjs3x52E4mIKCJCD6LPp5TCzMxMzZ8dO3YMBw8exMDAAADgiiuuQDKZxHPPPVdZ5siRI/jVr36Fd7/73QCAwcFBTExM4OWXX64s89JLL2FiYqKyDBEREREREREtHnI6iz5jN7Q6L6hrAugzdkNOL0zKIyKixSfU95Ieeugh3HzzzVi1ahVOnDiBHTt24Pnnn8fOnTtx8uRJfOELX8BHPvIRDAwM4K233sJDDz2Enp4efPjDHwYApFIp3HXXXXjggQfQ3d2Nrq4uPPjgg1i3bh2uv/56AMDatWtx00034e6778Y3vvENAMA999yDjRs34sILLwxt24mIiIiIiIgoHLmRXehVArpQdZeRSmB0ZBf6V38swJYREVEUhRpEz2az2LRpE44cOYJUKoVLL70UO3fuxAc+8AFMTU3htddew3e/+12Mj49jYGAAGzZswA9+8AMsXbq0so7HH38ciUQCt99+O6ampnDdddfhO9/5DnRdryzz/e9/H5/5zGdwww03AABuueUWbNu2LfDtJSIiIiIiIqLwGflxSAjoMAmiQ8DIjwfXKCIiiiyhlKp/x6CKyclJpFIpTExMsD46ERERERERUYxlhnegd+oZ6Fr9kIghBUbbNzITnYiIolcTnYiIiIiIiIjIT+mVG6CZlHIBAE0opFduCKhFREQUZQyiExEREREREdGiorX1IasPQtaJo0sFZPVBaG19wTaMiIgiiUF0IiIiIiIiIlp0+tdsRk4fhFLF0i15qcGQAkoBOX0Q/Ws2h91EIiKKCNZEt4k10YmIiIiIiIiaj5zOIjeyC0Z+HHqys1jqhRnoRERUhUF0mxhEJyIiIiIiIiIiIlp8EmE3gIiIiIiIiIiIqBnwzQai5sQgOhERERERERERUSNUAZn929Fn7EavEpAQ0AoKYvhpZMo19gXDcERxxYlFiYiIiIiIiIiIGpDZvx1pYzeEAHRNIalJ6JqCEEDa2I3M/u1hN5GIGsAgOhERERERERERkUtyOos+Yzc0UfvnmgD6jN2Q09lgG0ZEnmEQnYiIiIiIiIiIyKXcyC5IVSeCXiKVQG5kV0AtIiKvMYhORERERERERETkkpEfh4RFEB0CRn48mAYRkecYRCciIiIiIiIiInJJT3ZCgzJdRoOCnuwMpkFE5DkG0YmIiIiIiIiIiFxKr9wATVgE0YVCeuWGgFpERF5jEJ2IiIiIiIiIiMglra0PWX0Qsk4cXSogqw9Ca+sLtmFE5BkG0YmIiIiIiIiIiBrQv2YzcvoglAIMKZCXGgwpoBSQ0wfRv2Zz2E0kogYIpZT5+yYEAJicnEQqlcLExAQ6OjrCbg4REREREREREUWMnM4iN7ILRn4cerKzWOqFGehEsccguk0MohMREREREREREREtPomwG0BEREREREREFCXMJiYiomoMohMRERERERERAYAqILN/O/qM3ehVAhICWkFBDD+NTLmutWAohYhoseHEokREREREREREADL7tyNt7IYQgK4pJDUJXVMQAkgbu5HZvz3sJhIRUQgYRCciIiIiIiKiRU9OZ9Fn7IYmav9cE0CfsRtyOhtsw4iIKHQMohMRERERERHRopcb2QWp6kTQS6QSyI3sCqhFREQUFQyiExEREREREdGiZ+THIWERRIeAkR8PpkFERBQZDKITERERERER0aKnJzuhQZkuo0FBT3YG0yAiIooMBtGJiIiIiIiIaNFLr9wATVgE0YVCeuWGgFpERERRwSA6ERERERERES16WlsfsvogZJ04ulRAVh+E1tYXbMOIiCh0DKITEREREREREQHoX7MZOX0QSgGGFMhLDYYUUArI6YPoX7M57CYSEVEIhFLK/F0lAgBMTk4ilUphYmICHR0dYTeHiIiIiIiIiHwip7PIjeyCkR+HnuwslnphBjoR0aLFILpNDKITERERERERERERLT4s50JEREREREREREREVAeD6EREREREREREREREdSTCbgARERERERFFA+tAExERES3EIDoREREREdFipwrI7N+OPmM3epWAhIBWUBDDTyOjD6J/zWZA8PGRiIiIFid+CyIiIiIiIlrkMvu3I23shhCALhR0qMrP0sZuZPYD/WvvDbGFROQHvn1CRGQPg+hERERERESLmJzOoq8UQK9FE0CfsRty+jYG12KGAVKqi2+fEBE5wh6RiIiIiIhoEcuN7EKvEtCFqruMVAKjI7vQv/pjAbaMXGOAlCzw7RMiIme0sBtARERERERE4THy45Cok4ZeIiFg5MeDaRA1bE6AVFNIahK6piBEOUC6PewmUojKb59olm+fZINtGBFRhDGITkREREREtIjpyU5oqJ+FDgAaFPRkZzANooYwQEpWciO7IJXFwJkSyI3sCqhFRETRxyA6ERERERHRIpZeuQGaSSkXANCEQnrlhoBaRI1ggJSsxOntEzmdRWZ4Bw4NbUdmeAcHf4goNCyCRkREREREtIhpbX3I6INI18lelgrI6YPo54SUsVAOkOombxdEJUBK4dCTndAKEX/7hHX9iShimIlORERERES0yPWv2YycPgilAEMK5KUGQwqocgB9zeawm0g2sTwPWYnD2yes609EURNqEP2JJ57ApZdeio6ODnR0dGBwcBA//vGPKz9XSuELX/gCli9fjvb2drz//e/Hr3/96znrmJmZwX333Yeenh4sWbIEt9xyC0ZGRuYsMzY2hk2bNiGVSiGVSmHTpk0YHx8PYhOJiIiIiIiiTyTQv/ZeqNVbMdq+EbnENRht3wi1eiv6197LjM8YiUOAlMKltfUhqw9C1jlNpAKy+iC0kN4+YV1/IoqiUIPoK1euxJ//+Z/jlVdewSuvvIJrr70WH/rQhyqB8sceewxbt27Ftm3b8K//+q/o7+/HBz7wAZw4caKyjvvvvx9PPfUUduzYgZ/97Gc4efIkNm7cCMMwKsvccccd2LdvH3bu3ImdO3di37592LRpU+DbS0REREREFGVaWx/6V38MK9ZuRv/qj4UWRCP3oh4gpeDVqise5bdPWNefiKJIKKXMh6gD1tXVhS996Uv4wz/8Qyxfvhz3338//viP/xhAMeu8r68PX/ziF/HJT34SExMT6O3txfe+9z189KMfBQAcPnwYq1atwrPPPosbb7wRQ0NDuOiii7Bnzx6sX78eALBnzx4MDg5i//79uPDCC221a3JyEqlUChMTE+jo6PBn44mIiIiIiByQ01nkRnbByI9DT3YWs5AZHKWqetKyXE8aCppQyLKe9OJh4zyQM8ci14ccGtqOdOHnSGqy7jJ5qSGXuAYr1rLUlBXeJ4i8EZm7pmEY+Nu//VucOnUKg4ODOHDgADKZDG644YbKMq2trXjf+96HF198EZ/85Cexd+9e5PP5OcssX74cl1xyCV588UXceOON2L17N1KpVCWADgBXX301UqkUXnzxxbpB9JmZGczMzFT+Pjk56cNWExERERERucBJ98hMqTyPnL4No/OCZ5wgdvGYU1dcqDmTzRbrigP9a+9F/+qPhdjKhWIx8Wkc8D5B5KnQJxZ97bXXcPbZZ6O1tRWbN2/GU089hYsuugiZTAYA0Nc39wbf19dX+Vkmk0FLSwuWLVtmukw6nV7wuel0urJMLY8++milhnoqlcKqVasa2k4iIiIiIiKvcNI9soPleRavONcVZ11/b/A+QeSt0IPoF154Ifbt24c9e/bgv/7X/4qPf/zj+M1vflP5uRBze3yl1IJ/m2/+MrWWt1rP5z//eUxMTFT+HDx40O4mERERERER+SbOwTEiCkac64qzrn/jeJ8g8l7oQfSWlhasXr0aV155JR599FG8853vxF/8xV+gv78fABZki+dyuUp2en9/P2ZnZzE2Nma6TDa7sFMYHR1dkOVerbW1FR0dHXP+EBERERERhS3OwTEiCoaRH4eERT8BASM/HkyDHIryxKdxwPsEkfdCD6LPp5TCzMwMzjvvPPT39+O5556r/Gx2dhY//elP8e53vxsAcMUVVyCZTM5Z5siRI/jVr35VWWZwcBATExN4+eWXK8u89NJLmJiYqCxDREREREQUF3EPjhGR//RkJzTEuK54qa6/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Skp4MSfKEdY/otxg3SPKHdY/otxh/SPKDdY9osHDhUWJiIiIiIiIiIiIiGwwiE5EREREREREREREZINBdApcfn4+fvzjHyM/Pz/XRSEacVj/iHKDdY8od1j/iHKH9Y8oN1j3iAYfFxYlIiIiIiIiIiIiIrLBkehERERERERERERERDYYRCciIiIiIiIiIiIissEgOhERERERERERERGRDQbRiYiIiIiIiIiIiIhsMIhOgfqnf/onTJgwAQUFBRg7diwuvvhiNDY2Jr1mx44dOPvss1FcXIzKykosWbIEPT09OSox0dC3fft2XHrppZg8eTIKCwtx5JFH4sc//vGAesW6R5Qdt9xyC0466SQUFRVhzJgxaV/D+keUHatXr8bkyZNRUFCAOXPm4NVXX811kYiGnVdeeQVnn3026urqIITAE088kfR7KSWWL1+Ouro6FBYWYt68efjggw9yU1iiYea2227DCSecgNGjR6O6uhqLFi3Cli1bkl7DOkg0OBhEp0DNnz8fjz76KLZs2YLHH38c27Ztw9e+9jXr94Zh4Ctf+Qo6Ozvx2muv4eGHH8bjjz+Of/3Xf81hqYmGto8++gimaWLNmjX44IMPsGrVKtx777248cYbrdew7hFlT09PD8477zx897vfTft71j+i7HjkkUewdOlS/OAHP8CGDRvw93//9zjrrLOwY8eOXBeNaFjp7OzEF7/4Rdx9991pf3/HHXdg5cqVuPvuu/HOO++gtrYWp59+Og4cODDIJSUaftatW4crr7wSb775Jl544QX09vbijDPOQGdnp/Ua1kGiwSGklDLXhaDh66mnnsKiRYsQiUQQDofxpz/9CQsXLsTOnTtRV1cHAHj44YdxySWXoLW1FSUlJTkuMdHwcOedd+Kee+7Bp59+CgCse0SDYO3atVi6dCn27duX9HPWP6LsmDt3LmbPno177rnH+tm0adOwaNEi3HbbbTksGdHwJYTAH//4RyxatAhAbARsXV0dli5dihtuuAEAEIlEUFNTg9tvvx3f+c53clhaouFn9+7dqK6uxrp163DyySezDhINIo5Ep6xpb2/Hf//3f+Okk05COBwGALzxxhuYMWOGFUQAgAULFiASiWD9+vW5KirRsLN//36Ul5db/2bdI8od1j+i4PX09GD9+vU444wzkn5+xhln4PXXX89RqYhGns8++wzNzc1JdTE/Px+nnHIK6yJRFuzfvx8ArGc91kGiwcMgOgXuhhtuQHFxMSoqKrBjxw48+eST1u+am5tRU1OT9PqysjLk5eWhubl5sItKNCxt27YNv/jFL3DFFVdYP2PdI8od1j+i4LW1tcEwjAF1q6amhvWKaBDF6xvrIlH2SSlx3XXX4ctf/jJmzJgBgHWQaDAxiE6uli9fDiGE43/vvvuu9frrr78eGzZswJ///Gfouo5vfOMbSMwaJIQYsA0pZdqfE41kXuseADQ2NuLMM8/Eeeedh8suuyzpd6x7ROr81D8nrH9E2ZFah1iviHKDdZEo+6666iq8//77eOihhwb8jnWQKPtCuS4AHf6uuuoqXHDBBY6vmTRpkvX3yspKVFZWYurUqZg2bRrq6+vx5ptvoqGhAbW1tXjrrbeS3rt3715Eo9EBPadEI53XutfY2Ij58+ejoaEBv/zlL5Nex7pH5I3X+ueE9Y8oeJWVldB1fcAou9bWVtYrokFUW1sLIDYaduzYsdbPWReJgnX11VfjqaeewiuvvILx48dbP2cdJBo8DKKTq3hQ3I/4CPRIJAIAaGhowC233IKmpibrAv/nP/8Z+fn5mDNnTjAFJhomvNS9Xbt2Yf78+ZgzZw7uv/9+aFryRCPWPSJvMrn3pWL9IwpeXl4e5syZgxdeeAHnnnuu9fMXXngB55xzTg5LRjSyTJ48GbW1tXjhhRdw3HHHAYitWbBu3TrcfvvtOS4d0dAnpcTVV1+NP/7xj3j55ZcxefLkpN+zDhINHgbRKTBvv/023n77bXz5y19GWVkZPv30U/zoRz/CkUceiYaGBgCxxZ6mT5+Oiy++GHfeeSfa29uxbNkyXH755SgpKcnxNyAamhobGzFv3jxMmDABK1aswO7du63fxUcmsO4RZc+OHTvQ3t6OHTt2wDAMbNy4EQAwZcoUjBo1ivWPKEuuu+46XHzxxTj++OOtWVg7duxIWhOEiDJ38OBBbN261fr3Z599ho0bN6K8vBwTJkzA0qVLceutt+Koo47CUUcdhVtvvRVFRUW48MILc1hqouHhyiuvxO9+9zs8+eSTGD16tDUDq7S0FIWFhRBCsA4SDRIhE5NVE2Vg06ZNuOaaa/DXv/4VnZ2dGDt2LM4880z8x3/8B8aNG2e9bseOHfje976HF198EYWFhbjwwguxYsUK5Ofn57D0REPX2rVr8a1vfSvt7xIv8ax7RNlxySWX4IEHHhjw85deegnz5s0DwPpHlC2rV6/GHXfcgaamJsyYMQOrVq3CySefnOtiEQ0rL7/8MubPnz/g59/85jexdu1aSClx0003Yc2aNdi7dy/mzp2L//qv/7IWPiQi/+zymt9///245JJLAIB1kGiQMIhORERERERERERERGRDc38JEREREREREREREdHIxCA6EREREREREREREZENBtGJiIiIiIiIiIiIiGwwiE5EREREREREREREZINBdCIiIiIiIiIiIiIiGwyiExERERERERERERHZYBCdiIiIiIiIiIiIiMgGg+hERERERERERERERDYYRCciIiIiOoy9/PLLEEJg3759uS4KEREREdGIxCA6EREREQ07l1xyCYQQEEIgHA6jpqYGp59+On7zm9/ANM2cluWII47AsmXL0NnZqfT+k046CU1NTSgtLfW0zUWLFjm+Jl4mu/8uueQS5e0NFfPmzcPSpUtzXQwiIiIiGmJCuS4AEREREVE2nHnmmbj//vthGAZaWlrw3HPP4ZprrsHvf/97PPXUUwiFBq8pHC9LNBrFq6++issuuwydnZ245557XN+bl5eH2trawMvU1NRk/f2RRx7Bj370I2zZssX6WWFhYeDbzJZoNIpwODxst0dEREREucWR6EREREQ0LOXn56O2thbjxo3D7NmzceONN+LJJ5/En/70J6xdu9Z63f79+/Htb38b1dXVKCkpwamnnoq//vWv1u90Xcf69esBAFJKlJeX44QTTrDe/9BDD2Hs2LFKZamvr8eFF16Iiy66CE888QQAIBKJYMmSJaiurkZBQQG+/OUv45133rHem5rOZe3atRgzZgyef/55TJs2DaNGjcKZZ55pBcWXL1+OBx54AE8++aQ1qvzll18eUKba2lrrv9LSUgghkn72yiuvYM6cOSgoKMARRxyBm266Cb29vdb7hRBYs2YNFi5ciKKiIkybNg1vvPEGtm7dinnz5qG4uBgNDQ3Ytm2b9Z7ly5dj1qxZWLNmDerr61FUVITzzjtvQKqa+++/H9OmTUNBQQGOOeYYrF692vrd9u3bIYTAo48+innz5qGgoAC//e1vsWfPHvzzP/8zxo8fj6KiIsycORMPPfSQ9b5LLrkE69atw1133WXtl+3bt1v7M9ETTzwBIcSAcv/mN7/BEUccgfz8fEgpHc8dIiIiIho+GEQnIiIiohHj1FNPxRe/+EX84Q9/ABALin/lK19Bc3Mznn32Waxfvx6zZ8/Gaaedhvb2dpSWlmLWrFlWEPr999+3/uzo6AAQC3KfcsopnspRWFiIaDQKAPi3f/s3PP7443jggQfw3nvvYcqUKViwYAHa29tt33/o0CGsWLECDz74IF555RXs2LEDy5YtAwAsW7YM559/vhVYb2pqwkknneSpfM8//zy+/vWvY8mSJfjwww+xZs0arF27FrfcckvS626++WZ84xvfwMaNG3HMMcfgwgsvxHe+8x38+7//O959910AwFVXXZX0nq1bt+LRRx/F008/jeeeew4bN27ElVdeaf3+vvvuww9+8APccsst2Lx5M2699Vb88Ic/xAMPPJD0OTfccAOWLFmCzZs3Y8GCBeju7sacOXPwzDPP4P/+7//w7W9/GxdffDHeeustAMBdd92FhoYGXH755dZ+qa+vV94n8XI//vjj2LhxIwA4njtERERENHwwiE5EREREI8oxxxyD7du3AwBeeuklbNq0CY899hiOP/54HHXUUVixYgXGjBmD3//+9wBiebTjQfSXX34Zp512GmbMmIHXXnvN+tm8efOUt//222/jd7/7HU477TQrpcudd96Js846C9OnT8d9992HwsJC/PrXv7b9jGg0invvvRfHH388Zs+ejauuugp/+ctfAACjRo1CYWGhNfq9trYWeXl5nvbRLbfcgu9///v45je/iSOOOAKnn346br75ZqxZsybpdd/61rdw/vnnY+rUqbjhhhuwfft2XHTRRViwYAGmTZuGa665ZsAo+O7ubjzwwAOYNWsWTj75ZPziF7/Aww8/jObmZgCxwPxPf/pTLF68GJMnT8bixYtx7bXXDtj20qVLrdfU1dVh3LhxWLZsGWbNmoUjjjgCV199NRYsWIDHHnsMAFBaWoq8vDwUFRVZ+0XXdeV90tPTgwcffBDHHXccvvCFLyidO0REREQ0PDAnOhERERGNKFJKK1XH+vXrcfDgQVRUVCS9pqury0pDMm/ePPz617+GaZpYt24dTjvtNEyYMAHr1q3D7Nmz8fHHH7uORH/mmWcwatQo9Pb2IhqN4pxzzsEvfvELbNu2DdFoFF/60pes14bDYfzd3/0dNm/ebPt5RUVFOPLII61/jx07Fq2trZ73hZ3169fjnXfeSRp5bhgGuru7cejQIRQVFQEAvvCFL1i/r6mpAQDMnDkz6Wfd3d3o6OhASUkJAGDChAkYP3689ZqGhgaYpoktW7ZA13Xs3LkTl156KS6//HLrNb29vQMWVj3++OOT/m0YBn7yk5/gkUcewa5duxCJRBCJRFBcXJzp7gAATJw4EVVVVda/Vc4dIiIiIhoeGEQnIiIiohFl8+bNmDx5MgDANE2MHTs2bc7weJ7sk08+GQcOHMB7772HV199FTfffDPq6+tx6623YtasWaiursa0adMctzl//nzcc889CIfDqKursxaljOcxT8y/DSQH+tNJXdRSCAEppWMZvDBNEzfddBMWL1484HcFBQVpyxEvb7qfmaZpu634a4QQ1uvuu+8+zJ07N+l1qaPGU4PjP/3pT7Fq1Sr87Gc/w8yZM1FcXIylS5eip6fH/osC0DRtwL6Lp9px2p7KuUNEREREwwOD6EREREQ0Yrz44ovYtGkTrr32WgDA7Nmz0dzcjFAohEmTJqV9Tzwv+t133w0hBKZPn466ujps2LABzzzzjFI+9OLiYkyZMmXAz6dMmYK8vDy89tpruPDCCwHEArjvvvsuli5d6vt75uXlwTAM3++fPXs2tmzZkrbMmdqxYwcaGxtRV1cHAHjjjTegaRqmTp2KmpoajBs3Dp9++ikuuugiT5/76quv4pxzzsHXv/51ALEg9yeffJLUwZFuv1RVVeHAgQPo7Oy0AuXxnOdOVM4dIiIiIhoeGEQnIiIiomEpEomgubkZhmGgpaUFzz33HG677TYsXLgQ3/jGNwAA//AP/4CGhgYsWrQIt99+O44++mg0Njbi2WefxaJFi6yUIfPmzcNdd92Fc889F0IIlJWVYfr06XjkkUfw85//3HcZi4uL8d3vfhfXX389ysvLMWHCBNxxxx04dOgQLr30Ut+fO2nSJDz//PPYsmULKioqUFpaOmD0upMf/ehHWLhwIerr63HeeedB0zS8//772LRpE/7zP//Td7mA2Ej2b37zm1ixYgU6OjqwZMkSnH/++aitrQUALF++HEuWLEFJSQnOOussRCIRvPvuu9i7dy+uu+4628+dMmUKHn/8cbz++usoKyvDypUr0dzcnBREnzRpEt566y1s374do0aNQnl5OebOnYuioiLceOONuPrqq/H2229j7dq1rt9D9dwhIiIioqGPC4sSERER0bD03HPPYezYsZg0aRLOPPNMvPTSS/j5z3+OJ5980koNIoTAs88+i5NPPhn/8i//gqlTp+KCCy7A9u3brRzfQCwdi2EYSQuInnLKKTAMQ2kkupOf/OQn+OpXv4qLL74Ys2fPxtatW/H888+jrKzM92defvnlOProo3H88cejqqoK//u//+vp/QsWLMAzzzyDF154ASeccAJOPPFErFy5EhMnTvRdprgpU6Zg8eLF+Md//EecccYZmDFjBlavXm39/rLLLsOvfvUrrF27FjNnzsQpp5yCtWvXWil47Pzwhz/E7NmzsWDBAsybNw+1tbVYtGhR0muWLVsGXdcxffp0VFVVYceOHSgvL8dvf/tbPPvss5g5cyYeeughLF++3PV7qJ47RERERDT0CRlk8kQiIiIiIiIby5cvxxNPPKGULoWIiIiI6HDBkehERERERERERERERDYYRCciIiIiIiIiIiIissF0LkRERERERERERERENjgSnYiIiIiIiIiIiIjIBoPoREREREREREREREQ2GEQnIiIiIiIiIiIiIrLBIDoRERERERERERERkQ0G0YmIiIiIiIiIiIiIbDCITkRERERERERERERkg0F0IiIiIiIiIiIiIiIbDKITEREREREREREREdn4/78Orj94PR2/AAAAAElFTkSuQmCC"/>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=c7388bc4">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h3> Dew Point Temperature vs. Rentals</h3><br/>
<p>Dew Point Temperature indicates how warm and humid the air is, leading to more or less comfort, depending on the temperature. The point of -30 indicates colder, drier days, while the other edge, 30, indicates more moisture and more warmth. Translating this extreme to an average, a comfortable Dew Point temperature would be from 5 to 20 degrees.</p>
<p>It is possible to observe that users tend to prefer more humid days than dry days, this happens because warmer weathers tend to be more humid too, and our users already have a strong preference for warmer days. This can be showcased by the rentals outliers, mainly the ones above 2500, who are positioned around 5 to 20 degrees.</p>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell" id="cell-id=fc53e117">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In [13]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
<div class="cm-editor cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># creating scatter plot for moderate relationship variables</span>
<span class="n">sns</span><span class="o">.</span><span class="n">scatterplot</span><span class="p">(</span><span class="n">x</span> <span class="o">=</span> <span class="s1">'Humidity'</span>    <span class="p">,</span>
                <span class="n">y</span> <span class="o">=</span> <span class="s1">'Rentals'</span>     <span class="p">,</span>
                <span class="n">hue</span> <span class="o">=</span> <span class="s1">'Visibility'</span><span class="p">,</span>
                <span class="n">palette</span><span class="o">=</span><span class="s1">'coolwarm'</span><span class="p">,</span>
               <span class="n">data</span> <span class="o">=</span> <span class="n">bikes_data</span><span class="p">)</span>

<span class="c1"># adding and personalizing reference lines</span>
<span class="n">plt</span><span class="o">.</span><span class="n">axvline</span><span class="p">(</span><span class="n">x</span> <span class="o">=</span> <span class="mi">40</span><span class="p">,</span> <span class="n">color</span> <span class="o">=</span> <span class="s1">'green'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">axvline</span><span class="p">(</span><span class="n">x</span> <span class="o">=</span> <span class="mi">60</span><span class="p">,</span> <span class="n">color</span> <span class="o">=</span> <span class="s1">'green'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">axvline</span><span class="p">(</span><span class="n">x</span> <span class="o">=</span> <span class="mi">80</span><span class="p">,</span> <span class="n">color</span> <span class="o">=</span> <span class="s1">'green'</span><span class="p">)</span>
</pre></div>
</div>
</div>
</div>
</div>
<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>
<div class="jp-OutputArea jp-Cell-outputArea">
<div class="jp-OutputArea-child jp-OutputArea-executeResult">
<div class="jp-OutputPrompt jp-OutputArea-prompt">Out[13]:</div>
<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain" tabindex="0">
<pre>&lt;matplotlib.lines.Line2D at 0x274cbe13a10&gt;</pre>
</div>
</div>
<div class="jp-OutputArea-child">
<div class="jp-OutputPrompt jp-OutputArea-prompt"></div>
<div class="jp-RenderedImage jp-OutputArea-output" tabindex="0">
<img alt="No description has been provided for this image" class="" src="data:image/png;base64,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gsEgV1xxBampqTgcDk444QRKS0t/Uj+EKBLslblz53LZZZexaNEi5syZQyQSYfLkybS2tsbb3HfffTz00EM8/vjjLF26lMzMTI466iiam5v3Y89/WyxdupRnn32WIUOGJCwXY7P/qK+vZ/z48Wiaxqeffsq6det48MEH8Xq98TZifPYf9957L08//TSPP/4469ev57777uP+++/nsccei7cR4/Pr0draytChQ3n88ce7XL8vY3H11Vfz/vvv89ZbbzF//nxaWlqYOnUq0ehPKOprCgQ/gaqqKhMw586da5qmaRqGYWZmZpr33HNPvE0gEDA9Ho/59NNP769u/qZobm42e/fubc6ZM8ecNGmSedVVV5mmKcZmf3P99debEyZM6Ha9GJ/9y3HHHWdecMEFCcumTZtmnnvuuaZpivHZnwDm+++/H/+8L2PR0NBgappmvvXWW/E2ZWVlpizL5meffbbPxxaWIsFPorGxEYDk5GQAiouLqaioYPLkyfE2uq4zadIkvv/++/3Sx98al112GccddxxHHnlkwnIxNvuXf//734waNYrTTjuN9PR0hg8fznPPPRdfL8Zn/zJhwgS++uorNm3aBMDKlSuZP38+xx57LCDG50BiX8Zi2bJlhMPhhDbZ2dkMGjToJ42XKAgr2GdM0+Saa65hwoQJDBo0CICKigoAMjIyEtpmZGSwY8eOX72PvzXeeustfvzxR5YuXdppnRib/cu2bdt46qmnuOaaa7jppptYsmQJV155Jbqu87vf/U6Mz37m+uuvp7GxkX79+qEoCtFolDvvvJOzzjoLEPfPgcS+jEVFRQUWi4WkpKRObXZvvy8IUSTYZy6//HJWrVrF/PnzO62TJCnhs2manZYJfl5KSkq46qqr+OKLL7Bard22E2OzfzAMg1GjRnHXXXcBMHz4cNauXctTTz3F7373u3g7MT77h7fffpvXXnuNN954g4EDB7JixQquvvpqsrOzmT59erydGJ8Dh/9mLH7qeInpM8E+ccUVV/Dvf/+bb775htzc3PjyzMxMgE5KvKqqqpOqF/y8LFu2jKqqKkaOHImqqqiqyty5c3n00UdRVTV+/sXY7B+ysrIYMGBAwrL+/fuzc+dOQNw7+5s//elP3HDDDZx55pkMHjyY8847jz/+8Y/cfffdgBifA4l9GYvMzExCoRD19fXdttkXhCgS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"/>
</div>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=32b883d6">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h3>Humidity &amp; Visibility vs. Rentals</h3>
<p>Humidity and Visibility have a moderate relationship with rentals. Although their impact is moderate, they still add significant value to the analysis. Hence, this scatter plot compares rental counts with humidity (x-axis) and visibility (color).</p>
<p>Our Dew Point Temperature visualization indicated that users have preference for warmer and moderate humid days.</p>
<p>Days with lower visibility (darker blues hues) tend to exhibit higher humidity, as evidenced by the clustering of darker blues in the last two areas. In contrast, days with better visibility are, generally, less humid.</p>
<p>When focusing on the peak rental days (y-axis), we can see that users tend to utilize the services during days with high visibility, with a slight preference for days with low to moderate humidity.</p>
<hr/>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell" id="cell-id=b283dc24">
<div class="jp-Cell-inputWrapper" tabindex="0">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput" data-mime-type="text/markdown">
<h2>Conclusion</h2><br/>
<p>The bike rental service faces impacts from different variables, varying from high to low relationships between them. The visuals and analysis allowed us to understand preferences and patterns in the customers behavior that can lead to better strategies to retain one-time users, fortify relationships with frequent users, and acquire new users.</p>
<p>Throughout the 7 visualizations, we were able to identify that customers are comfort-sensitive; they are motivated by favorable weather conditions that make riding bicycles a comfortable activity. Users are more likely to rent bikes during the summer season, when its warm and sunny, with better visibility and moderate humidity.</p>
<p>Data also illustrates that riders tend to utilize the vehicle during commute hours, implying that most users rent bikes to commute, which provides the company with the information necessary to generate promotions and allocate the amount of bikes necessary to attend demand.</p>
</div>
</div>
</div>
</div>
</main>
</body>
</html>
