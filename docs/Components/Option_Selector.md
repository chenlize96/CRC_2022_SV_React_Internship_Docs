# Option Selector

## Overview

The database we use is powerful, there are thousands of variable to describe one element. 
It support vary detail information, but also make the data complex for developer.
Option Selector is a developer tool to deal with is problem. 

## Use Case

#### 0. open Option Selector

Go to the endpoint `/optionSelector`

#### 1. Variable tree:
The data for one element we get from database is an js object.
User can see all the variable key in a hierarchical dropdown tree menu 
at the left side of the page.
So that user can dive into the variable they want, 
and not been confused by thousands of variable.

#### 2. Change endpoint

User can input the endpoint in the input box and click set endpoint to change the endpoint.
The default endpoint is `voyage/`

The other supported endpoint is:

- Enslaved: `past/enslaved/`
- Enslavers: `past/enslavers/`
- Voyages: `voyage/`
- Places: `geo/`
- Estimates: `assessment/`

#### 3. Print data

User can input the id of the data and click PRINT button to print the data in console. 
So that user can see what the data look like.

#### 4. Select variable

User can click the check box on the left of the variable to select the variable. 
The selected variable will show as an input box with its variable name and flat label 
in the right side of the page.
You can change the flat label and click `X` button to de-selected them. 

This Use case is widely use in our project. 
Because the whatever the variable name and the origin flat label is very long,
and we like to custom them in a shorter version in dropdown, or table header.

#### 5. Export & Import

User can click the EXPORT button to export the selected variable as an json field. 
And user can click IMPORT button to import the other selected variable json field.

It is very useful when cooperate with the teammate. we use the variable tree too browse
the variable and discuss which variable we need then we can select the variables rename them,
export them and share with all the teammate.