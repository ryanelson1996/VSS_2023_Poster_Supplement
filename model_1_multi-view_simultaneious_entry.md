# Model 1 - Multi-view simulatenous entry.

In this model, we concatenated information about all 5 views together, and performed principal component analysis (PCA) on all of that combined data. This provided us with a multi-view PCA space, in which each component (and therefore each point in the space) contains information about all 5 views.

Below I will first show you an example of a reconstruction made using this model, and then further down you can see a video showing what some of the components look like.

Click [here](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_1_construction.html) for details on how the model was constructed and [here](https://ryanelson1996.github.io/VSS_2023_Poster_Supplement/model_1_reconstructing_frames.html) to see how the frames were reconstructed.

## Reconstructions

The video below shows some example reconstructions.
The top row is the actual frames. The second row down is the reconstructions made when we project in all 5 views together. In this particular model, this gives us a baseline of what we can actually acheive.
The subsequent rows shows the reconstructions made by projecting in just the view bounded by the red box. 
In the following video, scaling has been applied to make accurate reconstructions. To learn more about the scaling, click the link above that shows you how the frames were reconstructed.

<video src="https://user-images.githubusercontent.com/58479570/233998081-07c729e8-9ec0-4431-9193-f0ad4ff041ab.mp4" controls="controls" style="max-width: 730px;">
</video>

## PC Videos
The below videos shows what happens in you slide back and forth along a given component. In each video the face starts off as average, scales along the given component in one direction, then back along the component in the other direction, and then back to average.

PC 1
<video src="https://user-images.githubusercontent.com/58479570/235632148-d6f3fccf-a580-4785-8382-66c003f1b27c.mp4" controls="controls" style="max-width: 730px;">
</video>
<br>

PC 2
<video src="https://user-images.githubusercontent.com/58479570/235632178-60580d21-29b8-496a-9f2b-7e51e8907260.mp4" controls="controls" style="max-width: 730px;">
</video>
<br>

PC 3
<video src="https://user-images.githubusercontent.com/58479570/235632226-76b6f871-10d0-402c-b02b-b187626b774c.mp4" controls="controls" style="max-width: 730px;">
</video>

<br>

PC 4
<video src="https://user-images.githubusercontent.com/58479570/235632290-b1c92e26-e33d-4948-a293-837faa31d592.mp4" controls="controls" style="max-width: 730px;">
</video>

<br>

PC 5
<video src="https://user-images.githubusercontent.com/58479570/235632321-9df9852c-6701-4012-8d7d-6c76fa9eb7d2.mp4" controls="controls" style="max-width: 730px;">
</video>

<br>
