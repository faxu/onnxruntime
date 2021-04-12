---
title: Inference
parent: Get Started
nav_order: 3
---

# Use ONNX Runtime for Inference


## API Documentation

|API|Supported Versions|Samples|
|---|---|---|
|[Python](https://aka.ms/onnxruntime-python)| 3.6, 3.7, 3.8, 3.9) [Python Dev Notes](https://github.com/microsoft/onnxruntime/tree/master/docs/Python_Dev_Notes.md)| [Samples](https://github.com/microsoft/onnxruntime/tree/master/samples/#python)|
|[C#](../reference/api/csharp-api.md)| | [Samples](https://github.com/microsoft/onnxruntime/tree/master/samples/#C)|
|[C++](https://github.com/microsoft/onnxruntime/blob/master/include/onnxruntime/core/session/onnxruntime_cxx_api.h)| |[Samples](https://github.com/microsoft/onnxruntime/tree/master/samples/#CC)|
|[C](../reference/api/c-api.md)| | [Samples](https://github.com/microsoft/onnxruntime/tree/master/samples/#CC)|
|[WinRT](../reference/api/winrt-api.md) | [Windows.AI.MachineLearning](https://docs.microsoft.com/en-us/windows/ai/windows-ml/api-reference)| [Samples](https://github.com/microsoft/windows-Machine-Learning)|
|[Java](../reference/api/java-api.md)|8+|[Samples](https://github.com/microsoft/onnxruntime/tree/master/samples/#Java)| 
[Ruby](https://github.com/ankane/onnxruntime) (external project)| 2.4-2.7| [Samples](https://ankane.org/tensorflow-ruby)|
|[Javascript (node.js)](../reference/api/nodejs-api.md) |12.x | [Samples](https://github.com/microsoft/onnxruntime/blob/master/samples/nodejs) |



## Supported Accelerators

[Learn about Execution Providers](../reference/execution-providers)

|CPU|GPU|IoT/Edge/Mobile|Other|
|---|---|---|---|
|Default CPU - *MLAS (Microsoft Linear Algebra Subprograms) + Eigen*|NVIDIA CUDA|[Intel OpenVINO](../reference/execution-providers/OpenVINO-ExecutionProvider.md)||
|[Intel DNNL](../reference/execution-providers/DNNL-ExecutionProvider.md)|[NVIDIA TensorRT](../reference/execution-providers/TensorRT-ExecutionProvider.md)|[ARM Compute Library](../reference/execution-providers/ACL-ExecutionProvider.md) (*preview*)|[Rockchip NPU](../reference/execution-providers/RKNPU-ExecutionProvider.md) (*preview*)|
|[Intel nGraph](../reference/execution-providers/nGraph-ExecutionProvider.md)|[DirectML](../reference/execution-providers/DirectML-ExecutionProvider.md)|[Android Neural Networks API](../reference/execution-providers/NNAPI-ExecutionProvider.md) (*preview*)|[Xilinx Vitis-AI](../reference/execution-providers/Vitis-AI-ExecutionProvider.md) (*preview*)|
||[AMD MIGraphX](../reference/execution-providers/MIGraphX-ExecutionProvider.md) (*preview*)|[ARM-NN](../reference/execution-providers/ArmNN-ExecutionProvider.md) (*preview*)|


## Deploying ONNX Runtime
ONNX Runtime is cross-platform can be deployed to cloud, client, mobile, and Edge/IoT solutions. See the [Tutorials section](../tutorials) for examples.

## Build from Source

For production scenarios, it's strongly recommended to build only from an [official release branch](https://github.com/microsoft/onnxruntime/releases). 

See [Build from source](../how-to/build.md) for detailed instructions.
