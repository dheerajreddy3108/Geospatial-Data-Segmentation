# Geospatial-Data-Segmentation
Test analysis on satellite images for semantic segmentation


We start off my making image analysis and later decide on model to be built for Semantic Segmentation.

Image Segmentation can be defined as a process of classifying images at pixel level. Each pixel of the image in output is the class to which that pixel belongs to. Semantic Segmentation differs from object detection as semantic segmentation does not predict the bounding box of the object and prediction happens at pixel level. As output we get map of a location composed of 3 different categories from multispectral satellite image. 

## Data

The problem is addressed with the data given composed of 5686 images and labeled into 3 different classes. Each image is from a different location specified by its geographical locations. Image data is in mutlispectral format. It consists of 12 bands in total, while label is a single-band image. The images are stored in .tif format. Each image is of size 64x64. Few sample images and their respective labels are shoen below.
![32N_12E-230N_01_15](https://user-images.githubusercontent.com/55786239/126863187-a1866ecf-5981-4923-aac1-0613dae90c94.PNG)


