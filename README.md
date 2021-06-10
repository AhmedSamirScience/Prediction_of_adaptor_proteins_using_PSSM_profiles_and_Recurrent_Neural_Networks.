# Classification of adaptor and non adaptor proteins.

Prediction of adaptor proteins using PSSM profiles and Recurrent Neural Networks.

## 1 - Project Architecture
![alt text](https://github.com/AhmedSamirScience/Prediction-of-adaptor-proteins-using-PSSM-profiles-and-Recurrent-Neural-Networks.-/blob/main/Picture1.png)
![image](https://github.com/AhmedSamirScience/Prediction-of-adaptor-proteins-using-PSSM-profiles-and-Recurrent-Neural-Networks.-/blob/main/Picture2.png)

we will use an RNN model in this study to differentiate adaptor proteins from non-adaptor proteins. This is shown in Figure 46 and Figure 47 an overview of the implemented RNN model. The RNN model receives PSSM features as input from multiple 1-convolution (1-D) and one-dimensional average pooling layers and computes their features. The extracted features are then fed into GRUs, where the spatial context of the entire PSSM approach is explored and employed to make the final prediction. N represents the number of values is given as input sequence. The final pass through two layers of one-dimensional CNN and 1D one-dimensional average pool only reduced the length by N/9. As a result, this N/9 vector was sent to the GRU algorithm to fed, transferring features from the last GRU (i.e. 256 features) to the beginning of the sequence (i.e. to the input of the last sequence that acquired a feature). At long last, we computed the whole output through a Fully Connected (FC) layer (512 nodes), after which it was passed to a Sigmoid layer, and this value was finally obtained as a prediction. 



