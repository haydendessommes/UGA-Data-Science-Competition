# UGA Data Science Competition




<!-- PROJECT SHIELDS -->




<!-- PROJECT LOGO -->
<br />

  <h3 align="center">UGA Inaugural Data Science Competition</h3>
    <h4 align="center">Sponsored by Wells Fargo</h4>









<!-- ABOUT THE PROJECT -->
## About The Project

In order to apply for a loan, banks require individuals to provide things like proof of
income, proof of assets, and collateral. This is because it is not in the bank’s best interest to
loan money to people who are likely to default. However, even with ensuring that they only loan
money to the most responsible people, it is still not uncommon for people to default. If there was
a model that predicted whether someone would default based on data on their credit history,
banks could distribute money for loans more effectively. The goal of this project is to do just that,
build a model to predict whether or not a person will default on their loan based on their credit
history data.

The full report and code for data manipulation and logistic regression are contained in this repository. 

## Data
The datasets consist of historical data from a hypothetical bank XYZ in the Southeastern US. We were given a test dataset (5,000 records), a training dataset (20,000 records), and a validation dataset (3,000 records), each of which contains 20 predictor variables and one response variable. The response variable is Default_ind, an indicator variable that equals 1 if the approved account defaulted, and equals 0 if not defaulted. The predictor variables and their descriptions are shown below:
* Total debt on all credit products
* Average debt on all credit cards over last 12 months
* Age (months) of first credit product
* Age (months) of first credit product currently in good standing
* Age (months) of first credit card
* Number of non-mortgage credit products past due in last 12 months
* Number of non-mortgage credit products past due in last 6 months
* Number of mortgages past due in last 6 months
* Total amount of money past due on all accounts
* Number of credit inquiries in last 12 months
* Number of credit card inquiries in last 24 months
* Number of credit cards opened in last 36 months
* Number of auto loans opened in last 36 months
* Utilization on all credit card accounts
* % of open credit products with >50% utilization
* Utilization of credit product with highest credit limit
* % of open credit cards with >50% utilization
* Indicator: 1 if applicant has an account with XYZ Bank; 0 otherwise
* Self-reported annual income
* Residence state (AL, FL, GA, LA, MS, NS, SC)



### Exploratory Data Analysis

The majority of applicants did not default on their loans. Of the 20,000 records in the training set, only 1,586 of them (7.93%) defaulted. This class imbalance will be addressed later on in the report. For the predictors, there are several different classes of variables in the dataset. Most of the variables are continuous. However there are a few countable numeric variables, an indicator variable, and a categorical variable. Figures showing the distributions for each predictor can be shown in the report contained in this repository. Most of the numeric variables appear to be normally distributed, and several are skewed to the right. The only categorical predictor variable is the state indicator, which we will convert into binary indicators for each state. Only 3 predictors contained missing variables, each between 7%-10% of the total number of records: uti_card_50plus_pct, rep_income, avg_card_debt. The variables were tested to be missing at random, so they were imputed from the existing data. The records were then tested for multicollinearity, and the following predictors contained problematically high VIF numbers and were removed: credit_age, card_age, mortgages_past_due_6_months_num, credit_past_due_amount, uti_card. 

More details regarding our EDA Process can be found in our report.






<!-- GETTING STARTED -->
## Logistic Regression Modelling

Now that we have our predictor variables ready, we decided to run a stepwise regression to make sure we were only including predictors that had a significant impact on the model. This narrowed down the number of predictors to 10. A chart containing the odds ratios for each variable are shown in the report. Results of the logistic regression are shown below:

Precision: 0.2192

Recall: 0.7107

Accuracy: 0.7738

F1 Score: 0.3351


### Random Forest

We were assigned to produce two models: one logistic, and one machine learning model of our choice. We ran and fine-tuned this model through Weka, so no code is available. After running many models, we found Random Forest to be one of the most accurate, and was the easiest to explain to stakeholders. We decided to narrow down the number of predictors based off the mean decrease in Gini index, and then ran the model. The results were opposite to our logistic model, and are as follows:

Precision: 0.7987

Recall: 0.2967

Accuracy: 0.9376

F1 Score: 0.4327



### Conclusion

Although our Random Forest model had higher Accuracy and Precision, we recommended using the logistic model, as it higher recall. This is because the cost of approving a loan that will default is much higher than denying a loan that will not default. Going forward, we would like to explore more methods of machine learning and fine tune our logistic regression to produce a higher accuracy.  



## Contributers

Thomas Hills

William Matray

Patrick Nercession


