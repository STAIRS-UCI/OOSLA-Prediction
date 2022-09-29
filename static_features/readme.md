## Use Static Features on bug report close time prediction

In this folder, we provide three notebooks showing experimental results for predictions at 25%, 50%, and 75% of the specified SLA time.

Below are the static features that we used from paper "Predicting bug-fixing time: an empirical study of commercial software projects":

| **Feature name** | **Description**                                                                                                                    |
|------------------|------------------------------------------------------------------------------------------------------------------------------------|
| Submitter        | the bug report submitter                                                                                                           |
| Owner            | the developer who is responsible for resolving the bug.                                                                            |
| Severity         | the severity of a bug report                                                                                                       |
| Priority         | the priority of a bug report (Critical, Serious, Medium, Minor).                                                                   |
| ESC              | indicating whether the bug is externally discovered (reported by end-users) or an internally discovered bug (reported by QA team). |
| Category         | the category of the bug (such as Account management, Documentation, Configuration, etc.).                                          |
| Summary          | a short description of the bug.  
