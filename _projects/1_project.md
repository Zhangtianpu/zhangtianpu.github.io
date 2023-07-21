---
layout: page
title: Henan Highway Management System
img: assets/img/HighwaySystem.png
importance: 1
category: work
---

As a Data Algorithm Engineer in the Henan Province Highway Management System, my primary responsibilities include data processing and improving the accuracy of traffic flow prediction on the highway.

The system architecture can be illustrated as shown in Fig. 1, comprising three distinct layers: Data Layer, Model Layer, and Application Layer.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Overview.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 1. Overview of the highway management system.
</div>

In the system, I primarily focused on the development of the Model Layer and Application Layer. In the Model Layer, I addressed the issue of missing values in the original data using linear interpolation, and I also implemented data aggregation to facilitate traffic flow prediction.

I designed two distinct traffic flow prediction algorithms in the system, namely Multi-graph Spatio-temporal Graph Convolutional Network (MSTGCN) and Spatio-temporal Heritable Neural Networks for Traffic Flow Prediction (STHNN). MSTGCN is a fully convolutional network model based on GCN and TCN, which exhibits high-speed training and prediction capabilities. For data normalization, we employed a strategy to handle data imbalance caused by the long-tail distribution of traffic flow at network-wide toll stations. The model also incorporates graph convolutional networks to capture spatio-temporal features across various semantics. Additionally, meteorology and calendar features are utilized in the full connection stage to extract external characteristics of traffic flow. The overall architecture of this model is depicted in Fig. 2.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/MSTGCN.png" title="example image" class="img-fluid rounded z-depth-1" style="margin: 0 auto;" %}
    </div>
</div>
<div class="caption">
    Fig. 2. Overview of the MSTGCN.
</div>

Based on the Encoder-Decoder architecture, the STHNN model utilizes a larger number of parameters to achieve more precise prediction results. In our approach, we learn long-term global spatio-temporal correlations by merging features at different resolutions through the encoder-decoder process. Moreover, spatial heritability is achieved by condensing historical local spatial features in the novel spatial hidden state of each Gate Recurrent Unit (GRU) cell.

To further enhance the model's accuracy, we introduced a dedicated Update Graph module that aggregates historical features with current ones at each moment. This allows the updated spatio-temporal hidden states to better adapt to real traffic conditions. The overall architecture of the STHNN model is illustrated in Fig. 3.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/STGNN_overview.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 3. Overview of the STHNN.
</div>

Next, I will showcase the data visualization module of the Highway Management System. On this page, we conduct an analysis of vehicle traffic conditions on Henan Province highways. Based on the number of vehicles, we identify the busiest cities in Henan Province, as well as peak hours during weekends and weekdays. Please refer to the following diagram for more details.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/data visilazation.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 4. Data visualization.
</div>

In the Spatio-temporal feature data analysis module, historical traffic flow data for various toll stations is visualized using line charts to compare different temporal patterns between stations. Please refer to the following Fig 5. In this chart, users can access historical traffic flow data for different toll stations. The left-side menu allows users to select the time range of interest for the temporal analysis. Additionally, users can click on different toll station points to add them for comparison. The chart's interactive features enable users to hover over the lines to view detailed traffic flow data for each toll station on a specific day. This visualization enables users to gain insights into the temporal patterns and traffic conditions at various toll stations, facilitating better understanding and decision-making for the Highway Management System.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/spatio-tempoal feature data analysis.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 5. Spatio-tempoal feature data analysis.
</div>

In the Traffic flow prediction module, we conducted traffic flow prediction for all toll stations on the highways in Henan Province using two different methods: MSTCN and STHNN. To validate the accuracy of the model predictions, we compared real-time traffic flow data with the predicted traffic flow data using line charts. Users can also interact with the visualization by clicking on the corresponding toll station points to display real-time traffic flow and predicted results. The following diagram Fig. 6 illustrates this.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/traffic flow prediction.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 6. Traffic flow prediction.
</div>
