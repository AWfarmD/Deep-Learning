## Deep Learning MVP 

The goal of this project is to build a deep learning model to identify if a patient is healthy or has pneumonia through X ray images.

My baseline CNN model consists of four convolutional layers (Conv2D + MaxPooling2D ), followed by a Flatten, and then two Dense layers with a Dropout in between.  

The model stopped at epochs 18 and provided a validation accuracy score of 0.976. However, when plotting out the binaryentropy loss and accuracy through out the training below, it seems the model is overfitting.

![Crossentropy Loss](https://github.com/AWfarmD/Deep-Learning/blob/main/figures/Crossentropy%20Loss.png?raw=true)

![Accuracy](https://github.com/AWfarmD/Deep-Learning/blob/main/figures/Accuracy.png?raw=true)

My next step is to reduce overfitting with reducing model complexity (lower the number of convo layers and/or lower the number of filters within each convo layer), adding regularization (mainly Dropout), and/or useing image augmentation.  I may also try transfer learning to see if I can further improve the accuracy score.
