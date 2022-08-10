# Autocomplete

## Overview
The Autocomplete component is used for making suggestions of search terms based on the current user input. It is used both at the past/ and voyage/ endpoint

The Autocomplete component support features including: 

- selecting multiple values from the autocomplete dropdown menu. 
- deleting selection or modifying text input 
- matching unusual characters like "ç"
- Update results based on the value of other filter components
- ambiguous matching

&nbsp;

## External Package Used
#### Leaflet
- [Material UI](https://mui.com)

&nbsp;

## Functions
|  Name     |   Functionality  |
| -------   |  --------------- |
| endpoint   |  Switch between past/ and voyage/ endpoint for fetch requests  |
| fetchData    |  Post request for fetching autocomplete dropdown menu options           |
| onChange    |  Resets search object each time user input is changed   |
| renderInput    | Displays user input in the search box and updates textInput for post request |


