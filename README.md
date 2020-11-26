# A/B Testing

Final project based on Udacity's [A/B Testing](https://www.udacity.com/course/ab-testing--ud257) course.

<img src="https://www.amazeemetrics.com/content/uploads/2016/12/ab-testing-blog.png" width="500" height="300"/>

## Experiment Background - Free Trial Screener

Students have a choice between enrolling in a free trial for the paid version or to access the course material for free (without coaching support or a verified certificate). With this experiment, Udacity tried to divert students to the free course material with a 'trial screener' if they did not input the minimum weekly commitment time to complete the course within the 14-days trial period.

![screener](/Final_Project_Experiment_Screenshot.png)


## Experiment Setup

### Unit of Diversion

The unit of diversion used for this experiment is a cookie.

### Initial Hypotheses

- Check if the experiment reduced the number of students enrolling in the free trial 

    * H<sub>0</sub>: The experiment has no effect on the number of students who enroll in the free trial
    * H<sub>1</sub>: The experiment reduces the number of students who enroll in the free trial


- Check if the experiment reduced the number of students leaving the free trial (not enough time to complete the course)

    * H<sub>0</sub>: The experiment has no effect on the number of students who leave the free trial
    * H<sub>1</sub>: The experiment reduces the number of students who leave the free trial


- Check if the experiment caused a significant change in the number of students who continue past the free trial (we will not check if the student completed the course as it requires a big time investment)

    * H<sub>0</sub>: There is no significant difference in the number of students who continue past the free trial
    * H<sub>1</sub>: There is a significant difference in the number of students who continue past the free trial


### Choice of Metric

#### Evaluation Metric

| <p align="left">Metric</p>                   | <p align="left">Formula</p>                                                               | <p align="left">d<sub>min</sub></p> |
| ------------------------- | ---------------------------------------------------------------------- | --------------------------------------- |
| <p align="left">Gross Conversion</p>        | <p align="left"> Gross Conversion = # of user-ids that enrolled / # Clicks</p>      | <p align="left">0.01</p>                                    |
| <p align="left">Retention</p>         | <p align="left"> Retention = # of user-ids that paid / # of user-ids that enrolled</p>  | <p align="left">0.01</p>                                   |
| <p align="left">Net Conversion</p> | <p align="left"> Net Conversion = # of user-ids that paid / # Clicks</p>                                                         | <p align="left">0.0075</p>                                    |

#### Invariant Metric
## Measuring Variability
## Sizing the Experiment
## Experiment Analysis
### Sanity Check
### Practical and Statistical Significance
### Sign Tests
## Summary
## Recommendation
## Follow-Up Experiment
