---
title: About
parent: ONNX Runtime
nav_order: 1
---
# Contents
{: .no_toc }

* TOC placeholder
{:toc}

# What is ONNX Runtime?
ONNX Runtime is a software library for accelerating Machine Learning workloads with multi platform support and a flexible interface that allows for compatibility with different hardware.

# ONNX Runtime for Inferencing

ONNX Runtime Inference APIs are stable and production-ready since October 2019. ONNX Runtime powers machine learning models in key Microsoft products and services across Office, Azure, Bing, as well as dozens of community projects. 

Examples use cases for ONNX Runtime Inferencing include:

* Improve inference performance for a wide variety of ML models
* Run on different hardware and operating systems
* Train in Python but deploy into a C#/C++/Java app
* Train and perform inference with models created in different frameworks

## How it works
{: .no_toc }

ONNX Runtime applies a number of graph optimizations on the model graph then partitions it into subgraphs based on available hardware-specific accelerators. Optimized computation kernels in core ONNX Runtime provide performance improvements and assigned subgraphs benefit from further acceleration from each [Execution Provider](../reference/execution-providers).

## Get started with ORT for inferencing
{: .no_toc }

* [Get Started: Inferencing](../tutorials/get-started.html#inferencing)
* [ORT on Mobile](../tutorials/portability.html#mobile)
* [ORT on IoT/Edge](../tutorials/portability.html#iotedge)
* [ORT with Azure Machine Learning](..tutorials/ecosystem.html#azure-machine-learning-services)


# ONNX Runtime for Training
ONNX Runtime Training for PyTorch was released in April 2021, providing a one-line addition for existing PyTorch training scripts to accelerate training times. Current support is focused on large transformer models on multi-node NVIDIA GPUs, with more to come. 

## How it works
{: .no_toc }

Using the ORTModule class wrapper, ONNX Runtime for PyTorch runs the forward and backward passes of the training script using an optimized automatically-exported ONNX computation graph. ORT Training uses the same graph optimizations as ORT Inferencing, allowing for model training acceleration. 

 
## Get started with ORT for training
{: .no_toc }

* Get STarted: Training](../tutorials/get-started.html#training)





