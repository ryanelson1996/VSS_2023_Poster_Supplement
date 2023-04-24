# Model 2 - separate spaces, reconstructing frames

In this model, we have created a separate PCA space for each view, but still want to reconstruct motion in one viewpoint from motion in other viewpoints. In order to do this we can make use of the fact that we have learnt how the components in neighbouring views are correlated.
Let's say we start with view 2. We can project view 2's frames into view 2's space to determine the loadings in this space. We can then reconstruct view 2's frames by multiplying the frames by the loadings, and summing the frames together. 
We then want to reconstruct the frames in the neighbouring views (1 & 3). To do this we take our matrix of loadings, and can multiply it by the appropriate matrices of correlation coefficients. For example, for reconstructing view 3 this is the matrix of correlation coefficients that explains how components in view 2 and view 3 are correlated. This therefore provides an estimation of what the loadings in view 3 should be, and we can reconstruct the frames. Once we know the estimated loadings in view 3 we can can then cascade that process along until we have reconstructed the frames in all views.

<br>

<p align="center">
<img src="https://user-images.githubusercontent.com/58479570/234053071-d084724a-009f-4dba-a959-f731f7fabde3.png" width="700">
</p>

<br>

Unlike with model 1, no scaling at all has been applied to the reconstructions. The motion does become a bit muted however as the angular distance from the input view increases, but this is minimal. This muting of the motion is unsurprising given that the correlation coefficients have a max of +/- 1, and so the loadings can only ever get smaller when moving from one view to the next. I am currently looking at whether a combination of projection and correlation might provide an alternative 'association matrix' that would allow for loadings to also increase across views. 

Regardless, this models seems to make impressively accurate reconstructions (take a look at the reconstructions page).
