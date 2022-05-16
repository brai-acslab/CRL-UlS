# Identification of Crown and Rump in First-Trimester Ultrasound Images using Deep Convolutional Neural Network

# Summary

A Machine Learning Pipeline has been created utilisng 3 Machine Learning Models to identify the Crown and Rump in First-Trimester Ultrasound Images. The Crown and Rump is used to measure the Crown to Rump Length (CRL) which is used to the predict the gestational age of the fetus, this metric is used to inform important decisions in the early pregnancy.

The Machine Learning System segments the fetus in the image using a U-Net Model. The segmented image is then subject to an image classification model that implements a pre-trained CNN model, namely, VGG-16. This model is used to classify the segmented images into ‘Good’ and ‘Bad’. Finally, the segmented images are entered into a pre-trained ResNet34 model that identifies the Crown and Rump regions.

# Image Segmentation Model

Image Segmentation was highlighted in background research as vital for medical imaging. Paper by https://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/ informed of the importance of a U-Net Model. Code was adapted from an existing repositry from Yu-Jen Huang at https://github.com/Huangyuren/unet_SCM which details the implementation of the complex U-Net Model.


# Image Classification Model

The image classification model will classify the segmented images from the U-Net Model into 'Good' and 'Bad' segmentation categories. Different pre-trained architectures, including ResNet50, InceptionV3, VGG-16 and Xception, were evaluated for the performance. With the VGG-16 Model being best suited to perform the classification.

# Identification Model

Existing solutions for a model that identifies two points in an image were limited. The python library Fast.Ai was identified as a solution to this problem due to its use of a function to map coordinates to images for training data and the capability
to deploy pre-trained architecture. Labelling data was created using 'LabelMe' software and the JSON formatted labels were extracted for training.

# Access to the Dataset
Access to the dataset can be reqeusted through the following link: https://www.dropbox.com/sh/j7jizm564c6gu0n/AADGwuorqenNrutWrZNgyfy_a?dl=0 
The request will be reviewed by the dataset owner on a case-by-case basis.
