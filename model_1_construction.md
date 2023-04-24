# Model 1 - multi-view, simultaneous entry model construction

## Aim 
The aim of this model was to build an initial model that could learn and reconstruct motion across changes in view. The aim at this stage was to assess if this was at all possible, before then worrying about biological plausibility.

## Model construction
The easiest way to summarise this model, is that we concatenated frames across the 5 viewpoints, such that each frame now contained all 5 views.
The more informative description is that we took the X and Y warp fields (for more info on the warping, [click here](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/Warping.html)) and concatenated them with the RGB information. This provides a 128 x 128 x 5 matrix for each frame. 

<p align="center">
<img src="https://user-images.githubusercontent.com/58479570/234028096-88e293d7-cbe5-408a-8ff9-9c828b74fc17.png" width="700">
</p>
<br>

We then linearised each frame into a column vector, and concatenated frames together. E.g. the below plot shows 7 linearised frames strapped together. 
<p align="center">
<img src="https://user-images.githubusercontent.com/58479570/234027312-7158e419-a1ee-402f-90d0-59b446b04820.png" width="700">
</p>
<br>

We then stitched the 5 views together such that each frame (column) now contained all 5 views. This is how the models gets the name "multi-view, simultaneous entry"
<p align="center">
<img src="https://user-images.githubusercontent.com/58479570/234027636-6ddef865-aa57-4fdd-899f-17891b3a5556.png" width="700">
</p>
<br>

We then subtracted the average column from the matrix, and performed principal component analsis to create our multi-view PCA space.



