---
layout: page
title: project 1
description: a project with a background image
img: assets/img/HighwaySystem.png
importance: 1
category: work
related_publications: einstein1956investigations, einstein1950meaning
---

As a Data Algorithm Engineer in the Henan Province Highway Management System, my primary responsibilities include data processing and improving the accuracy of traffic flow prediction on the highway.

The system architecture can be illustrated as shown in Fig. 1, comprising three distinct layers: Data Layer, Model Layer, and Application Layer.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Overview.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig 1. Overview of the highway management system.
</div>

In the system, I primarily focused on the development of the Model Layer and Application Layer. In the Model Layer, I addressed the issue of missing values in the original data using linear interpolation, and I also implemented data aggregation to facilitate traffic flow prediction.

I designed two distinct traffic flow prediction algorithms in the system, namely Multi-graph Spatio-temporal Graph Convolutional Network (MSTGCN) and Spatio-temporal Heritable Neural Networks for Traffic Flow Prediction (STHNN). MSTGCN is a fully convolutional network model based on GCN and TCN, which exhibits high-speed training and prediction capabilities. For data normalization, we employed a strategy to handle data imbalance caused by the long-tail distribution of traffic flow at network-wide toll stations. The model also incorporates graph convolutional networks to capture spatio-temporal features across various semantics. Additionally, meteorology and calendar features are utilized in the full connection stage to extract external characteristics of traffic flow. The overall architecture of this model is depicted in Fig. 2.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/MSTGCN.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig 1. Overview of the MSTGCN.
</div>

Based on the Encoder-Decoder architecture, the STHNN model utilizes a larger number of parameters to achieve more precise prediction results. In our approach, we learn long-term global spatio-temporal correlations by merging features at different resolutions through the encoder-decoder process. Moreover, spatial heritability is achieved by condensing historical local spatial features in the novel spatial hidden state of each Gate Recurrent Unit (GRU) cell.

To further enhance the model's accuracy, we introduced a dedicated Update Graph module that aggregates historical features with current ones at each moment. This allows the updated spatio-temporal hidden states to better adapt to real traffic conditions. The overall architecture of the STHNN model is illustrated in Fig. 3.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/STGNN.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig 1. Overview of the STHNN.
</div>
