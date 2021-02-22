#  Random Forest Classification of Finger Movements using Electromyogram (EMG) Signals
## Abstract
The hands are one of the most frequently used organs in people's lives. However, people may suffer the loss of limbs due to work accidents, traffic accidents and health problem. For this reason, prosthetic hands are used to regain freedom of movement to disabled people. One of the fundamental problems in the development of prosthetic fingers is the recognition of finger movements using surface EMG data. This data is collected with an EMG sensor, which is used to get electrical signals created by muscles and nerves.
We here consider automatic generation and selection of EMG signal features without relying on domain knowledge, unlike previous studies. We then develop a classification method based on random forests. Our results show that the proposed method achieves %97,5 accuracy to classify 10 classes. We also present a discussion of the features which are important in distinguishing finger movements.

<p align="center">
  <img src="https://user-images.githubusercontent.com/48488423/98931946-c2dd5180-24ef-11eb-9499-f5fa58e3a352.png" width="400" />
</p>
<p  align="center">
    <em>Figure 1. Finger movements which corresponds to the EMG signals in the dataset</em>
</p>

## Approach
- Extracting features from time-series using tsfresh library unlike most of the previous work which relies on curated features based on expert knowledge
- Removing one of the interrelated features from data set by examining the correlation between extracted features
- Applying feature selection to only use important features for classification
- Optimizing the hyper-parameters of the Random Forest Algorithm by using a Randomized Search Algorithm
- Classifying the test data with the Random Forest Model

## Feature Extraction & Feature Selection


Each feature obtained with the "Tsfresh" library has a Gini Importance Value. This value is a numeric value that indicates how important the property is for the classification. These values are accepted as a threshold value and used in the feature selection phase. The model is created using features with a Gini Importance Value above a certain threshold value. In Figure 2, the results of the experiment in feature selection are shown. In the experiment, classification accuracies are compared when using the different threshold of Gini importance value. The highest accuracy was achieved by using 33 features obtained with the threshold value of 0,003.

<p align="center">
  <img src="https://user-images.githubusercontent.com/48488423/98933340-8dd1fe80-24f1-11eb-9e66-97cb4aa7ec0d.png" width="400" />
</p>
<p  align="center">
    <em>Figure 2. Change in the number of features and accuracy for different gini importance threshold values</em>
</p>
 
## Classification

In the classification phase of the study, in order to accurately evaluate the accuracy of the model, %20 of the dataset are reserved for testing and used %80 of the dataset for training. After the splitting process, the model is created using the parameters obtained after parameter optimization. Classification using 33 features has achieved %97,5 accuracy. Figure 3 shows the accuracy rates for each movement separately. The reason for errors can be that these muscle groups are close to each other.

<p align="center">
  <img src="https://user-images.githubusercontent.com/48488423/98933369-94f90c80-24f1-11eb-9e6e-df60025269b5.PNG" width="400" />
</p>
<p  align="center">
    <em>Figure 3. Confusion matrix of the finger movements
</em>
</p>

### For more detailed information about this study, you can review our article named "Random Forest Classification of Finger Movements using Electromyogram (EMG) Signals". 
[DOI: 10.1109/SENSORS47125.2020.9278619] (10.1109/SENSORS47125.2020.9278619)  
If you have problems accessing the article, you can contact me via mail.  
Contact info: ceseymayilmaz@gmail.com

