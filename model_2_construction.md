# Model 2 - separate spaces, model construction

## Aim
Model 1 worked well, however was not biologically plausible as the model could 'see' all 5 views at the same time. The aim of this model is to begin to explore whether we can make a more biologically plausible model.

## Model construction
This model follows some of the same steps as model 1, in that the videos are first aligned (warped) to the template for the given view, however rather than concatenating the frames across views, a separate space is created for each viewpoint. 

Because the different viewpoints contain different information, it cannot be assumed that the movement in the components in one view's space directly translates to the movements in the same components in a different views space. Therefore, we need to learn how the components in the different spaces are correlated.
To do this, we take the concurrent frames for two neighbouring views (say views 1 & 2) and project them into their respective spaces. For each frame we can see which components are 'active' in the 2 spaces, and therefore over a set of frames we can establish how components in one space are correlated with components in the other space. This builds up a correlation matrix of size c1 x c2 where c1 is the number of components in view 1's space and c2 is the number of components in view 2's space. We can then perform this operation with each set of neighboring views.

<p align="center">
<img src="https://user-images.githubusercontent.com/58479570/234806135-bf965463-a1fc-42db-a54c-7aac347ce1d6.png" width="700">
</p>
<br>

<p align="center">
<img src="https://user-images.githubusercontent.com/58479570/234032574-d804c630-2959-43d1-89ba-5bc78fea8355.png" width="700">
</p>
<br>

We could learn the correlations directly from view 1 to view 5, but this would not be biologically plausible, which is of course the whole aim of this model. As we can see from the reconstructions however, it still manages to reconstruct the motion across views remarkably well.
<br>

While this model is more biologically plausible, it is does not acheive all of the desired aims that we are after. While view-invariant as a system, there is no single 'unit' that is view-invariant. Therefore, we would want to add a further level to this model so that a single 'unit' in this level could be view-invariant.



