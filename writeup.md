# Vehicle Detection

## Data Summary and Classification
The main goal of this project is to learn feature extraction and using those features to identify the vehicles on the road. Execution of 
the project can be found in the following [ipython notebook](). Udacity car and not cars data set is used. This data looks like below:
![SampleData]()

HOG feature of all the data is extracted using hog function from skimage library, parameters used will be discussed below. 
![FeatureAndHOGimage1]()
![FeatureAndHOGimage2]()

Training and testind data sets are created and a Linear Support Vector Classifier is trained on them. Classifier has an accuracy of 98 
percent. Deep learning can be used for classification, however, SVM is faster to train (it took under a second) and it also gave pretty 
good accuracy.

## Vehicle Detection
For vehicle detection, a small window is slide through the selected part of the image. This sliding window starts at a given starting 
location (ystart) and stops at the given stopping location (ystop). This process is done roughly four or five times from different starting
locations. The entire search boxes looks like below:
![entiresearchwindow]()

Detected cars look like below:
![DetectCars]()

