# Vehicle Detection

## Data Summary and Classification
The main goal of this project is to learn feature extraction and using those features to identify the vehicles on the road. Execution of 
the project can be found in the following [ipython notebook](https://github.com/suji0131/Vehicle_Detection/blob/master/Vehicle_Detection.ipynb). Udacity car and not cars data set is used. This data looks like below:
![SampleData](https://github.com/suji0131/Vehicle_Detection/blob/master/output_imgs/DataSumm.png)

HOG feature of all the data is extracted using hog function from skimage library. I found following parameter combination to be optimal after trail and error. Color space used is 'YUV', orientation is 11, pix per cell is 16, cell per block is 2 and hog channel is set to two.
![FeatureAndHOGimage1](https://github.com/suji0131/Vehicle_Detection/blob/master/output_imgs/hog1.png)
![FeatureAndHOGimage2](https://github.com/suji0131/Vehicle_Detection/blob/master/output_imgs/hog2.png)

Training and testind data sets are created and a Linear Support Vector Classifier is trained on them. Classifier has an accuracy of 98 
percent. Deep learning can be used for classification, however, SVM is faster to train (it took under a second) and it also gave pretty 
good accuracy. The classifier is working as expected and using a simple sliding window it was able to detect the cars, see below image.
![Classifer_]()

## Vehicle Detection
For vehicle detection, a small window is slide through the selected part of the image. This sliding window starts at a given starting 
location (ystart) and stops at the given stopping location (ystop). This process is done roughly four or five times from different starting
locations. The entire search boxes looks like below:
![entiresearchwindow](https://github.com/suji0131/Vehicle_Detection/blob/master/output_imgs/searcharea.png)

A heat map is used to eliminate the chance of wrong detection. This is where starting sliding window at different locations is useful. Threshold limit for car detection is 2 i.e., a car should be detected atleast twice to be classified as car. This eliminates false positives. Scipy label function is then used to extract the labels in the heat map. Final rectangles are drawn around these.

Heatmap initial looks like below:

![HeatMap1](https://github.com/suji0131/Vehicle_Detection/blob/master/output_imgs/heatmap.png)

Heapmap after thresholding looks like below:

![Heatmap2](https://github.com/suji0131/Vehicle_Detection/blob/master/output_imgs/heatmapthres.png)

Image looks like this after lable extraction:

![lable](https://github.com/suji0131/Vehicle_Detection/blob/master/output_imgs/labels.png)

Detected cars look like below:

![DetectCars](https://github.com/suji0131/Vehicle_Detection/blob/master/output_imgs/detectingcars.png)

Below image displays detection on every test image:

![all_imgs](https://github.com/suji0131/Vehicle_Detection/blob/master/output_imgs/1alltest_imgs.png)

Video can be found [here]().
