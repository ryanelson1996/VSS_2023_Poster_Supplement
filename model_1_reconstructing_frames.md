# Model 1 - multi-view, simultaneous entry, reconstructing frames

With this particular model, we can reconstruct frames using both single-view inputs and multi-view inputs. The aim of the model is to be able to reconstruct motion across views, and so input one view and reconstruct in another. However, we can also recontruct the frames after projecting in all 5 views simultaneously. With this particular model, this seems to give the best estimation of what we can reconstruct, and also serves as method for scaling the single view loadings.
In summary, to reconstruct using the multi-view inputs, one simply projects the multi-view vectors into the space to determine the loadings on the components, multiplies the components by the loadings, and then sums across the components. Then add mu back in (as the PCA spaces are centered) and voila, this gives you reconstructed frames across all 5 views. 
To reconstruct all views from a single view, one can project in that single view, and essentially calculate the inner product between the frames and the portion of the components being projected onto (the portion of the components corresponding to the input view). This inner product can then be scaled, and then the same process can be applied as above to scale and sum the components to provide the reconstructions.


## Scaling
As one might deduce, projecting a single view in only projects onto about 1/5th of the PCA components (as there are 5 views) and as a result, the reconstructions made without any scaling contain very muted motion. The motion is there, but muted (see reconstruction below). However, if we multiply each of the loadings by 5 we end up with exaggerated motion (see reconstruction below). The reason for this can be observed when we look at the loadings from the multi-view reconstructions, which is a reason why they come in handy. By comparing the single-view loadings to the multi-view loadings, we can see that actually a non-uniform scaling is required. The early components needs to be scaled by a scale factor of close to 5, while the later components are scaled by a much smaller scaling factor. After trying to workout why this is, it turns out the later components are more specific to certain viewpoints, and so the motion in one view is not necessary consistent with motion in another view, and therefore some frames/views require a large scaling factor, and others a much smaller scaling factor, and as a result the desired scaling factor on average plateaus near x1.
To put it simply, scaling is a bit of a pain, and by no means perfect, but it has helped identify a potential problem.

## Uniform scaling factors / no scaling.
<br>

Reconstruction with no scaling applied. You can see that the motion is very muted in all views other than the input view.
<video src="https://user-images.githubusercontent.com/58479570/235636359-57fe8ffa-3454-4bdf-b5b2-e7b65be769fe.mp4" controls="controls" style="max-width: 730px;">
</video>

<br>

Reconstruction with a uniform 5x scaling factor applied.
<video src="https://user-images.githubusercontent.com/58479570/235638820-57bb5205-1c35-4405-b5cd-7f197c2ed1ab.mp4" controls="controls" style="max-width: 730px;">
</video>

<br>

## Non-uniform scaling factors (used for the demonstration reconstructions)

### Linear least squares 
Calculating the scaling factors:
The thin red line shows the loadings on PC 1 for 100 frames from a single view. The black line shows the loadings for those frames from the multi-view input.
The thick red line shows the estimated loadings following a linear least squares regression.
<p align="center">
<img src="https://user-images.githubusercontent.com/58479570/235639478-7b51e229-624d-429a-a019-bba928e9b9cf.PNG" width="700">
</p>

<br>

Scaling (m) and translation (c) factors determined using linear least squares regression:
Each column shows the scaling (m) and translation (c) factor to move the single-view loading onto the multi-view loading using " y = mx + c " where x is the single-view loading and y is the estimated multi-view loading. 
Top row shows the LLS estimation procedure. The middle row shows the average scaling factor. The bottom row shows the average translation factor.
The line in the middle and bottom rows shows the median scaling and translation factor respectively, and the shaded area shows the 95% range of calcuting these coefficients over 100 permutations of 100 random sets of frames.
To reconstruct the frames presented in the reconstructions demonstration for model one, we took the single view loadings, and multiplied them by the median scaling factor for each component, and added the median translation factor. 

<p align="center">
<img src="https://user-images.githubusercontent.com/58479570/235639623-27eb618d-5d21-40da-b266-e41fa75100ee.PNG" width="700">
</p>

<br>

### Alternateive methods
An alternative way to calculate the scaling is to simply divide the multi-view loadings by the single_view loadings, and average those values. The plot below shows the 
median (line) and IQR (shaded area) of doing such a calculation. These scaling factors are unsurprisingly very similar to the scaling factors estimated by LLS, but do not require many permutations of running LLS.
<p align="center">
<img src="https://user-images.githubusercontent.com/58479570/235643675-ea9101cf-7ef6-4b9f-8b97-3d6370149df4.png" width="700">
</p>

<br>

The above scaling only considers the inner product of the projection, but what about the scalar magnitude of the projection? The scalar magnitude is calcualted by taking the inner product and dividing it by the squared length of the vector being projected onto. The components themselves have a lenght of 1, so the inner product is the same as the scalar magnitude for the multi-view reconstructions, but each view's section of the component will be < 1, so perhaps we can use that information to scale the loadings? If we calculate and compare the single-view loadings calculated in this way with the multi-view loadings we still see a similar pattern of scaling factors being required, but now the averaging scaling factors start at ~1:
<p align="center">
<img src="https://user-images.githubusercontent.com/58479570/235645748-c60377fc-ea67-4bd7-a713-f751741ba63d.png" width="700">
</p>

<br>

I haven't included an example reconstruction here, but what happens is that the reconstructions look reasonable overaall, but the videos for the input view become exaggerated/distorted. The reason for this is again because we need to apply a scaling factor to down-regulate the loadings in the higher components, but why? The scaling factor isn't well predicted by the variance explained by the components. It turns out that the loadings on the different viewpoints actually because less correlated in the higher components. The motion and textures extracted must differ in some ways across the views in the higher components, as the correlation between the single-view loadings and the multi-view loadings decreases as the PC number increases. 
It turns out that the correlation coefficient is actually a good predictor of the required scaling factor. It appears that the scaling factor may not be a scaling factor as such, but more a result of the increased noise across views in the higher components.
<p align="center">
<img src="https://user-images.githubusercontent.com/58479570/235648931-cf1b0e49-6985-4bae-9931-b47a1f111f3e.png" width="700">
</p>

<br>









