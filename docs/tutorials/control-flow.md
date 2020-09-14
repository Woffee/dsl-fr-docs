---
layout: default
title: Control flow
parent: Tutorials
nav_order: 306
---


# Control flow

---

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



