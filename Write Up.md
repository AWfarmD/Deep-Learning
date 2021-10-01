## Pneumonia X-ray Classification

**Abstract**

The goal of this project was to build a deep learning model to classify if a patient is healthy or has pneumonia through X-ray images.  I worked with the Chest X-ray Images dataset from [Kaggle](https://www.kaggle.com/tolgadincer/labeled-chest-xray-images) utilizing simple convolution neural network and transfer learning to achieve this goal.

**Design**

About 1.3 million people were diagnosed with pneumonia in an emergency department during 2017, and about 50,000 people die from the disease each year in the United States. <sup>1</sup> Timely and accurate diagnosis are crucial for the outcome of the disease.  A deep learning diagnosis system may have the potential to aid in rapid evaluation of the chest X-ray and lead to better outcomes.

**Data**

I worked with the Chest X-ray Images dataset from Kaggle for the project.  The data set consists of two folders: train folder contains 3,883 images with pneumonia and 1,349 images without, and the test folder contains 390 images with pneumonia and 234 images without.  The train folder was then split to 80% training data and 20 % validation data.

**Methodology**

I first built a baseline CNN model consists of four convolutional blocks(Conv2D + MaxPooling2D), followed by a Flatten layer, and then two Dense layers with a Dropout in between, and the model provided a validation accuracy score of 0.98.  

As I performed 6 other models, all of them provided a validation accuracy score of 0.98.  I calculated each of their recall as it is the most important metric to look at because we do not want any patient with pneumonia to leave the hospital without being treated for the disease.  The top three models all have 100% of recall (These are most likely rounded up to 1 by the classification_report function).  I then checked their precision and accuracy, and the top performing model (transfer learning model 3) provides the best precision (89%) and accuracy (92%).

Transfer learning model 3 consists of MobileNetV2 followed by two Dense layers with a Dropout in between, and end with a output Dense layer.

**Tools**

- Pandas for EDA
- Matplotlib for visualization
- Keras for model training

**Communication**

Findings and slides will be presented.





1. Center for Disease Control and Prevention. Disease or Condition of the Week. _Pneumonia_. https://www.cdc.gov/dotw/pneumonia/index.html#:~:text=In%20the%20United%20States%2C%201.3,year%20in%20the%20United%20States. 