# Neural Net Visualizer

A browser-based tool for training and visualizing neural networks. Built as a hands-on companion to Andrew Ng's Intro to Generative AI course.

**Live app:** https://sushmitavnaik.github.io/nn-visualizer

---

## What it does

You can train a real neural network in your browser, watch it learn step by step, and understand what is happening at every stage. No installation required. No backend. Everything runs locally in your browser using TensorFlow.js.

You can use the built-in datasets or upload your own CSV file. The network automatically adjusts to however many input columns your data has.

---

## Features

**Data**
- Built-in datasets: spiral, circle, and XOR
- CSV upload with drag and drop
- Supports any number of input columns
- Automatic 80/20 train/test split, or upload your own separate test file
- Column picker to choose which two features to visualize on the decision boundary

**Training**
- Real neural network training using TensorFlow.js
- Adjustable learning rate, epochs, and batch size
- Live loss chart showing training accuracy and test accuracy as separate lines
- Overfitting detection with a plain English alert and specific suggestions for what to fix

**Network settings**
- 1 to 4 hidden layers
- 2 to 8 neurons per layer
- ReLU, Sigmoid, or Tanh activation functions
- Architecture presets for common configurations

**Visualization**
- Animated network diagram where line color shows weight strength (red = strong, blue = weak) and nodes pulse as weights update during training
- Live decision boundary updated every 5 epochs
- Backpropagation gradient magnitude bars showing which layers are learning the most
- Multi-class decision boundary drawn in up to 5 distinct colors

**Multi-class classification**
- Supports 2 to 5 output classes
- Softmax output layer for 3 or more classes, Sigmoid for 2
- Class probability display after training showing confidence for each class
- Auto-detects class count from uploaded CSV data

**Comparison mode**
- Train two different architectures on the same data at the same time
- Side by side test accuracy results showing which one won

**Learning companion**
- Course progress sidebar tracking concepts as you use the app
- Scoring system with badges for milestones like achieving 80% accuracy, discovering overfitting, or training a deep network
- Failure diagnosis explaining in plain English why a network is struggling and what to change
- Optional AI explanations after each training run using your own Anthropic API key (your key stays in your browser only)

---

## How to use it

1. Open the live app link above
2. Pick a dataset or upload your own CSV
3. Set the number of classes
4. Adjust the network shape and training settings
5. Hit Train

Nothing to install.

---

## Uploading your own data

Your CSV needs to follow this format:

```
feature1, feature2, ..., label
0.5, 0.3, 1
-0.2, 0.8, 0
0.1, -0.4, 1
```

- Any number of feature columns
- Last column must be the label (0 or 1 for binary, 0 to 4 for multi-class)
- First row must be column headers
- Minimum 20 rows recommended

Your data never leaves your device. Everything runs in your browser.

---

## How it compares to TensorFlow Playground

Google's TensorFlow Playground is the most well-known neural network visualizer. This comparison is based on the official TF Playground at playground.tensorflow.org and its public GitHub repository.

| Feature | TF Playground | This tool |
|---|---|---|
| Upload your own CSV | No | Yes |
| Separate test file upload | No | Yes |
| Multi-class classification | No (binary only) | Yes (2 to 5 classes) |
| Side by side architecture comparison | No | Yes |
| Explicit overfitting alert with suggestions | No | Yes |
| Backpropagation gradient magnitude display | No | Yes |
| Failure diagnosis with specific fix suggestions | No | Yes |
| AI plain English explanations | No | Yes |
| Scoring and course progress tracking | No | Yes |
| Train/test split | Yes | Yes |
| Decision boundary | Yes | Yes |
| Loss chart | Yes | Yes |
| Adjustable learning rate and batch size | Yes | Yes |
| Neuron activation visualization | Yes | Yes |
| Regression mode | Yes | No (classification only) |
| Feature engineering inputs | Yes | No |
| Noise slider | Yes | No |
| Regularization (L1/L2) | Yes | No |

---

## Built with

- TensorFlow.js for all neural network math and training
- Chart.js for the loss and accuracy chart
- PapaParse for CSV parsing
- SVG for the network diagram and decision boundary
- Anthropic Claude API for optional plain English explanations (user-supplied API key)
- Hosted on GitHub Pages

No frameworks. No build step. One HTML file.

---

## Background

This was built while studying Andrew Ng's Intro to Generative AI certification. Each phase of the project maps to a concept from the course: network architecture, forward pass, gradient descent, backpropagation, overfitting, and multi-class classification. Building it phase by phase made the concepts stick in a way that reading about them alone does not.

---

## Phases

The project was built incrementally over 7 phases:

- Phase 1: Static network diagram with weight initialization options and parameter counting
- Phase 2: Forward pass animation showing how a signal flows through the network step by step
- Phase 3: Live training loop with loss chart and built-in dataset selection
- Phase 4: Decision boundary visualization and backpropagation gradient display
- Phase 5: CSV upload, dynamic input layers, and train/test split
- Phase 6: Side by side comparison, Claude API explanations, failure diagnosis, scoring
- Phase 7: Multi-class classification with Softmax supporting 2 to 5 classes
