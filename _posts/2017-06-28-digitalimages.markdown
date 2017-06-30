---
layout: post
title:  "Introduction to Digital Images"
date:   2017-06-01 00:00:00
disqus: true
author: true
categories: computervision
---


Growing up as a child in Sango ota, Ogun State, Nigeria. Taking a picture was a very cumbersome process, you had go get a professional photographer, He/She would come over to the location take the pictures and it would take around 3 to 7 days for you to get your pictures, Unfortunately for you if you had a bad pose or terrible make up you just wasted time and effort because there is no do over.
Fast forward a couple of years everybody is now more or less a professional photographer, thanks to the ubiquity of modern high powered computing devices and the large effort by the scientific community  in the areas of information theory and image processing that has made available novel algorithms available .

People without any second thought take pictures share with friends apply filter,contracts upload to social sites like facebook,  instagram, etc. Few people ever wonder how these  images are captured, stored to make it easy to apply these image processing algorithms.

In this article I plan to share how modern computing devices capture and store digital images and make them easy for processing, storage and distribution.


#   Image as a Signal

A signal is  a function that maps/relates  a set  of one or more value(s) or number(input)  to another set of value(s) or number(output),  a specific number for the same signal or function would always map to the same number
A function has three main parts  namely input(s) sometimes referred to as independent variable(s), relation and output sometimes referred to as dependent variable, The relation describes the relationship between  the input variable and the output variable an example is the function describe below,  f(x) =  2x+7, here the input is x, the relation is 2x+7 and the output is the result of this computation.

<img src='https://d2mxuefqeaa7sj.cloudfront.net/s_A307448D73619847BBAE4637D13A7398C7639787817565D0F7DF3828E14DC089_1498646191782_FunctionMachine.png' class="center"/>



A signal can be analogue or digital, The fundamental difference between a digital signal and an analogue signal is that for  an analogue signal the range of values for the dependent variable and the independent variable is infinite, while for a digital signal that range is fixed.

For most physically occurring signals their input is time e.g sound, pressure, primarily because of how transducers work.


https://d2mxuefqeaa7sj.cloudfront.net/s_A307448D73619847BBAE4637D13A7398C7639787817565D0F7DF3828E14DC089_1498627363868_sampling.png
https://d2mxuefqeaa7sj.cloudfront.net/s_A307448D73619847BBAE4637D13A7398C7639787817565D0F7DF3828E14DC089_1498627363864_quantization.jpg


An analogue signal is converted to a digital signal, by going through a process call Analogue to digital conversion, in this process the signal is sampled and quantized,  sampling  involves measuring the instantaneous value of a signal at fixed time intervals  getting a sequence of values, referred to a discrete time values.
while quantisation involves  assigning a value from the fixed set of values to this instantaneous value, it could be the exact value or this closest value, in this process precision is usually lost.

The range(0 - 2^n) of these set of quantisation levels is determined by the number of bits (n) used to represent each quantised level, This is referred to as the resolution of the Analogue to digital converter, the more the bit the higher the resolution and the higher this resolution0 the better the detail and quality of the acquired digital signal, with respect to images the better and more real this image would appear.

An image is a signal with two inputs and one output, the two inputs are the spatial Cartesian coordinates and the output is the intensity level(measure of light) at that position f(x,y) = I


# Vision and Image formation


https://d2mxuefqeaa7sj.cloudfront.net/s_A307448D73619847BBAE4637D13A7398C7639787817565D0F7DF3828E14DC089_1498624558733_camera.png
https://d2mxuefqeaa7sj.cloudfront.net/s_A307448D73619847BBAE4637D13A7398C7639787817565D0F7DF3828E14DC089_1498624558738_eyes.png


A lot of modern engineering is inspired by nature and the way a modern camera captures an image is a model of how the eyes work.
The camera like the eyes consist of two fundamental parts the lens and the light intensity sensors, it also contains the iris, which controls the amount of light passing through the lense.


https://d2mxuefqeaa7sj.cloudfront.net/s_A307448D73619847BBAE4637D13A7398C7639787817565D0F7DF3828E14DC089_1498630810953_image_acquisition.png


The fundamental process of image formation and vision is the light from a light source falls on objects within a scene, some of these light is absorbed by the objects in the scene and some are reflected back, these reflected light intensity, then goes through a system of lenses depending on the intensity of the light the iris either contracts or detracts, the lense then focuses these reflected light on the light intensity sensors, these sensors are arranged in a grid like manner indexed by their x and y co-ordinates. Each point on the grid is referred to as a pixel which contains the measure light intensity at the position.
The  number of grid positions in the x and y co-ordinates, gives what is called image resolution, this is different from the ADC resolution, the multilication of the values of x and y, gives the total number of pixels in the image.
It is very common for manufactures of camera to say their camera is 3Mega Pixel camera, what they mean is the widght(x) and the height(y) of the image give the total number of pixels in the image.
The number of pixels in an image and the number of bits per pixel contribute to the quality of image, The higher the number of pixel there is in an image the smoother or clearer the image would appear and the higher the number of bits per pixel in an image the more real or the more colours the image would be able to represent their by improving the visual perception of the acquired digital image.



# Types of  Digital Image
  Binary Image

      Gray scale Image
      Colour Image


#  Image Storage Formats

     BMP Format
     Raw Format

References

1. [Signals and System, Tutorialspoint](https://www.tutorialspoint.com/signals_and_systems/index.htm)
2. [Functions, Math is fun](https://www.mathsisfun.com/sets/function.html)
3. [Sampling, Guassiansinewave.com](http://www.gaussianwaves.com/2014/07/sampling-a-signal-in-matlab/)

