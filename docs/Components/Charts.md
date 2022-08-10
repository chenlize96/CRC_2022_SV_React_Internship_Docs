# Chart


## Overview 
The Chart part includes Scatter, Bar and Pie, which all implement with `MUI` for UI layout purpose and `React-Plotly` to wrap passing data as reuseable React components.

The chart compoent support features as following:
#### General Plotly Features
- Data Visualization of Django API data
- Dropdown menu to select x, y and Aggregation function fields(for the pie plot: Sectors, Values and Aggregation function fields)
- Enable/ disable the y field for bar, value field by clicking the Colored blocks
- Real time changing title name, y-axis and x-axis
- Return error message once the plot fail to fetch data under the field selector
#### Scatter 
- Smooth Spline helps users check the trends of fetch data
  
#### Bar
- Supports fetching multiple y-axis data with multiple y-selector 
- Representing results side by side with different color to help users 


#### Pie
- Support users to check Proportion of each fetching result

&nbsp;

## External Package Used
#### MUI
[MUI]()
- Menu Part (Field Selecotr)
    - InputLabel
    - MenuItem
    - FormControl
    - Select 
    - Chip (to respresent choosen multiple y field single element)
    - Radio
  
- Error Message Alert
    - Alert Title
    - Alert  

- Layout
  - Box
  - Grid
  - 

#### React-Plotly
- [React-Plotly](https://plotly.com/javascript/react/): The main package contain methods to connect with API and chart user-friendly data visualization result as React components



#### useWindowSize
- [useWindowSize](https://github.com/jaredLunde/react-hook/tree/master/packages/window-size#readme)



&nbsp;

## Functions




&nbsp;


## Directory
```
src
|
|___VoyageApp
    |
    |___Component
        |VoyageScatter.js
        |___VoyageBar.js
        |___VoyagePie.js
```