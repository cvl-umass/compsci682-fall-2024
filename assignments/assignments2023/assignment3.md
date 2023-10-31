---
layout: page
mathjax: true
permalink: /assignments/assignments2023/assignment3/
---

**This assignment is due on Sunday, November 21 at 11:55pm EST.**

Starter code containing Colab notebooks can be downloaded [here](https://github.com/cvl-umass/compsci682-fall-2023/raw/main/assignments/assignments2023/assignment3_2023_updated.zip). Please note that you can finish the homework either using Google Colab or on your local machine.

- [Setup](#setup)
- [Goals](#goals)
- [Q1: Image Captioning with Transformers (25 points)](#q1-image-captioning-with-vanilla-rnns)
- [Q2: Generative Adversarial Networks (15 points)](#q4-generative-adversarial-networks)
- [Q3: Style Transfer (10 points)](#q2-networ-visualization)
- [Submitting your work](#submitting-your-work)]


## Setup
Please familiarize yourself with the [recommended workflow]({{site.baseurl}}/setup-instructions/#working-remotely-on-google-colaboratory) before starting the assignment.

In order to do the assignment, you will need to install either TensorFlow 1.7 (installation instructions [here](https://www.tensorflow.org/install)) or PyTorch (>=0.4, up to 1.3 as of 10/23/2019, instructions [here](http://pytorch.org/)) depending on which notebooks you decide to complete.

If you face difficulty re-using the python environment used in ealier assignments, we suggest that you create a fresh one. This involves only a few simple steps (using conda and pytorch-cpu for the example):

```bash
conda remove --name cs682 --all # delete old environment if there is one
conda create --name cs682 python=3.10
conda activate cs682
pip install -r requirements.txt
conda install pytorch torchvision cpuonly -c pytorch
```

**Note**. Ensure you are periodically saving your notebook (`File -> Save`) so that you don't lose your progress if you step away from the assignment and the Colab VM disconnects.

Once you have completed all Colab notebooks **except `collect_submission.ipynb`**, proceed to the [submission instructions](#submitting-your-work).

**You can do Questions 2 and 3 in TensorFlow or PyTorch. There are two versions of each of these notebooks, one for TensorFlow and one for PyTorch. No extra credit will be awarded if you do a question in both TensorFlow and PyTorch.**

## Goals
In this assignment you will implement transformer networks, and apply them to image captioning on Microsoft COCO. You will also explore methods for visualizing the features of a pretrained model on ImageNet, and also this model to implement Style Transfer. Finally, you will train a Generative Adversarial Network to generate images that look like a training dataset!

The goals of this assignment are as follows:

- Understand and implement Transformer networks. Combine them with CNN networks for image captioning.

- Understand how to train and implement a Generative Adversarial Network (GAN) to produce images that resemble samples from a dataset.

- Understand and implement techniques for image style transfer.


## Q1: Image Captioning with Transformers (25 points)
The notebook ``Transformer_Captioning.ipynb`` will walk you through the implementation of a Transformer model and apply it to image captioning on COCO.

## Q2: Generative Adversarial Networks (15 points)
In the Jupyter notebooks ``GANS-TensorFlow.ipynb``/``GANS-PyTorch.ipynb`` you will learn how to generate images that match a training dataset, and use these models to improve classifier performance when training on a large amount of unlabeled data and a small amount of labeled data. Please complete only one of the notebooks (TensorFlow or PyTorch). No extra credit will be awarded if you complete both notebooks.

## Q3: Style Transfer (10 points)
In the Jupyter notebooks ``StyleTransfer-TensorFlow.ipynb``/``StyleTransfer-PyTorch.ipynb`` you will learn how to create images with the content of one image but the style of another. Please complete only one of the notebooks (TensorFlow or PyTorch). No extra credit will be awardeded if you complete both notebooks.

## Submitting your work:
**Important**. Please make sure that the submitted notebooks have been run and the cell outputs are visible.

Once you have completed all notebooks and filled out the necessary code, you need to follow the below instructions to submit your work:

To make sure everything is working properly, **remember to do a clean run ("Kernel -> Restart & Run All") after you finish work for each notebook** and submit the final version with all the outputs. 

**1.** Generate a zip file of your code (`.py` and `.ipynb`) called `<UmassID>.zip` (For email address `arnaik@umass.edu` - zip file name is `arnaik.zip`). Please ensure you donot include the dataset folder in the zip.

**2.** Convert all notebooks (`.ipynb` files) into a single PDF file.

**3.** Please submit <UmassID>.zip and the pdf to Gradescope.

If you run code on your local machine on Linux or macOS,  you can run the provided `collectSubmission.sh` script from `assignment1/` to produce a file `<UmassID>.zip`.
