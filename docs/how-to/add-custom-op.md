---
title: Use custom operators
parent: How to
nav_order: 5
---
# Custom operators
ONNX Runtime provides options to include custom operators that are not official ONNX operators. The [contrib ops domain](https://github.com/microsoft/onnxruntime/blob/master/onnxruntime/contrib_ops) contains some common non-official ops, however it's not recommended to add operators here to avoid increasing binary size of the core runtime package.
## Contents
{: .no_toc }

* TOC placeholder
{:toc}

## Register a custom operator
A new op can be registered with ONNX Runtime using the Custom Operator API or RegisterCustomRegistry API.

### [Recommended] Custom Operator API

Use the custom operator C/C++ API (onnxruntime_c_api.h)

1. Create an OrtCustomOpDomain with the domain name used by the custom ops
2.  Create an OrtCustomOp structure for each op and add them to the OrtCustomOpDomain with OrtCustomOpDomain_Add
3.  Call OrtAddCustomOpDomain to add the custom domain of ops to the session options
  
See [this](https://github.com/microsoft/onnxruntime/blob/master/onnxruntime/test/shared_lib/test_inference.cc) for examples called `MyCustomOp` and `SliceCustomOp` that use the C++ helper API (onnxruntime_cxx_api.h).

You can also compile the custom ops into a shared library and use that to run a model via the C++ API. The same test file contains an example.

The source code for a sample custom op shared library containing two custom kernels is [here](https://github.com/microsoft/onnxruntime/blob/master/onnxruntime/test/testdata/custom_op_library/custom_op_library.cc).

See [this](https://github.com/microsoft/onnxruntime/blob/master/onnxruntime/test/python/onnxruntime_test_python.py) for an example called `testRegisterCustomOpsLibrary` that uses the Python API to register a shared library that contains custom op kernels. Currently, the only supported Execution Providers (EPs) for custom ops registered via this approach are the CUDA and the CPU EPs.

[E2E example: Export and run a PyTorch model with custom op](./export-pytorch-model.html)

#### CUDA custom ops
When a model being inferred on GPU, onnxruntime will insert MemcpyToHost op before a CPU custom op and append MemcpyFromHost after to make sure tensor(s) are accessible throughout calling, meaning there are no extra efforts required from custom op developer for the case.

When using CUDA custom ops, to ensure synchronization between ORT's CUDA kernels and the custom CUDA kernels, they must all use the same CUDA compute stream. To ensure this, you may first create a CUDA stream and pass it to the underlying Session via SessionOptions (use `OrtCudaProviderOptions` struct). This will ensure ORT's CUDA kernels use that stream and if the custom CUDA kernels are launched using the same stream, synchronization is now taken care of implicitly. For a sample, please see how the afore-mentioned `MyCustomOp` is being launched and how the Session using this custom op is created.

### [Alternate] Use RegisterCustomRegistry API

1. Implement your kernel and schema (if required) using the OpKernel and OpSchema APIs (headers are in the include folder).
2. Create a CustomRegistry object and register your kernel and schema with this registry.
3. Register the custom registry with ONNXRuntime using RegisterCustomRegistry API.

[Example](https://github.com/microsoft/onnxruntime/blob/master/onnxruntime/test/framework/local_kernel_registry_test.cc)

## Load operators from the custom op library
*COMING SOON*
