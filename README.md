# Face Generation using DCGANs and Pytorch

## Overview

This project from Udacity's nano-degree course "Deep-Learning" is about Face Generation using a Discriminator-Generator-Adversarial-Network (DCGAN). The task is to set up a discriminator and a generator model, which are concurrently trained in a competitive manner on a color image dataset with human faces. The goal of the discriminator is to discriminate real images from fake images, and the goal of the generator is to generate real-like fake images (given a randomly sampled latent vector as input) that should look as realistic as possible so the discriminator takes them for real ones.

The project is broken down in subtasks starting with loading and preprocessing the data, defining the discriminator and generator network models (incl. loss and optimization criteria), training the models and finally evaulating the performance and visualizing the outcome. The implemented solution is certainly not perfect and there is room for improvement. Nonetheless, it is a nice fun project and may serve as an example to start with.

The project is implemented as a Jupyter notebook and can be found there: [Project Notebook](dlnd_face_generation.ipynb)

## Installation

### 1. Install Anaconda with Python

In order to run the notebook please download and install [Anaconda](https://docs.anaconda.com/anaconda/install/) with Python 3.6 on your machine. Further packages that are required to run the notebook are installed in a virtual environment using conda.

### 2. Create a Virtual Environment

In order to set up the prerequisites to run the project notebook you should create a virtual environment, e. g. using conda, Anaconda's package manager, and the following command

```
conda create --name deep-learning
```

The virtual environment needs to be activated by

```
activate deep-learning
```

### 3. Download the project from github

You can download the project from github as a zip file to your Downloads folder from where you can unpack and move the files to your local project folder. Or you can clone from Github using the terminal window. Therefore, you need to prior install git on your machine e. g. using

```
conda install -c anaconda git
```

When git is installed you can create your local project version. Therefore, navigate to your project folder and clone the project from github using the command

```
git clone https://github.com/AndiA76/face-generation.git
```

Then change to the project directory

```
cd face-generation
```

### 4. Install Pytorch with GPU support

In order to run the project notebook you need to install Pytorch. If you wish to install Pytorch with GPU support you also need to take care of your CUDA version and some [dependencies with Pytorch](https://pytorch.org/get-started/previous-versions/). I have used Ubuntu 18.04 LTS with CUDA 10.0 and Python 3.6 to run the project notebook. Therefore you need to enter the following installation command:

CUDA 10.0
```
conda install pytorch==1.2.0 torchvision==0.4.0 cudatoolkit=10.0 -c pytorch
```

### 5. Further requirements 

Besides Pytorch you need to install a couple of further packages, which are required by the project notebook. The packages are specified in the [requirements.txt](requirements.txt) file (incl. OpenCV for Python). You can install them using pip resp. pip3:

```
pip install -r requirements.txt
```

### 6. Download the dataset

In order to run the notebook you will be using the [CelebFaces Attributes Dataset (CelebA)](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html) to train the DCGAN adversarial networks.

Since the project's main focus is on building the GANs, a pre-processed dataset is used. Each of the CelebA images has been cropped to remove parts of the image that don't include a face, then resized down to 64x64x3 NumPy images. Some sample data is show below.

<img src='assets/processed_face_data.png' width=60% />

> If you are working locally, you can download this data [by clicking here](https://s3.amazonaws.com/video.udacity-data.com/topher/2018/November/5be7eb6f_processed-celeba-small/processed-celeba-small.zip)

This is a zip file that you'll need to extract in the home directory of this notebook for further loading and processing using below command. After extracting the data, you should be left with a directory of data `processed_celeba_small/`

```
unzip processed_celeba_small.zip
```

### 7. Run the notebook

Now start a Jupyter notebook to run the project using following command

```
jupyter notebook
```

Navigate to your local project folder in the Jupyter notebook and open [dlnd_face_generation.ipynb](dlnd_face_generation.ipynb) file and run it.
