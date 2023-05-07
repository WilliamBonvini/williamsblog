---
author: William Bonvini
date: "2023-05-07"
draft: false
excerpt: Linear Feature Mapping and Nearest Neighbor Classification with Outlier Detection
layout: single
subtitle: Linear Feature Mapping and Nearest Neighbor Classification with Outlier Detection
title: Quantum Eigenfaces
links:
- icon: github
  icon_pack: fab
  name: Code
  url: https://github.com/WilliamBonvini/quantum_eigenfaces
---

Submitted paper for [IEEE International Conference on Quantum Computing and Engineering (QCE)](https://qce.quantum.ieee.org/2023/) on
the 1st of May 2023. 

### Abstract

We propose a quantum machine learning algorithm for data classification, inspired by the seminal com-
puter vision approach of eigenfaces for face recognition. The algorithm enhances nearest neighbor/centroid
classifiers with concepts from principal component analysis, enabling the automatic detection of outliers
and finding use in anomaly detection domains beyond face recognition. Assuming classical input data, we
formalize how to implement the algorithm using a quantum random access memory and state-of-the-art
quantum linear algebra, discussing the complexity of performing the classification algorithm on a fault-
tolerant quantum device. The asymptotic time complexity analysis shows that the quantum classification
algorithm can be more efficient than its classical counterpart. We showcase an application of this algo-
rithm for face recognition and image classification datasets with anomalies, obtaining promising results
for the running time parameters. This work contributes to the growing field of quantum machine learning
applications, and the algorithm’s simplicity makes it easily adoptable by future quantum machine learning
practitioners.



