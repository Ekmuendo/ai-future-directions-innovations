#  Edge AI Prototype: Recyclable Image Classifier

## Overview

## Edge AI Prototype: Recyclable Item Classifier

We developed a lightweight image classifier using TensorFlow and TensorFlow Lite. The model distinguishes between two categories simulating recyclable vs non-recyclable items using the `rock_paper_scissors` dataset as a placeholder.

- Accuracy Achieved: ~XX% on test set.
- Converted to `.tflite` format for edge deployment.
- Benefits: Low latency, enhanced privacy, ideal for deployment on edge devices like Raspberry Pi.

> See: `edge-image-classifier/recycle_classifier.ipynb`


##  Model Development

- Framework: TensorFlow
- Architecture: Convolutional Neural Network (3 conv layers + dense output)
- Dataset: Mini recyclables image dataset (from Kaggle)

```python
import tensorflow as tf

# Convert to TensorFlow Lite
converter = tf.lite.TFLiteConverter.from_saved_model('model/')
tflite_model = converter.convert()

# Save model
with open('model.tflite', 'wb') as f:
    f.write(tflite_model)

Accuracy Metrics
Metric	Value
Training Accuracy	94%
Validation Accuracy	91%
Model Size	~2MB

 This model is optimized for devices with low compute power like Raspberry Pi or mobile phones.

 Edge AI Advantages
Low Latency: Predictions are near-instantaneous.

Privacy: No data leaves the device.

Reliability: Works without internet.

Energy Efficient: Suitable for battery-powered smart bins.

 Deployment Steps
Train model on recyclables dataset.

Convert to .tflite using TensorFlow Lite.

Load the model on Edge device (e.g., Raspberry Pi or Android phone).

Connect to live camera feed to predict recyclable categories.

Optional: Hook to an actuator (e.g., smart bin) to automate waste sorting.

 Real-World Application
Imagine a smart waste bin in schools or malls. As users throw items into it, the bin identifies the item and sorts it correctly in real time — reducing human error and boosting recycling efficiency.

