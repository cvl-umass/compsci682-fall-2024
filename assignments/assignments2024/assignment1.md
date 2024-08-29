---
layout: page
mathjax: true
permalink: /assignments/assignments2023/assignment1/
---

Get the code as a zip file [here](https://github.com/cvl-umass/compsci682-fall-2023/raw/main/assignments/assignments2023/assignment1.zip). 

- [Setup](#setup)
- [Goals](#goals)
- [Q1: k-Nearest Neighbor classifier](#q1-k-nearest-neighbor-classifier)
- [Q2: Training a Support Vector Machine](#q2-training-a-support-vector-machine)
- [Q3: Implement a Softmax classifier](#q3-implement-a-softmax-classifier)
- [Q4: Two-Layer Neural Network](#q4-two-layer-neural-network)
- [Q5: Higher Level Representations: Image Features](#q5-higher-level-representations-image-features)
- [Submitting your work](#submitting-your-work)


### Setup

Please familiarize yourself with the [recommended workflow]({{site.baseurl}}/setup-instructions/#working-remotely-on-google-colaboratory) before starting the assignment. 

The assignment would be using Python = 3.10

**Note**. Ensure you are periodically saving your notebook (`File -> Save`) so that you don't lose your progress if you step away from the assignment and the Colab VM disconnects.

Once you have completed all Colab notebooks **except `collect_submission.ipynb`**, proceed to the [submission instructions](#submitting-your-work).


**Colab:**
If using colab, make a new folder, (ex. `cs682`) in google drive and upload the `assignment1` folder. After opening any notebook in colab you will need to uncomment and run the first code cell. This will mount google drive and cd into the `assignment1` directory. Do not forget to answer the inline questions. To write your response click on the text and then click the edit pencil icon that appears in the top right.

**Download data:**
Once you have the starter code, you will need to download the CIFAR-10 dataset.

Inside a colab notebook (ex. `knn.ipynb`), you can create a new cell (`Insert -> Code cell`) and run the following:

```
%cd ./cs682/datasets
!bash get_datasets.sh
%cd ../../
```

Alternatively, on your local comptuer run the following from the `assignment1` directory:

```bash
cd ./cs682/datasets
./get_datasets.sh
```

**Jupyter Notebook:**
After you have the CIFAR-10 data, if you are not using colab you should start the Jupyter Notebook server from the
`assignment1` directory. If you are unfamiliar with Jupyter, you should read our
[Jupyter tutorial]({{site.baseurl}}/setup-instructions/#jupyter-setup).

**NOTE:** If you are working in a virtual environment on OSX, you may encounter
errors with matplotlib due to the [issues described here](http://matplotlib.org/faq/virtualenv_faq.html). You can work around this issue by starting the Jupyter server using the `start_jupyter_osx.sh` script from the `assignment1` directory; the script assumes that your virtual environment is named `.env`.

### Goals

In this assignment you will practice putting together a simple image classification pipeline, based on the k-Nearest Neighbor or the SVM/Softmax classifier. The goals of this assignment are as follows:

- understand the basic **Image Classification pipeline** and the data-driven approach (train/predict stages)
- understand the train/val/test **splits** and the use of validation data for **hyperparameter tuning**.
- develop proficiency in writing efficient **vectorized** code with numpy
- implement and apply a k-Nearest Neighbor (**kNN**) classifier
- implement and apply a Multiclass Support Vector Machine (**SVM**) classifier
- implement and apply a **Softmax** classifier
- implement and apply a **Two layer neural network** classifier
- understand the differences and tradeoffs between these classifiers
- get a basic understanding of performance improvements from using **higher-level representations** than raw pixels (e.g. color histograms, Histogram of Gradient (HOG) features)

### Q1: k-Nearest Neighbor classifier (20 points)

The Notebook **knn.ipynb** will walk you through implementing the kNN classifier.

### Q2: Training a Support Vector Machine (25 points)

The Notebook **svm.ipynb** will walk you through implementing the SVM classifier.

### Q3: Implement a Softmax classifier (20 points)

The Notebook **softmax.ipynb** will walk you through implementing the Softmax classifier.

### Q4: Two-Layer Neural Network (25 points)
The Notebook **two\_layer\_net.ipynb** will walk you through the implementation of a two-layer neural network classifier.

### Q5: Higher Level Representations: Image Features (10 points)

The Notebook **features.ipynb** will walk you through this exercise, in which you will examine the improvements gained by using higher-level representations as opposed to using raw pixel values.

### Q6: Cool Bonus: Do something extra! (+10 points)

Implement, investigate or analyze something extra surrounding the topics in this assignment, and using the code you developed. For example, is there some other interesting question we could have asked? Is there any insightful visualization you can plot? Or anything fun to look at? Or maybe you can experiment with a spin on the loss function? If you try out something cool we'll give you up to 10 extra points and may feature your results in the lecture.

### Submitting your work

**Important**. Please make sure that the submitted notebooks have been run and the cell outputs are visible.

Once you have completed all notebooks and filled out the necessary code, you need to follow the below instructions to submit your work:

To make sure everything is working properly, **remember to do a clean run ("Kernel -> Restart & Run All") after you finish work for each notebook** and submit the final version with all the outputs. 

**1.** Generate a zip file of your code (`.py` and `.ipynb`) called `<UmassID>.zip` (For email address `arnaik@umass.edu` - zip file name is `arnaik.zip`). Please ensure you do not include the dataset folder in the zip.

If you run code on your local machine on Linux or macOS,  you can run the provided `collectSubmission.sh` script from `assignment1/` to produce a file `<UmassID>.zip`. Alternatively, in any colab notebook you can run the command `!bash collectSubmission.sh`. Make sure to rename the zip to `<UmassID>.zip`.

**2.** Convert all notebooks (`.ipynb` files) into a single PDF file. In colab this can be done by selecting `File -> Print -> Print to PDF`.

**3.** Please submit <UmassID>.zip and the pdf to Gradescope.
