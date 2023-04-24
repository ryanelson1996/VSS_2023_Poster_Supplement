# Model 1 - Multi-view simulatenous entry.

In this model, we concatenated information about all 5 views together, and performed principal component analysis (PCA) on all of that combined data. This provided us with a multi-view PCA space, in which each component (and therefore each point in the space) contains information about all 5 views.

Below I will first show you an example of a reconstruction made using this model, and then further down you can see a video showing what some of the components look like.

## Reconstructions

The video below shows some example reconstructions.
The top row is the actual frames. The second row down is the reconstructions made when we project in all 5 views together. In this particular model, this gives us a baseline of what we can actually acheive.
The subsequent rows shows the reconstructions made by projecting in just the view bounded by the red box. 

<video src="https://user-images.githubusercontent.com/58479570/233998081-07c729e8-9ec0-4431-9193-f0ad4ff041ab.mp4" controls="controls" style="max-width: 730px;">
</video>

## PC Videos
The below videos shows what happens in you slide back and forth along a given component. In each video the face starts off as average, scales along the given component in one direction, then back along the component in the other direction, and then back to average.

PC 1

<video src="https://user-images.githubusercontent.com/58479570/234008556-dcfe1a50-e1ec-4eb1-a012-4d2851bec102.mp4" controls="controls" style="max-width: 730px;">
</video>
<br>

PC 2

<video src="https://user-images.githubusercontent.com/58479570/234007982-16fe6393-0ed8-476f-8292-ad1099b7d610.mp4" controls="controls" style="max-width: 730px;">
</video>
<br>

PC 3

<video src="https://user-images.githubusercontent.com/58479570/234008003-4c6d1311-f2ef-42fe-b432-4687c2eea531.mp4" controls="controls" style="max-width: 730px;">
</video>
<br>

PC 4

<video src="https://user-images.githubusercontent.com/58479570/234008024-6d40776a-61c9-46de-9805-ce0f4b262797.mp4" controls="controls" style="max-width: 730px;">
</video>
<br>

PC 5

<video src="https://user-images.githubusercontent.com/58479570/234008066-97dd7b63-8fde-4995-bcec-eaf95255aff4.mp4" controls="controls" style="max-width: 730px;">
</video>
<br>
