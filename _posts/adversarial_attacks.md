---
title: Adversarial Attacks
tags: [White-Box Attacks, Deep Learning]
style: fill
color: secondary
description: Some introductory analysis into basic white box methods.
---

## Introduction
The goal of an adversial attack is to specifically add "noise" (or some other carefully picked input) to an image in such a manner that the human reader does not notice anything different, but a well-trained machine model will end up classifying the image incorrectly. For example, we have an image of a cat, but with some pixel changes here and there, we wish for the model to identify our cat as something else; perhaps a dog or even a car. 

The most well known example (which comes from the original paper https://arxiv.org/pdf/1412.6572.pdf) is as follows
![panda](https://images.openai.com/blob/e10713f3-900b-4cb2-8209-201d8c9394a2/adversarial_img_1.png)

Today we will be taking a closer look at white-box attacks. A white box attacks allows for the adversary to know the specifics of the model archetitecture, parameters, gradients, etc which allow for easier targeting. White-box attacks exploit the model's output gradient to generate fake examples which aim to look real. 


## Algorithm 1 --- FGSM

FGSM stand for Fast Gradient Sign Method


## 2. Another thing

I am now talking about a second thing, probably also good.

## 3. A third thing

We are now getting into the weeds of things that I am saying.  It is probably unlikely someone has made it thus far.

## 4. Thing #4.

At this point, you are probably no longer into me listing off things.  Let's put in an image to placate the reader:

![corg](https://media.istockphoto.com/photos/welsh-corgi-picture-id962032196?k=20&m=962032196&s=170667a&w=0&h=NhIyQdJgVw0cw_EeLtP3LcLExLuiAWPwzL6_WsRKUfQ=)

## 5. The last thing

This is my final thing, probably would be great if this was a TL;DR or summary.  But I don't have that for you.  I have given you so little already, why start saying anything useful now?

Besides, all anybody wants is the DERP:

![MAXIMUM DERP](http://3.bp.blogspot.com/-AXnXOPZgqMk/Un-xCBAa4gI/AAAAAAAAsWA/z_lZsvDoCRk/s1600/derpstages.jpg)
