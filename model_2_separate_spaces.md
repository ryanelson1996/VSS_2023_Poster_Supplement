# Model 2 - Separate spaces

In this model, we performed principal component analysis (PCA) on each view separately. We then assessed how the components in neighbouring spaces were correlated. We could then use these associations to reconstruct across views.

Below I will first show you an example of a reconstruction made using this model, and then further down you can see a video showing what some of the components look like.

## Reconstructions

The video below shows some example reconstructions.
The top row is the actual frames. 
The subsequent rows shows the reconstructions made by projecting in just the view bounded by the red box first, and then cascading the reconstruction process along the rest of the row. As you can see the action is slightly muted as the angular distance from the input view increases, but overall the model can reconstruct the motion very well. 

<video src="https://user-images.githubusercontent.com/58479570/234016428-d1be7ed6-f8db-4fb6-852a-2c21629ff72a.mp4" controls="controls" style="max-width: 730px;">
</video>
<br>

## PC Videos
The below videos shows what happens in you slide back and forth along a given component. In each video the face starts off as average, scales along the given component in one direction, then back along the component in the other direction, and then back to average. Note that in this model, the PCA has been performed on each view separately. The videos are from scaling along the given PC in each space separately, and therefore the action in one space might not correspond to the action in another space. For example while the actions in PC 1 are consistent across views (other than a sign flip), the motion in PC 5 differs across the views. This is ok because we do not reconstruct across views by repeating the same loading for a given component across views, and instead learn which components in which views represent correlated action across the spaces.

PC 1
<video src="https://user-images.githubusercontent.com/58479570/235630510-8da48e7a-d4a4-4680-a1cd-2ad9706cdc5d.mp4" controls="controls" style="max-width: 730px;">
</video>

<br>

PC 2
<video src="https://user-images.githubusercontent.com/58479570/235630601-1bfbdb0e-a996-4136-aa61-1b516119cbb6.mp4" controls="controls" style="max-width: 730px;">
</video>

<br>

PC 3
<video src="https://user-images.githubusercontent.com/58479570/235630638-8a306778-6e14-41c6-83c4-1ef3265f2e13.mp4" controls="controls" style="max-width: 730px;">
</video>

<br>

PC 4
<video src="https://user-images.githubusercontent.com/58479570/235630707-d8fcc19b-3da9-4fda-83da-38530ac5fdab.mp4" controls="controls" style="max-width: 730px;">
</video>

<br>

PC 5
<video src="https://user-images.githubusercontent.com/58479570/235630736-9d984788-b9c3-48ca-971d-c69e253de06c.mp4" controls="controls" style="max-width: 730px;">
</video>

<br>
