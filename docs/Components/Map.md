# Map

## Overview
The Map component is used for visualizing voyages data on the map. The visualization includes ports and regions where the voyages begin and end, as well as the general routes each voyage goes. 

The Map component support features including: 

- full-screen mode
- zoom in and zoom out
- cluster / uncluster ports under different zoom levels
- when click on the places (nodes), display the total number of enslaved people whose voyages start from this place to other places, or voyages which end in this place that come from other places in a popup window
- when click on the routes (curves), display the aggregated number of enslaved people from all voyages that go through that segment of the route in a popup window

&nbsp;

## External Package Used
#### Leaflet
- [Leaflet.markercluster](https://github.com/Leaflet/Leaflet.markercluster): used to cluster / uncluster nodes under different zoom levels
- [Leaflet.curve](https://github.com/elfalem/Leaflet.curve): used to render the curves on the map

&nbsp;

## Functions
|  Name     |   Functionality  |
| -------   |  --------------- |
| ReadFeature   |  Receive routes and nodes information from server. Draw the clustered nodes on the map           |
| drawUpdate    |  Draw the curves on the map                |

&nbsp;

## Customization
The style of the nodes / clustered nodes can be set in `Style.css`. Use leaflet function `divIcon()` to create a customized icon and use it as the node icon.

The style of nodes and curves can also be set they are rendered when passed as parameters. 

&nbsp;

## Directory
The following directory shows all files related to map. 
```
src
|
|___VoyageApp
    |
    |___Component
        |
        |___mapping
        |       Spatial.js
        |       Style.css
        |
        |___VoyageMap.js
```
