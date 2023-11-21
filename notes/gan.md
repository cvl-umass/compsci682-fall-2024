---
layout: page
permalink: /notes/gan/
---

Table of Contents:

- [Generative Adversarial Networks](#tf)
- [References](#add)

<a name='tf'></a>

## Generative Adversarial Networks

Generative Adversarial Networks (GANs) adopt a game-theoretical framework, differing from traditional neural networks. In this setup, learning occurs through a two-player game involving a Generator and a Discriminator. These two components act as adversaries, engaging in a continuous contest during training. This adversarial approach eliminates the need to approximate complex density functions, as the network learns to produce data that mimics a given training distribution.

### How it works

<div class="fig figcenter fighighlight">
  <img src="{{site.baseurl}}/assets/gan/gan_main.png" width="80%">
</div>

As you can identify from their names, a generator is used to generate real-looking images and the discriminator’s job is to identify which one is a fake. The entities/adversaries are in constant battle as one(generator) tries to fool the other(discriminator), while the other tries not to be fooled. To generate the best images you will need a very good generator and a discriminator. This is because if your generator is not good enough, it will never be able to fool the discriminator and the model will never converge. If the discriminator is bad, then images which make no sense will also be classified as real and hence your model never trains and in turn you never produces the desired output. The input, random noise can be a Gaussian distribution and values can be sampled from this distribution and fed into the generator network and an image is generated. This generated image is compared with a real image by the discriminator and it tries to identify if the given image is fake or real.

### Objective Function

<div class="fig figcenter fighighlight">
  <img src="{{site.baseurl}}/assets/gan/objective1.png" width="80%">
  <div class="figcaption">
    Minimax objective function
  </div>
</div>

Since a game-theoretic approach is taken, our objective function is represented as a minimax function. The discriminator tries to maximize the objective function, therefore we can perform gradient ascent on the objective function. The generator tries to minimize the objective function, therefore we can perform gradient descent on the objective function. By alternating between gradient ascent and descent, the network can be trained.

<div class="fig figcenter fighighlight">
  <img src="{{site.baseurl}}/assets/gan/gradientascent.png" width="70%">
  <div class="figcaption">
    Gradient Ascent on Discriminator
  </div>
</div>

<div class="fig figcenter fighighlight">
  <img src="{{site.baseurl}}/assets/gan/gradientdescent.png" width="50%">
  <div class="figcaption">
    Gradient Descent on Generator
  </div>
</div>

But when applied, it is observed that optimizing the generator objective function does not work so well, this is because when the sample is generated is likely to be classified as fake, the model would like to learn from the gradients but the gradients turn out to be relatively flat. This makes it difficult for the model to learn. Therefore, the generator objective function is changed as below.

<div class="fig figcenter fighighlight">
  <img src="{{site.baseurl}}/assets/gan/newobjgen.png" width="50%">
  <div class="figcaption">
    Modified objective: Gradient ascent on generator
  </div>
</div>

Instead of minimizing the likelihood of discriminator being correct, we maximize the likelihood of discriminator being wrong. Therefore, we perform gradient ascent on generator according to this objective function.


### Disadvantages
1. GANs are more unstable to train because you have to train two networks from a single backpropagation. Therefore choosing the right objectives can make a big difference.
2. Resource Intensive
3. Evaluating the performance of GANs is not straightforward. Unlike other machine learning models, where metrics like accuracy or precision can be used, assessing the quality of generated data is more subjective.


<a name='add'></a>

## References

- [Generative Adversarial Networks](https://arxiv.org/abs/1406.2661)
- [CS 231n Slides](http://cs231n.stanford.edu/slides/2017/cs231n_2017_lecture13.pdf)
- [Blog on GAN](https://towardsdatascience.com/generative-adversarial-networks-explained-34472718707a)
