---
layout: post
title:  "Introduction to Digital Images"
date:   2017-07-08 00:00:00
disqus: true
author: true
categories: computervision
---

Growing up as a child in Sango ota, Ogun State, Nigeria. Taking a picture was a very cumbersome process, you had go get a professional photographer, He/She would come over to the location take the pictures and it would take around 3 to 7 days for you to get your pictures, Unfortunately for you if you had a bad pose or terrible make up you just wasted time and effort because there is no do over.
Fast forward a couple of years everybody is now more or less a professional photographer, thanks to the ubiquity of modern high powered computing devices and the large effort by the scientific community  in the areas of information theory and image processing that has made available novel algorithms available for use in our daily lives.
People without any second thought take pictures share with friends apply filter, contrasts, upload to social sites like facebook,  instagram, etc. Few people ever wonder how these  images are captured, stored to make it easy to apply these image processing algorithms.
In this article I plan to share how modern computing devices capture and store digital images and make them easy for processing, storage and distribution.

# Image as a Signal

A signal is  a function that maps/relates  a set  of one or more value(s) or number(input)  to another set of value(s) or number(output),  a specific number for the same signal or function would always map to the same number
A function has three main parts  namely input(s) (sometimes referred to as independent variable(s)),  the relation and output (sometimes referred to as dependent variable), The relation describes the relationship between  the input variable and the output variable an example is the function describe below,  f(x) =  2x+7, here the input is x, the relation is 2x+7 and the output is the result of this computation.

<img src="https://d2mxuefqeaa7sj.cloudfront.net/s_A307448D73619847BBAE4637D13A7398C7639787817565D0F7DF3828E14DC089_1498646191782_FunctionMachine.png" />

A signal can be analogue or digital, The fundamental difference between a digital signal and an analogue signal is that for  an analogue signal the range of values for the dependent variable and the independent variable is infinite, while for a digital signal that range is fixed.

For most physically occurring signals their input is time e.g sound, pressure, primarily because of how transducers work.


<img src="https://d2mxuefqeaa7sj.cloudfront.net/s_A307448D73619847BBAE4637D13A7398C7639787817565D0F7DF3828E14DC089_1498627363868_sampling.png" />

<img src="https://d2mxuefqeaa7sj.cloudfront.net/s_A307448D73619847BBAE4637D13A7398C7639787817565D0F7DF3828E14DC089_1498627363864_quantization.jpg"/>

An analogue signal is converted to a digital signal, by going through a process call Analogue to digital conversion, in this process the signal is sampled and quantized,  sampling  involves measuring the instantaneous value of a signal at fixed time intervals  getting a sequence of values, referred to a discrete time values.
while quantisation involves  assigning a value from the fixed set of values to this instantaneous value, it could be the exact value or this closest value, in this process precision is usually lost.

The range(0 - 2^n) of these set of quantisation levels is determined by the number of bits (n) used to represent each quantised level, This is referred to as the resolution of the Analogue to digital converter, the more the bit the higher the resolution and the higher this resolution0 the better the detail and quality of the acquired digital signal, with respect to images the better and more real this image would appear.

An image is a signal with two inputs and one output, the two inputs are the spatial Cartesian coordinates and the output is the intensity level(measure of light) at that position f(x,y) = I


# Vision and Image formation

<img src="https://d2mxuefqeaa7sj.cloudfront.net/s_A307448D73619847BBAE4637D13A7398C7639787817565D0F7DF3828E14DC089_1498624558733_camera.png" />
<img src="https://d2mxuefqeaa7sj.cloudfront.net/s_A307448D73619847BBAE4637D13A7398C7639787817565D0F7DF3828E14DC089_1498624558738_eyes.png" />

A lot of modern engineering is inspired by nature and the way a modern camera captures an image is a model of how the eyes work.
The camera like the eyes consist of two fundamental parts the lens and the light intensity sensors, it also contains the iris, which controls the amount of light passing through the lense.


<img src="https://d2mxuefqeaa7sj.cloudfront.net/s_A307448D73619847BBAE4637D13A7398C7639787817565D0F7DF3828E14DC089_1498630810953_image_acquisition.png" />


The fundamental process of image formation and vision is the light from a light source falls on objects within a scene, some of these light is absorbed by the objects in the scene and some are reflected back, these reflected light intensity, then goes through a system of lenses depending on the intensity of the light the iris either contracts or detracts, the lense then focuses these reflected light on the light intensity sensors, these sensors are arranged in a grid like manner indexed by their x and y co-ordinates. Each point on the grid is referred to as a pixel which contains the measure light intensity at the position.
The  number of grid positions in the x and y co-ordinates, gives what is called image resolution, this is different from the ADC resolution, the multiplication of the values of x and y, gives the total number of pixels in the image.
It is very common for manufactures of camera to say their camera is a 3 Megapixel camera, what they mean is the width(x) and the height(y) of the image give the total number of pixels in the image, when multiplied together, this is essentially the area of the grid.

