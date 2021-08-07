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
## 2. Error analysis and performance auditing
### 2.1 Error analysis example 
+ Error analysis is a heart of machine learning development process
### 2.2 Prioritizing what to work on
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
### 2.3 Skewed dataset
+ Skewed dataset is the dataset having ratio of positive-negative very far from 50-50
+ Use confusion matrix
+ Precision, Recall, F1
### 2.4 Auditing Performance
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
### 2.2 A useful picture of data augmentation 
### 2.3 Data augmentation 
+ Goal: Create realistic examples that the algorimth does poorly on, but humans (or other baseline) do well on
### 2.4 Can adding data hurt
For unstructured data problems, if:
+  The model is large (low bias)
+  The mapping x -> y is clear (eg given only the input x, humans can make accurate predictions)<br>
The adding data rarely hurts accuracy
### 2.5 Adding features
### 2.6 Experiment tracking
+ What to track?
   + Algorimth/code versioning
   + Dataset used
   + Hyperparameters
   + Result
+ Tracking tools
   + Text files
   + Spreadsheet
   + Experiment tracking system
+ Desirable features
   + Information needed to replicate result
   + Experiment result, ideally with summary metrics/analysis
   + Perhaps also: resource monitoring, visuallisation, model error analysis
### 2.7 From bigdata to good data
Try to ensure consistently high-quality data in all phases of the ML project lifecycle <br>
Good data:
+ Covers important cases (good coverage of inputs x)
+ Is defined consistently (definition of labels y is unambiguous)
+ Has timely feedback from production data (distribution covers data drift and concept drift)
+ Is sized appropriately

## Week 2 Optional References
1. [Establishing a baseline](https://blog.ml.cmu.edu/2020/08/31/3-baselines/)
2. [Error analysis](https://techcommunity.microsoft.com/t5/azure-ai/responsible-machine-learning-with-error-analysis/ba-p/2141774)
3. [Experiment tracking](https://neptune.ai/blog/ml-experiment-tracking)
4. Brundage, M., Avin, S., Wang, J., Belfield, H., Krueger, G., Hadfield, G., … Anderljung, M. (n.d.). Toward trustworthy AI development: Mechanisms for supporting verifiable claims∗. Retrieved May 7, 2021 [link](http://arxiv.org/abs/2004.07213v2)
5. Nakkiran, P., Kaplun, G., Bansal, Y., Yang, T., Barak, B., & Sutskever, I. (2019). Deep double descent: Where bigger models and more data hurt. [link](http://arxiv.org/abs/1912.02292)
