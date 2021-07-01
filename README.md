# Classification of adaptor and non adaptor proteins.

Prediction of adaptor proteins using PSSM profiles and Recurrent Neural Networks.

***
## 1 - Abstract:

The primary role of adaptor proteins is to transport and transmitting a signal. There are often intracellular signaling proteins of modular design, each domain of which may have a specific binding affinity and interact by forming complexes with other molecules inside the cell. A large number of studies have discovered the adaptor proteins to be associated with various human illnesses. Therefore, the process of discovering the function of adaptor proteins is one of bioinformatics and computational biology's most critical challenges. Only a few computational biology studies have attempted to determine protein functions, and almost all of them used position-specific scoring matrix (PSSM) profiles in the process. But unfortunately, the neural networks failed to develop optimal processing sequence information. Our approach is based on deep learning using a recursive neural network architecture to avoid the problem of the neural networks had previously encountered. So, this research claims to have developed a new solution by including RNNs (recurrent neural networks) and PSSM (Position-Specific Scoring Matrix) techniques to solve this problem. 

Seems to have worked previously with state-of-the-art strategies that had proven effective, our methodology makes significant improvements in all of the common measurement metrics. Our results depend on the six measurements for our models such as accuracy, sensitivity, loss, the area under the curve (AUC), Matthew’s correlation coefficient (MCC), and specificity of both validation and training the model. 

This study opens the path for Recurrent Neural Network (RNN) and Position-Specific Scoring Matrix (PSSM) structures to be employed in computational biology and bioinformatics. The research approach we promote for is applicable to scientists who aim to improve the prediction results of protein function prediction problems.

***
## 2 - Dataset:

<p href="url"  align="center" ><img src="https://github.com/AhmedSamirScience/Prediction-of-adaptor-proteins-using-PSSM-profiles-and-Recurrent-Neural-Networks.-/blob/main/data_collection_diagram.png" height="600" width="400" ></p>

#### This dataset consists of 10,764 proteins belonging to two classes (In the Finsal Stage):

     9695 non-adaptor proteins. 
     1069 adaptor proteins.
     
     
### How was our dataset created?

Therfore, we obtained 4,049 adaptor proteins of all organisms. A solution to the proposed issue was resolved in binary classification, thus, we built a negative set of general protein sequence samples. In fact, our classifier was set out to detect adaptor proteins and non-only adaptor proteins. We needed a list of adaptors and non-adaptors for training the model properly. However, in reality, the number of non-adaptor proteins is already in the hundreds of thousands and for the dataset that related to adaptor proteins, it would definitely be a much smaller number of the non-adaptor proteins. This will seriously affect the model's performance because of having imbalanced data. Thus, in the majority of the problems that deal with bioinformatics, scientists are able to make assumptions only on the subset of negative protein data and treat it as a general protein. In this research, we selected this membrane protein, which contains a large enough number of sequences and functions for the analysis. In short, we target area most of the membrane proteins from the UniProt databases and discarded adaptor proteins. Subsequently, all the sequenced data was subsequently passed through the BLAST algorithm to identity redundant sequences with greater than 30% identity. To prevent the training of the model from overfitting, this step was important. Some sequences remained as adaptors for the benchmark dataset, and were further divided into 9695 non-adaptor proteins, while others were treated as adaptor proteins and the result was 1069 as shown in above Figure.

***
## 3 - Evaluation:

<p href="url"  align="center" ><img src="https://github.com/AhmedSamirScience/Prediction-of-adaptor-proteins-using-PSSM-profiles-and-Recurrent-Neural-Networks.-/blob/main/evaluation.png" height="300" width="400" ></p>


Our RNN model has been implemented throughout PyTorch with Google collaboration. We have been created a new RNN model from scratch with specified value of epochs was equals to 30. All in all, the learning rate has been held constant at 0.0001 during training. Up to great imbalance in the dataset between adapter and non-adaptor proteins, we implemented binary cross-entropy as part of our training process. As it turned out, the frequency factors were proportional to the inverse to the weight of the class weights. Specificity, Sensitivity, accuracy, MCC, AUC are the predictions had previously been calculated on them prior to this test. The "true positives", "false positives", "true negatives", and "false negatives" are facts, as opposed, respectively as shown in the above figure.

***
## 4 - Implementation And Project Architecture:

<p href="url"  align="center" ><img src="https://github.com/AhmedSamirScience/Prediction-of-adaptor-proteins-using-PSSM-profiles-and-Recurrent-Neural-Networks.-/blob/main/project_architecture.png" height="400" width="900" ></p>
<p href="url"  align="center" ><img src="https://github.com/AhmedSamirScience/Prediction-of-adaptor-proteins-using-PSSM-profiles-and-Recurrent-Neural-Networks.-/blob/main/rnn_model_architecture.png" height="400" width="630" ></p>

