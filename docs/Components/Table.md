# Table
## Overview
<br>
The Table component is used for visualizing voyages/enslaved people/enslavers data from the database.
Based on different types of data, the Table component can show distinct features and functions. 

The Table component support features including:

### Common Features

- adjust the rows' density by clicking `DENSITY` button
- choose the columns required to demonstrate by selecting multiple fields when click `COLUMNS` button
- export/print the current table by clicking `EXPORT` button
- pagination: switch to different page & choose the rows shown per page
- sorting: sort the selected field in ascending`↑` or descending`↓` order or unsort

&nbsp;
## Voyage Table

- open the corresponding `Voyage Modal` when click the row
- open the `UV Modal` when click the hyperlink in `Documentary Sources` column

&nbsp;
## Enslaved Table

- select one or more rows to view the connections with `enslavers`
- switch to `ENSLAVER TABLE` OR `GALLERY`
- open the `Past Modal` when click the name in `Enslaver Alias` column
- open the `Voyage Modal` when click the voyage ID in `Transaction Voyage ID` column

&nbsp;

## Enslaver Table

- select one or more rows to view the connections with `enslaved people`
- switch to `ENSLAVED TABLE` OR `GALLERY`
- open the `Past Modal` when click the number in `Number Enslaved` column

&nbsp;

## Directory
The following directory shows all files related to Table. 
```
src
|___CommonComponent
    |___Table
        |___Cell.js
        |___ColumnSelector.js
        |___Table.js
        |___tableStyle.css
```
