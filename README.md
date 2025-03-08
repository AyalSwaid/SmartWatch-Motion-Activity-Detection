![image](https://github.com/user-attachments/assets/c1650cf5-de2a-440a-8206-e6bc91a337cf)# SmartWatch-Motion-Activity-Detection
Predict human activities (e.g., walking, running, climbing stairs) from smartwatch IMU sensor data (accelerometer and gyroscope sequences in X, Y, Z axes). This is a research project, which means it includes baseline model and testing different approaches. 

# Dataset

Sensors used: Recorded data of Accelerometer and Gyroscope sensors from 8 users.

Data Format: Sequences of XYZ coordinates recorded from smartwatches.

Activities: 18 different types (e.g., walking, running, stairs climbing).

Data Split: 40% labeled, 60% unlabeled data, further divided into training, validation, and test sets.

![image](https://github.com/user-attachments/assets/02882730-0409-4e05-a708-6aaf47eb4988)



# Task

Classification task to predict user activities based on sensor sequences.
### Example
![image](https://github.com/user-attachments/assets/35612417-9616-41d5-8b56-637a1276890f)


# Models Implemented

## Baseine Naive approach Models:

Naive Bayes: Simple and stable, performs best with global sequence-level features.

XGBoost: Higher accuracy but prone to overfitting with more complex features.

We consider accuracy of 48% as our baseline, here is a table summarizes the performance, more details are in the pdf file.
![image](https://github.com/user-attachments/assets/8eceeba5-3f78-4a04-8d81-442f3eff115e)


## Deep Learning Models

### 1D CNN

Architecture: Three convolutional layers with max pooling, adaptive pooling, dropout, and fully connected layers.
![image](https://github.com/user-attachments/assets/528e0c3f-2468-4bc1-b3f5-728769c65e49)


Results:

![image](https://github.com/user-attachments/assets/2ce7ec83-03d9-4c9b-b18a-df8a37735961)


### GRU-Based Model

Architecture: GRU layer, linear transformation, ReLU, batch normalization, dropout, and fully connected layers.
![image](https://github.com/user-attachments/assets/bb320321-148b-47ee-82ef-8dda673373fc)


Results: Better generalization

![image](https://github.com/user-attachments/assets/bcfe47e5-6891-4fda-a06b-afab7ff7c317)


Autoencoder + Neural Network

Method: Self-supervised embeddings extracted via LSTM-based autoencoder.

![image](https://github.com/user-attachments/assets/6c36f712-46ba-49d5-b308-6404adaca129)


applied two methods to improve model generalization:

Normalization: Implemented Min-Max scaling.
Data Augmentation:
* Added Gaussian noise (mean=0, std=0.05).
* Included uniform distribution noise (range: -0.03 to 0.1).
* Applied random cropping, replacing cropped sections with zeros.
These augmentations were designed to enhance model generalization and performance.










