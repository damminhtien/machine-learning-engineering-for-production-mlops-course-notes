# Week 1: Collecting, Labeling and Validating Data
## 1. Introduction
### 1.1 Overview
+ The importance of data: 
  + Data is the hardest part of ML and the most important piece to get right ... Broken data is the most common cause of problems in production ML systems - Uber
  + No other activity in the ML lifecycle has a higher return on investment than improving the data a model has access to - Gojek
+ Managing the entire life cycle of data
  + Labeling
  + Feature space coverage
  + Minimal dimensionality
  + Maxium predictive data
  + Fairness
  + Rare conditions
+ Modern software development, accounts for
    + Scalability
    + Extebsibility
    + Consistency & reproducibility
    + Safety & security
    + Modularity
    + Testability
    + Monitoring
    + Best practices
### 1.2 ML pipelines
  + TFX: Data ingestion -> Data validation -> Feature Engineering -> Train model -> Validate model -> Push if good -> Serve Model 

## 2. Collecting data
### 2.1 Importance of data
+ Everything starts with data
  + Model aren't magic
  + Meaningful data:
    + maximize predictive content
    + remove non-informative data
    + feature space coverage
+ Garbage in, garbage out
  + data in, prediction out
+ Key points
  + Understand users, translate user needs into data problems
  + Ensure data coverage and high predictive signal
  + Source, store and monitor quality data responsibly

