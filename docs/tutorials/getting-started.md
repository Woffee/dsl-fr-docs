---
layout: default
title: Getting Started
parent: Tutorials
nav_order: 301
---


# Getting Started

---

## Hello-world

    print "Hello-world"

## Comments

Comments start with a #, and DSL-FR will ignore them:
    
    # this is a comment
    print "Hello-world"



## Types

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

<!-- ## Statements and Expressions -->

## Control Flow

 - `if-else`

```
if var1 > var2 
    ...
else if var1 < var2 
    ...
else
    ...

```



### Loops

 - `foreach`

```
foreach image in images
    ...
```

 - `repeat`

```
repeat 5 times
    ...
```


### Quantifiers

 - `exists`

As long as one image meets the condition, execute the following code.

```
exists img in images that img.contain(dog)
    ...
```



 - `ifall`

As long as one images meets the condition, execute the following code.

```
ifall img in images that img.contain(dog)
    ...
```






## Functions

- `function`

Functions in DSL-FR are similar with Ruby(a general programming language). When calling a function, the parentheses can be omitted. 

### Preposition parameters
{: .d-inline-block }

New
{: .label .label-green }

<!-- Similar with annotations. -->

When define a function, the main parameters are defined in parentheses after the function name. The remaining parameters are passed in as prepositions. 

The supported prepositions are `in`, `of`, `from`, `to`, `with`.

Multiple parameters are separated by commas.

For example, if a function is used to filter pictures within a specified time range, it can be defined as follows:

```
function filter( images )
    from : date1
    to : date2
    
    ... # filtering...

    return filtered_images
```

Then, you can call this function like this:

```
imgs = filter images from "Jan 1, 2020" to "Sept 1, 2020"
```





### Domain specific functions

 - `get()` 
 
 Get an attribute of an object.

```
function get( attr [, attr2...] ) of obj
    ...
    return attr
```


 - `select()` 

 Detect and return objects from images.

```
function select( obj_name [, obj_name2...] ) from images
    ...
    return objects
```
 
 
 - `mark()` 

 Identify objects from images and mark the boundaries of the objects.

```
function mark( obj_name [, obj_name2...] ) in images
    ...
    return images
```


### Other built-in functions

 - `calculate()`

Calculate some indicators of an object.

| Indicator        | Description       
|:-------------|:------------------|
| popularity  | The number of occurrences of an object per unit time | 
| visitation_rate  | The number of occurrences of the persons per unit time   |
| main_elements           | The main objects contained in the images |


```
function calculate( indicator ) of obj
    ...
    return value
```



## Modules

### User-defined modules

A module is composed of classes and methods. A module is composed of classes and functions. Write them into a file, and the file name (without extension) is the module name.



## Type extensions

DSL-FR provides an `extend` keyword that allows programmers to add and modify methods of various types at compile-time, including built-in types like `int` or `string`. 

```
extend image
    function save( filepath )
        ... # save image to the given filepath
```

## Aggregators

- `minimum`, `maximum`, `mean`

Aggregators are defined in the module "math".

```
import math

print math.maximum of [1,2,3]  # will output 3
```


## Visualizations

- `draw`

```
draw histogram with { 
    'x_axis': stats of persons
}

draw scatter_plot with { 
    'x_axis': stats of persons, 
    'y_axis': stats of smiles
}
```

## Pipelines
{: .d-inline-block }

New
{: .label .label-green }


### Basic Pipelne

For some research questions, we can subdivide each research question into small steps to solve it like a pipeline. In order to reduce intermediate calculations, we use keyword `pipeline` and symbol `|>` to abstract this process. A basic pipeline is as follows:

```
pipeline
    open "/paht/to/images" |> select smiles, persons |>
    draw scatter_plot with { 
        title:  "The relationship between the persons and smiles.",
        x_axis: persons,
        y_axis: smiles
    }

```

### Advanced Pipeline

For some complex research questions, we have a variety of tasks to deal with, but they are not related to each other, they can be processed in parallel. For such a pipeline containing multiple parallelizable processing tasks, we call it Advanced Pipelines. 

We use keyword `stage` to tag each task with a name. The result of each `stage` will be temporarily saved and can be used as the input of other tasks. For example:

```
pipeline
    stage s1
        open "/paht/to/images1" |> select smiles

    stage s2
        open "/paht/to/images2" |> select persons
    
    s1, s2 |>
        draw scatter_plot with { 
            title:  "The relationship between the persons and smiles.",
            x_axis: persons,
            y_axis: smiles
        }
```

## File operations

- `open`

Using built-in function `open`, we can open an image or the images in a folder by gicen a filepath.

```
image = open "car.png" 
    ... # do something with image

image = open "path/to/images/" 
    ... # do something with image
```


## Training a new model

TODO


## Debugging

TODO




    
    

    

    
