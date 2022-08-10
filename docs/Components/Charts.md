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
  
  
<details>
<summary>Merge multiple request time into once</summary>
MergeCallTimes: Since multiple Y-field request multiple times, merge multiple times as once could effectively avoid `CORS` error
</details>

#### Pie
- support users to check proportion of each sector with different color visualization

#### Scatter 
- smooth spline helps users check the trends of data selected 

&nbsp;

## External Package Used
#### MUI
[MUI](https://mui.com)

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

#### React-Plotly
- [React-Plotly](https://plotly.com/javascript/react/): The main package contain methods to connect with API and chart user-friendly data visualization result as React components



#### useWindowSize
- [useWindowSize](https://github.com/jaredLunde/react-hook/tree/master/packages/window-size#readme)



&nbsp;

## Functions


&nbsp;

## Customization
<details>
<summary>Customized Style</summary>

```js
function getStyles(name, chips, theme) {
    return {
      fontWeight:
        chips.indexOf(name) === -1
          ? theme.typography.fontWeightRegular
          : theme.typography.fontWeightMedium,
    };
  }
```
</details>
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