# Fraud Detection in Bank Transactions [[Our Reference Paper](https://www.researchgate.net/publication/337322677_Graph_Transformer_Networks?_tp=eyJjb250ZXh0Ijp7ImZpcnN0UGFnZSI6Il9kaXJlY3QiLCJwYWdlIjoiX2RpcmVjdCJ9fQ&__cf_chl_rt_tk=HDxWqtkbv0UbhyrepL2pCFg4DVXOEKj0kaLvpcnCSW0-1724273332-0.0.1.1-8553).]

This repository contains the solution for the Innotech AI Competition, focused on detecting fraudulent activities in bank transactions using advanced machine learning techniques. The project applies state-of-the-art algorithms to identify potentially fraudulent transactions with high accuracy.

![Final Perpose Model(Graph Transformer)](https://github.com/khanmhmdi/Fraud-Detection-Bank-Transaction/blob/main/Perposed%20Model.png)

![Final Perpose Model(Graph Transformer)](https://github.com/khanmhmdi/Fraud-Detection-Bank-Transaction/blob/main/Accuracy%20and%20Loss.png)

## Table of Contents
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Model Architecture](#model-architecture)
- [Results](#results)
- [Requirments](#requirments)
- [Usage](#usage)
- [Refrences](#refrences)




## Methodology

The approach to fraud detection in this project involves several key steps:

1. **Data Preprocessing:** 
    - Handling missing values.
    - Feature engineering to create meaningful features from raw data.
    - Data normalization and scaling.

2. **Exploratory Data Analysis (EDA):**
    - Visualizing the distribution of features.
    - Identifying correlations between features.
    - Detecting any anomalies in the data.

3. **Model Selection:**
    - Comparison of different machine learning models including Random Forest, Gradient Boosting, and Neural Networks.
    - Use of cross-validation techniques to ensure model robustness.
    - Hyperparameter tuning to optimize model performance.

4. **Evaluation Metrics:**
    - Precision, recall, F1-score, and AUC-ROC curve were used to evaluate the model performance.
    - Special emphasis on minimizing false positives to avoid disrupting legitimate transactions.

## Model Architecture

- **Convolutions:**
  - `conv1`: Edge Convolution (`EdgeConv`) for initial node feature aggregation.
  - `conv2` & `conv3`: Transformer-based convolutions (`TransformerConv`) with skip connections for advanced feature extraction.
- **Batch Normalization:**
  - Applied after each convolutional layer to stabilize and accelerate training.
- **Skip Connections:**
  - Skip connections are integrated into the convolutional layers (`conv2` and `conv3`) to retain information from previous layers.
- **Linear Layers:**
  - `lin1`: Reduces the dimensionality of the features before the final classification.
  - `lin`: Final classifier layer to output node class probabilities.
- **Global Mean Pooling:**
  - Aggregates node features into a graph-level representation.

### Forward Pass
1. **Node Embeddings:**
   - Nodes are passed through a series of convolutional layers with skip connections to refine their embeddings.
2. **Readout Layer:**
   - Node features are aggregated at the graph level using global mean pooling.
3. **Classification:**
   - The pooled features are passed through linear layers to predict the class of each node.

### Training
- **Optimizer:** Adam optimizer with a learning rate of 0.01.
- **Loss Function:** Negative Log-Likelihood Loss (`NLLLoss`) for classification.


## Dataset

The dataset used for this project was provided by the Innotech AI Competition and contains a large number of bank transaction records, including both legitimate and fraudulent transactions. The data includes features such as transaction amount, transaction time, account age, and more.

- **Dataset Source:** Provided by Innotech AI Competition.
- **Number of Transactions:** 100K.
- **Number of Features:** 10.


## Results

The model was evaluated using the test set provided by the competition, and it achieved the following results:

- **Accuracy:** 0.85
- **Recall:** 0.83
- **F1-Score:** 0.84

## Usage

You can check the jupyter files out and find the solution. check them base on this order:
1-Data Loader.ipynb
2-model-with-node_attr.ipynb

## Requirments
```bash
Pytorch
Pytorch geometric
Numpy
Pandas
Matplotlib
```
## Refrences

* Yun, Seongjun, et al. "Graph Transformer Networks." International Conference on Learning Representations, 2020. [Link to paper](https://www.researchgate.net/publication/337322677_Graph_Transformer_Networks?_tp=eyJjb250ZXh0Ijp7ImZpcnN0UGFnZSI6Il9kaXJlY3QiLCJwYWdlIjoiX2RpcmVjdCJ9fQ&__cf_chl_rt_tk=HDxWqtkbv0UbhyrepL2pCFg4DVXOEKj0kaLvpcnCSW0-1724273332-0.0.1.1-8553).
