---
layout: post
tags: Super-Resolution Attribution-Analysis
authors: "<a href='http://www.jasongt.com/'>Jinjin Gu</a>, <a href='https://xpixel.group/index.html'>Chao Dong</a>"
venue: Submitted
date: 2020-11-16 00:00
thumbnail: /assets/img/lam/web_cover.png
title: Interpreting Super-Resolution Networks with Local Attribution Maps
permalink: /lam.html
published: true
---

SR networks are mysterious and little works make attempt to understand them. In this work, we perform attribution analysis of SR networks, which aims at finding the input pixels that strongly influence the SR results. We propose a novel attribution approach called local attribution map (LAM) to interpret SR networks. Our work opens new directions for designing SR networks and interpreting low-level vision deep models.

<!--more-->

### Local Attribution Maps (LAM)

LAM is build based on the following **Auxiliary Principles**:
1. Interpreting local not global.
2. Interpreting hard not simple.
3. Interpreting features not pixels.

The framework of LAM:
<div style="text-align: center;">
<img src="/assets/img/lam/web_framework.png" alt="framework" style="border: none; width: 75%; align: center" class="pull-center img-responsive thumb img-thumbnail"/>
</div>

LAM inherits the integral gradient method yet with two unique features.
1. We use the blurred image as the baseline input.
2. We adopt a novel progressive blurring function as the path function.


### Results

<div style="text-align: center;">
<img src="/assets/img/lam/web_lam_results.png" alt="framework" style="border: none; width: 100%; align: center" class="pull-center img-responsive thumb img-thumbnail"/>
</div>

### Interesting Findings
Based on LAM, we have several interesting conclusions:
1. SR networks with a wider range of involved input pixels could achieve better performance.
2. Attention networks and non-local networks extract features from a wider range of input pixels.
3. Comparing with the range that actually contributes, the receptive field is large enough for most deep networks.
4. For SR networks, textures with regular stripes or grids are more likely to be noticed, while complex semantics are difficult to utilize.

<div style="text-align: center;">
<img src="/assets/img/lam/web_area_of_interest.png" alt="framework" style="border: none; width: 100%; align: center" class="pull-center img-responsive thumb img-thumbnail"/>
</div>

More information please refer to our paper.


### Try Our Online Demo on Colab!

We build an online demo hosted on Google Colab. You can try LAM attribution results to see its interesting results.

<div style="text-align: center;">
<img src="/assets/img/lam/lam-demo.png" alt="framework" style="width: 100%; align: center" class="pull-center img-responsive thumb img-thumbnail"/>
</div>

[Try Here!](https://colab.research.google.com/drive/1ZodQ8CRCfHw0y6BweG9zB3YrK_lYWcDk?usp=sharing)


### Resources
<!-- - Paper (CVPR 2021) -->
- Technical Report (arXiv)
- Technical Report (Full resolution)
- [Colab Demo](https://colab.research.google.com/drive/1ZodQ8CRCfHw0y6BweG9zB3YrK_lYWcDk?usp=sharing)
- Code on GitHub (Coming soon)


### Citation
If you find our work inspiring, please cite our work:

```
@article{gu2020interpreting,
  title   = {Interpreting Super-Resolution Networks with Local Attribution Maps},
  author  = {Gu, Jinjin and Dong, Chao},
  year    = {2020}
}
```

<!-- ### Acknowledgement -->
