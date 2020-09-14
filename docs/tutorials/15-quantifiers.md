---
layout: default
title: Quantifiers
parent: Tutorials
nav_order: 315
---

# Qipelines


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