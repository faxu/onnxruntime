---
title: Accelerate PyTorch models
grand_parent: Tutorials
parent: Inferencing
nav_order: 2
---
# Accelerate PyTorch model inferencing
{: .no_toc }

ONNX Runtime can be used to accelerate PyTorch models inferencing. Models should first be exported to ONNX format through [torch.onnx](https://pytorch.org/docs/stable/onnx.html).

## Contents
{: .no_toc }

* TOC placeholder
{:toc}

## Convert model to ONNX

* [Export PyTorch model with custom ops](./export-pytorch-model.md)

## Accelerate PyTorch model inferencing

* [Inference: accelerate reduced size BERT model through quantization](https://github.com/microsoft/onnxruntime/blob/master/onnxruntime/python/tools/quantization/notebooks/Bert-GLUE_OnnxRuntime_quantization.ipynb)

## Accelerate PyTorch model training

* [Training: accelerate pre-training of large BERT model](https://github.com/microsoft/onnxruntime-training-examples/tree/master/nvidia-bert)