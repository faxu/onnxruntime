---
title: Home
nav_order: 1
nav_exclude: true
---
# Version Compatibilties

ONNX Runtime is not explicitly tested with every variation/combination of environments and dependencies, so this list is not comprehensive. Please use this as starting reference. For specific questions or requests, please [file an issue](https://github.com/microsoft/onnxruntime/issues) on Github.

[Platforms](#Platforms) / [Languages](#Languages) / [Compilers](#Compilers) / [Dependent Libraries](Dependent-Libraries)

---


## Platforms

* Windows

  * Tested with Windows 10 and Windows Server 2019
  * May be compatible with Windows 7+
  * Windows Machine Learning ([WinRT](https://www.onnxruntime.ai/docs/reference/api/winrt-api.html))
    * CPU: Windows 8.1+
    * GPU: Windows 10 1709+

* Linux
  * Tested with CentOS 7
  * Should be compatible with [distributions supported by .NET Core](https://docs.microsoft.com/en-us/dotnet/core/install/linux)

* Mac
  * Tested with 10.14 (Mojave)
  * May be compatible with 10.12+ (Sierra)

* Android
  * Tested with API level 28 (v9 "Pie")
  * May be compatible with API level 21+ (v5 "Lollipop")

* iOS
  * Tested with iOS 12
  * May be compatible with any 64bit iOS version (5S+)

## Languages
* Python: 3.6 - 3.9
* Java: 8+
* NodeJS: 12.x+ or Electron v5.x+

## Compilers
* Windows 10: Visual C++ 2019
* Linux: gcc>=4.8

## Dependent Libraries
* [Submodules](https://github.com/microsoft/onnxruntime/tree/master/cgmanifests)
* See the [Execution Provider page](https://www.onnxruntime.ai/docs/reference/execution-providers/) for details on specific hardware libary version requirements
