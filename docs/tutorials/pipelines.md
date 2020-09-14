---
layout: default
title: Pipelines
parent: Tutorials
nav_order: 314
---

# Pipelines
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