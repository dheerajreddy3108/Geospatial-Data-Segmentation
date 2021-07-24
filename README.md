
# Geospatial-Data-Segmentation
Test analysis on satellite images for semantic segmentation


We start off my making image analysis and later decide on model to be built for Semantic Segmentation.

Image Segmentation can be defined as a process of classifying images at pixel level. Each pixel of the image in output is the class to which that pixel belongs to. Semantic Segmentation differs from object detection as semantic segmentation does not predict the bounding box of the object and prediction happens at pixel level. As output we get map of a location composed of 3 different categories from multispectral satellite image. 

## Data

The problem is addressed with the data given composed of 5686 images and labeled into 3 different classes. Each image is from a different location specified by its geographical locations. Image data is in mutlispectral format. It consists of 12 bands in total, while label is a single-band image. The images are stored in .tif format. Each image is of size 64x64. Few sample images and their respective labels are shown below.

![32N_12E-230N_01_15_1](https://user-images.githubusercontent.com/55786239/126863411-dde69b20-8c3f-48ea-b5eb-7e19db63e798.png)
![32N_12E-230N_01_15_label](https://user-images.githubusercontent.com/55786239/126863413-ad9ddf5b-f1e9-45c5-821a-080a5810ff43.PNG)

![32N_12E-230N_01_17_img](https://user-images.githubusercontent.com/55786239/126863421-bb0fabde-4cb5-431d-9186-21ac5546509e.PNG)
![32N_12E-230N_01_17_label](https://user-images.githubusercontent.com/55786239/126863422-8035c842-2f39-4948-9934-c41ad06cf1e2.PNG)

![32N_12E-230N_01_21_img](https://user-images.githubusercontent.com/55786239/126863424-51e019fb-2152-40e8-960b-b8b2990c688d.PNG)
![32N_12E-230N_01_21_label](https://user-images.githubusercontent.com/55786239/126863430-f256ab0e-5f4a-4b30-9f7c-07c546dc8ad7.PNG)

## Data Preparation

The models are to be built using 2 different types of Images. One model should make use of only Red, Blue and Greem Bands. These bands are indexed at 4,3 and 2 respectively. Important point to note is Raster count starts at 1 but not at 0. The bands are extracted using a loop and the images are made by stacking the bands. Labels are simple to extract as they are of single band. Both images and labels are segreggated for training and validation

Statistics of Data :

Training Samples - 400

Validation Samples - 100

Testing Samples - 30

The limied access of GPU made usage of few samples from entire lot of samples. Now we have data ready and the next step is to build model architecture. 

## Training

Three different architecutres are built and we can select one and train the model.
Three models that are built are DeepLabv3, Vanilla U_Net and U_Net with encoder of VGG pretrained and have weights of imagenet. The model architecuture is attached along with the repository. 

Once the model is selected the further step is to compile the model. Adam Optimizer is used and accuracy is taken as metrics. The model is trained for 200 epochs but EarlyStopping and ModelCheckpoint are used as well to stop training if the model is not learning. Once the model is trained, predictions are made and best weights are saved.



