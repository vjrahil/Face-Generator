# Face-Generator
In this project, I defined and trained a DCGAN model on a dataset of faces. The goal was to get a generator network to generate new images of faces that look as realistic as possible!
## Dataset Images
The CelebA dataset contains over 200,000 celebrity images with annotations. Since you're going to be generating faces, you won't need the annotations, you'll only need the images. Note that these are color images with 3 color channels (RGB)#RGB_Images) each. You can download the CelebA dataset by clicking [here](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html).
![i](https://user-images.githubusercontent.com/42621149/64477310-97f2c180-d1b7-11e9-9fbf-e619a741e20e.png)

## Model
A GAN is comprised of two adversarial networks, a discriminator and a generator.
### Discriminator
* The inputs to the discriminator are 32x32x3 tensor images.
* The output should be a single value that will indicate whether a given image is real or fake.

Convolutional Layers | Input Dimension | Output Dimension |  Activation Fucntion
------ | ----- | ------ |  -------------------
layer 1 | 3 | 64 | leaky relu
layer 2 | 64 | 128 | leaky relu
layer 3 | 128 | 256 | leaky relu
### Generator
* The inputs to the generator are vectors of some length z_size.
* The output should be a image of shape 32x32x3.

Deconvolutional Layers | Input Dimension | Output Dimension | Activation Function
---------------------- | ----- | ------ | -------------------
Layer 1 | 512 | 256 | relu
Layer 2 | 256 | 128 | relu
Layer 3 | 128 | 64 | relu
Layer 4 | 64 | 3 | relu
## Other Parameters
* **Epochs** = 40
* **Optimizer** = Adam
* **Z size** = 100
* **Weight Inititalization**
  * Initialize the weights to a normal distribution, centered around 0, with a standard deviation of 0.02.
  * The bias terms, if they exist, may be left alone or set to 0.
## Results
The dataset is biased; it is made of "celebrity" faces that are mostly white. After training the dataset over 40 epochs, I got the following result.
![Screenshot from 2019-09-07 21-28-21](https://user-images.githubusercontent.com/42621149/64477229-8a890780-d1b6-11e9-9ccf-d560e768c1ae.png)
