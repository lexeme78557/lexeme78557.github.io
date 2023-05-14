---
title: Adversarial Attacks
tags: [White-Box, Deep-Learning]
style: fill
color: secondary
description: Some introductory analysis into basic white box methods.
---

## Introduction
The goal of an adversial attack is to specifically add "noise" (or some other carefully picked input) to an image in such a manner that the human reader does not notice anything different, but a well-trained machine model will end up classifying the image incorrectly. For example, we have an image of a cat, but with some pixel changes here and there, we wish for the model to identify our cat as something else; perhaps a dog or even a car. 

The most well known example (which comes from the [original paper](https://arxiv.org/pdf/1412.6572.pdf)) is as follows
![panda](https://images.openai.com/blob/e10713f3-900b-4cb2-8209-201d8c9394a2/adversarial_img_1.png)
Clearly we can tell that the image is of a panda. This noise in the middle is scaled using "e" and then added to the image on the left to produce our right image which still looks like a panda but our model is 99.3% confident that we now have a gibbon instead. Crazy right?!?


Today we will be taking a closer look at white-box attacks. A white box attacks allows for the adversary to know the specifics of the model archetitecture, parameters, gradients, etc which allow for easier targeting. White-box attacks often exploit the model's output gradient to generate fake examples which aim to look real. 


## Algorithm 1 --- FGSM

FGSM stand for Fast Gradient Sign Method. First introduced as a concept in this [2014 paper](https://arxiv.org/pdf/1412.6572.pdf), its purpose was to provide a simple way to make adversarial examples of nonlinear models. The reason it is labelled as fast is that this method only requires one step which can be made efficient through [backpropagation](https://towardsdatascience.com/understanding-backpropagation-algorithm-7bb3aa2f95fd). It works by simply maximizing the loss function then adding it back to the original image with respect to the sign of the gradient to produce our adversarial image. 
![fgsm_eq](https://cdn-5f733ed3c1ac190fbc56ef88.closte.com/wp-content/uploads/2018/05/fgsm.png)
This is the mathematical formulation. The reason FGSM works is that we are slowly shifting the image so that the loss towards the correct label grows so much so that our model will relabel our image something else. In the example above, we are moving away from the true panda class and shifting instead to some other incorrect one. The algorithm does not care what the other one is as long as it is not panda.


## Algorithm 2 --- i-FGSM

i-FGSM, also known as Basic Iterative Method (BIM), is an extension of FGSM as its title would suggest. The method is iterative as it performs FGSM multiple times 


## Conclusions to Drawn


## Some Final Thoughts