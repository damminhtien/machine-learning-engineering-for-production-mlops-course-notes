# Week 2: Select and Train a Model

## 1. Selecting and Training a Model
### 1.1 Key challenges
+ Model development is an iterative process
+ Model + Hyper params + data -> Tranining -> Error analysis
+ Challenges in model development
   + Doing well on traing set (usually measured by average training error)
   + Doing well on dev/test sets
   + Doing well on business metrics/project goals 
### 1.2 Why low average error isn't good enough
+ Performance on disproportionately important examples
+ Performance on key slices of the dataset
+ Rare classes
### 1.3 Establish a baseline
+ Establishing a baseline level of performance
+ Unstructured and structured data
### 1.4 Tips for getting started
+ Getting started
   + Literature search to see what's possible (course, blogs, open-source projects)
   + Find open-souce implementations if available
   + A reasonable algorimth with good data will often outperform a great   algorimth with no so good data
+ Holding the model fixed, work to improve the data to do well on the problem
# 2. Error analysis and performance auditing
## 2.1 Error analysis example 
+ Error analysis is a heart of machine learning development process
## 2.2 Prioritizing what to work on
+ Decide on most important categories to work on based on:
   + How much room for improvement there is
   + How frequently that category appears
   + How easy is to improve accuracy in that category
   + How important it is to improve in that category
+ Adding/improving data dor specific categories
   + For categories you want to prioritize:
      +  Collect more data
      +  Use data augmentation to get more data
      +  Improve label accuracy/data quality
## 2.3 Skewed dataset
+ Skewed dataset is the dataset having ratio of positive-negative very far from 50-50
+ Use confusion matrix
+ Precision, Recall, F1
## 2.4 Auditing Performance
1. Brainstorm the ways the system might go wrong
   + Performance on subsets of data (eg ethnicity, gender)
   + How common are certain errors (eg FP, FN)
   + Performance on rare classes
2. Establish metrics to assess performance against these issues on appropriate slices of data
3. Get bussiness/product owner buy-in

## 2. Data centric
### 2.1 Data-centric AI development
+ Model centric view
   + Take the data you have, and develop a model that does as well as possible on it
   + Hold the data fixed and iteratively improve the code/model
+ Data centric view
+  The quality of data is paramount. Use tools to improve the data quality, this will allow multiple models to do well
+  Hold the code fixed and iteratively improve the data
