## Use contextual and dynamic features on bug close time prediction

In this folder, we provide three notebooks showing experimental results for predictions at 25%, 50%, and 75% of the specified SLA time.

Below are the contextual and dynamic features that we used from paper "Using dynamic and contextual features to predict issue lifetime in github projects":

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

