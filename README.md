# Facial-Recognition-using-FaceNet
facial recognition using FaceNet on LFW dataset

# Data Mining Project - semester 6 FAST-NU Islamabad, Pakistan
By:
Muhammad Bilal - 17i0317
Shayaan Farooq - 17i0093
Muhammad Huzaifa - 17i0305

# Project specifications:
-Runs on LFW data set (with a 160*160 centre crop)
-epochs = 10
-margin = 0.2
-offline triplet loss
-ZFNet 3 path siamese network
-KNN - classifier

# Running the code:
-It is an ipynb file, so keep running the cells until you reach the cell labelled "set paths". This specifies the dataset and takes a couple of seconds.
-Run the next couple of cells, until you read the cell labelled "training model for offline triplets/siamese network":
	-This cell will start the training, it takes about 230 seconds per epoch and it runs for a total of 10 epochs.
-I am  not attaching a trained model, howeve, If you wish to only load the model and not run the entire training again:
	-skip the training cell and just run the next cell labelled "loading saved model parameters".(The directory is according to my kaggle notebook,
	 so you will probably have to change it).
-Run the next three cells, they essentially pass all the train and test datapoints through the trained model to create respective embeddings.
-The next cell labelled "train accuracy" will give you the training accuracy.
-The next cell labelled "revised test accuracy" will give you the testing accuracy.
-The last cell is for saving the trained model.

# Something special:
The way we pick our triplets is a bit different. we randomly create a train test split. In which we choose those classes as test data that have atleast 20 images,
and we train the model on the remaining data. This split allows us to create around 30,000 triplets that are unique for every train. Even if you are just 
testing the accuracy and not training a model, the test classes you will get will always be random. The test accuracy is obtained by training the KNN classifier 
on some of the test data images while the rest are used for actual testing.


