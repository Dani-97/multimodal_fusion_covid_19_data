# Data repository description

## Description of the three scenarios:

- **scenario_I**: experiments that only use the clinical data.

- **scenario_II**: experiments that only use the imaging data.

- **scenario_III**: experiments that fuse the clinical data with the imaging data (multimodal 
fusion).

Moreover, when saying **hospitalized_and_urgencies** we are referring to the analysis I 
(estimation of the risk of hospitalization) and when we are saying **only_hospitalized** we are 
referring to the analysis II (estimation of the risk of death).

## Directories "results_scenario_*"

**results_scenario_I**, **results_scenario_II** and **results_scenario_III** include all the results from
each scenario. All the directories include CSV files with the following name structure:

`<risk_estimation>_XGBoost_Classifier_<#features>_features_Oversampling.csv`

**<risk_estimation>** can be **hospitalized_and_urgencies** or **only_hospitalized**.

**<#features>** can be an integer that denotes the number of features used for that particular experiment or 
"all" in case all the features were selected.

Additionaly, some CSV files have the following name structure:

`<risk_estimation>_XGBoost_Classifier_<#features>_features_Oversampling_feature_ranking_<#repetition>.csv`

**<#repetition>** is an integer between 0 and 4 referring to each repetition of a particular experiment. Thus, each
file will contain the feature ranking that was obtained from the training subset in that specific iteration.

## Directories "hospitalized_and_urgencies" and "only_hospitalized"

**hospitalized_and_urgencies** and **only_hospitalized** contain the CSV files with the comparisons for each risk estimation
analyses. These comparisons include the classification metrics (accuracy, mcc, f1_score, precision, recall, specificity and
auc_roc) and the number of features of each type. These CSV files are very useful to understand the evolution of the 
performance with respect to the total number of features in general and to the specific amount of each type of features in
particular. The comparison files are named as **comparison_scenario_I.csv**, **comparison_scenario_II.csv** and 
**comparison_scenario_III.csv**. As expected, the **comparison_scenario_I.csv** will include the evolution of the performance using
only clinical data, the **comparison_scenario_II.csv** will include the evolution of the performance using only imaging data and
the **comparison_scenario_III.csv** will include the evolution of the performance using both clinical and imaging features.

