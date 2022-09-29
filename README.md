# Team involvement and modification evolution history representation Learning on Bug Reports

This repository hosts the companian experiment results for paper "Out of Time: A Case Study of Using Team and Modification Representation Learning for Improving Bug Report Resolution Time Prediction in eBay". In this study, we compared the state-of-the-art bug report features that were proposed for bug report close time prediction with the features proposed by us. 

Folder "static_features" contains experimental result notebooks using static features, folder "contextual_dynamic_feature" contains experimental result notebooks using contextual and dynamic features, and folder "evolution_features" contains experimental results notebooks where our proposed bug report team participated and modified evolutionary history representations feature.

Below is the overview of our proposed feature extraction process and extrated features from bug reports to predict the report close time.

<p align="center">
  <img src="https://github.com/Jirigesi/OOSLA-Prediction/blob/main/framework.png" width="750" title="hover text">
</p>

## Comparison features
Below we present the details of the static features, contextual and dynamic features that researchers proposed for bug report close time prediction. 


## Static features 

Static features extracted from bug reports are the most popular group of features for predicting bug resolution time, so we use prediction model built using static features introduced by Zhang et al.~\cite{zhang2013predicting} as the baseline. Paper: “Predicting bug-fixing time: an empirical study of commercial software projects,” in 2013 35th International Conference on Software Engineering (ICSE). The static features contains the bug report Submitter, Owner, Severity, Priority, ESC indicating whether the bug is externally discovered (reported by end-users) or an internally discovered bug (reported by QA team), Category of the bug, and the Summary of the bug reports. 

Their F1 score was 0.728 to predict whether a bug report can be closed within the assigned time. The static features proposed by Zhang et al. included:

| **Feature name** | **Description**                                                                                                                    |
|------------------|------------------------------------------------------------------------------------------------------------------------------------|
| Submitter        | the bug report submitter                                                                                                           |
| Owner            | the developer who is responsible for resolving the bug.                                                                            |
| Severity         | the severity of a bug report                                                                                                       |
| Priority         | the priority of a bug report (Critical, Serious, Medium, Minor).                                                                   |
| ESC              | indicating whether the bug is externally discovered (reported by end-users) or an internally discovered bug (reported by QA team). |
| Category         | the category of the bug (such as Account management, Documentation, Configuration, etc.).                                          |
| Summary          | a short description of the bug.                                                                                                    |

### Dynamic and Contextual Features

The experimental results from Kikas et al.\cite{kikas2016using} indicate that their selected features outperformed existing prediction approaches. Paper: “Using dynamic and contextual features to predict issue lifetime in github projects,” in 2016 ieee/acm 13th working conference on mining software repositories. We use contextual and dynamic features introduced by Kikas et al.\cite{kikas2016using} as another baseline for our evaluation. Below are the dynamic and contextual features that Kikas et al. used:

| **Category**                          | **Feature name**                   | **Description**                                                                                                                                               |
|---------------------------------------|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Bug contextual features**           | Number of comments                 | number of comments the bug has received before the observation point.                                                                                         |
|                                       | Number of actors                   | number of unique persons involved with the bug before the observation point.                                                                                  |
|                                       | Number of labels                   | number of labels added to the bug before the observation point.                                                                                               |
|                                       | Number of subscribers              | number of persons subscribing to receive updates on the bug before the observation point.                                                                     |
|                                       | Mean comment size                  | average comment size of the comments received before the observation point.                                                                                   |
|                                       | Bug cleaned body Length            | length of the combined title and body with markdown parsed and tags removed.                                                                                  |
|                                       | Text score                         | classification score obtained from the cleaned bug title and content.                                                                                         |
|                                       |                                    |                                                                                                                                                               |
| **Bug submitter contextual features** | Number of reports from creator     | number of bug reports created by the bug submitter in the three months prior to bug opening.                                                                  |
|                                       | Number of bugs closed from creator | number of bugs created by the bug submitter that were closed in the three months prior to bug opening.                                                        |
|                                       | Number of comments by the creator  | number of total comments to the bug repository by the bug submitter in the three months before the bug opening.                                               |
|                                       |                                    |                                                                                                                                                               |
| **Participant contextual features**   | Number of comments by actors       | total number of comments performed by actors who committed code to the project repository during the period beginning from two weeks before the bug creation. |
|                                       |                                    |                                                                                                                                                               |
| **Project contextual features**       | nbugsCreatedInProject              | number of bugs created in the project during the three months prior to bug creation.                                                                          |
|                                       | nbugsCreatedInProjectClosed        | number of bugs created and closed in the project in the three months prior to bug creation.                                                                   |
|                                       | nActivityInProject                 | number of activities created in the project in the three months prior to bug creation.                                                                        |
|                                       | nbugsCreatedInProjectT             | number of bugs created in the project during the period of 2 weeks before the bug creation until the observation point time.                                  |
|                                       | nbugsCreatedInProjectClosedT       | number of bugs created and closed in the project during the period of 2 weeks before the bug creation until the observation point time.                       |
|                                       | nCommitsProjectT                   | number of commits in the project during the period of 2 weeks before the bug creation until the observation point time.                                       |


## The result of deploying predictive models on reducing Out of SLA (OOSLA) reports in eBay

We built an alert system for eBay  based on our prediction model which will send a reminder message to the responsible developer when the model predicts that a report will not be resolved within the specified time. From the below experiment result, we can observe the bug report prediction model can help company reduce the number of OOSLA reports. 



<p align="center">
  <img src="https://github.com/Jirigesi/OOSLA-Prediction/blob/main/OOSLA_ratio.png" width="550" title="hover text">
</p>
