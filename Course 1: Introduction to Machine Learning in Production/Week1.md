# Week 1: Overview of the ML lifecycle and deployment

## 1. The Machine Learning Project Lifecycle
### 1.1 Welcome
+ Introduction
  + Production machine learning extends beyond model development in a Jupyter notebook
  + It combines machine learning with modern software development practices
  + Success in machine learning teams requires expertise in both machine learning and software development
  + Teams develop products or services crucial to their company's operations, requiring continuous operation
  + Challenges often arise unexpectedly, such as deployment complexities
  + Effectively deploying models is essential for maximizing their value and understanding user behavior
+ Deployment example
  + Automated visual defect inspection, common in factories, involves using inspection software to control cameras capturing images of products
  + The software sends these images to a prediction server via an API call, which determines if the product is defective
  + Based on the prediction, the inspection control software decides whether to proceed with manufacturing
  + Deploying such a machine learning model requires setting up production servers, API interfaces, and additional software
  + Prediction servers may be located in the cloud or at the edge to ensure uninterrupted operation in manufacturing environments
+ ML in production
  + Deploying machine learning models requires more than just the machine learning code itself
  + While there has been significant progress in machine learning algorithms over the last decade, the actual machine learning code represents only a small portion of the overall project
  + In production, the machine learning code is often a small orange rectangle compared to the larger blue rectangle, which represents all the code necessary for the project
  + Typically, only 5-10% of a machine learning project involves actual machine learning code
  + Bridging the gap between a proof of concept model in a Jupyter notebook and production deployment can be challenging due to the substantial amount of additional code required
  + This gap, sometimes referred to as the proof of concept (POC) to production gap, often involves writing extensive additional code beyond the initial machine learning model code
