# Crack-Detection-with-Transfer-Learning
Crack detection model using transfer learning based on the Resnet50 model

Dataset: https://www.kaggle.com/datasets/xinzone/surface-crack

Dataset:

Training Data - split into 2 classes: Positive and Negative with 300 images in each of size 224x224

Test Data - 2 classes: Positive and negative with 100 images in each of size 224x224

Validation Data - 2 classes: Positive and negative with 100 images in each of size 224x224

Predict Set - 6 images of size 4800x3200


Data Augmentation:

Methods: 
         
         rotation_range = 3,
         
         vertical_flip=True,
         
         horizontal_flip = True,
         
         brightness_range = (0.5, 1.2))
         

Training Data: augmented to 23,907 images in each class

Test Data: augmented to 7232 images in each class

Validation Data: augmented to 7248 images in each class


Model Architecture:

Base Model: Resnet50, without Dense layers

Subsequent layers: Dense layer of size 2048, Dense layer of size 128, softmax layer for 2 classes
Optimizer: Adam - learning rate 0.001

Formula's used to calculate the Metrics:

Accuracy :  (True Positives + True Negatives)/ True Positives + True Negatives + False Positives + False Negatives

Precision : TruePositives / (True Positives + False Positives)

Recall : TruePositives / (True Positives + False Negatives)

F1Score : (2*Precision*Recall)/(Precision + Recall)

Metrics for trained model

![Screenshot_20230121_092429](https://user-images.githubusercontent.com/81284513/213842582-88ab274f-1aa4-4e95-8dca-710115909517.png)

Sample training images:

![image](https://user-images.githubusercontent.com/81284513/213267807-47243ad1-a49f-4981-9423-26bd1d1193a2.png)

![image](https://user-images.githubusercontent.com/81284513/213267917-a27004b9-5f05-4260-9038-5d2cccb5a3fc.png)


Sample prediction with image:

![image](https://user-images.githubusercontent.com/81284513/213268087-e0521485-def3-4b5a-8602-1baff377bfca.png)

Prediction: Cracked
