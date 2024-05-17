# deep-learning-challenge
Module 21 for U of M Data Analysis and Visualization Bootcamp


For this part of the assignment, you’ll write a report on the performance of the deep learning model you created for Alphabet Soup.

The report should contain the following:

Overview of the analysis: Explain the purpose of this analysis.

## Overview of the analysis

We are asked to build a model to predict whether applicants will be successful if funded by Alphabet Soup. To this end, we are provided a CSV file from Alphabet Soup listing past applicants, some key factors about their business, and whether or not the applicant was successful in their venture.

### Data Preprocessing

### What variable(s) are the target(s) for your model? 

Answer: the target for modeling is the IS_SUCCESSFUL binary variable. It is 1 if the applicant was successful, and 0 if not.

### What variable(s) are the features for your model?

Answer: Following the preprocessing steps in the notebook, we removed the columns 'EIN' and'NAME' as they were not useful for the analysis. We then combined some categories of 'APPLICATION_TYPE' that had a small number of values into a larger "Other" category, and did a similar reduction for the 'CLASSIFICATION' column. We then converted
the categorical features to numeric using pd.get_dummies(), split our data into train and test sets,  and finally scaled the data to prepare it for modeling purposes.



### Compiling, Training, and Evaluating the Model




## Results: Using bulleted lists and images to support your answers, address the following questions:



### How many neurons, layers, and activation functions did you select for your neural network model, and why?

In our initial network, we selected the following properties to get a baseline model:

number_input_features = 42

hidden_nodes_layer1 =  8

hidden_nodes_layer2 = 5

This is ok for a baseline model. We will further refine this by using keras_tuner in the next step.

Results of this model are as follows:

![https://github.com/schr0841/deep-learning-challenge/blob/main/images/img1.png]

### Were you able to achieve the target model performance?

### What steps did you take in your attempts to increase model performance?

On second look, the data preprocessing steps as instructed in the notebook are not the best way to go about it. The variable INCOME_AMT is an ordinal categorical variable with defined levels, but we lose information about this by using one-hot encoding. On the Step 3 of the notebook, we re-cleaned the data but accounted for this fact. We also input the levels explicitly as arguments to OrdinalEncoder(), as the default settings produced an incorrect ordering. 

### Summary: Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation.
