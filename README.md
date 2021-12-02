#### In this project, we will be taking data from the Ames Housing Dataset and iterating and refining a regression model to predict home prices for the Housing & Urban Development Agency in Ames, Iowa.
They would like to know how best to help homeowners in their city raise their property values, and which neighborhoods may need the most resources to raise the overall neighborhood values in the city.

We will be answering the following questions:
Which regression model is best for predicting the prices?
Which features/how many features are needed to make a model that works well?
What percent of our prediction prices are explained by our features?
What do the coefficients of the model tell us?
What are the prediction prices?
Which neighborhoods have the highest affect on our prediction prices (both negative and positive)?
How our coefficients can help guide homeowners into maximizing their dollar to raise their property value.

#### We will be using the following models to try to predict our target of home prices and choose the best one based on our metrics of 𝑟2 score and testing root mean squared errors (RMSE):
Linear Regression
Scaled Linear Regression (OLS - Ordinary Least Squares)
Ridge Regression
Lasso Regression
KNeighborsRegressor using Pipeline with StandardScaler
Ridge Regression using Pipeline with StandardScaler

#### For our Exploratory Data Analysis, we used the following methods:

- Replacing missing values with mean or median where possible
- Removing outliers that might skew our model using a combination of statistical descriptions and scatterplots
- Creating numerical ranking orders for our ordinal data (ordered discrete values)
- Creating new (dummy) columns for our nominal data (non-ordered discrete values)
- Correlation heatmaps and mutual_info_regression() to choose best features


#### After running our models, we ran a comparison to see which was the best:

 Model | Train $r^2$ | Test $r^2$ | Train RMSE | Test RMSE
 ----- | ----------- | ---------- | ---------- | --------- 
Linear Regression lr_2 poly|0.922634|0.909479|20652.405322|20886.176699
Pipe 2|Ridge|0.903731|0.903731|21176.599136|22715.132873
Lasso 1|0.933637|0.891434|19127.492934|22873.452186
OLS 1|0.934058|0.888544|19066.685849|23175.918158
Linear Regression lr|0.934059|0.888480|20652.405322|20886.176698
Lasso 2|0.923091|0.887965|20591.328756|23236.073333
OLS 2|0.925879|0.877720|20214.626716|24275.218044
Ridge 1|0.871199|0.876130|26647.345716|24432.571901
Ridge 2|0.859615|0.871608|27819.933563|24874.475680
Pipe 1 KNr|0.756153|0.756153|136.849687|34519.887022

 
### <div align="center">  ** Interpretation of Final Model & Conclusion: ** </div>

Our second iteration of the linear regression model using 187 features including polynomials performed the best out of all the models we tested. We cleaned, and iterated and refined our model and are happy to say that we are confident our model performs well and will perform about the same on new data as it did on our training model data.


The adjusted  $r^2$  score of the model is roughly $0.92$  which means that about  $92\%$  of the variability in the predictions of the target are explained by the features in the linear regression model with polynomial features.


Our CVS score mean is about  $89.5\%$  which is pretty close to our  $𝑟^2$  scores, and our RMSE values are closer together than in all the other models we tested.

While our model is not perfect, it is pretty good at predicting home prices in Ames, Iowa. If we wanted to make the model even better, we could continue to iterate and refine the models by trying different methods of cleaning certain columns, possibly removing more outliers, and trying different combinations of features. If there is any additional data that could possibly help predict home prices that is not within our datasets, we could also pull that in and clean and join it to our existing dataset.

#### This model is better than all the other models we tried in this project because of the following when compared with the metrics of the other models:

* Higher $r^2$ and adjusted $r^2$
* Smaller difference between training and testing metrics
* Higher CVS score

### Conclusions and recommendations:

- We should use the Linear Regression model with 187 features, including polynomial features to predict housing prices in Ames, Iowa.


- The found that the following neighborhoods decrease the prediction price (compared with Bloomington Heights) when all else is equal:

 - Edwards
 - Old Town
 - North Ames


- The following neighborhoods increase the prediction price (compared with Bloomington Heights) when all else is equal:

 - Northridge Heights
 - Stone Brook
 - Briardale
 - Northridge
 - Somerset


- The neighborhoods in the first category should be studied further to understand where they can be helped to raise their property values.
- The data from the coefficients of the features that we used in the final model should be used to make recommendations to those homeowners.
- Offer incentives to the homeowners in form of tax write-offs or discounts for upgrades to homes.
