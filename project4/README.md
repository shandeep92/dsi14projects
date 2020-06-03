# Project 4: West Nile Virus Prediction

![](https://github.com/shandeep92/dsi14projects/blob/master/project4/plot_images/lineplot_wnvpresent_over_months.png)

### Problem Statement

- To predict locations with high potential of having mosquitoes carrying West Nile Virus.
- Find out factors that contribute to the growth and spread of the virus in mosquitoes.

### Executive Summary


#### Context
West-Nile-Virus(WNV) is a mosquito-borne disease that has plagued the continental United States since 1999. The vast majority of infected people will develop mild symptoms that will subside over a few days to several weeks (source). About 1 out of 150 infected people develop a serious illness. The sometimes neuroinvasive virus may cause encephalitis and meningitis, which can prove to be fatal. There is currently no vaccine to prevent or medication to treat WNV (source).

Outbreaks typically intensify over as little as a couple of weeks; however, human case reports are lagging indicators of risk since case reports occur weeks after the time of infection. Thus, environmental surveillance – monitoring enzootic and epizootic WNV transmission in mosquitoes and birds – forms a timelier index of risk, and is an important cornerstone for implementing effective WNV risk reduction efforts.Research and operational experience shows that increases in WNV infection rates in mosquito populations can provide an indicator of developing outbreak conditions several weeks in advance of increases in human infections. Aggressive and timely efforts to reduce the number of infected adult mosquitoes will optimally impact human WNV case incidence (source).

#### Scope
The goal of this project is to derive a plan to deploy pesticides throughout the city of Chicago. Hence, the scope of our plan for deployment and cost analysis will also be limited within the city of Chicago.

However, the model that we have trained can certainly be used in other states/cities within the United States to predict the potential outbreak of West Nile Virus.

The modelling techniques and strategies will be presented to biostaticians, epidemiologists, American Public Health Service and decision makers from Centers for Disease Control and Prevention (CDC).

### Cost-Benefit Analysis and Conclusion
#### Cost-Benefit Analysis
The insecticide that we recommend is Zenivex. It has proven to be effective in eliminating mosquitoes that carry West Nile Virus. It degrades rapidly and it is also harmless to humans and pets. Hence, it is an excellent choice for mosquitoes control (source: CBS Chicago).

The calculations below are based on a sample size of 2076 readings with our model built on 8304 readings.

Model Performance:
Accuracy: 73.4%
Recall: 91.2%
Specificity: 72.4%

Our model was optimised such that we have minimal false negatives (as shown by our recall score). Even though this resulted in more false positives, we find that it is a worthy tradeoff as the cost of spraying is much cheaper than the cost of medical expenses and productivity loss, as shown below.

Price/fluid-ounce is USD 22,948.75 / 35200 = USD 0.65

1.5 fluid cost/acre = USD 0.65 * 1.5 = USD 0.97/acre

Spray location in sqm = 3.14 * (100m^2) = 31,400sqm

1 acre = 4046.86sqm so 1 spray location = USD 0.97 * (31400/4046.86) = USD 7.52 (excl. overhead costs)
If even a single person contracted the virus in a given area, medical costs would vastly exceed the cost of spraying said location at USD 7.52.

WNND: Mild Cases: USD 6,317 and Severe Cases: USD 33,143; Productivity Loss: USD 10,800

WNF: Medical Cost: USD 167 and Productivity Loss: USD 955 (source: NCBI)

Deployment of Model
We have also deployed our model so that it can be used by the relevant departments such as the operations team to identify the locations that require spraying. This can also be used in other cities/states. The engine works such that anyone can upload a CSV file with the features that are needed for predictions and a table indicating the presence of West Nile Virus will be generated.

However, the main limitation is that the model was deployed on our local server using a flask application. We can look into improving it by deploying it to cloud. We can also improve the frontend interface so that it can provide more useful information and visualizations.

#### Conclusion and Recommendation
We have selected the RandomForestClassifier with hyperparameter class_weight='balanced_subsample' as our model of choice, with what we deemed was the best balance between accuracy and sensitivity (due to the nature of our prediction being disease related and the minimisation of false negatives are imperative). RandomForestClassifier performed the best in these two metrics when compared to LogisticRegression, GradientBoosting and SVC models. RandomForestClassifier also performed relatively well with SMOTE as our balancing technique, however comparing the significant increase in sensitivity, we felt that a slight decrease in accuracy using class_weight='balanced_subsample' was justified. Other balancing techniques such as ADASYN and ClusterCentroids were considered as well. However, ADASYN was inferior to our selection and ClusterCentroids is an undersampling technique that brought the negative class down to a number that would be detrimental to the model performance.

The model was created based on the data of 8304 readings in Chicago between 2007 and 2013. The applicability of this model can be brought over and applied to other states across the United States as it generalizes quite well as was seen in our test sample.

There are a few limitations to our model and our data. Due to the imbalanced nature of our positive and negative classes, we have had to use balancing techniques which are weightage inflation and oversampling methods. Acquiring more data would be better in reducing this phenomena and aid in generating a more reliable model.

The hyperparameters involved in the instantiation of our model were based on a trial and error method in maximising both accuracy and sensitivity, as GridSearchCV prioritises a singular metric and not a balance of two. There may be a combination of hyperparameter settings that could have done better and could have been missed out during the trial and error phase, as there are too many variations of such combinations to have been covered.

The features involved that took the predominant influence on our models were Average Positive Distance, Sunrise, Sunset and DewPoint. Average Positive Distance was a newly engineered feature based on the average distance of previously positively tested mosquito traps from each individual trap being tested. These are factors to be looked into when considering the presence of West Nile Virus in a particular location. Due to the nature of our features being beyond what is humanly controllable, mitigation efforts can be only limited to methods such as spraying - which would be done in locations churned within our model based on the aforementioned features.

Mitigation efforts to curb the spread of West Nile Virus should not be the responsibility of the state alone, especially when considering households and their individual influences on mosquito population. The state could further educate the population through campaigns and programmes on measures and steps to take at home or within their communities. Integrated vector management programs should be carried out and the severity of the disease should be communicated to the public in a manner to illicit preventive action without reliance on statutory intervention.

### Dataset

The dataset, along with description, can be found here: [https://www.kaggle.com/c/predict-west-nile-virus/](https://www.kaggle.com/c/predict-west-nile-virus/).
