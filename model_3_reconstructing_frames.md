# Model 3 - multi-view, paired entry, reconstructing frames

Reconstructing frames with Model 2 is much like reconstructing frames with Model 1. One can project in the multi-view inputs as well as single-view inputs.

<br>

Reconstructing with Model 3 is however a work in progress. Unlike Model 1, the multi-view reconstructions are no longer a good estimation. The motion in these videos is in the right form, but is caricatured (and a little jittery). This is because the motion in components in no longer of the same magnitude across the views. In some views the motion is much more pronounced than others, and so this ends up caricaturing some of the motion when the multi-view vectors are projected in, as the comparative loadings on the different views is imbalanced. Therefore I am currently working on ways to normalise the magnitude of the motion in each view.

<br>

Another problem with this model, which I have tried to correct, is that the motion in some views in some components is flipped relative to other views. This can be seen in the videos of some of the components. Currently the approach for fixing this is to project in all views, and identify which views have a loading in the opposite direction to view 1. I can then simply multiply those views by -1 so that the motion now goes in the same direction as view 1.
