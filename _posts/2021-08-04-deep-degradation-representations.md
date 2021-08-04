---
layout: post
tags: Super-Resolution
authors: "Yihao Liu*, Anran Liu*, <a href='http://www.jasongt.com/'>Jinjin Gu</a>, Zhipeng Zhang, Wenhao Wu, Yu Qiao, <a href='https://xpixel.group/index.html'>Chao Dong</a>"
venue: "arXiv, 2021"
date: 2021-08-04 00:00
thumbnail: /assets/img/ddr/web_cover.png
title: Discovering "Semantics" in Super-Resolution Networks
permalink: /ddr.html
published: true
---

Can we find any “semantics” in SR networks? In this paper, by analyzing the feature representations with dimensionality reduction and visualization, we successfully discover the deep semantic representations in SR networks, i.e., deep degradation representations (DDR), which relate to the image degradation types and degrees.

<!--more-->

### Deep Degradation Representations (DDR) in Super-Resolution Networks

### Introduction
Super-resolution (SR) is a fundamental and representative task of low-level vision area. It is generally thought that the features extracted from the SR network have no specific semantic information, and the network simply learns complex non-linear mappings from input to output. Are there any ''semantics'' in SR networks? If yes, do these semantics have different definitions from those in classification networks?

In this study, we give affirmative answers to the above questions by unfolding the semantics hidden in super-resolution networks. Specifically, different from the artificially predefined semantics associated with object classes in high-level vision, semantics in SR networks are distinct in terms of **image degradations** instead of image contents. Thus, *the semantics in this paper have different indications for SR and classification networks.* More interestingly, such degradation-related semantics are spontaneously existing, without involving relevant data or pre-labelling.

Our findings could lay the groundwork for the interpretability of SR networks, and inspire better solutions for more challenging tasks, like blind SR for real-world images.

<div style="text-align: center;">
<img src="/assets/img/ddr/representation_compare.png" alt="framework" style="border: none; width: 100%; align: center" class="pull-center img-responsive thumb img-thumbnail"/>
</div>

### Conclusions
1. **Differences in Semantics between Classification and Super-Resolution Networks**
Semantics in classification networks are coherent with the artificially predefined labels (semantic categories). However, semantics in SR networks are in terms of degradation types regardless of the image contents. Simply but vividly, we name this kind of semantics as deep degradation representations (DDR).
2. During training, the SR networks are only provided with downsampled clean data, without any exposure to blur/noise data. Nevertheless, when testing, the SR networks can produce deep representations that can distinguish different degradation types. This phenomenon is never discussed before.

<div style="text-align: center;">
<img src="/assets/img/ddr/cluster.png" alt="framework" style="border: none; width: 100%; align: center" class="pull-center img-responsive thumb img-thumbnail"/>
</div>



3.  For MSE-based SR method, global residual learning (GR) is essential for producing discriminative feature representations on degradation types. It is inferred that learning the global residual could remove most of the content information of input image and make the network concentrate more on the contained degradation, thus the learned representations are discriminative.
4. For GAN-based method, whether there is global residual (GR) or not, the deep features are bound to be discriminative to degradation types. This implies that adversarial learning can help the network learn more informative features for low-level degreadations instead of image content.
5. There appears to be a spectrum (continuous transition) for the discriminability of the deep degradation representations, i.e., the discriminability has a monotonic relationship with the divergence between degradation types and degrees.

### Inspirations and Future Work
1. Interpreting the Generalization of SR Networks
By incorporating more degraded data into training, the model becomes robust to handle more degradation types, and the distributions of the deep representations of different degraded data become unanimous with that of clean data. This can partially explain and evaluate the generalization ability of different models in feature level.

<div style="text-align: center;">
<img src="/assets/img/ddr/train_noise.png" alt="framework" style="border: none; width: 70%; align: center" class="pull-center img-responsive thumb img-thumbnail"/>
</div>


2. Developing Degradation-adaptive Algorithms
One big challenge for image restoration is that there are myriad real-world and complicated cases with various degradation types and degrees. One key to solve this problem is to make the algorithm be degradation-adaptive, so that it can specifically deal with different degradations. The deep degradation representations in super-resolution networks, which are discriminative to different degradation types and degrees. This naturally provides the insight to solve the problem of blind restoration, where the profile of the degradation modeling is unknown and inaccessible. Concretely, we can leverage the deep degradation representations as prior knowledge to guide the subsequent modules to perform degradation-aware and degradation-adaptive processes.

3. Disentanglement of Image Content and Degradation
In low-level vision, the deep degradation representations can make it possible to decompose an image into content and degradation information, which can promote a number of new areas, such as degradation transferring and degradation editing. Further, more in-depth research on deep degradation representations will also greatly improve our understanding of the nature of images.



### Citation
If you find our work inspiring, please cite our work:

```
comming soon
```
