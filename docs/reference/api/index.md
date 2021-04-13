---
title: API docs
parent: Reference
has_children: true
nav_order: 1
has_toc: false
---
# APIs

## Inferencing
|API|Supported Versions|Samples|
|---|---|---|
|[C](../reference/api/c-api.md)| | [Samples](https://github.com/microsoft/onnxruntime/tree/master/samples/#CC)|
|[C++](https://github.com/microsoft/onnxruntime/blob/master/include/onnxruntime/core/session/onnxruntime_cxx_api.h)| |[Samples](https://github.com/microsoft/onnxruntime/tree/master/samples/#CC)|
|[C#](../reference/api/csharp-api.md)| | [Samples](https://github.com/microsoft/onnxruntime/tree/master/samples/#C)|
|[Java](../reference/api/java-api.md)|8+|[Samples](https://github.com/microsoft/onnxruntime/tree/master/samples/#Java)| 
|[Python*](https://aka.ms/onnxruntime-python)| 3.6, 3.7, 3.8, 3.9| [Samples](https://github.com/microsoft/onnxruntime/tree/master/samples/#python)|
|[Node.js](../reference/api/nodejs-api.md) |12.x | [Samples](https://github.com/microsoft/onnxruntime/blob/master/samples/nodejs) |
|[WinRT](../reference/api/winrt-api.md) | [Windows.AI.MachineLearning](https://docs.microsoft.com/en-us/windows/ai/windows-ml/api-reference)| [Samples](https://github.com/microsoft/windows-Machine-Learning)|
[Ruby](https://github.com/ankane/onnxruntime) (external project)| 2.4-2.7| [Samples](https://ankane.org/tensorflow-ruby)|


**For Python compiler version notes, see [this page](https://github.com/microsoft/onnxruntime/tree/master/docs/Python_Dev_Notes.md)*

## Training
The ORT Training API is a PyTorch frontend that implements the torch.nn.Module interface. For example usage, see
[ONNX Runtime Training Examples](https://github.com/microsoft/onnxruntime-training-examples). 