We will use an RNN model in this study to differentiate adaptor proteins from non-adaptor proteins. This is shown in the above Figures an overview of the implemented RNN model. The RNN model receives PSSM features as input from multiple 1-convolution (1-D) and one-dimensional average pooling layers and computes their features. The extracted features are then fed into GRUs, where the spatial context of the entire PSSM approach is explored and employed to make the final prediction. N represents the number of values is given as input sequence. The final pass through two layers of one-dimensional CNN and 1D one-dimensional average pool only reduced the length by N/9. As a result, this N/9 vector was sent to the GRU algorithm to fed, transferring features from the last GRU (i.e. 256 features) to the beginning of the sequence (i.e. to the input of the last sequence that acquired a feature). At long last, we computed the whole output through a Fully Connected (FC) layer (512 nodes), after which it was passed to a Sigmoid layer, and this value was finally obtained as a prediction. 

***
## 5 - Experimental Results:

<p  href="url" align="center"  >
  <img src="https://github.com/AhmedSamirScience/Prediction-of-adaptor-proteins-using-PSSM-profiles-and-Recurrent-Neural-Networks.-/blob/main/acc_result.png"             height="300" width="400"  />
 <img src="https://github.com/AhmedSamirScience/Prediction-of-adaptor-proteins-using-PSSM-profiles-and-Recurrent-Neural-Networks.-/blob/main/auc_result.png"              height="300" width="400" /> 
</p>
<p  href="url" align="center"  >
  <img src="https://github.com/AhmedSamirScience/Prediction-of-adaptor-proteins-using-PSSM-profiles-and-Recurrent-Neural-Networks.-/blob/main/mcc_result.png"             height="300" width="400"  />
 <img src="https://github.com/AhmedSamirScience/Prediction-of-adaptor-proteins-using-PSSM-profiles-and-Recurrent-Neural-Networks.-/blob/main/senstivity_result.png"              height="300" width="400" /> 
</p>
<p href="url"  align="center" ><img src="https://github.com/AhmedSamirScience/Prediction-of-adaptor-proteins-using-PSSM-profiles-and-Recurrent-Neural-Networks.-/blob/main/specifity_result.png" height="300" width="400" ></p>

Our best result of the model, we have got it in the twenty-one epoch's number and the results were 0.71 for training loss, 0.84 for training accuracy, 0.92 for training sensitivity,  0.83 for training specificity, 0.54 for MCC,  0.94 for the area under the cover, 1.01 for loss validation, 0.81 for accuracy validation, 0.77 for the validation sensitivity, 0.82 for validation specificity, 0.41 for MCC validation, and 0.87 for the area under the curve. According to these above figures, the worst result of the model, we have got it in the thirty epoch's number and the results were 1.04 for training loss, 0.73 for training accuracy, 0.82 for training sensitivity,  0.72 for training specificity, 0.35 for MCC,  0.83 for the area under the cover, 1.09 for loss validation, 0.72 for accuracy validation, 0.77 for the validation sensitivity, 0.72 for validation specificity, 0.31 for MCC validation, and 0.80 for the area under the curve.
 
|              | Sensitivity | Specificity | Accuracy| AUC  | MCC   |                                               
| ------------ |:-----------:| -----------:| --------|:----:| -----:|
| k-NN.        | 0.635       | 0.750       | 0.738  | 0.770 | 0.254 |
| RF           | 0.185       | `0.968`     | `0.890`| 0.837 | 0.214 |
| SVM          | 0.397       | 0.934       | 0.881  | 0.818 | 0.332 |
| CNN          | 0.532       | 0.875	   | 0.841  | 0.774 | 0.328 |
| RNN          | 0.81        | 0.751       | 0.757  | 0.853 | 0.373 |
| Our Rnn Model| `0.92`      | 0.83        | 0.84   | `0.94`| `0.54`|
     

***
## 6 - Suggestions for improvement:

Last but not least, physical characteristics was already successfully applied in bioinformatics. Theoretically, this can be done as such, since it is possible to mix PSSM characteristics and physicochemical proteins. Following this, these hybrid capabilities could be inserted into our proposed architecture. It is important that future studies focus on these hybrid features in order to better the protein function prediction results.

***
## ➠ Contributing
I will be more than happy if you decide to contribute and/or fork my repo and make something awesome out of it. I will love seeing some feedback or stars from you guys.

***
#### ➠ To get more information about our repository, just send us a message from [here](https://www.linkedin.com/in/ahmedsamir13/) and we will send you the documents related to this study for a better understanding!
 












