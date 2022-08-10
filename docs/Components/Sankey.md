# People-sankey

## Overview
The People-sankey component is used for visualizing transaction information and relationship between enslaved people and enslavers. The visualization includes nodes of enslaved people, transaction and enslavers showing role of enslavers, type of transactions, detail information of voyages.

The People-sankey component support features including:

- clicked pop-over of Card component on enslaved people nodes
- mouseenter pop-over of age and height information on enslaved people nodes, voyages and transactions information including date, year, place and amount on transaction nodes.
- Voyage-modal component triggered by clickable voyage id button  

&nbsp;

## External Package Used
#### d3-sankey
- [d3-sankey](https://github.com/d3/d3-sankey)

&nbsp;

## Functions
|  Name     |   Functionality  |
| -------   |  --------------- |
| renderStory   |  render Card component on enslaved people nodes            |
| sankey    |  Draw the sankey graph using nodes list on the canvas                |

&nbsp;

## Customization
The style of canvas, nodes and links be set in `Style.css`.

&nbsp;

## Directory
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
