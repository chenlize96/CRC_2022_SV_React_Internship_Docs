# Chart


## Overview 
The Chart part includes Scatter, Bar and Pie, which all implement with `MUI` for UI layout purpose and `React-Plotly` to wrap passing data as reuseable React components.

The chart compoent support features as following:
#### General Plotly Features
- Data Visualization of Django API data
- Dropdown menu to select x, y and Aggregation function fields(for the pie plot: Sectors, Values and Aggregation function fields)
- Enable/ disable the y field for bar, value field by clicking the Colored blocks
- Real time changing title name, y-axis and x-axis

#### Scatter 
- Smooth Spline helps users check the trends of fetch data
- 

#### Bar
- Supports fetching multiple y-axis data and representing results side by side with different color


#### Pie
- Support users to check Proportion of each fetching result

&nbsp;

## External Package Used
#### MUI
- 

#### React-Plotly
- [React-Plotly](https://plotly.com/javascript/react/): The main package contain methods to connect with API and chart user-friendly data visualization result as React components







&nbsp;

## Functions





&nbsp;


## Customization




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