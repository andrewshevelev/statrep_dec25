
# Introduction

## Published Research

Approach to Finding a Robust Deep Learning Model IEEE Access https://doi.org/10.1109/ACCESS.2025.3578926

## How Do We Define Robustness?
<!-- <v-clicks depth="3"> -->

* We propose an empirical definition:  
  * A model is called **robust** if the <!-- <span v-mark="{ at: 7, color: 'rgba(188, 13, 138, 0.66)', type: 'underline' }"> -->variation in quality <!-- </span>  -->among its different<!-- <span v-mark="{ at: 3, color: 'rgba(57, 147, 1, 1)', type: 'underline' }"> --> instances<!-- </span>  --> is minimal.
* What is model instance? 
  * All model instances have an identical set of hyperparameters but differ in their:
    * (internal) nondeterministic initial states and algorithms;
    * (external) training samples drawn from the same population.

<!-- * C1. By the definition above, any constant model would be absolutely robust.
  * Therefore, to find a practically useful robust model, we need to solve a dual optimization problem: to identify a robust model with the best average performance. -->

<!-- * С2. The robustness of a model depends on the robustness of the<!-- <span v-mark="{ at: 7, color: 'rgba(188, 13, 138, 0.15)', type: 'highlight' }"> -->
<!-- quality metric<!-- </span> used. -->
<!-- </v-clicks> -->



---
zoom: 0.85  
---

# Evaluating Robust Model Selection Algorithm on CIFAR-10

<div class="flex gap-8">
  <div class="flex-1">

- Dataset **CIFAR-10**:
    - 50k/10k train/validation samples.


- Base model:
    - [Benchopt](https://github.com/benchopt/benchopt)-optimized **ResNet-18** from [paperswithcode.com](paperswithcode.com) benchmark ([archived version](http://web.archive.org/web/20250405043955/https://paperswithcode.com/paper/benchopt-reproducible-efficient-and#code));
    - Validation accuracy: 95.55% while trained on augmented sample of 50k examples.


- Model search space generation:  
  - Created **72 variations** of the base model by adjusting training hyperparameters:  
    - Batch size / Maximum learning rate / L2 regularization parameter.


- Evaluation procedure:  
  - Applied the **Robust Model Selection Algorithm** to all 72 models<br> on **three different subsets** of the training data of sizes:
    - 10k, 20k, and 30k samples (for better model accuracy differentiation).

</div>
  <div class="w-40 flex items-center">
    <img src="/public/cifar10_example.png" class="h-full object-contain" />
  </div>
</div>



