> - MLOPs is a set of practices that aims to deploy and maintain machine learning models in production reliably and efficiently.
> - The term MLOps is defined as "the extension of the DevOps methodology to include machine learning and data science assets as first-class citizens within the DevOps ecology."

- Exponential growth of data
- Importance of Artificial Intelligence
- Hidden technical debt in machine learning system.
![[hiddenTechinalDebtML.png]]

- ML Teams and roles
![[mlTeamsRoles.png]]

- ML Modell in Production
![[mlInProduction.png]]


- MLOps Possible Scenarios
	- model performance starts to decays, let's take example of fraud detection:- Assume you have trained your model for fraud detection, let's say you have deployed it as well and you will see model is giving incorrect prediction, so most probably frauders changed their strategy to fraud, so you need to collect data and retrain.
	- we might need to reformulate our problem at it gets difficult to gather the data which we need.
	- Violation of assumption which we made during training.
	- Business Objectives changes.




# Post Deployment Woes
## Accounting for latency
- 53% of visits are abandoned if a mobile site takes longer than 3 seconds to load.
## Maintaining Fairness
- Microsoft created a twitter bot to learn from users. It quickly become a Racist Jerk.
## Lack of Exploitability & Auditability
## It is painfully slow.

# Model-centric vs Data-centric
## Model-centric
- Hold the _data fixed_ and iteratively improve the code/model
- Mostly people are here.
## Data-centric
- Hold the _model fixed_ and iteratively improve the data
- focus here.

# What is the business problem we are trying to solve?
- Any ML projects starts with this.
## The cost of wrong predictions
- The costs of incorrect predictions can be quite high. Overstock leads to wasted resources and possible write-offs for unsold products. Understock, on the other hand, results in missed sales opportunities and unsatisfied customers.
## Breaking down the sales forecasting process
- We decompose the forecasting process into its components tasks such as data gathering, historical sales analysis, market trend analysis, and actual forecasting.
## Identifying AI/ML Opportunities
AI/ML could be useful in the actual forecasting task, where it could analyze past sales data and market trends to predict future sales with higher accuracy than traditional methods.
## Estimating the ROI of AI/ML Implementation
The ROI could be estimated by comparing the potential increase in sales and decrease in wasted resources due to improved forecasts, against the costs of developing and maintaining the AI/ML
## Prioritizing Tasks for AI/ML Implementation
In this case, there's primarily one task could benefit from AI/ML, which is the actual forecasting. Therefore, we prioritize it for implementation.
## Structuring the AI/ML Implementation
In this case, there's primarily one task that could benefit from AI/ML, which is the actual forecasting. Therefore, we prioritize it for implementation.
## Understanding the Machine Learning Canvas
_The Machine Learning Canvas_: A tool with ten blocks that helps us structure and plan our ML application development.

# Value Proposition
- Defining the problem, its importance, and our end-user persona.
- Geoffrey Moore's value Positioning Statement Template: For (Target Customer) who(need), our (product/service) is (product category) that (benefit).
# Data Sources
- Identifying potential sources of data, including internal database, APIs, open datasets, and more.
- considering hidden costs such as data storage and purchasing external data.
# Prediction Task
- Deciding the ML task: Supervised or Unsupervised? Anomaly detection? Classification, regression, or ranking?
- Thinking about input, output, and the degree of model complexity.
# Feature Engineering
- Working with domain experts to extract features from raw data sources.
# Offline Evaluation
- Setting up metrics to evaluate system performance pre-deployment.
- Understanding model prediction errors and their impacts.
# Decisions
- Using predictions to make decisions: How will the end-user interact with our predictions?
- Possible hidden cost, including human intervention.
# Collecting Data
- Collecting new data for model re-training and preventing model decay.
- Cost considerations for data collection and the role of humans in data labeling.

# Building Models
- Deciding frequency of model re-training and associated hidden costs.
- Planning for changes in tech stack and scaling.
# Live Evaluation & Monitoring
- Setting up metrics the track system performance post-deployment.
- Understanding the correlation between model metrics and business metrics.
# When not to implement AI/ML?
- Identifying situations where AI/ML may not be the best solution.
# Workflow if Machine Learning-based Software Development
- Three main artifices in ML-based software: Data, ML Model, and Code.
- Three main phases: Data Engineering, ML Model Engineering, and Code Engineering.
# Data Engineering Introduction
- Data acquisition and data preparation
- Most resource and time-consuming phase
- Prevents propagation of data errors to the next phase.
# Data Engineering Pipeline
- Data Ingestion: Collection of data from different sources
- Exploration and Validation: Understanding data content and structure
- Data Wrangling: Formatting and cleaning the data
- Data Labeling: Assigning category to data points
- Data Splitting: Division of data into training, validation, and test datasets.
# Model Engineering Introduction
- Core of the ML workflow: writing and executing ML algorithms
- Obtaining the ML model
# Model Engineering Pipeline
- Model Training: Applying ML algorithms on training data
- Model Evaluation: Validating the model pre-deployment
- Model Testing: Final acceptance test using test dataset.
- Model Packaging: Exporting model into a consumable format for business application.
# Model Deployment Introduction
- Model Serving: Addressing the ML model in a production environment
- Model Performance Monitoring: Observing performance on live, unseen data
- Model performance Logging: Recording every inference request



# Reference
- [3 hours mlops free course youtube](https://www.youtube.com/watch?v=dPmH3G9NQtY&list=PPSV)
- 