---
title: Install ONNX Runtime
parent: How to
nav_order: 1
---

# Install ONNX Runtime
{: .no_toc }

## Contents
{: .no_toc }

* TOC placeholder
{:toc}

See the [installation matrix](https://onnxruntime.ai) for recommended instructions for desired combinations of target operating system, hardware, accelerator, and language. 

Details on OS versions, compilers, language versions, dependent libraries , etc can be found under [Compatibility](../resources/compatibility.md#Environment-compatibility).


## Requirements
### General
All builds require the English language package with `en_US.UTF-8` locale. On Linux, install [language-pack-en package](https://packages.ubuntu.com/search?keywords=language-pack-en)
by running `locale-gen en_US.UTF-8` and `update-locale LANG=en_US.UTF-8`

###  CUDA build
The GPU (CUDA) package requires:

  |Linux|Windows|
  |---|---|
  |**CUDA 11.0.3 and cuDNN 8.0.2.4**<br/>libcudart 11.0.221<br/>libcufft 10.2.1.245<br/>libcurand 10.2.1.245<br/>libcublasLt 11.2.0.252<br/>libcublas 11.2.0.252<br/>libcudnn 8.0.4|**CUDA 11.0.3 and cuDNN 8.0.2.39**|

    
   CUDA version dependencies for older ONNX Runtime releases are listed [here](../reference/execution-providers/CUDA-ExecutionProvider.html#version-dependency).

### Windows builds
Windows builds require [Visual C++ 2019 runtime](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads)

## Install
The following build variants are available as officially supported packages. Others can be [built from source](../how-to/build.md) from each release branch.

1. Default CPU Provider
2. GPU Provider - NVIDIA CUDA
3. GPU Provider - [DirectML](../reference/execution-providers/DirectML-ExecutionProvider.md) (Windows) - *recommended for optimized performance and compatibility with a broad set of GPUs on Windows devices*

*Note: Dev builds created from the master branch are available for testing newer changes between official releases. Please use these at your own risk. We strongly advise against deploying these to production workloads as support is limited for dev builds.*

|Repository|Official build|Nightly build|
|---|---|---|
|Python|If using pip, run `pip install --upgrade pip` prior to downloading.||
||CPU: [**onnxruntime**](https://pypi.org/project/onnxruntime)| [ort-nightly (dev)](https://test.pypi.org/project/ort-nightly)|
||GPU: [**onnxruntime-gpu**](https://pypi.org/project/onnxruntime-gpu) | [ort-gpu-nightly (dev)](https://test.pypi.org/project/ort-gpu-nightly)|
|C#/C/C++|CPU: [**Microsoft.ML.OnnxRuntime**](https://www.nuget.org/packages/Microsoft.ML.OnnxRuntime) | [ort-nightly (dev)](https://aiinfra.visualstudio.com/PublicPackages/_packaging?_a=feed&feed=ORT-Nightly)|
||GPU: [**Microsoft.ML.OnnxRuntime.Gpu**](https://www.nuget.org/packages/Microsoft.ML.OnnxRuntime.gpu)|[ort-nightly (dev)](https://aiinfra.visualstudio.com/PublicPackages/_packaging?_a=feed&feed=ORT-Nightly)|
|Java|CPU: [**com.microsoft.onnxruntime/onnxruntime**](https://search.maven.org/artifact/com.microsoft.onnxruntime/onnxruntime)|
||GPU: [**com.microsoft.onnxruntime/onnxruntime_gpu**](https://search.maven.org/artifact/com.microsoft.onnxruntime/onnxruntime_gpu)|
|nodejs|CPU: [**onnxruntime**](https://www.npmjs.com/package/onnxruntime)|
|Other|[Contributed non-official packages](https://docs.microsoft.com/en-us/windows/ai/windows-ml/get-started-uwp) (including Homebrew, Linuxbrew, and nixpkgs).<br/>*These are not maintained by the core ONNX Runtime team and may have limited support; use at your discretion.*|


## Docker Images
* [ONNX-Ecosystem](https://github.com/onnx/onnx-docker/tree/master/onnx-ecosystem): Includes ONNX, ONNX Runtime (CPU, Python), dependencies, tools to convert from various frameworks, and Jupyter notebooks to get started
* [Dockerfiles for ONNX Runtime](https://github.com/microsoft/onnxruntime/tree/master/dockerfiles)

