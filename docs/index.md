---
title: Home
nav_order: 0
nav_exclude: true
---

# Welcome to ONNX Runtime!

**ONNX Runtime** is a cross-platform machine learning **inferencing and training accelerator** for models from popular ML/DNN frameworks, including PyTorch, TensorFlow/Keras, scikit-learn, and more.

ONNX Runtime provides computation acceleration through [graph transformations](./resources/graph-optimizations.html) and optimizations, and is able to take advantage of hardware accelerators on a variety of devices through its [Execution Provider interface](./reference/execution-providers)).

Some examples of problems that ONNX Runtime can help with:

* Improve inference performance for a wide variety of ML models (see [acceleration tutorials](./tutorials/acceleration) to get started)
* Reduce time and cost of training large models [see [ORT Training examples](https://github.com/microsoft/onnxruntime-training-examples)]
* Train in Python but deploy into a C#/C++/Java app
* Run on different hardware and operating systems [see [portability tutorials](./tutorials/portability)]
* Train and perform inference with models created in different frameworks

## ONNX Runtime Inferencing
[ONNX Runtime inference](get-started/inference.md) APIs are stable and production-ready since October 2019 [1.0 release](https://github.com/microsoft/onnxruntime/releases/tag/v1.0.0). ONNX Runtime powers machine learning models in key Microsoft products and services across Office, Azure, Bing, and more, as well as dozens of community projects. 

## ONNX Runtime Training
[ONNX Runtime training](get-started/training.md) for PyTorch was released in April 2021, providing a one-line addition for PyTorch training workflows to accelerate training times. Current support is focused on large transformer models on multi-node NVIDIA GPUs, with more to come.

Using the ORTModule class wrapper, ONNX Runtime for PyTorch runs the forward and backward passes of the training script using an optimized automatically-exported ONNX computation graph. ORT Training uses the same graph optimizations as ORT Inferencing, allowing for model training acceleration. 