The number of pixels in an image and the number of bits per pixel contribute to the quality of image, The higher the number of pixels there is in an image the smoother or clearer the image would appear and the higher the number of bits per pixel in an image the more real or the more colours the image would be able to represent their by improving the visual perception of the acquired digital image.

# Types of  Digital Image
## Binary Image
<img src="https://d2mxuefqeaa7sj.cloudfront.net/s_A307448D73619847BBAE4637D13A7398C7639787817565D0F7DF3828E14DC089_1499581478706_binary.png" />



As indicated by the name, binary images are images that contain only to discrete levels  in the pixels of image, you guessed the discrete levels represent black and white, the integral values usually does not matter much but the common values are 0 and 255, 0 and 1. where 0 is for black in all instances.

## Gray scale Image
<img src="https://d2mxuefqeaa7sj.cloudfront.net/s_A307448D73619847BBAE4637D13A7398C7639787817565D0F7DF3828E14DC089_1499581499318_gray_capture.png" />


Gray scale images contain discrete levels between 0 and 255, i.e from  black to white and the several shades of gray, Gray scale images are represented by 8 bits per pixel that is why there  are 256 different levels.

## Colour Image
<img src="https://d2mxuefqeaa7sj.cloudfront.net/s_A307448D73619847BBAE4637D13A7398C7639787817565D0F7DF3828E14DC089_1499581515978_color_image_proc.png"  />


In primary school in my Fine Arts class, I was taught a concept called three primary colours Red, Green, Blue (RGB),  I was taught a combination of these three colours in a the right proportion can form all other colours that exist.
Digital Images too apply this concept, In that a colour image is  three grids of f(x,y) called channels where each channel contains pixel for RED, GREEN and BLUE, mathematically a  coloured image is f(x,y)r + f(x,y)g + f(x,y)b = I.
Imagine for each spatial pixel position, the value of the Red, Green, Blue are added together to get the final colour to be displayed at that position

#  Image Storage Formats

We have set the perfect pose, taken the perfect picture, we would like to apply that filter and all those cool things that would make we look awesome and share with our friends and they drool over how wonderful our life is.  But wait before the computer can apply  this cool things we want the computer needs to be able to store and retrieve this  image.
The intended processing to be supported by the image, has a huge impact on the format the image is stored.
Firstly I would like to describe how the image is represented in memory, Images are stored in memory as they are sampled in the spatial domain, N By M array of measured intensity the intersection f(x,y) for the array is called a pixel, depending on the number of bits(2,4,8,16,24) used in the quantisation the storage requirement of an image in memory is N * M * 8, for an 8 bit per pixel image, while  (N **M ** 8) * 3 for a colour image.

So as a general rule the better the quality of the image the larger it is most likely going to be in memory. The problem is this sucks, because the larger the image the more expensive it would be  to store and share with friends how sad. Fear not, Not so long ago a man named Claude Shannon was able to mathematically prove that given any dataset we are able to quantify the information in that dataset, this idea lead to things like compression, which helps us capture large images and use only a part of the captured image and still main high quality and visual perception of the image.

##  Bitmap  Format

As the name suggests,  it is  a bit-map of the intensities of a captured image, it is can be visualised as storing the image matrix to a file.
A bitmap image file has three major parts,  the file header, bitmap information and the bitmap array.
The file header is of size 14 bytes provides stores the storage format and the image size, The bitmap information part contains information such as the width and height of the image, if compressed or not,  while the bitmap array contains the image array.


##  Raw Format

A raw image usually represent the raw image acquired from the image sensors, it contains the originally acquired intensity levels before any image processing has been done on the acquired images.
It is especially useful for researcher and professional photographers as it provide them with the greatest control.

## JPEG

Full meaning is Joint Photographic expert group, the major feature of this image format is its compression algorithm, unlike bitmap images that uses, run-length encoding for compression, it uses discrete cosine transform.
This makes JPEG’s relatively smaller than bitmap, As a result of compression the quality of image tends to be lost.
JPEG are more common image form as an output of a  digital camera .

# Conclusion

Digital photograghy  is all around us, we tend to capture all the moments we exprience, and share those wonderful images with our friends and family, Hopefully you now understand digital images better and have a apperciation for the science involved, In a future article I plan to share some fundamental image processing techniques.

# LINKS
1. [Signals and System, Tutorialspoint](https://www.tutorialspoint.com/signals_and_systems/index.htm)
2. [Functions, Math is fun](https://www.mathsisfun.com/sets/function.html)
3. [Sampling, Guassiansinewave.com](http://www.gaussianwaves.com/2014/07/sampling-a-signal-in-matlab/)
4. https://en.wikipedia.org/wiki/Binary_image
5. https://en.wikipedia.org/wiki/BMP_file_format