+ The requirements surrounding ML infrastructure
![Surrounding ML](https://media.licdn.com/dms/image/D5612AQHvU-_pViyBkg/article-inline_image-shrink_1500_2232/0/1685660240368?e=1713398400&v=beta&t=tGyz5nGu1RX4ukUwoboDA01nRjvrPiuK29PXZs730rQ)
  + Apart from machine learning code, managing data involves components like data collection, verification, and feature extraction
  + Post-deployment, monitoring and analyzing the system is crucial, requiring additional components
  + This course covers the various software components necessary for a successful production deployment beyond just machine learning codes

### 1.2 Steps of an ML Project
![ML lifecycle](https://seunghan96.github.io/assets/img/mlops/img6.png)
+ Scoping: Define the project and determine the application of Machine Learning (ML)
+ Data Acquisition: Obtain and organize data, establish baselines, label data, and prepare for training
+ Modeling: Select, train, and analyze errors iteratively, potentially revisiting data acquisition. Assess model performance and reliability before deployment through audits
+ Deployment: Implement the model into production, monitor, track data, and maintain the system
  + Maintenance: Adapt to changes in data distribution, retrain models, and update systems as needed
  + Continuous Improvement: Feed live data back into the system to update and enhance the model iteratively
+ This structured approach can serve as a guide for planning and executing ML projects

### 1.3 Case study: speech recognition
### 1.4 Course outline

## 2. Deployment
### 2.1 Key challenges
+ There are two major categories of challenges in deploying a machine learning model: (1) machine learning or the statistical issues; (2) software engine issues
+ Concept drift and data drift
  + Concept drift and data drift are common challenges in deployments, referring to changes in data after system deployment
  + Speech recognition systems, for example, may experience performance degradation due to changes in language or device
  + Recognizing data changes is crucial to updating learning algorithms accordingly
  + Changes can occur gradually (e.g., language evolution) or suddenly (e.g., pandemic-induced shifts in consumer behavior)
  + Examples include credit card fraud systems failing during the COVID-19 pandemic due to sudden changes in purchase patterns
  + Addressing concept drift involves adapting to shifts in the relationship between input (x) and output (y)
  + Data drift involves changes in the distribution of input data (x) over time
  + Detecting and managing changes post-deployment is critical for maintaining system performance and reliability in machine learning applications
+ Sofware engineering issues
  + Checklist of questions
    + Realtime or Batch
    + Cloud vs. Edge / browser
    + Compute resources (CPU/GPU/memory)
    + Latency, throughput (QPS)
    + Logging
    + Security and privacy
  + Software engineering issues are crucial in implementing prediction services, requiring consideration of real-time vs. batch predictions, deployment location (cloud, edge, browser), and available resources
  + The choice between real-time and batch predictions depends on application requirements, such as response time and compute availability
  + Deployment location varies based on factors like internet reliability and resource constraints, with options including cloud, edge, and web browsers
  + Resource availability, including CPU, GPU, and memory, influences software architecture decisions and model complexity
  + Latency and throughput, measured in queries per second (QPS), are critical metrics for real-time applications like speech recognition
  + Logging data for analysis and retraining, and ensuring security and privacy, are essential considerations, particularly in sensitive domains like healthcare
  + Utilizing a checklist during software design can aid in making informed decisions and ensuring appropriate software engineering choices for prediction service implementation
+ Deploying a system involves two main tasks: writing the software for production deployment and monitoring and maintaining the system's performance, particularly in response to concept drift and data drift
+ Initial deployment practices differ from those for ongoing maintenance and updates of deployed systems
+ Viewing deployment as the finish line may be misleading, as it's often just the beginning of ongoing work to adapt to changes in data and maintain model performance

### 2.2 Deployment patterns
+ Common deployment cases
  + New product/ capacity
  + Automate/assist with manual task
  + Replace previous ML system
+ Key ideas
  + Gradual ramp up with monitoring
  + Rollback
+ Visual inspection example
  + Shadow mode deployment is a common pattern where a machine learning algorithm operates alongside human inspectors without influencing factory decisions
  + During this phase, the algorithm's outputs are not used for decision-making; instead, human judgment prevails
  + The purpose is to gather data on the algorithm's performance compared to human judgment
  + This allows verification of the algorithm's accuracy before considering it for real decision-making tasks
  + Shadow mode deployment serves as an effective strategy for assessing algorithm performance before granting it decision-making authority
+ Canary deployment
  + Canary deployment is a common pattern for transitioning a learning algorithm to making real decisions
  + Initially, the algorithm is rolled out to a small fraction (e.g., 5%) of traffic
  + Operating on a small percentage allows monitoring and mitigates the impact of any mistakes on a small portion of traffic
  + Gradual ramp-up of traffic percentage occurs as confidence in the algorithm's performance grows
  + The term "canary deployment" originates from the practice of coal miners using canaries to detect gas leaks, indicating early problem detection
  + Canary deployment aims to identify issues early, minimizing potential consequences in factory or other contexts where the algorithm is deployed
+ Blue green deployment
<br/>![blue green deployement](https://i0.wp.com/neptune.ai/wp-content/uploads/2022/10/Model-Deployment-Strategies_13.png?resize=795%2C314&ssl=1)<br/>
  + Blue-green deployment is another deployment pattern used in transitioning between software versions
  + In this scenario, the existing software version is referred to as the "blue" version, while the new version, incorporating the learning algorithm, is the "green" version
  + Initially, all traffic is routed to the blue version, allowing it to make decisions
  + When ready to switch to the new version, traffic routing is instantly redirected to the green version
  + This deployment strategy enables quick rollback to the blue version if issues arise, providing an added layer of safety
  + Blue-green deployment can be implemented either with a sudden 100% traffic switch or gradually, depending on preference and requirements
+ Degrees of automation
![degree of automation](https://velog.velcdn.com/images%2Fyeomja99%2Fpost%2Ffa86d7ec-2002-45f8-93e4-19ddff4bf67c%2Fimage.png)
  + Deployment should be viewed as a spectrum of automation rather than a binary decision of deploy or not deploy
  + Various degrees of automation exist, ranging from human-only systems to full automation with machine decisions
  + Shadow mode deployment allows learning algorithms to provide predictions without influencing factory decisions
  + AI assistance provides human inspectors with highlighted regions of interest, enhancing decision-making
  + Partial automation involves the algorithm making decisions confidently, but deferring uncertain cases to humans
  + Human judgment in partial automation can be valuable for algorithm improvement
  + Partial automation is suitable when algorithm performance isn't sufficient for full automation
  + Full automation entails the algorithm making all decisions without human intervention
  + Deployment applications typically start with human-centric decisions and gradually transition to full automation based on system performance and application needs
  + Both AI assistance and partial automation fall under the category of human-in-the-loop deployments
  + While consumer software often requires full automation, many applications, such as factory inspections, benefit from human-in-the-loop deployments

### 2.3 Monitoring
+ Monitoring dashboard
  + Monitoring a machine learning system's performance is commonly done through dashboards that track various metrics over time
  + Dashboards can monitor different aspects depending on the application, such as server load or the fraction of non-null outputs in a speech recognition system
  + Significant changes in monitored metrics may indicate potential issues with the system
  + When deciding what to monitor, it's essential to brainstorm with the team about possible problems and determine metrics that can detect these issues
  + For example, tracking server load can help detect spikes in user traffic that may overload the service
+ Metrics
  + Metrics for monitoring machine learning systems can be categorized into software metrics and algorithmic performance metrics
  + Software metrics include memory usage, compute resources, latency, throughput, and server load
  + Input metrics assess changes in input distribution, such as average input length or percentage of missing values
  + Output metrics evaluate algorithm performance, like the frequency of null outputs in a speech recognition system or user behavior patterns
  + Deployments should be viewed as iterative processes, requiring ongoing monitoring and adjustment of metrics
  + It may take several iterations to converge on the right set of metrics, with adjustments based on real-world performance and user data
  + Setting thresholds for alarms based on chosen metrics helps identify issues and trigger necessary actions
  + Adapting metrics and thresholds over time ensures they remain relevant and effectively flag potential concerns
  + Responses to issues may involve adjusting software implementation for software-related issues or updating the model for performance or accuracy problems
  + Maintenance and retraining of machine learning models over time are often necessary to maintain optimal performance
![iterative deployment](https://editor.analyticsvidhya.com/uploads/52043MLops9.png)
+ Model maintenance
  + When updating a model, manual retraining with engineers' involvement is more common than automatic retraining
  + Developers often prefer manual intervention to ensure control over the retraining process, especially in critical applications
  + However, in some consumer software Internet applications, automatic retraining is employed
  + Monitoring the system is crucial to identifying potential problems that may necessitate deeper error analysis or acquiring additional data for model updates
  + Continuous monitoring allows for maintaining or improving system performance over time

### 2.4 Pipeline monitoring
+ Speech recognition example: Audio => VAD => Speech recognition => Transcript
  + Speech recognition systems typically employ a multi-step pipeline, starting with a Voice Activity Detection (VAD) module
  + The VAD module determines if someone is speaking before passing the audio to the speech recognition system
  + The VAD module helps optimize bandwidth usage by streaming only the relevant audio to the cloud server
  + Changes in the VAD module, such as alterations in audio clipping due to new microphone technologies, can impact the performance of the speech recognition system
  + Coordination between modules is essential in machine learning pipelines, as changes in one module can affect the performance of subsequent modules
+ User profile example: User data => User profile => Recommender => Recommended products
  + User profiles are often built using data such as clickstream data, which reveals user behavior
  + These profiles aim to capture key attributes or characteristics of users, such as car ownership, to tailor services or recommendations
  + Machine learning algorithms are typically employed to predict user attributes based on available data
  + User profiles are then utilized by recommendation systems to generate personalized recommendations for users
  + Changes in input data, such as alterations in clickstream patterns, can impact the accuracy of user profiles
  + Consequently, shifts in user profiles may affect the quality of recommendations provided by recommendation systems
+ Metrics to monitor
  + Building complex machine learning pipelines involves a mix of ML-based and non-ML-based components
  + It's beneficial to brainstorm metrics to monitor changes, including concept drift or data drift, at multiple stages of the pipeline
  + These metrics encompass software metrics for individual components or the overall pipeline, as well as input and output metrics
  + Considerations include the rate at which data changes, which varies depending on the application
  + User data generally changes relatively slowly, especially in large consumer-facing businesses, with exceptions like societal shocks such as COVID-19
  + In contrast, enterprise or business data can shift quickly due to changes in operations or manufacturing processes

## Optional References
1. [Concept and Data Drift](https://towardsdatascience.com/machine-learning-in-production-why-you-should-care-about-data-and-concept-drift-d96d0bc907fb)
2. [Monitoring ML Models](https://christophergs.com/machine%20learning/2020/03/14/how-to-monitor-machine-learning-models/)
3. [A Chat with Andrew on MLOps: From Model-centric to Data-centric](https://youtu.be/06-AZXmwHjo)
4. Konstantinos, Katsiapis, Karmarkar, A., Altay, A., Zaks, A., Polyzotis, N., … Li, Z. (2020). Towards ML Engineering: A brief history of TensorFlow Extended (TFX). http://arxiv.org/abs/2010.02013 
5. Paleyes, A., Urma, R.-G., & Lawrence, N. D. (2020). Challenges in deploying machine learning: A survey of case studies. http://arxiv.org/abs/2011.09926
6. Sculley, D., Holt, G., Golovin, D., Davydov, E., & Phillips, T. (n.d.). Hidden technical debt in machine learning systems. Retrieved April 28, 2021, from Nips.c https://papers.nips.cc/paper/2015/file/86df7dcfd896fcaf2674f757a2463eba-Paper.pdf
