# Smart-TV Gesture Recognition

Gesture Recognition System for Smart TVs

### Project Overview

Our goal is to develop a gesture recognition feature for smart televisions produced by a leading home electronics company. This feature will allow users to control their TVs using hand gestures captured by the built-in webcam, eliminating the need for a remote control.

### Problem Description

The objective is to create a system capable of identifying five distinct gestures performed by users, each corresponding to a specific command:

- Thumbs up: Increase the volume
- Thumbs down: Decrease the volume
- Left swipe: Rewind 10 seconds
- Right swipe: Fast forward 10 seconds
- Stop: Pause playback

### Dataset Description

We have a dataset comprising several hundred videos, each categorized into one of the five gesture classes. These videos, typically 2-3 seconds in duration, consist of sequences of 30 frames captured by a webcam, mimicking real-world usage scenarios. The dataset is provided in a compressed zip file, containing 'train' and 'val' folders, each with accompanying CSV files. The videos are further organized into subfolders, with each subfolder representing a single gesture instance.

### Dataset Understanding

Each row in the CSV files corresponds to a video and contains three key pieces of information: the subfolder name containing the video frames, the gesture label, and a numeric label representing the gesture class (0-4). It's important to note that while all frames within a video subfolder share the same dimensions, different videos may have varying dimensions, necessitating preprocessing steps for standardization.

### Model Architecture

We explore two commonly used architectures for video analysis:

1. Standard CNN + RNN architecture: This approach involves using a convolutional neural network (CNN) to extract feature vectors from individual frames, followed by feeding these vectors into a recurrent neural network (RNN) for temporal analysis. The RNN output is then passed through a softmax layer for classification.

2. 3D convolutional network: Unlike traditional 2D convolutions, 3D convolutions operate in three dimensions (x, y, and z), making them suitable for processing video data directly. Each video, treated as a sequence of RGB frames, is represented as a 4-D tensor input to the network.

### Model Evaluation

We implement both architectures using the Keras API with TensorFlow backend. Key steps include reading and preprocessing images, data augmentation if necessary, defining appropriate model parameters (batch size, epochs, image size, etc.), and experimenting with different model configurations.

### Conclusion

Conv3D model gave the Validation Accuracy of 0.80. The model used was intermediate one which had training accuracy of 0.98 and validation accuracy of 1.00. Since, the accuracies are close to each other, the model is not overfitting.