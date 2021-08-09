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
