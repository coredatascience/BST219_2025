# Final project prompt

 You and your team of data scientists were hired by a company to gain insights on the dataset in your chosen prompt. 

1. Perform any necessary data pre-processing and cleaning, and document your steps. Depending on the prompt you selected, this may involve transforming variables, creating new variables, and merging data frames. In particular, you may need to make some decisions on how to handle missing data, such as removing rows or columns with a significant amount of missing observations, creating an "unknown" category, or replacing/imputing the missing values. You do not need to develop a rigorous process or cite references, but please briefly justify your choices. 

2. Make and interpret 4-10 visualizations to help you understand the relationships between the variables in your dataset. We highly encourage you to explore the data on your own, but when preparing your response to this question, please be parsimonious in your plots and select visualizations that help you tell a story about the data. If you need to make additional plots to support your responses to the other questions (e.g. to motivate data cleaning or modeling choices), that's fine. 

3. Build any 2 machine learning models that use your choice of covariates to predict the given outcome variable. Explain why you chose those covariates and interpret the model performances. If you are including categorical variables as covariates in a `glmnet` model (lasso or ridge regression), please remember that you will need to convert your covariate data frame into a *model matrix*, e.g. by calling the `model.matrix` function:

```r
model_matrix = model.matrix(~.-1, my_covariate_df)
```

4. The company stakeholders want to know what decision they should make on their stated goal/question. Based on your analysis, make recommendations for a non-technical audience. 

5. Any additional information that might be useful to collect/have? Other open-ended/non-coding question(s)? 


### NYPD complaints

The file `allegations_202007271729.csv` contains records about closed cases for every police officer on the NYPD force as of late June 2020 who had at least one substantiated allegation against them, spanning from September 1985 to January 2020. Information on the variables in this dataset can be found in `CCRB Data Layout Table.xlsx`. This data was downloaded from 
[Kaggle](https://www.kaggle.com/datasets/mrmorj/civilian-complaints-against-nyc-police-officers) and originally reported on by ProPublica. Your goal is to recommend a model to predict the disposition ruled by the Civilian Complaint Review Board (CCRB) and identify key variables that appear to be associated with the board's ruling. 

Please restrict your analysis to observations that were either "Substantiated" or "Exonerated", excluding observations that were "Unsubstantiated". This means that your models should predict whether the CCRB determined that the officer violated NYPD rules (yes = Substantiated, no = Exonerated), excluding cases where the CCRB could not conclude if the conduct occurred (Unsubstantiated). If you choose to incorporate information on officer rank and command, you will most likely want to collapse or otherwise simplify the categories for these variables (see the Rank Abbrevs and Command Abbrevs tabs in `CCRB Data Layout Table.xlsx`). If you do so, please briefly justify your reasoning. 

