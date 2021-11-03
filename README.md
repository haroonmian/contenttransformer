## Available Scripts

In the project directory, you can run:

### `npm install`

And then just run

### `npm start`

This app contains global store of useReducer and Context API with actions. Action file contains the exact requirement of project.

This App contains JSON text input for user and also a result text box in the bottome of JSON text input.
All operations should be performed according to below details.

Consider this simple JavaScript data structure (the "content") which consists of an array 
of objects. Each object has an "id" property. For example:

[{
		"id": "cat"
	},
	{
		"id": "frog"
	},
	{
		"id": "dog"
	},
	{
		"id": "horse"
	},
	{
		"id": "caribou"
	}
]

The ids in an instance of the "content" data structure are unique (and must remain so). 
For example, it would be an error to attempt to add a new object to the above array with 
an "id" of "cat".

A simple language is used to describe transformations which can be applied to the 
"content" data structure described above. Each transformation is an object with properties 
that describe how the content should be transformed. All transforms contain two common 
properties; "type" and "target". The "type" property determines the type of transformation 
to be performed. The "target" property determines the object in the data array to be 
transformed. An example transform is below:

{
    "type":"remove",
	"target": {
		"id": "cat"
	}
}

The target of a transform may be identified by its "id" (as above), or by its position in 
the array (zero-based). An example of this is below:

{
    "type":"move",
	"target": {
		"pos": "0"
	},
	"distance": 2
}

This transformation attempts to move the first item in the array forward by a distance of 
two places (so it will now be in third position in the array). If the distance would place 
the moved item outside the bounds of the array, then the move should "wrap around". For 
example, moving the first item in the array by a distance of -1 should place the item at 
the end of the array, and conversely moving the last item in the array by a distance of 1 
should place the item at the beginning of the array.

There are three types of transformation:

1. Remove

Delete the item identified by its "id" from the "data" array. See the examples below:

{
    "type":"remove",
	"target": {
		"id": "cat"
	}
}

2. Rename

Rename the item identified by its "id" to the value specified in the "newid" property.

{
	"type":"rename",
	"target": {
		"id": "horse"
	},
	"newid":"lion"
}

3. Move

Move the item identified by its current position forwards or backwards through the array 
by the specified distance (negative distance indicate moving backwards, positive distance 
indicates moving forward). 

{
	"type":"move",
	"target": {
		"pos": 2
	},
	"distance":-1
}

{
	"type":"move",
	"target": {
		"pos": 0
	},
	"distance":2
}

An array of transformations can be applied to content by iterating over the array and 
applying each transformation in order. Each transform should be applied only if it is 
"possible". If a transform cannot be applied, it should be ignored and the next transform 
should be processed. The list below specifies the situations in which each type of 
transformation should be ignored:

- Remove should be ignored if: 
	- no object with the specified id exists
- Rename should be ignored if: 
	- no object with the specified id exists
	- another object exists with the same id as "newid"
	
Implement (and test) a JavaScript/Typescript function called transform which takes a 
content array and a transformations array as parameters and returns the transformed 
content array. Your solution should take into account performance as well as good style 
and correctness. You may create helper functions and additional data structures in your 
implementation if you find them useful, but the transform function must return a valid 
content array as described above. You should be prepared to discuss your design in our 
next interview.

The function prototype and sample usage is supplied below:

function transform(content, transformations) {
	//To be implemented
}

let content = { /* ...*/ };
let trans = = { /* ...*/ };

let result = transform(content, trans);

An example content and a transformation list are provided for testing. You should create 
your own additional content and transformation lists to support you development and 
testing needs. You should pay attention to the correctness and performance of your 
solution.

Please provide a user interface using the web technology/framework of your choice 
to showcase the most appropriate way to present a visualisation of the 
pre- and post- state of the data, and provide users with a way to see how their 
transformation task has executed.


--------------------------------------

Semlr Confidential
------------------

The information contained in this file and its accompanying data files is confidential to 
Semlr Limited. The IP for all work contained in this file and the accompanying data files 
belongs to Semlr Limited. You are not permitted to post this content online, share or 
distribute the contents of these files in any form without written permission.
