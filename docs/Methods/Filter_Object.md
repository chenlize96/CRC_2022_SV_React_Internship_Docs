# Filter Object

## Overview
Filter Object contains all the filters that have been created. The variables that are filtered on as well as their values will be stored in a dictionary and pass along to other components. When sending requests to the server, these filters will be applied and the result will be updated. 

&nbsp;

## Format
The filter object is a dictionary which contains the variables and their values, which looks like the following: 
```
{
    "id": [
        132469,
        786657
    ],
    "voyage_captainconnection__captain__name": [
        "Vaughan, Jason",
        "Allboy, John"
    ],
    "voyage_itinerary__imp_principal_port_slave_dis__geo_location__latitude": [
        -180,
        180
    ],
    "voyage_itinerary__imp_principal_port_slave_dis__geo_location__longitude": [
        -180,
        180
    ],
    "voyage_itinerary__imp_principal_place_of_slave_purchase__geo_location__latitude": [
        -17.017801825707558,
        15.752818536900337
    ],
    "voyage_itinerary__imp_principal_place_of_slave_purchase__geo_location__longitude": [
        -14.765625000000002,
        25.312500000000004
    ]
}
```
&nbsp;

## Usage
The filter object is usually applied when sending requests to the server. The variables and values in the filter object are appended as the request body and send to the server. The following is an exmaple: 
```
var data = new FormData();   //create variable for request body   

for (var property in filter_object) {           // append variables and values in filter object to request body
    filter_object[property].forEach((v) => {
    if(v.length != 0){
        data.append(property, v);
    }
    });
}

axois.post('url', data=data)    // send the request to endpoint
```
&nbsp;

## Declaration, Set & Delete
The filter object created being a `useState` hook, and pass along to other components. Being a Hook means changeing the filter object requires the function declared in the hook declaration. 

An example of filter object declaration looks like this:
```
const [filter_obj, set_filter_obj] = useState({})
```

Adding a new filter to the filter object looks like the following: 
```
set_filter_obj({ ...filter_obj, [key]: [values] })
```

Deleting an entry in the filter object looks like the following:
```
let temp = { ...filter_obj }
delete temp[key]
set_filter_obj(temp)
```