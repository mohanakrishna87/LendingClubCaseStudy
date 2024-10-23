# Lending Club Case Study

## Table of Contents
* [Problem Statement & Business Objective](#problem-statement&business-objectives)
* [Data Understanding](#data-understanding)
* [Data Cleaning](#data-cleaning)
* [Data Conversion](#data-conversion)
* [Univariate Analysis](#univariate-analysis)
* [Bivariate Analysis](#bivariate-analysis)
* [Correlation Analysis](#correlation-analysis)
* [Proposals](#proposals)
* [References](#references)

## Problem Statement & Business Objective
Lending Club is a company specializes in lending various types of loans to urban customers.
When the company receives a loan application, the company has to make a decision for loan approval based on the applicant’s profile.
Two types of risks are associated with the bank’s decision: 
If the applicant is likely to repay the loan, then not approving the loan results in a loss of business to the company
If the applicant is not likely to repay the loan, i.e. he/she is likely to default, then approving the loan may lead to a financial loss for the company 
The data given in the CSV contains information about past loan applicants and whether they ‘defaulted’ or not. 
The aim is to identify patterns which indicate if a person is likely to default, which may be used for taking actions such as denying the loan, reducing the amount of loan, lending (to risky applicants) at a higher interest rate, etc.
When a person applies for a loan, there are two types of decisions that could be taken by the company:   
Loan accepted: If the company approves the loan, there are 3 possible scenarios described below:       
Fully paid: Applicant has fully paid the loan (the principal and the interest rate)        
Current: Applicant is in the process of paying the instalments, i.e. the tenure of the loan is not yet completed. These candidates are not labelled as 'defaulted'.        
Charged-off: Applicant has not paid the instalments in due time for a long period of time, i.e. he/she has defaulted on the loan     
Loan rejected: The company had rejected the loan (because the candidate does not meet their requirements etc.). Since the loan was rejected, there is no transactional history of those applicants with the company and so this data is not available with the company (and thus in this dataset)

## Data Understanding
Dataset Attributes:
Primary Attribute : loan_status : This is the column that we can solely depend on for our analysis. This column has three values 
Fully_Paid : Customers who have fully paid off the loan
Charged_Off : Defaulters who did not pay the installments 
Current : Active applicants who are paying the installments on regular basis
We are excluding “Current” values from our analysis as this category of customers will not help in our analysis
All these attributes provided by the customer while filling the loan application form are useful for our analysis
These attributes can be further classified into two categories
Customer related : DTI, annual_income, house_ownership, emp_length etc
Loan business related: loan_amnt, term, issue_d, purpose, int_rate etc

## Data Cleaning
We have 111 columns in the provided data. 
On careful analysis, we have performed the below operations to clean up the data
Dropped Customer behaviour columns : 'collection_recovery_fee', 'delinq_2yrs', 'desc', 'earliest_cr_line', 'emp_title', 'id', 'inq_last_6mths', 'last_credit_pull_d', 'last_pymnt_amnt', 'last_pymnt_d', 'member_id', 'open_acc', 'out_prncp', 'out_prncp_inv', 'pub_rec', 'recoveries', 'revol_bal', 'revol_util', 'title', 'total_acc', 'total_pymnt', 'total_pymnt_inv', 'total_rec_int', 'total_rec_late_fee', 'total_rec_prncp', 'url’ 
54 columns were having empty values. Directly dropped those columns
There are 9 columns with unique values which were dropped as they wont make any sense for analysis
No duplicate rows were found
Dropped all the rows whose loan_status = ‘current’ 
Dropped 3 columns are the % of missing values is >=65%

## Data Conversion
Converted all the numeric columns to float to maintain the uniformity
Int_rate column was of object type and contained % symbol in the values. Removed % symbol and converted the values into int 
Removed ‘months’ string from term column and converted into int
Rounded off the useful numeric column values to 2 digits
Converted issue_d column to YYYY-MM-DD format 

## Univariate Analysis

## Bivariate Analysis

## Proposals
Thorough assessment for High loan amounts ( > 15K USD)
Careful Consideration for those who are taking loans for Debt Consolidation purpose
Dynamic interest rates : Consider having flexible interest rates based on the DTI
Home Ownership : Minimize the loan approval process and make it easy to get loans for those applicants who owns a house. 
Annual Income consideration : introduce maximum affordable capping of loan amount for those applicants whose annual income < 40K USD

## Technologies Used
- [Python - Version 3.9.12](https://www.python.org/download/releases/3.0/)
- [numpy - Version 1.21.5](https://github.com/numpy)
- [pandas - Version 1.4.2](https://github.com/pandas-dev/pandas)
- [matplotlib - Version 3.5.1](https://github.com/matplotlib)
- [seaborn - Version 0.11.2](https://github.com/seaborn)
- [Jupyter Notebook - Version 3.3.2]()

## Acknowledgements
Give credit here.
- The project references insights and inferences from live presentation by Upgrad faculty
- The project reference course materieals from upGrads curriculm 
- https://stackoverflow.com/questions/56611698/pandas-how-to-read-csv-file-from-google-drive-public
- 


## Contact
Team :
[Mohana Krishna V](https://www.linkedin.com/in/mohana-krishna-436178141/)
[Monalisa Patra](https://www.linkedin.com/in/monalisa-p-39a63757)
