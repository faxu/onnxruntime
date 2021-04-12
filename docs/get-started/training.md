---
title: Training
parent: Get Started
nav_order: 3
---

# Use ONNX Runtime for Training
## ONNX Runtime Training
[ONNX Runtime training](get-started/training.md) for PyTorch was released in April 2021, providing a one-line addition for existing PyTorch training scripts to accelerate training times. Current support is focused on large transformer models on multi-node NVIDIA GPUs, with more to come. 

**How it works**: using the ORTModule class wrapper, ONNX Runtime for PyTorch runs the forward and backward passes of the training script using an optimized automatically-exported ONNX computation graph. ORT Training uses the same graph optimizations as ORT Inferencing, allowing for model training acceleration. 

  * **[ONNX Runtime pre-training sample for BERT-Large](https://github.com/microsoft/onnxruntime-training-examples)**

## Train PyTorch model with ONNX Runtime

ONNX Runtime (ORT) has the capability to train existing PyTorch models through its optimized backend. For this, we have introduced an python API for PyTorch, called ORTTrainer, which can be used to switch the training backend for PyTorch models (instance of `torch.nn.Module`) to `orttrainer`. This requires some changes in the trainer code, such as replacing the PyTorch optimizer, and optionally, setting flags to enable additional features such as mixed-precision training. Here is a sample code fragment to integrate ONNX Runtime Training in your PyTorch pre-training script:

_NOTE: The current API is experimental and expected to see significant changes in the near future. Our goal is to improve the interface to provide a seamless integration with PyTorch training that requires minimal changes in users’ training code._ 

```python
import torch
...
import onnxruntime
from onnxruntime.training import ORTTrainer, optim

# Model definition
class NeuralNet(torch.nn.Module):
  def __init__(self, input_size, hidden_size, num_classes):
    ...
  def forward(self, data):
    ...

model = NeuralNet(input_size=784, hidden_size=500, num_classes=10)
criterion = torch.nn.Functional.cross_entropy 
model_description = {'inputs':  [('data', ['in', 'batch_size']),
                                 ('target', ['label_x_batch_size'])],
                     'outputs': [('loss', [], True),
                                 ('output', ['out', 'batch_size'])]}

optimizer_config = optim.AdamConfig(lr=learning_rate)

trainer = ORTTrainer(model,              # model
                     model_description,  # model description
                     optimizer_config,   # optimizer configuration
                     criterion)          # loss function

# Training Loop
for t in range(1000):
  # forward + backward + weight update
  loss, y_pred = trainer.train_step(input_data, target_labels, learning_rate)
  total_loss += loss.item()
  ...
```

## Build ONNX Runtime Training from source

To use ONNX Runtime training in a custom environment, like on-prem NVIDIA DGX-2 clusters, you can use these [build instructions](../how-to/build.md#training) to generate the Python package to integrate into existing trainer code.
