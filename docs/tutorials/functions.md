---
layout: default
title: Functions
parent: Tutorials
nav_order: 307
---


# Functions


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
    return marked_images
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