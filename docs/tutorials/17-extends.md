---
layout: default
title: Type extensions
parent: Tutorials
nav_order: 317
---

# Type extensions

DSL-FR provides an `extend` keyword that allows programmers to add and modify methods of various types at compile-time, including built-in types like `int` or `string`. 

```
extend image
    function save( filepath )
        ... # save image to the given filepath
```
