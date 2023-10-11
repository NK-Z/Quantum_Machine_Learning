# Quantum Variational Classifier with 24 Parameters
First notebook "Train_QNN.ipynb"(Quantum Neural Network)
This notebook demonstrates the use of a Quantum Variational Classifier (VQC) with 24 trainable parameters. The dataset used is the Iris dataset, which consists of 150 samples, each with four features and three labels.

## Observations from Dataset Description

- There are 150 samples in the dataset.
- Each sample has four features.
- There are three labels in the dataset.
- The dataset is perfectly balanced, with 50 samples in each class.
- Features are not normalized, and their value ranges vary, suggesting the potential benefits of feature scaling.

## Data Preprocessing

The features are normalized using Min-Max scaling to bring them to the same scale.

## Data Visualization

A pairplot is created to visualize the relationships between features, colored by class.

## Train-Test Split

The dataset is split into training and testing sets (80% training, 20% testing).

### Feature Map
Our data is classical, meaning it consists of a set of bits, not qubits. We need a way to encode the data as qubits. This process is called Feature map We usually refer to this mapping as data encoding, data embedding, or data loading. While feature mapping is a common ML mechanism, this process of loading data into quantum states does not appear in classical machine learning as that only operates in the classical world. A ZZ Feature Map with 24 dimensions is used to encode the features.

### Ansatz

An EfficientSU2 Ansatz with 24 parameters is employed. The circuit has 16 trainable weights (`θ[0], ..., θ[23]`).

## Optimization

The COBYLA optimizer is used for training.

## Training

The VQC is constructed with the specified feature map, ansatz, and optimizer. The training process is visualized using a callback function.

## Results

After training, the model's performance is evaluated on both the training and testing sets.

- Quantum VQC on the training dataset: 90.00%
- Quantum VQC on the test dataset:     90.00%

## Note

- The model uses an EfficientSU2 Ansatz with 24 parameters.
- The dataset and code can be found in this repository.

---
Secound notebook is "qnn.ipynb"

Quantum Convolutional Neural Network (QCNN) for Image Classification
Overview
This code implements a Quantum Convolutional Neural Network (QCNN) to classify images as either "1" or "2" in Hindu-Arabic writing. The network is designed to handle both clean images and images with added noise.

## Dependencies
Python 3.x
Libraries: qiskit, sklearn, matplotlib, numpy
## Usage
Run the provided code.
The dataset will be generated, consisting of images of handwritten digits "1" and "2".
The images will be split into training and testing sets.
The QCNN will be trained on the training set.
The accuracy of the model will be evaluated on the test set.
## Code Structure
generate_dataset(num_images): Generates a dataset of images and labels.
conv_circuit(params): Defines a quantum circuit for the convolutional layer.
conv_layer(num_qubits, param_prefix): Creates a quantum circuit for a convolutional layer.
pool_circuit(params): Defines a quantum circuit for the pooling layer.
pool_layer(sources, sinks, param_prefix): Creates a quantum circuit for a pooling layer.
... (other functions for circuit generation and visualization)
## Results
The accuracy of the model on both the training and test sets will be displayed.
Example images from the test set along with the QCNN predictions will be shown.
## Additional Notes
The initial parameters for the QCNN can be loaded from a JSON file named "good starting point.json".
