---
layout: post
title: Caffe Network Visualization
modified:
categories: til
excerpt:
tags: [caffe, vqa, lstm]
image:
  feature:
date: 2016-02-29T21:56:30+01:00
---

A really helpful tool to visualize Caffe neural networks: [Netscope](http://ethereon.github.io/netscope/quickstart.html)   

For instance, check out :

- [GoogLeNet](http://ethereon.github.io/netscope/#/preset/googlenet)
- [VGG-16](http://ethereon.github.io/netscope/#/preset/vgg-16)
- [ResNet-152](http://ethereon.github.io/netscope/#/gist/d38f3e6091952b45198b)

This tool also allows visualization of custom layers, since it does not strictly
validate the network.
Here's a [visualization](http://ethereon.github.io/netscope/#/gist/7c29a507243a3b52a2bb) of the [Ask-Neurons](https://www.mpi-inf.mpg.de/departments/computer-vision-and-multimodal-computing/research/vision-and-language/visual-turing-challenge/#c8775) VQA model that I'm currently working on, which includes LSTMs.

<figure class="half">
	<a href="http://ethereon.github.io/netscope/#/gist/7c29a507243a3b52a2bb"><img src="/images/ask-neurons-netscope.png"></a>
</figure>
