# Project: Build a Traffic Sign Recognition Program
The goal of this project is to classify different traffic signs by training deep neural networks

#**Traffic Sign Recognition** 

##Writeup Template

**Build a Traffic Sign Recognition Project**

The goals / steps of this project are the following:
* Load the data set (see below for links to the project data set)
* Explore, summarize and visualize the data set
* Design, train and test a model architecture
* Use the model to make predictions on new images
* Analyze the softmax probabilities of the new images
* Summarize the results with a written report

---
###Writeup / README


###Data Set Summary & Exploration 


I used the numpy library to calculate the size and dimensions of training and test dataset: 

(see output at In [2])

* The size of training set is 34799
* The size of test set is 12630
* The shape of a traffic sign image is (32, 32, 3)
* Number of classes = 43


####2. Visualization of the dataset.

A random image is picked from the training set and the corresponding label is displayed. 

###Design and Test a Model Architecture

####1. The training images are converted from RGB to Gray.

As a first step, I decided to convert the images to grayscale because it would simplify the algorithm and reduce the complexity for computation.

The output at In [3] shows a traffic sign image before and after grayscaling.



####2. LeNet Architecture is used in this model., (See In [6])

layers, layer sizes, connectivity, etc.) Consider including a diagram and/or table describing the final model.

My final model consisted of the following layers:

| Layer         		|     Description	        					                         
|:---------------------:|:---------------------------------------------:
| Input         		| 32x32x3 RGB image   							 
| Convolution 3x3     	| Filter size is 3 x 3, 1x1 stride, Valid padding, outputs 30x30x12
| RELU					|												
| Max pooling	      	| 2 x 2 Filter size, 1x1 stride,  outputs 29x29x12 				
| Convolution 5x5	    | Filter size is 5 x 5, 1x1 stride, Valid padding, outputs 25x25x22     									|
| RELU
| Max pooling           | Filter size is 2x2, 2x2 stride, Valid padding, output = 12x12x22.
| Fully connected		| Output =800        									
| RELU                  | 
| Dropout               | Drop out technique is used to prevent overfitting
| Softmax				| etc.        									
| Fully connected		| Output = 400				|												|
| RELU					|													|
| Dropout               |
| Fully connected       | Output = 43 = number of Labels

####3. To train the model, I used an Adam optimizer with batch size equal to 100, Number of Epochs =17, Learning rate = 0.0005 and sigma =0.01

####4. 

My final model results were:

* Validation set accuracy of 0.97
* Test set accuracy of 0.95


* LeNet Architecture was chosen
* Lenet Architecture has proven to be efficient for Digit recognition. 
  Since the traffic signs mostly consist of shapes, letters and numbers, the computation of weights and biases will be similar.
* The final model's accuracy on the training, validation and test set have been consistent (above 0.93) upon multiple iterations.

###Test a Model on New Images

####1. Ten German traffic signs found on the web were used to test the model. (In [12]):

Here are the results of the prediction:

| Image	with sign Label	|         Prediction	        					
|:---------------------:|:---------------------------------------------:| 
| Yield(13)      		        | Yield (13)  									
| Right Turn(33)     			| Right turn (33)										
| No Entry(17)					| No Entry(17)											
| Pedestrian Crossing(27)	    | Pedestrian Crossing(27)				 				
| Keep Right(38)			    | Keep Right(38)
| Stop(14)                      | Stop(14)
| Children crossing(28)         | Children crossing(28)
| Intersection(11)     		    | Speed Limit-50(2)
| Speed Limit-50(2)             | Speed Limit-50(2)
| General caution(18)           | General caution(18)

The model was able to correctly guess 9 of the 10 traffic signs, which gives an accuracy of 90%. 

####2. Top 5 SoftMax probabilities

For the 7th image (Intersection), the model failed to predict the correct output.


The top 5 SoftMax probabilities were Priority road(12), No passing for vehicles over 3.5 metric tons(10), Roundabout mandatory(40),  Speed Limit-50(2), Speed limit (100km/h)(7)



