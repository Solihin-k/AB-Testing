# Free Trial Screener

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

| <p align="left">Metric</p>                   | <p align="left">Formula</p>                                                               | <p align="left">d<sub>min</sub></p> |
| ------------------------- | ---------------------------------------------------------------------- | --------------------------------------- |
| <p align="left">Number of cookies</p>        | <p align="left"> # of unique daily cookies to view the course overview page</p>      | <p align="left">0.01</p>                                    |
| <p align="left">Number of clicks</p>         | <p align="left"> # of unique daily cookies to click the 'start free trial' button</p>  | <p align="left">0.01</p>                                   |
| <p align="left">Click-through-probability (CTP)</p> | <p align="left"> # clicks / # cookies</p>                                                         | <p align="left">0.0075</p>                                    |


## Measuring Variability

The standard errors (SE) of the evaluation metrics were calculated analytically. We expect the analytically calculated standard error of retention to not match the empirically standard error as the unit of diversion and unit of analysis is different.

Metric_Name | SE 
------------ | ------------- 
Gross_conversion | 0.020231
Retention | 0.054949
Net_conversion | 0.015602


## Sizing the Experiment

Retention was dropped at this point as we would need to conduct the experiment for 119 days if Udacity were to divert its entire traffic.

Metric_Name | sample_size 
------------ | ------------- 
Gross_conversion | 638940
Retention | 4737771
Net_conversion | 685336


## Experiment Analysis

### Sanity Check

All three of our invariant metrics passed the sanity check (equally distributed between the control and experiment group).

Metric_name | CI_lower | CI_upper | margin_error | within_CI
------------ | ------------- | ------------ | ------------- | -------------
Cookies | 0.49882 | 0.50118 | 0.5006 | yes
Clicks | 0.495884 | 0.504116 | 0.5005 | yes
CTP | 0.0798659 | 0.0.0843857 | 0.0821824 | yes


### Practical and Statistical Significance

Gross conversion is both statistically and practically significant. Net conversion is neither statistically nor practically significant.

Metric_name | CI_lower | CI_upper | d-hat | stat_sig | prac_sig
------------ | ------------- | ------------ | ------------- | ------------- | --------------
Gross_conversion | -0.0291203 | -0.0119894 | -0.0100 | yes | yes
Net_conversion | -0.0116043 | 0.00185686 | 0.0075 | no | no


### Sign Test

A sign test was conducted as an additional form of analysis, and the results confirmed our earlier conclusion on the statistical significance of the evaluation metrics.

Metric_name | num_success | p_value | stat_sig 
------------ | ------------- | ------------ | ------------- 
Gross_conversion | 4 | 0.0026 | yes 
Net_conversion | 10 | 0.6776 | no 


## Summary

The gross conversion rate dropped in the experimental group by approximately 2% and the screener proved to be effective at reducing the number of students that enrolled in the free trial. Net conversion, however, was reduced by approximately 0.5% indicating that the screener had a negative effect on the number of students that would go on to complete the 14-day trial.


## Recommendation

Recommended to not launch the change to Udacity's website.
