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


### Obstetrics and periodontal therapy 

The `opt` data frame in the `opt.rData` file contains data from a randomized controlled trial that was used to determine whether treatment of maternal periodontal disease can reduce risk of preterm birth and low birth weight. This dataset was taken from the [`medicaldata` R package](https://github.com/higgi13425/medicaldata); documentation can be found [here](https://higgi13425.github.io/medicaldata/reference/opt.html). Your goal is to assess if maternal periodontal disease treatment impacts birthweight and determine whether treatment should be recommended moving forward. 

During the data processing step, you will need to create a low birthweight variable, where low birthweight is defined as <2500 g. This is the outcome variable that you should use in your models. Please note that several numeric variables were coded as factors in this dataset (see documentation or explore this on your own), but you most likely do not want to treat them as factors/categorical. 

