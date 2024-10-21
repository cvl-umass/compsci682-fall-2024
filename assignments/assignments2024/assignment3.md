---
layout: page
mathjax: true
permalink: /assignments/assignments2024/assignment3/
---

**This assignment is due on Tuesday, November 26 at 11:55pm EST.**

Starter code containing Colab notebooks can be downloaded [here](https://github.com/cvl-umass/compsci682-fall-2024/raw/main/assignments/assignments2024/assignment3.zip). Please note that you can finish the homework either using Google Colab or on your local machine.

- [Setup](#setup)
- [Goals](#goals)
- [Q1: Image Captioning with Transformers (25 points)](#q1-image-captioning-with-vanilla-rnns)
- [Q2: Self-Supervised Learning for Image Classification (15 points)](#q2-self-supervised-learning)
- [Q3: Style Transfer (10 points)](#q3-networ-visualization)
- [Submitting your work](#submitting-your-work)]


## Setup
Please familiarize yourself with the [recommended workflow]({{site.baseurl}}/setup-instructions/#working-remotely-on-google-colaboratory) before starting the assignment.

In order to do the assignment, you will need to instal PyTorch (>=0.4, up to 1.3 as of 10/23/2019, instructions [here](http://pytorch.org/)) depending on which notebooks you decide to complete.

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

## Goals
In this assignment you will implement transformer networks, and apply them to image captioning on Microsoft COCO. You will also explore methods for visualizing the features of a pretrained model on ImageNet, and also this model to implement Style Transfer. Finally, you will train a Generative Adversarial Network to generate images that look like a training dataset!

The goals of this assignment are as follows:

- Understand and implement Transformer networks. Combine them with CNN networks for image captioning.

- Understand how to leverage self-supervised learning techniques to help with image classification tasks.

- Understand and implement techniques for image style transfer.


## Q1: Image Captioning with Transformers (25 points)
The notebook ``Transformer_Captioning.ipynb`` will walk you through the implementation of a Transformer model and apply it to image captioning on COCO.

## Q2: Self-Supervised Learning for Image Classification (15 points)
n the notebook ``Self_Supervised_Learning.ipynb``, you will learn how to leverage self-supervised pretraining to obtain better performance on image classification tasks. 

## Q3: Style Transfer (10 points)
In the Jupyter notebook ``StyleTransfer.ipynb`` you will learn how to create images with the content of one image but the style of another. 

## Submitting your work:
**Important**. Please make sure that the submitted notebooks have been run and the cell outputs are visible.

Once you have completed all notebooks and filled out the necessary code, you need to follow the below instructions to submit your work:

To make sure everything is working properly, **remember to do a clean run ("Kernel -> Restart & Run All") after you finish work for each notebook** and submit the final version with all the outputs. 

**1.** Generate a zip file of your code (`.py` and `.ipynb`) called `<UmassID>.zip` (For email address `arnaik@umass.edu` - zip file name is `arnaik.zip`). Please ensure you donot include the dataset folder in the zip.

**2.** Convert all notebooks (`.ipynb` files) into a single PDF file.

**3.** Please submit <UmassID>.zip and the pdf to Gradescope.

If you run code on your local machine on Linux or macOS,  you can run the provided `collectSubmission.sh` script from `assignment3/` to produce a file `<UmassID>.zip`.
