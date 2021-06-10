# Classification of adaptor and non adaptor proteins.

Prediction of adaptor proteins using PSSM profiles and Recurrent Neural Networks.

## 1 - Project Architecture:
![alt text](https://github.com/AhmedSamirScience/Prediction-of-adaptor-proteins-using-PSSM-profiles-and-Recurrent-Neural-Networks.-/blob/main/Picture1.png)
![alt text](https://github.com/AhmedSamirScience/Prediction-of-adaptor-proteins-using-PSSM-profiles-and-Recurrent-Neural-Networks.-/blob/main/Picture2.png)

We will use an RNN model in this study to differentiate adaptor proteins from non-adaptor proteins. This is shown in the above Figures an overview of the implemented RNN model. The RNN model receives PSSM features as input from multiple 1-convolution (1-D) and one-dimensional average pooling layers and computes their features. The extracted features are then fed into GRUs, where the spatial context of the entire PSSM approach is explored and employed to make the final prediction. N represents the number of values is given as input sequence. The final pass through two layers of one-dimensional CNN and 1D one-dimensional average pool only reduced the length by N/9. As a result, this N/9 vector was sent to the GRU algorithm to fed, transferring features from the last GRU (i.e. 256 features) to the beginning of the sequence (i.e. to the input of the last sequence that acquired a feature). At long last, we computed the whole output through a Fully Connected (FC) layer (512 nodes), after which it was passed to a Sigmoid layer, and this value was finally obtained as a prediction. 

## 2 - Dataset:

we obtained 4,049 adaptor proteins of all organisms. A solution to the proposed issue was resolved in binary classification, thus, we built a negative set of general protein sequence samples. In fact, our classifier was set out to detect adaptor proteins and non-only adaptor proteins. We needed a list of adaptors and non-adaptors for training the model properly. However, in reality, the number of non-adaptor proteins is already in the hundreds of thousands and for the dataset that related to adaptor proteins, it would definitely be a much smaller number of the non-adaptor proteins. This will seriously affect the model's performance because of having imbalanced data. Thus, in the majority of the problems that deal with bioinformatics, scientists are able to make assumptions only on the subset of negative protein data and treat it as a general protein. In this research, we selected this membrane protein, which contains a large enough number of sequences and functions for the analysis. In short, we target area most of the membrane proteins from the UniProt databases and discarded adaptor proteins. Subsequently, all the sequenced data was subsequently passed through the BLAST algorithm to identity redundant sequences with greater than 30% identity. To prevent the training of the model from overfitting, this step was important. Some sequences remained as adaptors for the benchmark dataset, and were further divided into 9695 non-adaptor proteins, while others were treated as adaptor proteins and the result was 1069 as shown in comming Figure.









