## Deep Learning Write Up

**Abstract**

The goal of this project was to build a deep learning model to classify if a patient is healthy or has pneumonia through X-ray images.  I worked with the Chest X-ray Images dataset from [Kaggle](https://www.kaggle.com/tolgadincer/labeled-chest-xray-images), utilizing simple convolution neural network and transfer learning to achieve this goal.

**Design**

About 1.3 million people were diagnosed with pneumonia in an emergency department during 2017, and about 50,000 people die from the disease each year in the United States. <sup>1</sup> Timely and accurate diagnosis are crucial for the positive outcome of the disease.  A deep learning diagnosis system may have the potential to aid in rapid evaluation of the chest X-ray and lead to better outcomes.

**Data**

I worked with the Chest X-ray Images dataset from Kaggle for the project.  The data set consists of two folders: train folder which contains 3,883 images with pneumonia and 1,349 images without, and the test folder which contains 390 images with pneumonia and 234 images without.  The train folder was then split to 80% training data and 20 % validation data.

**Methodology**

I first built a CNN model consists of four convolutional blocks(Conv2D + MaxPooling2D), followed by a Flatten layer, and then two Dense layers with a Dropout layer in between, and the model provided a validation accuracy score of 0.98.  

I then tried to leverage transfer learning and see if I'm able to build a transfer learning model with a better validation accuracy score. The base model that I used for transfer learning was MobileNetV2 with imagenet as weights.  The first model with transfer learning consists of MobileNetV2 base model, a Flatten layer, and then three Dense layers (two with relu activation, and one with sigmoid activation). It used the adam optimizer and binary crossentropy as the loss function, and reduce learning rate on plateau when validation crossentropy loss does not improve with 3 epochs was applied to it. The model provided a validation accuracy score of 0.98.

I then performed four other transfer learning models, each with the same basic structure as the first model plus different combinations of Dropout layer with different percentage added among the three Dense layers. All four models provided a validation accuracy score of about 0.98, so I calculated each of their recall as it is the most important metric to look at because it is more detrimental to have a patient who is infected with pneumonia to go home without further check up. There were three models with a recall score of 1 (These are most likely rounded up to 1 by the classification report function), so I then checked their precision score, and model 3 provided the best precision score of 0.89. And as the final model, it provided an accuracy score of 0.92 on the test data.

**Tools**

- Pandas for EDA
- Matplotlib for visualization
- Keras/ TensorFlow and Google Colab for model training

**Communication**

Findings and slides will be presented.





1. Center for Disease Control and Prevention. Disease or Condition of the Week. _Pneumonia_. https://www.cdc.gov/dotw/pneumonia/index.html#:~:text=In%20the%20United%20States%2C%201.3,year%20in%20the%20United%20States. 
