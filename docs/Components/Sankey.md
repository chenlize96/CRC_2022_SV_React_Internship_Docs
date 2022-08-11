# Sankey

## People sankey

### Overview
The People-sankey component is used for visualizing transaction information and relationship between enslaved people and enslavers. The visualization includes nodes of enslaved people, transaction and enslavers showing role of enslavers, type of transactions, detail information of voyages.

The People-sankey component support features including:

- clicked pop-over of Card component on enslaved people nodes
- mouseenter pop-over of age and height information on enslaved people nodes, voyages and transactions information including date, year, place and amount on transaction nodes.
- Voyage-modal component triggered by clickable voyage id button  

&nbsp;

### External Package Used
##### d3-sankey
- [d3-sankey](https://github.com/d3/d3-sankey)

&nbsp;

### Functions
|  Name     |   Functionality  |
| -------   |  --------------- |
| renderStory   |  render Card component on enslaved people nodes            |
| sankey    |  Draw the sankey graph using nodes list on the canvas                |

&nbsp;

### Customization
The style of canvas, nodes and links be set in `Style.css`.

&nbsp;

### Directory
The following directory shows all files related to sankey. 
```
src
|
|___PASTApp
    |
    |___Component
        |
        |___Sankey.js
        |___styles.css
```
-----
## Map sankey
### Overview
The Map Sankey is used reflect the prople voyage flow between different sites with importing json data. It allows users interact with map by clicking an edge to get specific path on the map. Besides, if users wants to reset the sankey just click the button on the top of the sankey. In the Sankey file, `CircularSankey.js` is to defined the passing prop and drawing rules (this has been covered in `d3-sankey-circular`). `CircularExample.js` is about the fetching data, processing data as expected format (it will list as following quote box)

> Fetching data is not following the `d3-sankey` drawing style, we have to transfer as a ideal format as following
<details>
<summary>Fetching data & Nodes & Links</summary>

Fetching data
```
{
    "Africa": {
        "Africa": 168878,
        "Brazil": 3520059,
        "Caribbean": 5063754,
        "Europe": 9179,
        "Mainland North America": 365978,
        "Other": 190794,
        "Spanish Mainland Americas": 644166
    },
    "Brazil": {
        "Brazil": 96539,
        "Caribbean": 3970,
        "Mainland North America": 83,
        "Other": 37,
        "Spanish Mainland Americas": 54734
    },
    "Caribbean": {
        "Africa": 29,
        "Caribbean": 159258,
        "Mainland North America": 45570,
        "Other": 6679,
        "Spanish Mainland Americas": 121479
    },
    "Europe": {
        "Mainland North America": 30
    },
    "Mainland North America": {
        "Africa": 10,
        "Brazil": 2,
        "Caribbean": 7900,
        "Mainland North America": 67808
    },
    "Other": {
        "Brazil": 497,
        "Caribbean": 1182,
        "Mainland North America": 4615,
        "Other": 15,
        "Spanish Mainland Americas": 554
    },
    "Spanish Mainland Americas": {
        "Africa": 70,
        "Brazil": 1299,
        "Caribbean": 736,
        "Mainland North America": 10,
        "Spanish Mainland Americas": 1171
    }
}
```

Node

```
key: Integer
value: Object:{name: ___ , index: ___ , sourceLinks: ____ , targetLinks ____, value: ____, x0: ..., x1: ...., y0: ..., y1: ...}
```

```
0: {name: 'Africa', index: 0, sourceLinks: Array(7), targetLinks: Array(4), partOfCycle: true, …}
1: {name: 'Brazil', index: 1, sourceLinks: Array(5), targetLinks: Array(5), partOfCycle: true, …}
2: {name: 'Caribbean', index: 2, sourceLinks: Array(5), targetLinks: Array(6), partOfCycle: true, …}
3: {name: 'Europe', index: 3, sourceLinks: Array(1), targetLinks: Array(1), partOfCycle: false, …}
4: {name: 'Mainland North America', index: 4, sourceLinks: Array(4), targetLinks: Array(7), partOfCycle: true, …}
5: {name: 'Other', index: 5, sourceLinks: Array(5), targetLinks: Array(4), partOfCycle: true, …}
6: {name: 'Spanish Mainland Americas', index: 6, sourceLinks: Array(5), targetLinks: Array(5), partOfCycle: true, …}
```

Link
```
key: Integer
value: Object:{source: {Object}, target: {Object}, value: ..., width: ..., y0:..., y1:...} 
```

```
0: {source: {…}, target: {…}, value: 168878, index: 0, circular: true, …}
1: {source: {…}, target: {…}, value: 3520059, index: 1, circular: false, …}
2: {source: {…}, target: {…}, value: 5063754, index: 2, circular: false, …}
3: {source: {…}, target: {…}, value: 9179, index: 3, circular: false, …}
4: {source: {…}, target: {…}, value: 365978, index: 4, circular: false, …}
5: {source: {…}, target: {…}, value: 190794, index: 5, circular: false, …}
6: {source: {…}, target: {…}, value: 644166, index: 6, circular: false, …}
7: {source: {…}, target: {…}, value: 96539, index: 7, circular: true, …}
8: {source: {…}, target: {…}, value: 3970, index: 8, circular: false, …}
9: {source: {…}, target: {…}, value: 83, index: 9, circular: false, …}
10: {source: {…}, target: {…}, value: 37, index: 10, circular: false, …}
```
</details>


&nbsp;
### External Package Used
##### d3
- [d3](https://react-d3-library.github.io/)
- [d3-sacle](https://github.com/d3/d3-scale)
- [d3-shape](https://github.com/d3/d3-shape)
- [d3-sankey-circular](https://github.com/tomshanley/d3-sankey-circular)

##### visx
- [visx](https://airbnb.io/visx/)
<br>
This package is used to plot the verital and horizontal block (mainly for node blocks)

##### react-query
- [react-query](https://tanstack.com/query/v4)
<br>
This package is used to fetching, caching, synchronizing and updating server state

&nbsp;

### Functions
|  Name     |   Functionality  |
| -------   |  --------------- |
| Click Edge Lighten   |  render Card component on enslaved people nodes            |
|  Hover on Node    |  Lighten all edges which are connected with the hover node                |
| Connect with Map    |  Display the data which is related to the chosen edge                |


&nbsp;

### Directory
```
src
|
|___PASTApp
    |
    |___Component
        |___ mapping 
                |___sankey
                        |___CircularExample.js
                        |___CircularSankey.js
                        |___var.js
```
