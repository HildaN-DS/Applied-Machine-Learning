# Assignment 3 – Training Neural Networks on MNIST

## Course
**DSA 8401 – Applied Machine Learning**  
**Programme:** Master of Science in Data Science and Analytics

## Assignment Overview

This assignment investigates the design, training and evaluation of neural networks using the MNIST handwritten digit dataset.

The work begins with custom fully connected neural networks and progressively examines the effect of:

- network depth and width;
- activation functions;
- gradient behaviour;
- weight initialization;
- optimizers;
- learning rates;
- batch sizes;
- regularization.

After selecting and evaluating the best fully connected model, a classical convolutional neural network is introduced as a benchmark.

## Dataset

The assignment uses the **MNIST handwritten digits dataset**, containing:

- 60,000 training images;
- 10,000 test images;
- grayscale images of size `28 × 28`;
- 10 digit classes from `0` to `9`.

The original training data was split into:

- 55,000 training samples;
- 5,000 validation samples.

The 10,000 test images were kept untouched until final model evaluation.

## Notebook

The complete implementation is available in:

```text
notebook/assignment-03-neural-networks-mnist.ipynb
```

## Technologies

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- TensorFlow / Keras


## Structure

```text
03-Neural-Networks-MNIST/
│
├── README.md
│
├── notebook/
│   └── assignment-03-neural-networks-mnist.ipynb
│
└── reports/
    └── assignment3-Training-Neural-Networks-MNIST-instructions.pdf