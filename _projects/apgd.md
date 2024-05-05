---
layout: page
title: point clouds
description: Improving corruption robustness for point cloud classifiers. Final project for CSE 493G1 Deep Learning.
img: assets/img/perturbed_chairs.png
importance: 1
category: work
related_publications: false
---

<img src="/assets/img/perturbed_chairs.png" alt="drawing" width="80%"/>

(a) A point cloud of a chair from ModelNet40. (b) The same chair perturbed using APGD, which a standard DGCNN model classified as a night stand. 

## About
Point cloud data is used widely to represent 3D objects in systems such as driver assistance systems. However, real-world object detectors often produce corrupted point clouds due to external factors such as rain and noise, which can fool many AI models that rely on point cloud data. This project aims to increase corruption robustness for point cloud classifiers through adversarial training, which a popular method to increase adversarial robustness. In this project, I conduct the following:
* Implement adversrial training using Auto-Projected Gradient Descent (APGD) on a Dynamic Graph Convolutional Neural Network (DGCNN) model, which outperformed other DGCNN models using other data augmentation techniques in both corruption and adversarial robustness.
* Evaluate adversarial robustness on various pre-trained point cloud classifiers. 
* Analyze the relationships between corruption and adversarial robustness.

The bulk of the technical work involved implementing adversarial training for point cloud classifiers by leveraging the [AutoAttack](https://arxiv.org/abs/2003.01690) framework which first introduced APGD as an evasaion attack. I first modified AutoAttack's APGD [code](https://github.com/fra31/auto-attack) to handle point cloud data and then incorporated it into the training phase of point cloud classifiers. I did so by perturbing training data using APGD and further following adversarial training methodology introduced in [this paper](https://arxiv.org/abs/1706.06083) by Madry et al.

## Full synthesis paper
[Paper](https://masanakura.github.io/assets/pdf/cse493_report.pdf)