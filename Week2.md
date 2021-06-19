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
