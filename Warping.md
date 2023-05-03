# Warping

In order to make the spaces, we first need to bring the frames into alignment. The videos are therefore warped to align each frame in a video to a template frame for that view. This uses the Multi-channel Gradient Model developed by Johnston and colleages (1992, 1999). The output of this is that each frame is then spatially aligned to the reference frame, but still has deviations in texture relative to this template frame. We also are provided with horizontal and vertical warp fields that explain how to move the pixels in order to move from the individual frame to the reference frame. 

<p align="center">
<img src="https://user-images.githubusercontent.com/58479570/235941049-39731d83-be76-40cf-b224-79bd75b4b46e.png" width="700">
</p>

These fields can be inverted so that we can then determine how to move from the shape of the template frame back to an individual frame.

<p align="center">
<img src="https://user-images.githubusercontent.com/58479570/235941077-7afa3a3e-0224-4314-98bb-1805a5b8407c.png" width="700">
</p>

<br>

This therefore gives us both texture and shape deviations from the template that can be used to reconstruct the given frame.

<p align="center">
<img src="https://user-images.githubusercontent.com/58479570/234024167-d38625b9-0357-47ed-a12a-2f3911756d1b.png" width="700">
</p>

<br>




## References

Johnston, A., McOwan, P. W., & Buxton, H. (1992). A computational model of the analysis of some first-order and second-order motion patterns by simple and complex cells. Proceedings of the Royal Society of London. Series B: Biological Sciences, 250(1329), 297-306. [https://doi.org/10.1098/rspb.1992.0162](https://doi.org/10.1098/rspb.1992.0162)

Johnston, A., McOwan, P. W., & Benton, C. P. (1999). Robust velocity computation from a biologically motivated model of motion perception. Proceedings of the Royal Society of London. Series B: Biological Sciences, 266(1418), 509-518. [https://doi.org/10.1098/rspb.1999.0666](https://doi.org/10.1098/rspb.1999.0666)

