# Resnet50 Quantization for Inference Speedup in PyTorch

Quantization for deep learning is the process of approximating a neural network that uses 32-bit floating-point/continuous numbers by a neural network of low bit width discrete numbers i.e. 8-bit integers. This dramatically reduces both the memory requirement(by factor of 4) and computational cost of using neural networks.

We use **static quntization** to quantize the model. Static quantization quantizes the weights and activations of the model. It requires calibration with a representative dataset to determine optimal quantization parameters for activations. Static Quantization is typically used when both memory bandwidth and compute savings are important. It usally works well with CNNs.



| Method               | Accuracy      | Avgerage Inference time | Inference Speed-up
| -------------------- | ------------- | ---------------------   |  -------------------
| Baseline             | 78.2%  | 0.241 seconds | -
| Static Quantization  | 77.9%  | 0.125 seconds | *2X*

By quantizating ResNet50, we achieve **2X better inference time**, while accuracy only drops **0.3%**.
