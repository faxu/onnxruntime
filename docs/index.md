---
title: ONNX Runtime
has_children: false
nav_order: 1
---
# Welcome to ONNX Runtime
{: .no_toc }

ONNX Runtime is an accelerator for machine learning models with multi platform support and a flexible interface to integrate with hardware-specific libraries. ONNX Runtime can be used with models from PyTorch, Tensorflow/Keras, TFLite, scikit-learn, and other frameworks.


## Contents
{: .no_toc }

* TOC placeholder
{:toc}


## ONNX Runtime for Inferencing

ONNX Runtime Inference powers machine learning models in key Microsoft products and services across Office, Azure, Bing, as well as dozens of community projects.

Examples use cases for ONNX Runtime Inferencing include:

* Improve inference performance for a wide variety of ML models
* Run on different hardware and operating systems
* Train in Python but deploy into a C#/C++/Java app
* Train and perform inference with models created in different frameworks

### How it works
{: .no_toc }

The premise is simple. 
1. **Get a model.** This can be trained from any framework that supports export/conversion to ONNX format. See the [tutorials](./tutorials/inferencing) for some of the popular frameworks/libraries. 
2. **Load and run the model with ONNX Runtime.** See the [basic tutorials](./tutorials/inferencing/api-basics.md) for running models in different languages.
3. ***(Optional)* Tune performance using various runtime configurations or hardware accelerators.** There are lots of options here - see [How to: Tune Performance](./how-to/tune-performance.md) as a starting point.

Even without step 3, ONNX Runtime will often provide performance improvements compared to the original framework. 

ONNX Runtime applies a number of graph optimizations on the model graph then partitions it into subgraphs based on available hardware-specific accelerators. Optimized computation kernels in core ONNX Runtime provide performance improvements and assigned subgraphs benefit from further acceleration from each [Execution Provider](./reference/execution-providers).

### >> [Get started with ORT for inferencing](./tutorials/inferencing) <<

---

## ONNX Runtime for Training
Released in April 2021, ONNX Runtime Training provides a one-line addition for existing PyTorch training scripts to accelerate training times. The current support is focused on large transformer models on multi-node NVIDIA GPUs, with more to come. 

### How it works
{: .no_toc }

Using the ORTModule class wrapper, ONNX Runtime for PyTorch runs the forward and backward passes of the training script using an optimized automatically-exported ONNX computation graph. ORT Training uses the same graph optimizations as ORT Inferencing, allowing for model training acceleration. 

 
### >> [Get started with ORT for training](./tutorials/training) <<





