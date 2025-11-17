# AI-Generated vs. Real Art Classification
This project aims to classify whether a visual artwork was created by Artificial Intelligence or a human artist using Convolutional Neural Network (CNN) model.

# Project Overview
With advancement of AI tools, AI-generated artwork is becoming popular in digital art world. This study focuses on making the distinction using a deep learning model built with the TensorFlow and Keras libraries.

## Dataset
**Classes:** AiArtData and RealArt.  
**Total Images (Full Set):** Approximately 970 images (622 training + 154 validation + 194 test).  
**Dataset Link:** https://www.kaggle.com/datasets/cashbowman/ai-generated-images-vs-real-images  

## Model Architecture
The model utilizes a standard Convolutional Neural Network (CNN) structure:  
**Input Layer:** Image input size of 150 x 150 x 3.  
**Convolution/Pooling Layers:** Four sequential pairs of Convolutional (Conv2D) and Max Pooling (MaxPooling2D) layers. The number of filters in these layers is 32, 64, 128, and 128, respectively.  
**Flatten Layer:** Converts the convolutional output into a single vector.  
**Dropout Layer:** A dropout rate of 50% is applied to help prevent overfitting.  
**Dense Layers:** A dense layer with 512 neurons (using relu activation) and a single-neuron output layer (using sigmoid activation) for binary classification.  
**Total Parameters:** 3,453,121  
**Optimization and Loss:** adam optimizer and binary_crossentropy loss function were used.  

## Results

The model was trained for 20 epochs and achieved the following performance metrics on test dataset:

**Overall Performance (Test Set)**
Test Loss: 0.7528
Test Accuracy: 0.6289 ($\approx \mathbf{62.89\%}$62.89%)

## Interpretation of Results

**General Performance:** Although the model's accuracy of 62.89% is better than random guessing (50%), it does not demonstrate perfect discriminative power. This suggests that AI-generated art successfully mimics the distinguishing features of real art.  

**Precision vs. Recall:**
AiArtData: The model identified AI art with high recall (0.88). This means a large majority of the AI-generated works in the test set were correctly identified. However, 0.61 precision indicated that some real artworks were incorrectly labeled as "AI-generated".  
RealArt: The model struggled to identify real art. The recall value is quite low (0.32) meaning only 32% of real artworks were correctly identified. This shows that the model misclassified many images belonging to the RealArt class as AiArtData (False Negatives).  

**Future Improvements:** The test results show that the model has difficulty recognizing the Real Art class, resulting a high number of False Negatives. Future work could focus on improving data augmenting techniques, experimenting with different model architectures or using a more balanced and larger dataset to improve performance.  
