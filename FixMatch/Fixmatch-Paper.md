# Notes on FixMatch Original Paper

## Abstract
1. FixMatch combines two methods, **consistency regularization** and **pseudo-labeling**
2. Steps:
-> weakly augmented unlabeled images
-> retain pseudo-labels if the $confidence\:level> threshold$
-> strongly augmented unlabeled images, predict its label

![fixmatch1](fixmatch1.PNG)
