---
layout: post
tags: Super-Resolution Attribution-Analysis
authors: "Liangbin Xie<sup>*</sup>, <a href='https://xinntao.github.io'>Xintao Wang<sup>*</sup></a>, Zhongang Qi, <a href='https://xpixel.group/index.html'>Chao Dong</a>, Ying Shan"
venue: "Neural Information Processing Systems (<b>NeurIPS</b>), Spotlight, 2021"
date: 2021-08-03 00:00
thumbnail: assets/img/faig/web_cover.png
title: Finding Discriminative Filters for Specific Degradations in Blind Super-Resolution
permalink: /faig.html
published: true
---

Recent blind super-resolution methods typically consist of two branches, one for degradation prediction and the other for conditional restoration. Our experiments show that a one-branch network can achieve comparable performance to the two-branch scheme. How can one-branch networks automatically learn to distinguish degradations? We propose a new diagnostic tool -- Filter Attribution method based on Integral Gradient (FAIG), which aims at finding the most discriminative filters instead of input pixels/features for degradation removal in blind SR networks. Our findings can not only help us better understand network behaviors inside one-branch blind SR networks, but also provide guidance on designing more efficient architectures and diagnosing networks for blind SR.

<!--more-->

### Filter Attribution Integrated Gradients (FAIG)

Key ideas of FAIG:
1. given the same input, the changes of the network output can be attributed to the changes of network parameters (i.e., filters).
2. The baseline network $F(\bar{\theta})$ is a pure SR network that cannot remove any degradations.
3. The target network $F(\theta)$ is a re-trained network that can deal with complex degradations.


The formuala of FAIG:
$$
\operatorname{FAIG}_{i}(\theta, x)=\int_{\alpha=0}^{1} \frac{\partial \mathcal{L}(\gamma(\alpha), x)}{\partial \gamma(\alpha)_{i}} \times \frac{\gamma(\alpha)_{i}}{\partial \alpha} d \alpha
$$

$$
\mathcal{L}(\theta, x)=\left\|F(\theta, x)-x^{g t}\right\|_{2}^{2}
$$

$$
\gamma(\alpha)=\bar{\theta}+\alpha \times(\theta-\bar{\theta})
$$

### Results

<div style="text-align: center;">
<img src="assets/img/faig/results.png" alt="framework" style="border: none; width: 100%; align: center" class="pull-center img-responsive thumb img-thumbnail"/>
</div>

### Contributions

1. Our findings provide a better understanding
of the mechanism under blind SR networks, especially, bringing insightful connections between popular two-branch methods and unified one-branch networks.
2. The discovered discriminative filters for specific degradations allow us not only to perform degradation prediction, but also achieve a controllable adjustment of restoration strength without introducing extra parameters.
3. Exploiting the interpretability of blind SR would bring great significance for future works in i) designing more
efficient architectures; ii) diagnosing an SR network, such as determining the boundary of network restoration capacity and improving algorithm robustness.


More information please refer to our paper.

### Resources


### Citation
If you find our work inspiring, please cite our work:
```
@misc{xie2021finding,
      title={Finding Discriminative Filters for Specific Degradations in Blind Super-Resolution},
      author={Liangbin Xie and Xintao Wang and Chao Dong and Zhongang Qi and Ying Shan},
      year={2021},
      eprint={2108.01070},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```

