---
layout: default
title: Detect objects
parent: Tutorials
nav_order: 310
---


# Detect objects

---


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
    




