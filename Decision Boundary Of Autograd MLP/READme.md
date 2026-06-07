# Autograd Neural Network from Scratch

A minimal implementation of an **automatic differentiation engine** and **multi-layer perceptron (MLP)** built entirely from scratch in Python, inspired by Andrej Karpathy's micrograd project.

This project demonstrates:

* Reverse-mode automatic differentiation (backpropagation)
* Computational graph construction
* Gradient-based optimization
* Fully connected neural networks
* Non-linear activation functions (ReLU)
* Training on a non-linearly separable dataset (concentric circles)
* Decision boundary visualization

---

## Features

### Automatic Differentiation Engine

The `Value` class provides:

* Scalar values
* Computational graph tracking
* Automatic gradient computation
* Backpropagation through arbitrary expressions

Supported operations:

* Addition (`+`)
* Multiplication (`*`)
* Subtraction (`-`)
* Negation (`-x`)
* Power (`**`)
* ReLU activation

Example:

```python
a = Value(2.0)
b = Value(-3.0)

c = a * b + a
c.backward()

print(a.grad)
print(b.grad)
```

---

## Neural Network Architecture

The network is implemented using three building blocks:

### Neuron

A single neuron computes:

```text
ReLU(w·x + b)
```

### Layer

A collection of neurons operating in parallel.

### MLP (Multi-Layer Perceptron)

Stacked layers forming a feed-forward neural network.

Architecture used in this example:

```text
Input (2)
   ↓
Hidden Layer (8)
   ↓
Hidden Layer (8)
   ↓
Output Layer (1)
```

---

## Dataset

The project generates a synthetic **concentric circles dataset**.

Classes:

* Inner circle → label = +1
* Outer circle → label = -1

The dataset is intentionally non-linear, making it a good benchmark for neural networks.

Example visualization:

```text
      ○ ○ ○ ○ ○
   ○             ○
  ○   Inner (+1)  ○
   ○             ○
      ○ ○ ○ ○ ○

   Outer Ring (-1)
```

---

## Loss Function

The model is trained using Mean Squared Error (MSE):

```python
loss = (prediction - target) ** 2
```

Average loss over the dataset:

```python
total_loss = total_loss * (1.0 / len(X))
```

---

## Training

Training procedure:

1. Forward pass
2. Compute loss
3. Zero gradients
4. Backpropagation
5. Gradient descent update

Parameter update rule:

```python
parameter -= learning_rate * gradient
```

Default hyperparameters:

| Parameter     | Value  |
| ------------- | ------ |
| Epochs        | 50     |
| Learning Rate | 0.05   |
| Hidden Layers | [8, 8] |
| Dataset Size  | 100    |

---

## Running the Project

### Requirements

Install dependencies:

```bash
pip install numpy matplotlib
```

### Execute

```bash
python main.py
```

Expected output:

```text
Epoch 0: Loss = ...
Epoch 10: Loss = ...
Epoch 20: Loss = ...
Epoch 30: Loss = ...
Epoch 40: Loss = ...
Epoch 49: Loss = ...
Saved decision boundary plot.
```

---

## Output

After training, the script generates:

```text
decision_boundary.png
```

The image shows:

* Learned decision regions
* Training samples
* Neural network classification boundary

---

## Project Structure

```text
.
├── main.py
├── decision_boundary.png
└── README.md
```

---

## Mathematical Background

### Forward Pass

For a neuron:

```text
z = w₁x₁ + w₂x₂ + ... + b
```

Activation:

```text
a = ReLU(z)
```

### ReLU

```text
ReLU(x) = max(0, x)
```

Derivative:

```text
1 if x > 0
0 otherwise
```

### Backpropagation

Gradients are computed using the chain rule:

```text
dL/dx = dL/dy × dy/dx
```

The computational graph is traversed in reverse topological order.

---

## Learning Goals

This project is useful for understanding:

* How PyTorch autograd works internally
* Reverse-mode differentiation
* Computational graphs
* Backpropagation mechanics
* Neural network training from first principles

---

## Future Improvements

Possible extensions:

* Tanh activation
* Sigmoid activation
* Cross-entropy loss
* Mini-batch gradient descent
* Adam optimizer
* Softmax classifier
* GPU acceleration
* Vectorized operations
* Graph visualization

---

## Inspiration

Inspired by:

* Andrej Karpathy's Micrograd
* Neural Networks: Zero to Hero series
* PyTorch Autograd

---

## License

This project is open-source .

