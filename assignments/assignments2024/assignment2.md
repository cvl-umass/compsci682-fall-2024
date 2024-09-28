---
layout: page
mathjax: true
permalink: /assignments/assignments2024/assignment2/
---

In this assignment you will practice writing backpropagation code, and training
Neural Networks and Convolutional Neural Networks. The goals of this assignment
are as follows:

- understand **Neural Networks** and how they are arranged in layered
  architectures
- understand and be able to implement (vectorized) **backpropagation**
- implement various **update rules** used to optimize Neural Networks
- implement **batch normalization** for training deep networks
- implement **dropout** to regularize networks
- effectively **cross-validate** and find the best hyperparameters for Neural
  Network architecture
- understand the architecture of **Convolutional Neural Networks** and train
  gain experience with training these models on data

### Setup
Get the code as a zip file [here](https://github.com/cvl-umass/compsci682-fall-2024/raw/main/assignments/assignments2024/assignment2.zip). 

Please familiarize yourself with the [recommended workflow]({{site.baseurl}}/setup-instructions/#working-remotely-on-google-colaboratory) before starting the assignment. 

The assignment would be using Python = 3.10

**Note**. Ensure you are periodically saving your notebook (`File -> Save`) so that you don't lose your progress if you step away from the assignment and the Colab VM disconnects.

Once you have completed all Colab notebooks **except `collect_submission.ipynb`**, proceed to the [submission instructions](#submitting-your-work).


**Colab:**
If using colab, make a new folder, (ex. `cs682`) in google drive and upload the `assignment2` folder. After opening any notebook in colab you will need to uncomment and run the first code cell. This will mount google drive and cd into the `assignment2` directory. Do not forget to answer the inline questions. To write your response click on the text and then click the edit pencil icon that appears in the top right.

**Download data:**
Once you have the starter code, you will need to download the CIFAR-10 dataset.

Inside a colab notebook, you can create a new cell (`Insert -> Code cell`) and run the following:

```
%cd ./cs682/datasets
!bash get_datasets.sh
%cd ../../
```

Alternatively, on your local comptuer run the following from the `assignment2` directory:

```bash
cd ./cs682/datasets
./get_datasets.sh
```

**Compile the Cython extension:** 
Convolutional Neural Networks require a very
efficient implementation. We have implemented of the functionality using
[Cython](http://cython.org/); you will need to compile the Cython extension
before you can run the code. 

Inside a colab notebook, you can create a new cell (`Insert -> Code cell`) and run the following:

```
%cd cs682
!python setup.py build_ext --inplace
%cd ..
```
Alternatively, on your local comptuer run the following from the `assignment2/cs682` directory:

```bash
python setup.py build_ext --inplace
```

**NOTE:** Check [this page](https://github.com/cython/cython/wiki/CythonExtensionsOnWindows) if you are using windows and having the "unable to find vcvarsall.bat" error.

**Jupyter Notebook:**
After you have the CIFAR-10 data, if you are not using colab you should start the Jupyter Notebook server from the
`assignment2` directory. If you are unfamiliar with Jupyter, you should read our
[Jupyter tutorial]({{site.baseurl}}/setup-instructions/#jupyter-setup).

**NOTE:** If you are working in a virtual environment on OSX, you may encounter
errors with matplotlib due to the [issues described here](http://matplotlib.org/faq/virtualenv_faq.html). You can work around this issue by starting the Jupyter server using the `start_jupyter_osx.sh` script from the `assignment2` directory; the script assumes that your virtual environment is named `.env`.

### Q1: Fully-connected Neural Network (16 points)
The notebook `FullyConnectedNets.ipynb` will introduce you to our
modular layer design, and then use those layers to implement fully-connected
networks of arbitrary depth. To optimize these models you will implement several
popular update rules.

### Q2: Batch Normalization (34 points)
In the notebook `BatchNormalization.ipynb` you will implement batch
normalization, and use it to train deep fully-connected networks.

### Q3: Dropout (10 points)
The notebook `Dropout.ipynb` will help you implement Dropout and explore
its effects on model generalization.

### Q4: ConvNet on CIFAR-10 (30 points)
In the notebook `ConvolutionalNetworks.ipynb` you will implement several
new layers that are commonly used in convolutional networks. You will train a
(shallow) convolutional network on CIFAR-10, and it will then be up to you to
train the best network that you can.

### Q5: PyTorch (10 points)
For this last part, you will be working in PyTorch, a popular deep learning framework.

Open up either `PyTorch.ipynb`. There, you will learn how the framework
works, culminating in training and convolutional network of your own design on CIFAR-10 to
get the best performance you can.

### Submitting your work

**Important**. Please make sure that the submitted notebooks have been run and the cell outputs are visible.

Once you have completed all notebooks and filled out the necessary code, you need to follow the below instructions to submit your work:

To make sure everything is working properly, **remember to do a clean run ("Kernel -> Restart & Run All") after you finish work for each notebook** and submit the final version with all the outputs. 

**1.** Generate a zip file of your code (`.py` and `.ipynb`) called `<UmassID>.zip` (For email address `arnaik@umass.edu` - zip file name is `arnaik.zip`). Please ensure you donot include the dataset folder in the zip.

**2.** Convert all notebooks (`.ipynb` files) into a single PDF file.

**3.** Please submit <UmassID>.zip and the pdf to Gradescope.

If you run code on your local machine on Linux or macOS,  you can run the provided `collectSubmission.sh` script from `assignment2/` to produce a file `<UmassID>.zip`.

