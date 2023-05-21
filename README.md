# Additional materials for VSS poster presentation, May 2023
Thank you for taking the time to view our poster and for following the links to the supplementary materials.
Below you can find additional details about how the multi-view spaces were constructed, and videos of reconstructions across views using these spaces, and videos depicting what the components of the PCA spaces look like. 

<br>

## Abstract and poster pdf
The abstract and pdf of our poster can be found [here](https://www.visionsciences.org/presentation/?id=5453).

<br>

## Aim
Currently it is unclear if view-invariance of faces in humans is acheived using a single 3D representation, or interpolation using a set of 2D representations. The aim of our work is to explore how and whether it is possible to build a view-invariant representation of faces that can learn and reconstruct facial motion across changes in view, but using a set of 2D representations rather than a 3D representation.

<br>

## Methods

### Video collection and warping
Videos were recorded simultaneously from 5 viewpoints while actors (n=9) repeated a selection of sentences, such as "Miss Black thought about the lap". 

Warping is a necessary part of the model construction for each of the models. In summary it aligns each frame to a template frame for the respective view. [Click here](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/Warping.html) to see how and why warping is performed.

<br>

### Model construction
While some details of model contruction was the same (such as the warping and linearisation of frames), other elements were (unsurprisingly) different. Click on each of the links below to see how each model was constructed. The summary is that the models varied in how (and whether) frames were concatenated across views, and whether a multi-view space was made, or a separate space for each viewpoint.

[Model 1](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_1_construction.html) multi-view, simultaneous entry

[Model 2](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_2_construction.html) separate spaces

[Model 3](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_3_construction.html) multi-view, paired entry

<br>

### Reconstructing frames
After making the models, we then want to see how well the models can reconstruct frames across views. Click on each of the links below to see how reconstructions were made.

[Model 1](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_1_reconstructing_frames.html) multi-view, simultaneous entry

[Model 2](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_2_reconstructing_frames.html) separate spaces

[Model 3](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_3_reconstructing_frames.html) multi-view, paired entry

<br>

## Reconstructions and PCA component videos
By clicking on each of the links below, you can see examples of the reconstructions made using the different models and demonstration videos depicting the PCA components.

[Model 1](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_1_multi-view_simultaneious_entry.html)  multi-view, simultaneous entry

[Model 2](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_2_separate_spaces.html) separate spaces

[Model 3](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_3_paired_entry_reconstructions.html) multi-view, paired entry

<br>

## Measuring reconstruction accuracy
This is currently a work in progess, but we want to be able to quantify the reconstruction accuracy. We can visually assess the reconstructions to see how accurate they look, but to compare models and scaling methods it can be useful to add some numbers. Some methods of quantifying reconstruction accuracy can be seen by following [this link](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/measuring_reconstruction_accuracy.html).
        

<br>

## Summary
In summary, we have been able to reconstruct motion well across views, with Model 2 being both the most accurate reconstructions and the most biologically plausible. 

Model 1 showed accurate reconstructions, but lacks biological plausibility due to being able to 'see' all 5 views at once. 

Model 3 contains 'units' (components) that contain information about all 5 views, and so shows some promise, but the motion can vary across the views within a given component. This would need to be fixed for the model to be plausible. 

Model 2 does not (yet) have any 'units' that contain information about all 5 views, but we are able to reconstruct motion remarkably well across views using this model and it is more biologically plausible.

This suggests that a 3D representation of the face may not be necessary for mentally rotating a face during speech, and that a 2D representation may be sufficient.

<br>

## Contact  

If you have any questions, or any suggestions, please feel free to get in touch!

Twitter: [@Ryan_J_Elson](https://twitter.com/Ryan_J_Elson)  

Email: [ryan.elson@nottingham.ac.uk](ryan.elson@nottingham.ac.uk)  

<br>

## References  

Asthana, A., Marks, T. K., Jones, M. J., Tieu, K. H., & Rohith, M. V. (2011, November). Fully automatic pose-invariant face recognition via 3D pose normalization. In 2011 international conference on computer vision (pp. 937-944). IEEE. [[DOI]](https://doi.org/10.1109/ICCV.2011.6126336)

Burt, A. L., & Crewther, D. P. (2020). The 4D space-time dimensions of facial perception. Frontiers in psychology, 11, 1842. [[DOI]](https://doi.org/10.3389/fpsyg.2020.01842)

Hassner, T., Harel, S., Paz, E., & Enbar, R. (2015). Effective face frontalization in unconstrained images. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 4295-4304). [[LINK]](https://www.cv-foundation.org/openaccess/content_cvpr_2015/html/Hassner_Effective_Face_Frontalization_2015_CVPR_paper.html)

Taigman, Y., Yang, M., Ranzato, M. A., & Wolf, L. (2014). Deepface: Closing the gap to human-level performance in face verification. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 1701-1708). [[LINK]](https://openaccess.thecvf.com/content_cvpr_2014/html/Taigman_DeepFace_Closing_the_2014_CVPR_paper.html)

Valentine, T. (1991). A unified account of the effects of distinctiveness, inversion, and race in face recognition. The Quarterly Journal of Experimental Psychology Section A, 43(2), 161-204. [[DOI]](https://doi.org/10.1080/14640749108400966) 
