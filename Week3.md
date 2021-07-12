# Week 3: Define data and establish baseline
### 3.1 Why data definition is hard?
+ The labels may be inconsistent
+ Preparing data well will have huge impact on success of ML project

### 3.2 More label ambiguity examples
+ Data definition questions:
  + What is the input x?
    + Lighting? Contract? Resolution?
    + What features need to be included?
  + What is the target label y?
    + How we can ensure labeler give inconsistent labels?

### 3.3 Major types of data problems
+ Unstructured versus structured data
  + Unstructured data
    + May or may not have huge collection of unlabeled examples x
    + Humans can label more data
    + Data augmentation more likely to be helpful
  + Structured data
    + May be more difficult to obtain more data
    + Human labeling may not be possible (with some exeptions)
+ Small versus big data
  + Small data
    + Clean labels are critical
    + Can manually look through dataset and fix labels
    + Can get all the labelers to talk to each other
  + Big data
    + Emphasis on data process

### 3.4 Small data and label consistency

### 3.5 Improving label consistency
+ How
  + Have multiple labelers label same example
  + When there is a disagreement, have MLE, subject matter expert (SME) and/or labelers discuss definition of y to reach agreement
  + If labelers believe that x doesn't contain enough information consider changing x
  + Iterative until it is hard to significantly increase agreement
+ Small data vs. big data (unstructured data)
  + Small data
    + Usually small number of labelers
    + Can ask labelers to discuss specific labels
  + Big data
    + Get to consistent definition with a small group
    + Then send labeling instructions to labelers
    + Can consider having multiple labelers label every example and using voting or consensus labels to increase accuracy
 
### 3.6 Human level performance (HLP)
  + Why measure HLP?
    + Estimate Bayes error / irreduciblle error to help with error analysis and prioritization 
  + Other uses of HLP
    + In academia, establish and beat a respectable benchmark to support publication
    + Business or product owner asks for 99% accuracy. HLP helps establish a more reasonable target
    + 'Prove' the ML system is superir to humans doing the job and thus the business or product owner should adopt it

### 3.7 Raising HLP
