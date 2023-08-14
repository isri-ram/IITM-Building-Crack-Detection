# IIT-Madras Shaastra Hackathon Building Crack Detection

We are using a modified Resnet50 model to detect cracks in concrete structures. Larger images will be cut down into equal patches. Image as well as video can be given as input. However, there might be some lag when we use video.

<h3>Dataset Description:</h3>

**Dataset:** https://www.kaggle.com/datasets/xinzone/surface-crack

Training Data - split into 2 classes: Positive and Negative with 300 images in each of size 224x224

Test Data - 2 classes: Positive and negative with 100 images in each of size 224x224

Validation Data - 2 classes: Positive and negative with 100 images in each of size 224x224

Predict Set - 6 images of size 4800x3200

Due to the small number of images in both classes, we're performing data augmentation.

<h3>Data Augmentation:</h3>

Methods: 
         
* rotation_range = 3
         
* vertical_flip
         
* horizontal_flip
         
* brightness_range = (0.5, 1.2)
         
**After Augmentation:**

Training Data: augmented to 23,907 images in each class

Test Data: augmented to 7232 images in each class

Validation Data: augmented to 7248 images in each class


**Model Architecture:**

Model: Resnet50(Modified)

Subsequent layers: Dense layer of size 2048, Dense layer of size 128, softmax layer for 2 classes
Optimizer: Adam - learning rate 0.001

<h3>Results</h3>
Metrics for the trained model

![Screenshot_20230121_092429](https://user-images.githubusercontent.com/81284513/213842582-88ab274f-1aa4-4e95-8dca-710115909517.png)

Sample training images:

![image](https://user-images.githubusercontent.com/81284513/213267807-47243ad1-a49f-4981-9423-26bd1d1193a2.png)

![image](https://user-images.githubusercontent.com/81284513/213267917-a27004b9-5f05-4260-9038-5d2cccb5a3fc.png)


Sample prediction with image:

<img src="https://user-images.githubusercontent.com/81284513/213268087-e0521485-def3-4b5a-8602-1baff377bfca.png" width="500" height="500">

<h3>Prediction: Cracked</h3>
