
# Kratin Project

## Introduction

About 82% of people who die of coronary heart disease are 65 or older. At older ages, women who have heart attacks are more likely than men to die from them within a few weeks. Men have a greater risk of having a "Heart Attack" than women do, and they have attacks earlier in life.

so this Statistics motivated me to build a Machine learning model that detects the Risk of getting a Heart attack in People whose age is Greater Than 65 and the Output Of the model will tell you whether you are having the risk of getting the heart attack or not. if you are having the risk of getting the heart attack then it will print what factors that lead that person to risk of getting heart attack.

## Data Discription



- age: age in years
- sex: sex
  - 1 = male
  - 0 = female
- cp: chest pain type
  - Value 0: typical angina
  - Value 1: atypical angina
  - Value 2: non-anginal pain
  - Value 3: asymptomatic
- trestbps: resting blood pressure (in mm Hg on admission to the hospital)
- chol: serum cholestoral in mg/dl
- fbs: (fasting blood sugar > 120 mg/dl)
  - 1 = true;
  - 0 = false
- restecg: resting electrocardiographic results
   - Value 0: normal
  - Value 1: having ST-T wave abnormality (T wave inversions and/ or ST elevation or depression of > 0.05 mV)
  - Value 2: showing probable or definite left ventricular  hypertrophy by Estes' criteria
- thalach: maximum heart rate achieved
- exang: exercise induced angina
  - 1 = yes
  - 0 = no
- oldpeak = ST depression induced by exercise relative to rest
- slope: the slope of the peak exercise ST segment
  - Value 0: upsloping
  - Value 1: flat
  - Value 2: downsloping
- ca: number of major vessels (0-3) colored by flourosopy
- thal:
  - 0 = error (in the original dataset 0 maps to NaN's)
  - 1 = fixed defect
  - 2 = normal
  - 3 = reversable defect
- target (the lable):
  - 0 = no disease,
  - 1 = disease


imported the necessary Libraries to read and visualize the data and to build the Machinee Learning Model.

![kratin 0 ](https://github.com/1Mukhesh/Kratin-/assets/79844593/74fb9564-832b-464f-9c1a-7bb43c29fea3)

got the data from different age groups and filteredthr data to have age of 65 and more than 65 and got 710 desired data points.and proceding with that 710 samples for the further Analysis.

![image](https://github.com/1Mukhesh/Kratin-/assets/79844593/e91b87f5-244a-4a89-a3e1-afcbc05f63f9)

Analyzed and visualized the data 

![image](https://github.com/1Mukhesh/Kratin-/assets/79844593/f70b955b-fec9-4f08-9cab-5635ae988079)

![image](https://github.com/1Mukhesh/Kratin-/assets/79844593/4982d1cb-1a27-4693-9263-b676d796b270)

![image](https://github.com/1Mukhesh/Kratin-/assets/79844593/f09a523f-d589-4ed9-b67d-182e39728b11)

![image](https://github.com/1Mukhesh/Kratin-/assets/79844593/dcfad411-2474-4cb4-a96c-3acf0515377f)

 
calculated the Variance Inflation Factor (VIF) for each independent variable in a dataset. VIF is a measure of Multicollinearity among predictor variables in 
analysis. High VIF values indicate that the predictor variables are highly correlated with each other, which can cause issues such as unstable coefficient estimates and inflated standard errors in  models.


![image](https://github.com/1Mukhesh/Kratin-/assets/79844593/597464e9-44af-4edf-be85-2f96b12cc998)


it comes out to be there is Multicolinearity in data. so to reduce this Multicolinearity between the Predictor variables. so to reduce this multicolinearity issue performed Pca with 7 principle Components.meaning the dimensionality of the dataset is reduced to 7 principal components. so overall we eliminated the multicolinerty issue.

took out few samples form data to demostrate. on the best final model achieved.
![image](https://github.com/1Mukhesh/Kratin-/assets/79844593/24ea5844-c658-4658-b624-5b13665a6045)

## Model Building

first splitted the whole dataset into training and testing data. we rae using 70% of the data for traing and remining 30% to teating perpose and created a basic random forest model with 100 trees and achieved 95% of accuracy on test data and 100% accuracy on the training dataset which means the model is overfitting the data, meaning the model is memorising the training data and failed to find to the under lying pattren in the data but this can be rectified with parameter tuning.

![image](https://github.com/1Mukhesh/Kratin-/assets/79844593/7ac9cb33-60f5-4ff7-a0ef-c639b81bddac)

used grid search cv to find the best parameters of the random forest with 5 cross validation folds. 

![image](https://github.com/1Mukhesh/Kratin-/assets/79844593/e5d803bd-dae2-4b87-ae57-a59c027d1e7f)

trained new random forest model by taking the best parameters referance. and used cross validation technique to train the best model on data to get more reliable results and tested the accuracy of the model in each fold. got the mean accuracy of 0.9225352112676056 and Standard deviation of CrossValidation accuracy: 0.021360212518455046

printed the feature importance of the model. 

![image](https://github.com/1Mukhesh/Kratin-/assets/79844593/747c6473-171b-4546-ba1a-3e0fba35f8b4)

passed the prototype data to the final model and print the predictions. 
if model finds that the person is at the risk of heart attack then it will print "The patient is at RISK of a HEART ATTACK." and will give the factores that lead him/her to the risk of heart attack.
if model find that the person is not at the risk of heart attack then 
the model will print  "The patient is not at risk of a heart attack."
