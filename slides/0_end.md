---
layout: end
hideInToc: true
---

---
layout: statement
---

## Thank you for the attention!

<br>
<br>

<!-- #### Happy to answer your questions by e-mail <a href="mailto:aboldyrev@hse.ru">aboldyrev@hse.ru</a> and via Telegram <a href="https://t.me/aboldyrev">@aboldyrev</a> -->

<PoweredBySlidev mt-10 />


---
---
level: 2
zoom: 1.1
---

# Conclusions

* We propose a procedure to measure the robustness of machine learning models.

* We supplement such a procedure with a meta-algorithm for robust model selection.

* The two robust models for two specific problems found using this method have the best convergence and the smallest loss variability among the $2\times6912$ models considered.
    * The models we found are more robust than the models selected by NAS from a similar search space.
    * ~ 8x speedup in training time is observed compared to an exhaustive search;
        * The total training time can be further reduced by using robust model search on subsamples.

<br>

##### A paper with this method has been published in the IEEE Access journal. DOI: [10.1109/ACCESS.2025.3578926](https://doi.org/10.1109/ACCESS.2025.3578926)


---
layout: center
class: text-center
---

# Backup slides



---

---
layout: statement
---

# Early Results
## Selection by epoches


---

# Accuracy by Epoches

<center>
<figure>
    <img src="/dots_epoches_20_50.png" style="width: 900px !important;">
</figure>
</center>


---

# Accuracy by Epoches

<center>
<figure>
    <img src="/dots_epoches_20_50_top7.png" style="width: 900px !important;">
</figure>
</center>


---

# Accuracy by Epoches

<center>
<figure>
    <img src="/epoches_kendall.png" style="width: 670px !important;">
</figure>
</center>



---

# Accuracy Overlap by Epoches

<center>
<figure>
    <img src="/epoches_overlap.png" style="width: 670px !important;">
</figure>
</center>

---

# Robust Model Selection Algorithm

<div class="grid grid-cols-[2fr_2fr] gap-5">
<div>
  <br>
    <figure>
    <img src="/model_selection_algorithm.png" style="width: 335px !important;">
    <figcaption style="font-size: 12px; position: absolute"><br>Published in <a href="https://doi.org/10.1109/ACCESS.2025.3578926">https://doi.org/10.1109/ACCESS.2025.3578926</a>
    </figcaption>
  </figure>
</div>
<div>
<div>
  <figure>
    <img src="/Energy_randomization_sources_2_FC_all_annotated.svg" style="width: 360px !important;">
  </figure>
</div>
<br>
<div>

#### Effective reduction of model trainings:
<div class="grid grid-cols-[5fr_6fr] gap-5">
<div>
<center>
  <figure>
    <img src="/Energy_model_selection_criterion.svg" style="width: 205px !important;">
  </figure>
</center>
</div>
<div>

* 41567 (ours)<br> vs.<br> 345600 (full search);
* for 6912 models with 50 instances each;

</div>
</div>

</div>
</div>
</div>

---

# Selected Models: Energy Reconstruction

<div class="grid grid-cols-[2fr_3fr] gap-10">
<div>
<br>
<figure>
    <img src="/energy_models.png" style="width: 355px !important;">
</figure>
<br>

```markdown {*}{maxHeight:'300px'}
================================================
Layer              Output Shape         Param #
================================================
Model 1 (Energy)  [-1]                  --
|--Conv2d         [-1, 32, 13, 13]      288
|--ReLU           [-1, 32, 13, 13]      --
|--MaxPool2d      [-1, 32, 6, 6]        --
|--Conv2d         [-1, 64, 4, 4]        18,432
|--ReLU           [-1, 64, 4, 4]        --
|--MaxPool2d      [-1, 64, 3, 3]        --
|--Linear         [-1, 9]               5,193
|--ReLU           [-1, 9]               --
|--Linear         [-1, 1]               10
================================================
Trainable params: 23,923
================================================

================================================
Layer              Output Shape         Param #
================================================
Model 2 (Energy)  [-1]                  --
|--Conv2d         [-1, 32, 13, 13]      288
|--ReLU           [-1, 32, 13, 13]      --
|--MaxPool2d      [-1, 32, 6, 6]        --
|--Conv2d         [-1, 64, 4, 4]        18,432
|--ReLU           [-1, 64, 4, 4]        --
|--MaxPool2d      [-1, 64, 3, 3]        --
|--Linear         [-1, 9]               5,202
|--ReLU           [-1, 9]               --
|--Linear         [-1, 1]               10
================================================
Trainable params: 23,932
================================================
```
</div>
<div>

<figure>
    <img src="/Energy_B_Loss_vs_epoch_Models_1_2.svg" style="width: 500px !important;">
</figure>

<div class="grid grid-cols-[2fr_2fr] gap-1">
<div>
<figure>
    <img src="/Energy_A_4_bins_corrected.svg" style="width: 235px !important;">
</figure>
</div>
<div>
<figure>
    <img src="/Energy_B_4_bins_corrected.svg" style="width: 235px !important;">
</figure>
</div>
</div>

</div>
</div>

---
zoom: 0.99
---

# Selected Models: Position Reconstruction

<div class="grid grid-cols-[2fr_3fr] gap-10">
<div>
<br>
<figure>
    <img src="/position_models.png" style="width: 355px !important;">
</figure>
<br>

```markdown {*}{maxHeight:'300px'}
================================================
Layer              Output Shape         Param #
================================================
Model 3 (Position)  [-1]                --
|--Conv2d           [-1, 32, 13, 13]    288
|--PReLU            [-1, 32, 13, 13]    32
|--MaxPool2d        [-1, 32, 6, 6]      --
|--Conv2d           [-1, 64, 4, 4]      18,432
|--PReLU            [-1, 64, 4, 4]      64
|--MaxPool2d        [-1, 64, 1, 1]      --
|--Linear           [-1, 64]            4,160
|--PReLU            [-1, 64]            64
|--Linear           [-1, 9]             585
|--PReLU            [-1, 9]             9
|--Linear           [-1, 1]             10
================================================
Trainable params: 23,644
================================================

================================================
Layer              Output Shape         Param #
================================================
Model 4 (Position)  [-1]                --
|--Conv2d           [-1, 32, 13, 13]    288
|--PReLU            [-1, 32, 13, 13]    32
|--MaxPool2d        [-1, 32, 6, 6]      --
|--Conv2d           [-1, 64, 4, 4]      18,432
|--PReLU            [-1, 64, 4, 4]      64
|--MaxPool2d        [-1, 64, 1, 1]      --
|--Linear           [-1, 64]            4,160
|--PReLU            [-1, 64]            64
|--Linear           [-1, 9]             603
|--PReLU            [-1, 9]             9
|--Linear           [-1, 1]             10
================================================
Trainable params: 23,662
================================================
```
</div>
<div>

<figure>
    <img src="/Position_B_Loss_vs_epoch_Models_3_4.svg" style="width: 500px !important;">
</figure>

<div class="grid grid-cols-[2fr_2fr] gap-1">
<div>
<figure>
    <img src="/Position_A_4_bins.svg" style="width: 235px !important;">
</figure>
</div>
<div>
<figure>
    <img src="/Position_B_4_bins.svg" style="width: 235px !important;">
</figure>
</div>
</div>

</div>
</div>

---

# Model Path in the Algorithm: Mean Accuracy
<center>
<figure>
    <img src="/model_path_mean_10k.png" style="width: 740px !important;">
</figure>
</center>

* Train: 10k samples
* ⭐ - base model
