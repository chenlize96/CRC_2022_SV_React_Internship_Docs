# Charts

## Overview 
The Chart part includes Scatter, Bar and Pie, which all implement with `MUI` for UI layout purpose and `React-Plotly` to wrap passing data as reuseable React components.

The chart compoent support features as following:
#### General Features
- data interactivable plotly graph
- data visualization of Django API data
- dropdown menu of select fields and radio button of aggregation function
- multiselct of y field in bar chart and enable/ disable by clicking in select field or the colored blocks 
- real time changing names of title, y-axis and x-axis

#### Bar
- supports fetching multiple y-axis data and representing results side by side with different color

#### Pie
- support users to check proportion of each sector with different color visualization

#### Scatter 
- smooth spline helps users check the trends of data selected 

&nbsp;

## External Package Used
#### MUI
- [Material UI](https://mui.com)

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
        |___VoyageBar.js
        |___VoyagePie.js
        |___VoyageScatter.js
```