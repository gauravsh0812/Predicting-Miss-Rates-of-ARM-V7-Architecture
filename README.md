Predicting Miss Rates of ARM V7 Architecture
======================================

#### Miss Rate 

A Machine Learning based model that can be used to predict the miss rate of the mobile architecture _ARM V7 Cortex_ for an application for any user speciﬁc conﬁguration i.e. data cache retention time, write Latency and write Energy. Our model is essentially a 2 stage **_Ensemble Machine Learning_** model. 
The main challenge is to cover a wide range of applications. 

This project deals with both _micro-architectural dependent and independent features_ of applications with different configuration sets to develop a well defined Machine Learning model. 

#### NOTE: The performance of the model are micro-architectural and application dependent. Hence it may vary for the different architecture and set of applications. 

# Prerequisite 

Jupyter Notebook

Python 3

Pandas

NumPy

Matplotlib (for visualization)

Seaborn (for visualization)

SciPy

sklearn (to import various ML packages)

# Working

<img width="860" alt="Screen Shot 2021-05-02 at 4 04 51 PM" src="https://user-images.githubusercontent.com/57118584/116826070-2f144600-ab60-11eb-93b7-f3c514c1a226.png">

An _**Ensemble Machine Learning**_ based model consist of _**Random Forest(RF) Regressors**_ for each of the four feature at primary stages, whose results then fed into the the _**K-NN Regressor**_ to predict the final Miss Rate for that application. Several Machine Learning algorithm like Adaboost, Decision Tree, Support Vector Regressor(SVR), K- Nearest Neighbor(KNN) and Naive-Bayes and their possible combinations were tested and compared based on the final accuracy. At last, the based on the best results, Random Forest and K-NN Ensemble Machine Learning  Model has been selected. The entire comaprison table is provided in the Jupyter Notebook(.ipyb file). 

To elaborate further, each of these four feature were trained individually using RF Regressor (no. of estimator = 1000) with Write Latency and Write Energy as inputs. These RF Regressors are then tested for the predicting that particular feature against the test data. After a prediction is made at individual RF stage we ﬁnally test all four feature’s outcome for predictions using a KNN Regressor (K=13) against the miss rate from Dataset 2 in the ﬁnal stage.
