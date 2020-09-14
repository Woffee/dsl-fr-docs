---
layout: default
title: Data types
parent: Tutorials
nav_order: 305
---


# Built-in Data types


### Basic types

| Type        | Description       
|:-------------|:------------------|
| bool  | Boolean values(true, false) | 
| float  | 64-bit floating point values   |
| int           | 64-bit signed integer values |
| string           | Array of Unicode characters      |

### Array types

Arrays are containers that hold values all of the same type. 

```
a1 = [7,8,9]
```

The indexes of the array are all integers, from the front to the back to increase from 0, like 0, 1, 2, 3... From the back to the front, they are negative, and decreases from -1, like -1, -2, -3 ...

```
v1 = a1[ 2 ]  # v1 will be 9
v2 = a1[ -1]  # v2 will also be 9
```

### Dictionary type

Dictionaries are containers that associate keys of a given type with values of another type. They are can grow dynamically.

	dic1 = {
		"filename": "car.png",
		"date": "Aug 23, 2020"
	}
	print filename of dic1  # will output "car.png"

### Set type

Sets are containers that only store the unique values they have seen. They are can grow dynamically. 

```
s1 = set of [ 1, 2, 2, 3]  # s1 will be [1,2,3] because duplicate elements will be ignored

```


### Domain specific types

 - `Image`

| Attribute        | Type    | Description       
|:-------------|:------------------|:---------|
| filename | string | filename of the image |
| date | datatime | create date of the image |
| tag | string | tag of the image |
| ... |  | other attributes defined by users |


- `DetectedObject`

| Attribute        | Type    | Description       
|:-------------|:------------------|:---------|
| label | string | name of the detected object |
| polygons | array of locations | the boundary of the detected object |
| model_used | string | the model used to detect the object |
| superclass | string | the superior category of the detected object |
| count | int | the number of detected objects in the image |

