# surgical-instrument-segmentation
binary and muli class segmentation of surgical instruments

in this work I used TersnausNet (Unet + vgg16 as an encoder) to segment surgical instruments:

## about the Dataset :
The dataset I worked with is given in the endovis 2017 challenge , it is acquired from the stereo camera images of the da vinci Xi robot during several different porcine procedures, the frames are sampled from 30 Hz videos at a rate of 2 Hz .every video sequence consists of two stereo channels taken from left and right cameras and has a 1920 × 1080 pixel resolution in RGB format.

This data is labelled manually by a trained team at Intuitive Surgical. As it's clear from the image below we are going to solve 2 tasks : binary segmentation involves just separating the image into instruments and background whereas the multi class segmentation tests whether the user can recognize which segmentation corresponds to which da Vinci instrument type.

![alt text](https://github.com/medardif123/surgical-instrument-segmentation/blob/main/f1.PNG) ![alt text](https://github.com/medardif123/surgical-instrument-segmentation/blob/main/f2.PNG) ![alt text](https://github.com/medardif123/surgical-instrument-segmentation/blob/main/f3.PNG)

## About the metrics :
to evaluate the model i have used 2 metrics : Dice coefficient and the intersection over union.
## About the Loss :
for the loss function we have used the jaccard distance which is complementary to the jaccard index and it’s
obtained by subtracting the jaccard index from 1 .
this distance measures the dissimilarity between the predicted segmentation and the ground truth.
## Results :
# the results of the binary segmentation :
| Task | loss | dice | IOU |
| -----| -----|----- | ----|
|binary|0.036|0.88|0.96|
|multiClass|0.26|0.69|0.73|
 
## Some predictions :
#### binary
| Image | Ground Truth | predicted |
| ------| -----------  | ----------|
|<img src="https://github.com/medardif123/surgical-instrument-segmentation/blob/main/frame000.jpg" width="200" height="200" />|<img src="https://github.com/medardif123/surgical-instrument-segmentation/blob/main/gtb_frame000.png" width="200" height="200" />|<img src="https://github.com/medardif123/surgical-instrument-segmentation/blob/main/binary_000.png" width="200" height="200" />|
|<img src="https://github.com/medardif123/surgical-instrument-segmentation/blob/main/frame050.jpg" width="200" height="200" />|<img src="https://github.com/medardif123/surgical-instrument-segmentation/blob/main/gtb_frame050.png" width="200" height="200" />|<img src="https://github.com/medardif123/surgical-instrument-segmentation/blob/main/binary_050.png" width="200" height="200" />|
#### Multiclass 
| Image | Ground Truth | predicted |
| ------| -----------  | ----------|
|<img src="https://github.com/medardif123/surgical-instrument-segmentation/blob/main/15frame010.jpg" width="200" height="200" />|<img src="https://github.com/medardif123/surgical-instrument-segmentation/blob/main/15gtframe010.png" width="200" height="200" />|<img src="https://github.com/medardif123/surgical-instrument-segmentation/blob/main/multi_15010.png" width="200" height="200" />|
|<img src="https://github.com/medardif123/surgical-instrument-segmentation/blob/main/17frame100.jpg" width="200" height="200" />|<img src="https://github.com/medardif123/surgical-instrument-segmentation/blob/main/17gtframe100.png" width="200" height="200" />|<img src="https://github.com/medardif123/surgical-instrument-segmentation/blob/main/multi_17100.png" width="200" height="200" />|
