# Pivot table


&nbsp;

## Overview

A pivot table is a table of grouped values that aggregates the individual items of a more extensive table within one or more discrete categories. The summary include sums, averages, or other statistics (Normalized rows, normalized columns), which the pivot table groups together using a chosen aggregation function applied to the grouped values.


&nbsp;

## External package used
- [@mui/material/TableContainer](https://mui.com/material-ui/api/table-container/): used to create container for drawing tables.
- [@mui/material/Table](https://mui.com/material-ui/react-table/): used to render the elegant pivot table to display sets of data, which could be highly customized.


&nbsp;

## Props

|  Parameter Names     | Type | Functionality  |
| -------   |  --------------- |  --------------- |
| filter_object   |  object  |  An object with dictionary contained contraints specified by filter for visualizing data on Pivot table (e.g., group_by parameters, voyage ID ranges).  |
| dataset    |  Integer  | Specify which dataset to use (0 for trans-Atlantic, 1 for intra-America). |



&nbsp;

## Functions
|  Name     |   Functionality  |
| -------   |  --------------- |
| PivotTable   |  Generate drop down menus for column/row selection and which data to show in cell, render radio button for selecting aggregation function used, call the function "Pivot" to render the table according to selected columns/rows. |
| Pivot    |  Draw the Pivot Table according to params given by caller function "PivotTable" .  |
