---
title: Install
parent: Get Started
nav_order: 1
---

# Install ONNX Runtime
{: .no_toc }

## Contents
{: .no_toc }

* TOC placeholder
{:toc}

Use this guide to install ONNX Runtime and its dependencies, for your target operating system, hardware, accelerator, and language. Details on OS versions, compilers, language versions, dependent libraries , etc can be found here: [Compatibility](../resources/compatibility.md#Environment-compatibility) 

For an overview, see the [installation matrix](https://onnxruntime.ai).


## Requirements
### General
All builds require the English language package with `en_US.UTF-8` locale
   - On Linux, install [language-pack-en package](https://packages.ubuntu.com/search?keywords=language-pack-en)
by running `locale-gen en_US.UTF-8` and `update-locale LANG=en_US.UTF-8`
   - On Windows, 

###  CUDA build
The GPU (CUDA) package requires:

  |Linux|Windows|
  |---|---|
  |CUDA 11.0.3 and cuDNN 8.0.2.4<br/><ul><li> libcudart 11.0.221</li><li>libcufft 10.2.1.245</li><li>libcurand 10.2.1.245</li><li>libcublasLt 11.2.0.252</li><li>libcublas 11.2.0.252</li><li>libcudnn 8.0.4</li></ul>|CUDA 11.0.3 and cuDNN 8.0.2.39|

    
   CUDA version dependencies for older ONNX Runtime releases are listed [here](../reference/execution-providers/CUDA-ExecutionProvider.html#version-dependency).

### Windows builds
Windows builds require [Visual C++ 2019 runtime](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads)

## Install
The following build variants are available as officially supported packages. Others can be built from source from each release branch: see [Build from source](../how-to/build.md)

* Default CPU Provider
* GPU Provider - NVIDIA CUDA
* GPU Provider - DirectML (Windows)
  * *On Windows, the [DirectML execution provider](../reference/execution-providers/DirectML-ExecutionProvider.md) is recommended for optimal performance and compatibility with a broad set of GPUs.*

If using pip, run `pip install --upgrade pip` prior to downloading.

|Repository|Official build|Nightly build|
|---|---|---|
|Python|CPU: [**onnxruntime**](https://pypi.org/project/onnxruntime)| [ort-nightly (dev)](https://test.pypi.org/project/ort-nightly)|
||GPU: [**onnxruntime-gpu**](https://pypi.org/project/onnxruntime-gpu) | [ort-gpu-nightly (dev)](https://test.pypi.org/project/ort-gpu-nightly)|
|C#/C/C++|CPU: [**Microsoft.ML.OnnxRuntime**](https://www.nuget.org/packages/Microsoft.ML.OnnxRuntime) | [ort-nightly (dev)](https://aiinfra.visualstudio.com/PublicPackages/_packaging?_a=feed&feed=ORT-Nightly)|
||GPU: [**Microsoft.ML.OnnxRuntime.Gpu**](https://www.nuget.org/packages/Microsoft.ML.OnnxRuntime.gpu)|[ort-nightly (dev)](https://aiinfra.visualstudio.com/PublicPackages/_packaging?_a=feed&feed=ORT-Nightly)|
|Java|CPU: [**com.microsoft.onnxruntime/onnxruntime**](https://search.maven.org/artifact/com.microsoft.onnxruntime/onnxruntime)|
||GPU: [**com.microsoft.onnxruntime/onnxruntime_gpu**](https://search.maven.org/artifact/com.microsoft.onnxruntime/onnxruntime_gpu)|
|nodejs|CPU: [**onnxruntime**](https://www.npmjs.com/package/onnxruntime)|
|Other|[Contributed non-official packages](https://docs.microsoft.com/en-us/windows/ai/windows-ml/get-started-uwp) (including Homebrew, Linuxbrew, and nixpkgs)|
||These are not maintained by the core ONNX Runtime team and may have limited support; use at your discretion.|

Note: Dev builds created from the master branch are available for testing newer changes between official releases. Please use these at your own risk. We strongly advise against deploying these to production workloads as support is limited for dev builds.

## Docker Images
* [ONNX-Ecosystem](https://github.com/onnx/onnx-docker/tree/master/onnx-ecosystem): Includes ONNX, ONNX Runtime (CPU, Python), dependencies, tools to convert from various frameworks, and Jupyter notebooks to get started
* [Dockerfiles for ONNX Runtime](https://github.com/microsoft/onnxruntime/tree/master/dockerfiles)

