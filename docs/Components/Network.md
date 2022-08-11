# Network

## Overview

Network is a component used to display the network diagram of the relationship between enslaver, enslaved people, and voyage.
- red node: enslaved people
- green node: enslaver
- orange node: voyage
- bigger node: selected enslaver/enslaved people

You can hold mouse left key to drag the graph, you can use mouse wheel to zoom in and out.
You can drag the node, and double click the enslaver node or enslaved people node to browse the relation graph.
The selected people name is shown in the title, and it is isolated with other component. 
If you double click node to browse to other people's relation graph, 
it will change the selected people, but this change will not influence other component.
And when you go to other component and come back to network, the network will be reset.

---------------------------

## Use Case

User could select some people in PAST page table,
and click CONNECTION button and go to network tab to see the network.
Or click the chip in Enslaver Alias column in enslaved table,
or click the chip in Number Enslaved column in enslaver table,
and go to network tab to see the network.

-------------------

## props

#### selectedData:

Selected data is an Object to tell network the selected people's id and the type. 
It has three field: enslaver, enslaved, type. 
enslaver is an Array which contain all the selected enslaver's id, 
enslaved is the similar but the enslaved people's id.
type is a string which represent enslaver/enslaved which one is current target.
This design allow table to support deal with enslaver and enslaved at the same time.

#### width, height:

User can use these two props to customize the size of network component. 

______________

## Notification

Network can't support too many node, so if the total node is over 100, 
it will only show a part of the network. 
And inorder to avoid having too many node, 
user can only allow to select no more than 10 people.

The API sever will ben the client who sent too many request in a short time,
in order to prevent sending too many request,
we change the behavior of clicking the chip in the enslaver table, Number Enslaved column.
Originally, it will show all the relationship of the enslaved people.
It need to make a query of each enslaved people, and some enslaver have hundreds of enslaved people,
that will crash the page.
So now it will only show the relationship of the enslaver. 
Because all the enslaved people is connected to that enslaver, 
so the graph is similar, just it will ignore the relationship between enslaved people and other enslaver.