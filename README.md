# Quantum Variational Classifier with 24 Parameters
First notebook Train QNN (Quantum Neural Network)
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

