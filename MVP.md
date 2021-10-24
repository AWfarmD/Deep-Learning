## Deep Learning MVP 

The goal of this project is to build a deep learning model to identify if a patient is healthy or has pneumonia through X ray images.

My baseline CNN model consists of four convolutional layers [Conv2D (each with relu activation) + MaxPooling2D ], followed by a Flatten, and then two Dense layers (one with relu activation and the other with sigmoid activation) with a Dropout layer (0.2) in between.  It used adam opimizer, binary crossentropy as the loss function, and was set to run with 30 epochs with an early stop if validation loss does not improve after 5 epochs. The model stopped at epochs 18 and provided a validation accuracy score of 0.976. 

My next step is to leverage transfer learning with MobileNetV2 as the base model and imagenet as weights to see if I can build a transfer learning model that can provide a better validation accuracy score. 
