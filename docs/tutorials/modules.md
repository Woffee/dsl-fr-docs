---
layout: default
title: Class and module
parent: Tutorials
nav_order: 311
---

# Class and module

## Class

Defining a class in DSL-RF is similar with Python.

```
class Dog:
    kind = 'canine'         # class variable shared by all instances

    function __init__(self, name)
        self.name = name    # instance variable unique to each instance

    function eat(self)
        print "eating"

dog = Dog('Charlie')
print dog.kind       # will output 'canine'
print dog.name       # will output 'Charlie'
dog.eat()            # will output 'eating'
```


## Mudole

A module is composed of classes, functions and variables. Write them into a file, and the file name (without extension) is the module name.

Also similar with Python.

```
import math

print math.maximum of [ 1,2,3 ]
```