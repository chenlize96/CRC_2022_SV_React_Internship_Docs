# Flat_Files
Flat files are those static files which can be `.json` or `.js`. The purpose of making those flat_files is to set default value lists or customize menu variables. 

## Nested Variable-tree
The nested variable-tree files can be found at `src/Util/tableVars.js`,`src/PASTApp/EnslavedApp/vars.js`,`src/PASTApp/EnslaverApp/vars.js`. 

This is the example from tableVars.js. All of the nested Variable-tree are constructed in this format. The categories of vaiables can be customized. However, please make sure all the variables have been included in the options_flat file, so that the function can find the labels for each variables. 

functions identify the tail be recognizing the `null`, so please keep the `null`

```javascript
export const columnOptions = {
  "id": {
    "id": null,
  },
  "voyage_ownercrewandcaptain": {
    'voyage_shipownerconnection__owner__name': null,
    'voyage_captainconnection__captain__name': null,
    "voyage_crew": {
      'voyage_crew__crew_died_complete_voyage': null,
      'voyage_crew__crew_first_landing': null,
      'voyage_crew__crew_voyage_outset': null,
    },
  },
  "voyage_sourceconnection__text_ref": {
    'voyage_sourceconnection__text_ref': null,
  },
}
```

The categories of the top level cannot be omitted, and the Cascading will deal with this situatioin appropriately and seperately. 
```javascript
  "id": {
    "id": null,
  },
```
## Options_Flat
Options_flat file provides labels and types for variables. These options_flat files are produced by [Option_Selector](../Components/Option_Selector.md). Here is a shortcut for those files. And the pathes for each options_flat files are `src/VoyageApp/options.json`,`src/PASTApp/EnslavedApp/options.json`,`src/PASTApp/EnslaverApp/options.json`.

```javascript
{
  "dataset": {
    "type": "<class 'rest_framework.fields.IntegerField'>",
    "label": "Dataset",
    "flatlabel": "Dataset"
  },
  "last_update": {
    "type": "<class 'rest_framework.fields.DateTimeField'>",
    "label": "Last update",
    "flatlabel": "Last update"
  },
  "voyage_in_cd_rom": {
    "type": "<class 'rest_framework.fields.BooleanField'>",
    "label": "Voyage in 1999 CD-ROM?",
    "flatlabel": "Voyage in 1999 CD-ROM?"
  },
}
```

Be careful, for now, you cannot directly import the option_flat file to Option_Selector because there is an alien keys, for example 
```javascript
"personal_information": {
    "type": "table",
    "label": "Personal Information",
    "flatlabel": "Personal Information"
}
```
To import the file into Option_Selector, please delete it first, and add it to the option_flat files after you export new option_flat files.


## Other Default Settings 