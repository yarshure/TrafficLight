# TrafficLight
A sample project use Apple CoreML &amp; Vision to detect traffic lights

# How to use
## install coremltools
## clone caffemodel

This project doesn't contain a ML model, that means you can't just download and run, you need to find a model or train one by yourself.
The One I used for testing is from davidbrai's project [Recognizing Traffic Lights with Deep Learning] (https://github.com/davidbrai/deep-learning-traffic-lights)
David's Model works great, it's the my first recommendation if you wanna try this code.

## write convert script 

```Python
import coremltools

caffe_model = ('train_squeezenet_scratch_trainval_manual_p2__iter_8000.caffemodel', 'deploy.prototxt')
labels = 'labels.txt'
coreml_model = coremltools.converters.caffe.convert(caffe_model,class_labels=labels,  image_input_names='data')
coreml_model.save('TFM.mlmodel')
```


labels.txt 
```
none
green
red
```

You can use Apple's coremltools to convert it to a MLModel, set the input/output interface you want,
and integrate your model with my code.

# About
TrafficLight Project provide full support for video capture, AVCapture arguments setting, and CoreML, Vision Integration,
it's more about a sample or a toy，dont try it in realworld driving.
