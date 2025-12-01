---
layout: statement
---

# Results
## Selection by algorithm


---

# Models Accuracy Distribution

<!-- <br><br> -->
<!-- <div style="display: flex; justify-content: center; align-items: center; height: 100%;">
    <figure>
        <img src="/accuracy_distribution2.png" style="width: 500px;">
    </figure>
</div> -->
<center>
<figure>
    <img src="/accuracy_distribution3.png" style="width: 900px !important;">
</figure>
</center>

<br>
<div class="grid grid-cols-[2fr_2fr_2fr] gap-5">
<div>

* Models: 72
</div>
<div>

* Instances: 20 
</div>
<div>

* Train sample: 30k examples
</div>
</div>

<!-- ---

# Algorithm Selection Steps

<div style="display: flex; justify-content: center; align-items: center; height: 100%;">
    <figure>
        <img src="/algo_select_steps_30k_k5.png" style="width: 640px;">
    </figure>
</div> -->


---

# Model Path in the Algorithm: Mean Accuracy
<center>
<figure>
    <img src="/model_path_mean_30k_k5_72_new.png" style="width: 760px !important;">
</figure>
</center>

<br>
<div class="grid grid-cols-[2fr_2fr_2fr] gap-5">
<div>

* Warmup steps = 3
</div>
<div>

* ⭐ - base model 
</div>
<div>

* Train sample: 30k examples
</div>
</div>

<!-- ---

# Model Path in the Algorithm: Mean Accuracy
<center>
<figure>
    <img src="/model_path_mean_20k.png" style="width: 740px !important;">
</figure>
</center>

<br>
<div class="grid grid-cols-[2fr_2fr_2fr] gap-5">
<div>

* Train sample: 20k examples
</div>
<div>

* Warmup steps = 3
</div>
<div>

* ⭐ - base model 
</div>
</div> -->




---

# Comparison with Grid Search

<br>

<center>
<figure>
    <img src="/confidence_level_by_mean.png" style="width: 550px !important;">
</figure>
</center>

<div class="grid grid-cols-[2fr_2fr_2fr] gap-5">
<div>

* Instances: 20
</div>
<div>

* Models: 72
</div>
<div>

* Train sample: 30k examples
</div>
</div>


---

# Model Path in the Algorithm: Std Accuracy
<center>
<figure>
    <img src="/model_path_std_30k_k5_72.png" style="width: 760px !important;">
</figure>
</center>

<br>
<div class="grid grid-cols-[2fr_2fr_2fr] gap-5">
<div>

* Train sample: 30k examples
</div>
<div>

* Warmup steps = 5
</div>
<div>

* ⭐ - base model 
</div>
</div>


---
level: 2
zoom: 1.1
---

# Conclusions

* We propose a procedure to measure the robustness of machine learning models.

* We supplement such a procedure with a meta-algorithm for robust model selection.

* We tested their approach on the data of the CIFAR 10

* Showed that our algorithm is more efficient than Grid Search

<!-- * The two robust models for two specific problems found using this method have the best convergence and the smallest loss variability among the $2\times6912$ models considered.
    * The models we found are more robust than the models selected by NAS from a similar search space.
    * ~ 8x speedup in training time is observed compared to an exhaustive search;
        * The total training time can be further reduced by using robust model search on subsamples. -->

<br>

##### A paper with this method has been published in the IEEE Access journal. DOI: [10.1109/ACCESS.2025.3578926](https://doi.org/10.1109/ACCESS.2025.3578926)


---

# Accuracy Overlap

<center>
<figure>
    <img src="/accuracy_overlap_models_1.png" style="width: 500px !important;">
</figure>
</center>

---

# Accuracy Overlap

<center>
<figure>
    <img src="/accuracy_overlap_models_5.png" style="width: 500px !important;">
</figure>
</center>


---

# Std Overlap

<center>
<figure>
    <img src="/std_overlap_models_1.png" style="width: 500px !important;">
</figure>
</center>

---

# Std Overlap

<center>
<figure>
    <img src="/std_overlap_models_10.png" style="width: 500px !important;">
</figure>
</center>




