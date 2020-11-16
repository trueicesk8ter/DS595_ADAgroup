# DS595_ADAgroup
DS 595 Group Project

# A proposal for the project, (Due November 4 at 5 pm) 
## a. Members’ names (2-3 people) 
Mario Arduz, Geri Dimas, Vincent Filardi
## b. Description of the problem
We wish to improve the accuracy in the testing phase by our choice of optimizer. We want to evaluate the performance of 3 optimizers with the testing and training errors. All in all, we want to help our model to generalize well to new observations.
## c. Description of the data set (dimensions, names of variables with their Description) 
MNIST Dataset :

The MNIST database is a dataset of handwritten digits.
 60,000 training samples
10,000 test samples
 Each image is represented by 28x28 pixels
each containing a value 0 - 255 with its grayscale value

If MNIST goes well, we will look into CIFAR-10, a database of 10 labeled classes: airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck.
60,000 training samples
10,000 test samples
Each color image is represented by 32x32 pixels.
Data -- a 10000x3072 NumPy array of uint8s. Each row of the array stores a 32x32 color image. The first 1024 entries contain the red channel values, the next 1024 the green, and the final 1024 the blue. The image is stored in row-major order so that the first 32 entries of the array are the red channel values of the first row of the image.
Labels -- a list of 10000 numbers in the range 0-9. The number at index i indicates the label of the ith image in the array data.
## d. Regression or classification? 
This project falls under the category of classification.
. 
In this project, the goal is to classify images correctly. We have labeled data and, therefore, can use this for training, validation, and testing purposes. 

For the MNIST dataset, the goal of the classifier is to identify handwritten images from 0-9. If this goes well, we will use the CIFAR-10 dataset to classify which item is in the image. There are a total of 9 different labeled items. 

## e. The optimization algorithms and loss functions you plan to try here 
ADAM, SGD a top of the line algorithm from a paper by Matthews and Weare (2019) Langevin Markov Chain Monte Carlo with stochastic gradients. 

We plan to use and compare these three algorithms testing and training performance on the MNIST and CIFAR-10 dataset. 


## f. Comments and/or concerns?

One concern is that we are implementing a state of the art optimizer; making sure we can read the paper, understand the algorithm then, and adequately implement it correctly may be challenging. 
In case we run into a huge problem with the implementation of the Langevin MCMC with stochastic gradients, we will compare Adam and SGD to a variety of optimizers such as Nesterov Momentum, RMS prop, and ADAgrad.


## Response From Dr. Mangoubi
This sounds like a good project!

I think it is good that you have a backup plan in case programming the Langevin MCMC proves too difficult.  (MCMC algorithms can be quite difficult to get to work on a neural network.)

Also, please make sure to describe both the loss function AND the algorithm you are using (see the project description for details on the requirements of the project).  I am guessing that the function you are minimizing (or sampling from, in the case of MCMC) is defined by a neural network, but this should be stated explicitly.  Also, when defining the loss function, are you using cross entropy loss, MSE loss, KL divergence loss, etc.?
