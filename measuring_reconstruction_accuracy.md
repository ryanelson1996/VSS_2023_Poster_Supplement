# Measuring reconstruction accuracy
As well as visually inspecting the reconstructions, it can also be useful to measure and quantify reconstruction accuracy. Below I have outlined some of the methods that we can use to go about this.

1) Correlation/SSE/ED in image space:
    - We can measure the correlation, sum of squared error, or Euclidean distance in the image space based on the pixel values. This is performed between the original frames and the reconstructed frames, and can be calculated for each view separately. This is calculated for each frames, and then we can average the values together.
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
