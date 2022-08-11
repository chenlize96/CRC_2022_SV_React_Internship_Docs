# UVModal

## Overview

The UVModal component is an interface for visualizing IIIF manifest with the help of universal viewer and is used at the /documents endpoint and table component in /voyage endpoint.

It employs MUI components `Modal` and `Box` as a window container in front of the webpage embedding the universal viewer with entered URL of a IIIF manifest and supports features including:

- Trigger the full-screen mode
- Zoom In and Out of the image
- Rotate the image
- Download and share the image
- View the information of the image

&nbsp;
## External Components & Packages Used 
- [MUI Modal](https://mui.com/material-ui/api/modal/) 
- [MUI Box](https://mui.com/material-ui/api/box/)
- [Universal Viewer](https://github.com/UniversalViewer/universalviewer)

&nbsp;
## Props

|  Parameter Names | Functionality  |
| -------   |  --------------- |
| uvOpen    |  Specify whether to render the universal viewer modal in front of the webpage |
| setUVOpen |  Set the boolean value of uvOpen |
| url       |  Specify the url of IIIF manifest visualized by the universal viewer modal  |



&nbsp;
## Functions
|  Name     |   Functionality  |
| -------   |  --------------- |
| useUniversalViewer   |  Resize the universal viewer modal corresponding to the change of window size.   |
| UniversalViewer    |  Display the universal viwer with the entered url of IIIF manifest. |
| UVModal    |  Render the modal containing the universal viewer triggered by user. |


&nbsp;
## Directory
The following directory shows all files related to UVModal. 
```
src
|
|___CommonComponent
    |
    |___UVModal.js
```