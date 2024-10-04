<h2> Temporal Crowd Flow classification of Sequential Frames </h2>

**Motivation:**
   
With a growing population, crowd flow analysis has be- come increasingly critical. It plays a key role in preventing overcrowding, improving emergency evacuations, and en- hancing security by detecting anomalies and enabling real- time decision-making. Crowd movement is often shaped by complex, non-linear patterns influenced by various factors. Deep learning models, particularly neural networks, excel at capturing these non-linear dynamics and providing more accurate predictions. Our goal is to study crowd flow across different settings using deep neural networks for more ef- fective analysis and insights.


**Literature review:**
 
To explore the complexities and current advancements in crowd flow analysis, we are conducting a comprehensive review of various topics. Below is a summary of the litera- ture we are reviewing:
Crowd counting research done by Weizhe Liu [3] fo- cuses counting people by estimating people flows. They propose a method to divide the scene into multiple regions and estimate the number of people in each region. And then they generate 9 density maps representing the people mov- ing in different directions using CNNs taking two frames as input.
Crowd counting research done by Zhang et al. [6] fo- cuses on the use of convolutional neural networks (CNNs) for crowd counting. They propose a multi-column CNN model that can capture different scales of crowd density.
Convolutional neural network models can only take im- ages as input and cannot take temporal information along with images. We are studying the use of RNNs, LSTMs, and attention mechanisms for crowd flow prediction [2] which remembers previously processed data.
These models can be trained to consider the temporal information when making predictions.
We are also looking at model architectures used for a combination of density map generation and flow prediction [7].

**Data:**
   
We are currently evaluating the below datasets for contents which closely align to our crowd flow classification idea. While the dataset is promising, we are going to manually annotate the ground truth for these data sets.
1. Data set used by Berkan Solmaz, Brian E. Moore [5]
2. The MOT15 benchmark dataset contains video se- quences in unconstrained environments filmed with both
staticandmovingcameras: [1]
3. Pedestrian Detection Challenge data sequences with
moreaccurategroundtruth. [4]


**Approach:**

Our approach is to combine the concepts used by Weizhe Liu and Dupont et al. We will use the dataset from Berkan Solmaz [5], MOT15 [1] and MOT17 [4] for training and testing our model.
The task we are trying to solve is to classify the crowd behaviour in sequential frames into the final output classes. There is no annotated dataset available in the desired format for this task. For the Berkan and Brian dataset we will use the image data sequences used in the paper but manually annotate the ground truth according to our output classes. For MOT15, and MOT17 datasets, we will sample the frame sequences and annotate them into the output classes.
We will use multiple models to compare their learning capability of crowd patterns with temporal parameters. To
reduce the dependency on large annotated datasets, we will use active learning and semi-supervised learning techniques to train our model. And to reuse the existing models which are trained with feature extraction and crowd counting, we will use transfer learning techniques.

**Evaluation metric:**

For evaluating the effectiveness of our proposed approach in crowd flow prediction and classification, we will em- ploy several metrics to gauge both accuracy and robust- ness. First, standard classification metrics such as accuracy, precision, recall, and F1-score will be used to assess the performance of the models in classifying crowd behavior across the final output classes. To better understand how well the model captures temporal dependencies, we will uti- lize mean squared error (MSE) and root mean squared er- ror (RMSE) for assessing the accuracy of flow prediction. Additionally, confusion matrices will be generated to visu- alize wrong classifications across classes, and area under the curve (AUC) will be applied to evaluate performance in imbalanced data scenarios. Lastly, metrics like model con- vergence and training time will also be monitored to assess efficiency of our proposed model.


**References:**

[1] L Leal-Taixe ́. Motchallenge 2015: Towards a benchmark for multi-target tracking. arXiv preprint arXiv:1504.01942, 2015. 1
[2] Wei Li, Wei Tao, Junyang Qiu, Xin Liu, Xingyu Zhou, and Zhisong Pan. Densely connected convolutional networks with attention lstm for crowd flows prediction. IEEE Access, 7: 140488–140498, 2019. 1
[3] Weizhe Liu, Mathieu Salzmann, and Pascal Fua. Counting people by estimating people flows. IEEE transactions on pattern analysis and machine intelligence, 44(11):8151–8166, 2021. 1
[4] Anton Milan. Mot16: A benchmark for multi-object tracking. arXiv preprint arXiv:1603.00831, 2016. 1
[5] Berkan Solmaz, Brian E. Moore, and Mubarak Shah. Iden- tifying behaviors in crowd scenes using stability analysis for dynamical systems. IEEE Transactions on Pattern Analysis and Machine Intelligence, 34(10):2064–2070, 2012. 1
[6] Yingying Zhang, Desen Zhou, Siqin Chen, Shenghua Gao, and Yi Ma. Single-image crowd counting via multi-column convolutional neural network. In 2016 IEEE Conference on Computer Vision and Pattern Recognition (CVPR), pages 589–597, 2016. 1
[7] Jie Zhu, Fan Feng, and Bo Shen. People counting and pedes- trian flow statistics based on convolutional neural network and recurrent neural network. In 2018 33rd Youth Academic An- nual Conference of Chinese Association of Automation (YAC), pages 993–998, 2018. 1
