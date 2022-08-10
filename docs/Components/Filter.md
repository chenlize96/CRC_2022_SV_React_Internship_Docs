# Filter

&nbsp;

## Overview
The Filter is used to filter the result based on user selection. Users can filter on variables of different types including numberic, text, or visual filters. For each type of variable, there are different filter components including range sliders, multi-selections with autocomplete, and bounding boxes on the map. These filters will carry along in the Voyage app and Past app and affect other components. This page will introduce these filters extensively.

&nbsp;

## Range Slider

The Range Slider is used for selecting value ranges for numberic values. The component uses MUI components `Slider` and `Input` and support features including: 

- setting the default range as minimum and maximum values of the variable selected
- drag the slider to change the range
- click on the slider bar to change the range
- enter values in the input boxes to change the range
- adjust the value to minimum or maximum when the value entered in the input box is out of range

An example Range Slider component looks like following: 

![Example Range Slider](./Slider.png)


### External Component Used 
- [MUI Slider](https://mui.com/material-ui/api/slider/) 
- [MUI Input](https://mui.com/material-ui/api/input/)


### Functions
|  Name     |   Functionality  |
| -------   |  --------------- |
|  GetSlider  |   Render range slider component based on the varibale selected       |
|  handleCommittedChange    |   Set the value when user drags the slider |
|   handleChange    | Set the value when user clicks on the slider bar  |
|   handleBlur  |  Handle the situation when the input value is out of range |

&nbsp;

## Auto Complete

### Overview
The Autocomplete component is used for making suggestions of search terms based on the current user input. It is used both at the past/ and voyage/ endpoint

The Autocomplete component support features including: 

- selecting multiple values from the autocomplete dropdown menu. 
- deleting selection or modifying text input 
- matching unusual characters like "ç"
- Update results based on the value of other filter components
- ambiguous matching

&nbsp;

### External Package Used
#### Leaflet
- [Material UI](https://mui.com)

&nbsp;

### Functions
|  Name     |   Functionality  |
| -------   |  --------------- |
| endpoint   |  Switch between past/ and voyage/ endpoint for fetch requests  |
| fetchData    |  Post request for fetching autocomplete dropdown menu options           |
| onChange    |  Resets search object each time user input is changed   |
| renderInput    | Displays user input in the search box and updates textInput for post request |

## Bounding Box

## Directory
```
src
|
|___CommonComponent
|   |
|   |___Filter
|       |
|       |___Autocomplete.js
|       |___Slider.js
|       |___ComponentFac.js
|
|___Component
    |
    |___BoundingBoxFilter.js
```




