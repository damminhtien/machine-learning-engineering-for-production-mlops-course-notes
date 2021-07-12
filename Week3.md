# Week 3: Define data and baseline

## 1. Define Data and Establish Baseline
### 1.1 Why data definition is hard?
+ The labels may be inconsistent
+ Preparing data well will have huge impact on success of ML project

### 1.2 More label ambiguity examples
+ Data definition questions:
  + What is the input x?
    + Lighting? Contract? Resolution?
    + What features need to be included?
  + What is the target label y?
    + How we can ensure labeler give inconsistent labels?

### 1.3 Major types of data problems
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

### 1.4 Small data and label consistency

### 1.5 Improving label consistency
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
 
### 1.6 Human level performance (HLP)
  + Why measure HLP?
    + Estimate Bayes error / irreduciblle error to help with error analysis and prioritization 
  + Other uses of HLP
    + In academia, establish and beat a respectable benchmark to support publication
    + Business or product owner asks for 99% accuracy. HLP helps establish a more reasonable target
    + 'Prove' the ML system is superir to humans doing the job and thus the business or product owner should adopt it

### 1.7 Raising HLP
  + When the ground truth label is externally defined., HLP gives an estimate for Bayes error / irreducible error. But often GT is just another human label
  + When the label y comes from a human label. HLP << 100% may indicate ambiguous labeling instruction
  + Improving label consistency will raise HLP
  + This makes it harder for ML to beat HLP But the more consistent labels will raise ML performance, which is ultimately likely to benefit the actual application performance
 
## 2.Label and Organize Data
### 2.1 Obtaining data
+ How long should you spend obtaining data?
  + Get into this iteration loop as quickly possible
  + Instead of asking: How long it would take to obtain m examples? Ask: How nuch data can we obtain in k days
  + Exception: if you have worked on the problem before and from experience you know you need m examples
+ Labeling data
  + Options: in-house vs. outsourced vs. crowdsourced
  + Having MLEs label data is expensive. But doing this for just a few days is usually fine
  + Who is qualified to label?
    + Speech recognition - any reasonably fluent speaker
    + Factory inspection, medical image diagnosis - SME (subject matter expert)
    + Recommender systems - maybe impossible to label well
  + Dont increase data more than 10x at a time


