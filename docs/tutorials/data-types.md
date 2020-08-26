---
layout: default
title: Data types
parent: Tutorials
nav_order: 305
---


# Built-in Data types


Text Type:	string

Numeric Types:	int, float

Sequence Types:	list

Mapping Type:	dict

Set Types:	set

Boolean Type:	bool


---

## Declaring Variables

    set price to 50000


## List

Initialize a list:

	set myList to ["a", "b", "c", "d", "e"]

Index starts from 1, so you can modify an element as follows:

	set item 2 of myList to "bb"
	# then myList is ["a", "bb", "c", "d", "e"]

Similarly, read an element:

	print item 2 of myList 
	# will output "bb"

Negative indexing means beginning from the end, -1 refers to the last item, -2 refers to the second last item etc.

	print item -1 of myList 
	# will output "e"


## Dictionary

	set dic1 to {
		"filename": "car.png",
		"date": "Aug 23, 2020"
	}
	print filename of dic1  # will output "car.png"


