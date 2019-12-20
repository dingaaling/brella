# brella
Flight delay insurance powered by delay prediction risk score and marketplace

## Code

`delayStats.ipynb`
This notebook explores a dataset of 2016 flights, filtering for those that originated from Boston, and visualizing the features and overall statistics of delay times. Given the distribution of delay times, the 4 "delay blocks" were chosen for the final risk score calculation:
1) <= 30 min
2) > 30 min and <= 60 min
3) > 60 min and <= 120 min
4) > 120 min

Other statistics were calculated such as number of total and delayed flights by month, carrier, and destination airport, to understand importance of various features.

`riskCalc.ipynb`
This notebook was an early test to compare a regression model of predicting the exact flight delay time or a classification model to group the delay into one of the 4 "delay blocks." While some delay time prediction results from a Random Forest Regressor looked promising, the error rate was significant enough that ultimately the decision was made to use the delay blocks in the final model.

`delayPred.ipynb`
This notebook focuses on testing different models to predict a delay block for Boston origin flights. KFold method (4 splits) was used to partition training, validiation, and testing sets. Logistic Regression, Bagging Classifier, Gradient Boosting, AdaBoost, Multilayer Perceptron (MLP), K Nearest Neighbors, and Random Forest Classifiers were tested, with Gradient Boosting Classifer producing the best result, with a score of 0.862. 

## Flight Delay Insurance Model
![](https://github.com/dingaaling/brella/blob/master/Brella-Model.png)
