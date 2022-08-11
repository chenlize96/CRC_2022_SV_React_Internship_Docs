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
You are free to set default variables for components. For example 
```javascript
export var bar_x_vars = [
  "voyage_ship__imputed_nationality__name",
  "voyage_ship__rig_of_vessel__name",
  "voyage_outcome__particular_outcome__name",
  "voyage_outcome__outcome_slaves__name",
  "voyage_outcome__outcome_owner__name",
  "voyage_outcome__vessel_captured_outcome__name",
  "voyage_outcome__resistance__name",
  "voyage_itinerary__imp_port_voyage_begin__geo_location__name",
  "voyage_itinerary__imp_region_voyage_begin__geo_location__name",
  "voyage_itinerary__imp_principal_place_of_slave_purchase__geo_location__name",
  "voyage_itinerary__imp_principal_region_of_slave_purchase__geo_location__name",
  "voyage_itinerary__imp_principal_port_slave_dis__geo_location__name",
  "voyage_itinerary__imp_principal_region_slave_dis__geo_location__name",
  "voyage_itinerary__imp_broad_region_slave_dis__geo_location__name",
  "voyage_itinerary__place_voyage_ended__geo_location__name",
  "voyage_itinerary__region_of_return__geo_location__name",
  "voyage_dates__imp_arrival_at_port_of_dis_yyyy",
];

export var bar_y_vars = [
  "voyage_dates__imp_length_home_to_disembark",
  "voyage_dates__length_middle_passage_days",
  "voyage_ship__tonnage_mod",
  "voyage_crew__crew_voyage_outset",
  "voyage_crew__crew_first_landing",
  "voyage_slaves_numbers__imp_total_num_slaves_embarked",
  "voyage_slaves_numbers__imp_total_num_slaves_disembarked",
  "voyage_slaves_numbers__imp_jamaican_cash_price",
];

Please find the correct file to edit, and keep them same formats. 
```

## Others
There are some utils not used. For example `hierFalse2True()`. You can use them to convert flat variables to a nested format.
for example: `hierFalse2True("voyage_itinerary__region_of_return__geo_location__name")` returns ->
```javascript
{
    "voyage_itinerary": {
        "voyage_itinerary__region_of_return:"{
            "voyage_itinerary__region_of_return__geo_location":{
                "voyage_itinerary__region_of_return__geo_location__name":null
            }
        }
    }
}
```