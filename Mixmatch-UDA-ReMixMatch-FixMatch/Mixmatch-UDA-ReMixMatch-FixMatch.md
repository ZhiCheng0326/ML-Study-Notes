# MixMatch-UDA-ReMixMatch-FixMatch
## Introduction
1. Published timeline: MixMatch -> UDA -> ReMixMatch -> FixMatch  

2. Main techniques:
* Consistency regularization
* Entropy minimization

## Consistency Regularization
* Where and how to input noise?
  * Via Data Augmentation
  * Input noise at middle of training
  * Add noise at input pictures in the beginning
  * Modify the network structure (**Dropout**)  

* How to measure consistency?
  * KL Divergence
  * L2 Loss(more strict constraint according to the author of temporal ensembling)

## Entropy Minimization
When temperature=0, *temperature sharpening*=*Pseudo label*  

Pseudo label has simple implementation because it does not have *'temperature'* as hyperparameter.
### Methods of entropy minimization:
1. Temperature sharpening
* MixMatch
* UDA
* ReMixMatch

2. Pseudo label
* FixMatch

# Compare four of the SOTA Methods
For **entropy minimization** task:

![img1](mixmatch1.PNG)

For **consistency regularization** task:

![img2](mixmatch2.PNG)

Comparing **loss** for unlabeled data:

![img2](mixmatch3.PNG)

Methods to prevent overfitting in MixMatch and UDA:
1. MixMatch uses **mixup**
2. UDA uses **Training Signal Annealing(TSA)**

## Training Signal Annealing(TSA) $^{[2]}$
TSA prevents overfitting by **removing labeled samples that the model is already confident** about from the training set.

Specifically, examples are removed from the training set when the model's predicted probability of the correct class **exceeds a certain threshold**.

The threshold can be changed dynamically from $\frac{1}{K}$ to 1. This means only **towards the end** of training is the model allowed to **see every example** in the dataset.

This means that the model is **gradually allowed to become more confident** and see more examples = receive more training signal as training progresses, hence the term "Training Signal Annealing".



# FixMatch-The Winner
FixMatch simplify MixMatch, UDA and ReMixMatch and achieves better performance:
1. temperature sharpening -> pseudo label
2. cross entropy with threshold:  
 在计算 unlabeled loss 时，对 prediction 的 confidence 超过阈值的 unlabeled instance 才算入 unlabeled loss，这样使得 unlabeled loss 的权重可以固定


# Reference
[1][半监督学习MixMatch、UDA、ReMixMatch、FixMatch](https://www.cnblogs.com/wuliytTaotao/p/12727922.html#consistency-regularization)  
[2][mlexplained](https://mlexplained.com/2019/06/02/papers-dissected-mixmatch-a-holistic-approach-to-semi-supervised-learning-and-unsupervised-data-augmentation-explained/)
