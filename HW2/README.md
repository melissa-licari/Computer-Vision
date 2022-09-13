# Project 2

Sensor noise often arises in images taken in low-light conditions. Noise can significantly degrade the quality of a digital image. Averaging multiple images recorded in rapid succession -- in which the random noise in each image tends to be independent -- will allow us to generate a higher-quality image. Because the camera may move while recording indivdiual images, we will need to align the images before averaging. You will implement this temporal denoising algorithm.

We provide 18 images record in a low-light setting. One of the images is shown below. Each image is slightly mis-aligned from the previous image in the sequence. Your first goal is to align each image in the sequence to the first image. Once aligned, the images will be averaged to yield a (partially) denoised image.

Write a python function that takes as input two images and returns the horizontal and vertical offset that best aligns the two images. You need only search an offset between +/- 15 pixels. Use a simple brute-force approach to search over all horizontal and vertical translations in this range and find the translation that best aligns the images. You can use a simple sum of squared pixel differences from the green channel only as a measure of alignment. You may find the numpy function roll useful for translating an image.

Align each image to the first image and denoise by pixel-wise averaging all of the aligned images (I scaled the images into the pixel intensity range [0,1] to avoid numeric overflow).
![noise-small-1](https://user-images.githubusercontent.com/90009524/189786625-4c021377-1dde-4d99-a71d-5492f8521fa4.png)
