# Model 2 - Separate spaces

In this model, we performed principal component analysis (PCA) on each view separately. We then assessed how the components in neighbouring spaces were correlated. We could then use these associations to reconstruct across views.

Below I will first show you an example of a reconstruction made using this model, and then further down you can see a video showing what some of the components look like.

## Reconstructions

The video below shows some example reconstructions.
The top row is the actual frames. 
The subsequent rows shows the reconstructions made by projecting in just the view bounded by the red box first, and then cascading the reconstruction process along the rest of the row. 

<video src="https://user-images.githubusercontent.com/58479570/234016428-d1be7ed6-f8db-4fb6-852a-2c21629ff72a.mp4" controls="controls" style="max-width: 730px;">
</video>
<br>

## PC Videos
The below videos shows what happens in you slide back and forth along a given component. In each video the face starts off as average, scales along the given component in one direction, then back along the component in the other direction, and then back to average. Note that in this model, the PCA has been performed on each view separately, therefore the videos are from scaling along the given PC in each space separately, and therefore the action in one space might not correspond to the action in another space.

PC 1

<br>
PC 2

<br>
PC 3

<br>
PC 4

<br>
PC 5

<br>
