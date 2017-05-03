# conv-benchmark



# Results

### Keras CPU

![keras_cpu](results/keras_cpu.png)

||conv1x1|conv3x1|conv1x3|conv3x3sep|conv3x3|conv5x5|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|processing time [sec]|6.859|14.329|14.184|7.509|44.746|121.381|
|vs 3x3|0.153|0.320|0.317|0.168|1.000|2.713|
|theoretical complexity|0.111|0.333|0.333|0.016|1.000|

### Keras GPU

![keras_gpu](results/keras_gpu.png)

||conv1x1|conv3x1|conv1x3|conv3x3sep|conv3x3|conv5x5|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|processing time [sec]|1.231|1.609|1.371|1.481|1.568|2.931|
|vs 3x3|0.785|1.026|0.875|0.944|1.000|1.870|
|theoretical complexity|0.111|0.333|0.333|0.016|1.000|

### PyTorch CPU

![pytorch_cpu](results/pytorch_cpu.png)

||conv1x1|conv3x1|conv1x3|conv3x3sep|conv3x3|conv5x5|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|processing time [sec]|7.281|19.112|17.575|22.769|63.507|176.341|
|vs 3x3|0.115|0.301|0.277|0.359|1.000|2.777|
|theoretical complexity|0.111|0.333|0.333|0.016|1.000|

### PyTorch GPU

![pytorch_gpu](results/pytorch_gpu.png)

||conv1x1|conv3x1|conv1x3|conv3x3sep|conv3x3|conv5x5|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|processing time [sec]|0.102|0.170|0.167|3.797|0.229|1.103|
|vs 3x3|0.444|0.744|0.728|16.581|1.000|4.816|
|theoretical complexity|0.111|0.333|0.333|0.016|1.000|