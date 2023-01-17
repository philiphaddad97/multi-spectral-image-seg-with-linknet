# Image segmentation and region classification on Multi-Spectral Images using Deep Learning

## Introduction

Semantic segmentation algorithms assign a label to every pixel in an image. Inremote sensing, semantic segmentation is often referred to as image classifica-tion,  and  semantic  segmentation  of  non-RGB  imagery  has  numerous  applica-tions, such as land-cover classification, vegetation classification, urban planning,and natural disasters such as floods, earthquakes, hurricanes..etc. And after thebreakthrough in Deep Convolutional Neural Networks (DCNNs ) which had asignificant performance in the different computer vision topics such as Semanticsegmentation, however, it’s all about the RGB images and not about the non-RGB or Multi-Spectral Images (MSI) -which are the images that have more thanthree channels.- and with the lack of the annotated datasets that DCNNs need,so in this paper, we are going to work on methods that will enable us to use thepower of DCNNs with MSI.Keywords:Multi-Spectral Images·Synthetic imagery·Aerial Images·ImageSegmentation.

## Dataset Overview

RIT-18 is a high-resolution benchmark, designed to evaluate the semantic seg-mentation  of  MSI,  collected  by  a  UAS.  multispectral  data  set  for  validation.Compared with other more popular multispectral/hyperspectral data sets, themain advantage of RIT-18 is that the training and testing sets are separated.Unfortunately the ground truth for the testing set is not published This is anexcellent characteristic. Current hyperspectral data sets usually consist of a sin-gle image that is randomly sampled for training and testing sets.The Dataset is a six-band (channels) multispectral data set covering visible andnear-infrared regions. Because the ground truth for the testing set is not pub-lished, here, we use the original validating set for testing. The size of trainingdata  is  9394×5642,  that  of  validation  data  is  8833×6918  and  the  test  data  is 12446x7654.

## Proposed Method with LinkNet as State of Art

The main idea to start solving an image segmentation problem is to pick one of the famous architecture in this field and modify it, bychanging the encoder or use one of the other machine learning technique.The proposed model is to use LinkNet[7] which is a novel deep neural networkarchitecture  which  allows  it  to  learn  without  any  significant  increase  in  num-ber of parameters, and it must must be faster because it has much less numberof parameters than the other model and that’s lead to work efficiently on theembedded devices or with drones

## Experiments and results

During the training processes, I tried manually different learning rates (1-2, 1e-3, 1e-4) with Adam Optimizer and Stochastic gradient descent using batch size (16, 32, 64) and Regularization using weight-decay (1e-2, 1e-3, 1e-4). And the best Average Accuracy is 27%, and here I choose AA instead of other mercies like F1-score to compare results with the CoinNet in the literature [7] because they tested on the "original" validation data with 52% with considering some differences in the classes appearance during the patching process.
In general the method perform well when materials are conjoint to large areas.However, the results in some small-scale classes are unwarranted. For example, class “Person” and “Buoy” are seldom correctly classified. This drawback is can be explain that during the encoder process small materials can hardly be observed before upsampling. Since the spatial resolution of RIT-18 is 4.7 cm, a single “Person” may account for only dozens of pixels.

#### If you find my work useful for your research, please consider citing it and/or letting me know. I would greatly appreciate it.