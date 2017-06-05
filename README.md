# Benchmarking different convolutions
Evaluating efficiency of several types of convolutions.

[Keras implementation](conv_keras.ipynb)

[PyTorch implementation](conv_pytorch.ipynb)


## Results

### Summary

||conv1x1|conv3x1|conv1x3|conv3x3sep|conv3x3|conv5x5|conv3x3dilated|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|Keras CPU|6.736|14.133|14.043|7.184|43.700|118.898|49.442|
|Keras GPU|1.135|1.525|1.440|1.556|1.571|2.848|2.008|
|PyTorch CPU|6.956|17.209|16.916|16.480|50.636|133.781|111.480|
|PyTorch GPU|0.102|0.180|0.186|1.951|0.230|1.024|0.484|

### Keras CPU

![keras_cpu](results/keras_cpu.png)

||conv1x1|conv3x1|conv1x3|conv3x3sep|conv3x3|conv5x5|conv3x3dilated|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|processing time [sec]|6.736|14.133|14.043|7.184|43.700|118.898|49.442|
|vs 3x3|0.154|0.323|0.321|0.164|1.000|2.721|1.131|
|theoretical complexity|0.111|0.333|0.333|0.016|1.000|2.778|1.000|

### Keras GPU

![keras_gpu](results/keras_gpu.png)

||conv1x1|conv3x1|conv1x3|conv3x3sep|conv3x3|conv5x5|conv3x3dilated|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|processing time [sec]|1.135|1.525|1.440|1.556|1.571|2.848|2.008|
|vs 3x3|0.722|0.971|0.916|0.990|1.000|1.812|1.278|
|theoretical complexity|0.111|0.333|0.333|0.016|1.000|2.778|1.000|

### PyTorch CPU

![pytorch_cpu](results/pytorch_cpu.png)

||conv1x1|conv3x1|conv1x3|conv3x3sep|conv3x3|conv5x5|conv3x3dilated|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|processing time [sec]|6.956|17.209|16.916|16.480|50.636|133.781|111.480|
|vs 3x3|0.137|0.340|0.334|0.325|1.000|2.642|2.202|
|theoretical complexity|0.111|0.333|0.333|0.016|1.000|2.778|1.000|

### PyTorch GPU

![pytorch_gpu](results/pytorch_gpu.png)

||conv1x1|conv3x1|conv1x3|conv3x3sep|conv3x3|conv5x5|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|processing time [sec]|0.102|0.173|0.169|3.786|0.230|1.108|
|vs 3x3|0.441|0.750|0.733|16.447|1.000|4.816|
|theoretical complexity|0.111|0.333|0.333|0.016|1.000|2.778|

`cudnn.benchmark = True`

||conv1x1|conv3x1|conv1x3|conv3x3sep|conv3x3|conv5x5|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|processing time [sec]|0.096|0.173|0.169|1.716|0.229|0.984|
|vs 3x3|0.418|0.753|0.735|7.485|1.000|4.291|
|theoretical complexity|0.111|0.333|0.333|0.016|1.000|2.778|

`cudnn.benchmark = True`, `cudnn.fastest = True`

||conv1x1|conv3x1|conv1x3|conv3x3sep|conv3x3|conv5x5|conv3x3dilated|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|processing time [sec]|0.102|0.180|0.186|1.951|0.230|1.024|0.484|
|vs 3x3|0.444|0.780|0.809|8.464|1.000|4.446|2.101|
|theoretical complexity|0.111|0.333|0.333|0.016|1.000|2.778|1.000|

## References

C. Szegedy, V. Vanhoucke, S. Ioffe, J. Shlens, Z. Wojna, "Rethinking the Inception Architecture for Computer Vision," in Proc. of CVPR, 2016.

A. G. Howard, M. Zhu, B. Chen, D. Kalenichenko, W. Wang, T. Weyand, M. Andreetto, and H. Adam, "MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications," in arXiv:1704.04861, 2017.

F. Chollet, "Xception: Deep Learning with Depthwise Separable Convolutions," in Proc. of CVPR, 2017.
