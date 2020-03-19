### Deep AR paper
Developed at Amazon. 

#### summary
##### Goal
Intended for large scale forecasting of 1000s or 1000000s of related time series.
* A giant global model 
* LSTM-based RNN + probablistic forecasting (predicts distribution)
* Negative binomial likelihood

##### Advantagees
1. Little need for feature engineering
2. Good ci estimate from Monte Carlo Samples
3. Cold start capability enabled by item similarity
4. Allow choices of different likelihood functions for noise used for interval estimation, 
as opposed classical assumptions of gausssian noise, which may not be the case
 for bursty demand data.

#### Interesting Parts
##### 3.2 Training
Briefly mentioning how cold start is handled by padding with 0 time series before t = 1 (starting time). 
This allows the model to learn the behaviour of "new".

##### 3.3 Scale handling 
1. Handling of scales v factor to be incorporated to output z and likelihood
2. Handling of imbalance, oversampling infrequent high-velocity items (scale is large) 
proportional to v factor 

##### 3.4 Features
* Date related features.
* Rough product category

##### 4. Applications amd Experiments
4.2 Plausible preidction interval learned from data, showing non-linear uncertainty.

##### 6. Supplementary Materials
rho-risk metric: quantile loss is good for noise is not gaussian.  
"Quantile loss functions turn out to be useful when we are interested in 
predicting an interval instead of only point predictions. Prediction interval from least square 
regression is based on an assumption that residuals (y — y_hat) have constant variance across 
values of independent variables. We can not trust linear regression models which violate this 
assumption. We can not also just throw away the idea of fitting linear regression model as 
baseline by saying that such situations would always be better modeled using non-linear functions 
or tree based models. This is where quantile loss and quantile regression come to rescue as regression 
based on quantile loss provides sensible 
prediction intervals even for residuals with non-constant variance or non-normal distribution."


#### Questions
1. what does velocity mean?
2. About figure 1. What is this fig trying to say. What does it mean by scale-free. What is normal? 
Should it look like clusters normally?
3. ch 3.2 cold star paragraph, why is the last part a good thing?
4. what is Figure 5 trying to say? what is coverage.


##### Refs:   
Source:    
- https://arxiv.org/abs/1704.04110  
doc:
- https://docs.aws.amazon.com/sagemaker/latest/dg/deepar_how-it-works.html  
Slides:  
- https://forecasters.org/wp-content/uploads/gravity_forms/7-c6dd08fee7f0065037affb5b74fec20a/2017/07/Januschowski_Tim_ISF2017.pdf

easy explanation RNN  
- https://towardsdatascience.com/illustrated-guide-to-recurrent-neural-networks-79e5eb8049c9  
- https://www.youtube.com/watch?v=LHXXI4-IEns  

easy explanation LSTM  
- https://towardsdatascience.com/illustrated-guide-to-lstms-and-gru-s-a-step-by-step-explanation-44e9eb85bf21   
- https://www.youtube.com/watch?v=8HyCNIVRbSU  

refs about quantile loss functions:   
- https://en.wikipedia.org/wiki/Quantile_regression  
- https://heartbeat.fritz.ai/5-regression-loss-functions-all-machine-learners-should-know-4fb140e9d4b0   
- https://www.evergreeninnovations.co/blog-quantile-loss-function-for-machine-learning/   

