# BMEN 509

## Introduction
Imaging for medical purposes involves the following:
* Radiologists - Specialists who specialize in medical imagery
* Technologists - Specializing in the development and implementation of imaging
* Medical Physicists
* Nurses
* Biomedical Engineers - Engineering the devices

Imaging is important for moderating the progress of a disease, and to see if certain treatments are effective. Medical Images are mostly grey-scale images where the light intensity at a certain pixel [n1, n2] is denoted as x[n1, n2].

## Study Areas
The following are areas as to how to evaluate an image:
* Image Quality - Means to evaluate an image
* Image Processing - Way to extract certain features
* Image communication - How we communicate images with others
* Image formation - Creating the image

## Transforming an Image
When we transform an image, an analogue detector (ADC) has a quantization effect. Values are mapped to discrete values (depending on the strength of the ADC). The quantization error is the different between true and digital signals.

According to Nyquist's Theorem, we need to sample twice as fast as the bandwidth (up and down distance) of a signal. Any frequency lower than this will cause *aliasing*. Aliasing will cause the appearance of image artifacts, which causes a distortion of the image.

## Spatial Resolution
Spatial Resolution is the ability of a imaging system to resolve small independent objects in close proximity to another. Basically, the ability for a system to differentiate two objects in the image.

The spatial resolution can be evaluated using the following techniques:
* Line Spread Function - Blurring in 2D 
* Point Spread Function - Blurring in 3D
* Modulation Transfer Function (Evaluate Frequency)

When light (x-ray) hits a imaging surface, the light may diffract, naturally causing some line spread. Line spread can be computed using the Gaussian function. You can also compute the full width at half maximum of the line spread.

## Spatial Frequency
Lines per mm. This measures sharpness. It's associated with the spatial resolution of the whole system (and can be computed from the point spread function). 

## Signal to Noise Ratio (SNR)
Computed as the average signal power over the standard deviation of the noise.

## Contrast to Noise Ratio (CNR)
The absolute difference between the average of two signals over the standard deviation of the noise.

## Sensitivity
The accuracy of the diagnosis. Is computed as the (True Positives) / (True Positives + False Negatives) = (True Positives) / (Total Positives)

## Specificity
The proportion of actual negatives. Is equal to (True Negatives) / (False Positives + True Negatives).

## Accuracy
(True Positives + True Negatives) / (Entire Population)

