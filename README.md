# Additional materials for VSS poster presentation, May 2023
Thank you for taking the time to view our poster and for following the links to the supplementary materials.
Below you can find additional details about how the multi-view spaces were constructed, and videos of reconstructions across views using these spaces, and videos depicting what the components of the PCA spaces look like. 


## Methods

### Video collection
- Video collection was performed by a previous PhD student. 
- Videos were recorded simultaneously from 5 viewpoints while actors (n=9) repeated a selection of sentences, such as "Miss Black thought about the lap". 

<br>

### Warping
Warping is a necessary part of the model construction. [Click here](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/Warping.html) to see how and why warping is performed.

<br>

### Model construction
While some details of model contruction was the same (such as the warping and linearisation of frames), other elements were (unsurprisingly) different. Click on each of the links below to see how each model was constructed. The summary is that the models varied in how (and whether) frames were concatenated across views, and whether a multi-view space was made, or a separate space for each viewpoint.

[Model 1](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_1_construction.html) multi-view, simultaneous entry

[Model 2](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_2_construction.html) separate spaces

[Model 3](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_3_construction.html)  multi-view, paired entry

<br>

### Reconstructing frames
After making the models, we then want to see how well the models can reconstruct frames across views. Click on each of the links below to see how reconstructions were made.

[Model 1](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_1_reconstructing_frames.html) multi-view, simultaneous entry

[Model 2](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_2_reconstructing_frames.html) separate spaces

[Model 3](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_3_reconstructing_frames.html) multi-view, paired entry

<br>

## Reconstructions and PCA component videos
By clicking on each of the links below, you can see examples of the reconstructions made using the different models.

#### Model 1 - multi-view, simultaneous entry
[Click here](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_1_multi-view_simultaneious_entry.html) to view the reconstructions and PCA components for model 1.

#### Model 2 - separate spaces
[Click here](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_2_separate_spaces.html) to view the reconstructions and PCA components for model 2.

#### Model 3 - multi-view, paired entry
[Click here](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_3_paired_entry_reconstructions.html) to view the reconstructions and PCA components for model 3.

## Measuring reconstruction accuracy
This is currently a work in progess, but we want to be able to quantify the reconstruction accuracy. We can visually assess the reconstructions to see how accurate they look, but to compare models and scaling methods it can be useful to add some numbers. Some methods of quantifying reconstruction accuracy can be seen below.

1) Correlation/SSE/ED in image space:
    - We can measure the correlation, sum of squared error, or Euclidean distance in the image space based on the pixel values. This is performed between the original frames and the reconstructed frames, and can be calculated for each view                 separately. This is calculated for each frames, and then we can average the values together.
    - STRENGTHS: 
        - Can measure this for each model and scaling factor.
        - Correlation coefficients are easily iterpretable.
    - LIMITATIONS: 
        - ED and SSE are harder to interpret. Close to 0 is great, but what classifies as bad?
        - All measures are sensitive to spatial position. If the reconstruction has the appropriate action but is translated by a few pixels then this will seriously impact the reconstruction accuracy.
        - Correlation coefficient inflated by the background pixels.
        
2) Correlation/SSE/ED in the deviation vectors.
    - Each image (actual or reconstructed) can be described using a deviation vector. This has the texture deviations of the face relative to average once aligned, and the X/Y warp fields to move the pixels from the template shape to the individual frame.
    - In the same way method as in image space, you can compare the actual deviation vectors to the reconstructed deviation vectors.
    - STRENGTHS:
        - Measures are less affected by spatial translations, because the texture deviations are aligned to the average shape you can compare the differences in textures without worrying as much about translations.
    - LIMITATIONS:
        - Correlation coefficient again sensitive to background pixels.
        - ED and SSE also have no intuitive upper limit, but can still of course compare across different models/scaling methods.
        
3) Loadings in separate view spaces
    - As well as comparing reconstructions using the image properties, you can also compare their similarity in PCA space. You take your actual frame and your reconstructed frame for a given view, and project them both into a PCA space specific for that view. You can then compare measures such as the correlation in the loadings, the SSE or ED in the loadings, etc.
    - STRENGTHS:
        - Measure less sensitive to background pixels.
        - Correlation less senstive to caricaturing. If motion/texture is caricatured slightly then the reconstruction might look very accurate, but the correlation in image space might then be reduced. The correlation in the loadings however won't be affected by caricaturing (this can also be a weakness).
        - Can still compare across different methods and scaling factors.
    - LIMITATIONS:
        - As noted above, correlation less sensitive to caricaturing. 
        - If you use Model 2, which projects into separate spaces, the loadings for the reconstructions and the original frames of the input views SHOULD be identical, so not necessarily a good measure of reconstruction accuracy.
        - SSE/ED again somewhat arbitrary.
        
An alternative method that we have not yet explored is to the present the reconstructions to participants and obtain perceptual similarity ratings. For example, we might present a probe stimulus, and then ask which of two reconstructions (using different models or scaling factors) is the most accurate. This of course would be very costly in terms of time compared to the automatic methods of measuring reconstruction accuracy outlined above.
        

<br>

## Contact  

Twitter: [@Ryan_J_Elson](https://twitter.com/Ryan_J_Elson)  

Email: [ryan.elson@nottingham.ac.uk](ryan.elson@nottingham.ac.uk)  

<br>

## References  

Asthana, A., Marks, T. K., Jones, M. J., Tieu, K. H., & Rohith, M. V. (2011, November). Fully automatic pose-invariant face recognition via 3D pose normalization. In 2011 international conference on computer vision (pp. 937-944). IEEE. [[DOI]](https://doi.org/10.1109/ICCV.2011.6126336)

Burt, A. L., & Crewther, D. P. (2020). The 4D space-time dimensions of facial perception. Frontiers in psychology, 11, 1842. [[DOI]](https://doi.org/10.3389/fpsyg.2020.01842)

Hassner, T., Harel, S., Paz, E., & Enbar, R. (2015). Effective face frontalization in unconstrained images. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 4295-4304). [[LINK]](https://www.cv-foundation.org/openaccess/content_cvpr_2015/html/Hassner_Effective_Face_Frontalization_2015_CVPR_paper.html)

Taigman, Y., Yang, M., Ranzato, M. A., & Wolf, L. (2014). Deepface: Closing the gap to human-level performance in face verification. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 1701-1708). [[LINK]](https://openaccess.thecvf.com/content_cvpr_2014/html/Taigman_DeepFace_Closing_the_2014_CVPR_paper.html)

Valentine, T. (1991). A unified account of the effects of distinctiveness, inversion, and race in face recognition. The Quarterly Journal of Experimental Psychology Section A, 43(2), 161-204. [[DOI]](https://doi.org/10.1080/14640749108400966) 
