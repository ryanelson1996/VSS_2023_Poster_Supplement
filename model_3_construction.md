# Model 3 - multi-view, paired entry, model construction

## Aim
The aim of this model was to explore another multi-view model, which is more biologically plausible than Model 1. This model would have view-invariant 'units' unlike Model 2, but would carry over the idea of activating neighbouring views. 

## Model construction
In this model, we used the idea that view-selective neurons are broadly tuned, and so if you see a face talking in one view, it is likely to be activating at least a few neighbouring sets of neurons. We therefore concatenated frames for 2 neighbouring views, say views 1 & 2, and then as if the head rotated during speech, rotated such that we now activate one of the previous sets of neurons (view 2) and activated the next neighbouiring set (view 3) and continued that idea along until we had reached all 5 views. The rest of the vectors are filled with zeros, allowing us to essentailly have place holder for each missing view whilst containing all information in one big matrix.

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/58479570/234040994-fdb576dc-39c0-477a-902d-2ff2de1f1729.png" width="700">
</p>
<br>

We then perform a PCA on that big matrix.

<br>

To see how the frames were reconstructed, [click here](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_3_reconstructing_frames.html).

To see example reconstructions and demonstrations of some of the components, [click here](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_3_paired_entry_reconstructions.html).

