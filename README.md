# Diagnosing Tumor in the Brain Using Image Processing and Machine Learning
In this project, healthy and tumor brain MR images were processed using image processing. Thus, rapid diagnosis of brain tumor became easier. 


## Used Libraries
I developed the project in Google Colab environment. Also I imported Keras library because of it is the optimal library for creating deep learning models. I used the VGG19 Model and it gives more realistic results than the other models. In order to see the images, I used OpenCV library. Also, I used OS library in order to show the images that are saved in the folders. 


## Train/Test Split
With the help of ImageDataGenerator, images that were splited before as train and test are called. The Batch size has been chosen as 16 and target size has been chosen as (224x224). It can be seen below the examples from the both classes.  

Example for "Yes"

<p align="center">
<img src="img/Y4.jpg">
</p>

Example for "No" 

<p align="center">
<img src="img/3no.jpg">
</p>


## Generating Model and Preparation for Training
The input size of image for VGG19 has been chosen as 224x224x3. After training with VGG19 model, a deep learning model has been generated by using inputs as the output from VGG19 model. This deep learning model consists of a flatten method to get one dimensional input. Then, the dropout process has been applied to prevent possible overfitting problem. And last, a dense layer has been added with one unit to classify and its activation function is sigmoid.

The model has been compiled with loss function equals to binary_crossentropy which is used for binary classification problems. Its optimizer equals to Adam optimizer. The metric to calculate the model's efficiency has been chosen as Accuracy. 

<table>
  
  <tr>
    <td> VGG19 </td>
  </tr>
  <tr>
    <td> Flatten </td>
  </tr>
  <tr>
    <td> Dropout 0.4 </td>
  </tr>
  <tr>
    <td> 1-Dense-Sigmoid </td>
  </tr>
  
</table>

## Training Process
The training has been begun with using 60 epochs. Loss and accuracy for training set respectively equals to 0.6757, 0.6856 and for validation set respectively equals to 0.4282, 0.8333 for the first epoch. And for the last epoch,  loss and accuracy for training set respectively equals to 0.0344, 0.9956 and for validation set respectively equals to 0.1787, 0.9167. The training has been run for three hours by using Google Colab's CPU. 

## Training Process and Result
According to the test results, the model has been performed %83 of accuracy and the loss value is 0.25. The result can be improved by increasing the number of data and using different parameters (loss, activation function, optimizer, batch size, epoch number etc.).

## Prediction
After the training process was completed, a prediction process was performed on the data shown above and the tumor was found. The size of the image has been adjusted to 224x224 by using OpenCV library. Then, it reshaped to a tensor to prediction process. With predict method from Keras library, the prediction has been done. The result 0 denotes without tumor, the result 1 denotes with tumor. Then this prediction process has been applied to all the images that were splited for testing. Some of the results have been shown below. 

<p align="center">
<img src="img/Fotoram.io (2).jpg">
</p>





