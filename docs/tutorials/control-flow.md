---
layout: default
title: Control flow
parent: Tutorials
nav_order: 306
---


# Control flow

---

## Selection

### if-else

Equals: a == b
Not Equals: a != b
Less than: a < b
Less than or equal to: a <= b
Greater than: a > b
Greater than or equal to: a >= b

    if var1 > var2 then
        # do something
    else if var1 < var2 then
        # do something 
    else
        # do something
    end if

## Iteration

### foreach

    foreach img in imgs
        print size of img
    end foreach

### repeat

Repeat unlimited times:

    repeat
        # do something
    end repeat

Break from above:

    repeat
        if image_list is empty then
            break
        end if
        # do something
    end repeat

Repeat *n* times:

    repeat 5 times
        # do something
    end repeat



