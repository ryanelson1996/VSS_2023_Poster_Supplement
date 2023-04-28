# Model 3 - multi-view, paired entry - reconstructions

In this model we aimed to create a single PCA space, in which we concatenated neighbouring viewpoints, and filled the rest of the space with zeros. The hope was that the overlap between neighbouring viewpoints would allow the associations to be learned across all 5 views.

In the reconstructions below, we have not applied any scaling, unlike in the reconstruction video for Model 1. The aim of the scaling is to work out what scaling is required to move the single-view loadings onto the multi-view loadings, which in Model 1 gave the best reconstructions. In this model however, the multi-view reconstructions aren't great (these are the reconstructions from projecting in all 5 views together). As can be seen below, the reconstructions from the multi-view inputs are caricatured. By looking at the PC videos further down, you can see that this is because the magnitude of the motion across the views now differs across the viewpoints. 

## Reconstructions
The video below shows some example reconstructions. The top row is the actual frames. The second row down is the reconstructions made when we project in all 5 views together. In this particular model, this gives us a baseline of what we can actually acheive. The subsequent rows shows the reconstructions made by projecting in just the view bounded by the red box.



## PC Videos
The below videos shows what happens in you slide back and forth along a given component. In each video the face starts off as average, scales along the given component in one direction, then back along the component in the other direction, and then back to average.

This is where you can see some interesting things happening. In PC 1, the face is moving in the same direction in all 5 views, but the magnitude of the motion seems to differ across views. The middle views move a lot more than the full frontal (far left) and full profile (far right).

In PC 10, there is another interesting thing happening. In some views, the motion is going in the opposite direction than in others (despite efforts to repair this, which seems to have worked for some components but not other), but the exact flip of motion is not always apparent. The full profile view is doing a different action. The head is moving, but the mouth barely changes at all unlike the other views.
