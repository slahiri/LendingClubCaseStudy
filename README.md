# Lending Club Case Study

## Table of Contents
* [Problem Statement](#problem-statement)
* [Objectives](#objectives)
* [Dataset Analysis](#dataset-analysis)
* [Conclusions](#conclusions)
* [Technologies Used](#technologies-used)
* [Acknowledgements](#acknowledgements)
* [Glossary](#glossary)
* [Team](#team)

## Problem Statement
Lending Club is a consumer finance marketplace for personal loans that matches borrowers who are seeking a loan with investors looking to lend money and make a return.

It specialises in lending various types of loans to urban customers. When the company receives a loan application, the company has to make a decision for loan approval based on the applicant's profile.

Like most other lending companies, *lending loans to ‘risky’* applicants is the largest source of financial loss *(called credit loss)*. The credit loss is the amount of money lost by the lender when the borrower refuses to pay or runs away with the money owed.

In other words, **borrowers** who **default** cause the largest amount of **loss to the lenders**. In this case, the customers labelled as *'charged-off' are the 'defaulters'*.

The core objective of the excercise is to **help the company minimise the credit loss**. There are two potential sources of **credit loss** are:
* Applicant **likely to repay the loan**, such an applicant will bring in profit to the company with interest rates.** Rejecting such applicants will result in loss of business**.
 * Applicant **not likely to repay** the loan, i.e. and will potentially default, then approving the loan may lead to a financial loss* for the company

## Objectives
The goal is to *identify these risky loan applicants*, then such loans can be reduced thereby cutting down the amount of credit loss. Identification of such applicants using EDA using the given [dataset](./data/loan.csv), is the aim of this case study.

If one is able to *identify these risky loan applicants*, then such loans can be reduced thereby cutting down the amount of credit loss. Identification of such applicants using EDA is the aim of this case study.

In other words, **the company wants to understand the driving factors (or driver variables)** behind loan default, i.e. the variables which are strong indicators of default.  The company can utilise this knowledge for its portfolio and risk assessment. 

## Dataset Analysis
The data given below contains the information about past loan applicants and whether they ‘defaulted’ or not. The aim is to identify patterns which indicate if a person is likely to default, which may be used for taking actions such as denying the loan, reducing the amount of loan, lending (to risky applicants) at a higher interest rate, etc.

* The dataset reflects loans post approval, thus does not represent any information on the rejection criteria process
  * Overall objective will be to observe key leading indicaters (driver variables) in the dataset, which contribute to defaulters 
  * Use the analysis as a the foundation of the hypothesis
* The overall loan process is represented by three steps
   * Potential borrower requests for loan amount (loan_amnt)
   * The approver approves/rejects an amount based on past history/risk (funded_amnt)
   * The final amount offered as loan by the investor (funded_amnt_inv)
 
### Leading Attribute
* Loan Status - Key Leading Attribute (loan_status). The column has three distinct values
  * Fully-Paid - The customer has successfuly paid the loan
  * Charged-Off - The customer is "Charged-Off" ir has "Defaulted"
  * Current - These customers, the loan is currently in progress and cannot contribute to conclusive evidence if the customer will default of pay in future
    *  For the given case study, "Current" status rows will be ignored

### Important Columns
The given columns are leading attributes, or **predictors**. These attributes are available at the time of the loan application and strongly helps in **prediction** of loan pass or rejection. Key attributes
* **Customer Demographics**
  * Annual Income (annual_inc) - Annual income of the customer. Generally higher the income, more chances of loan pass
  * Home Ownership (home_ownership) - Wether the customer owns a home or stays rented. Owning a home adds a collateral which increases the chances of loan pass.
  * Employment Length (emp_length) - Employment tenure of a customer (this is overall tenure). Higher the tenure, more financial stablity, thus higher chances of loan pass
  * Debt to Income (dti) - The percentage of the salary which goes towards paying loan. Lower DTI, higher the chances of a loan pass.
  * State (addr_state) - Location of the customer. Can be used to create a generic demographic analysis. There could be higher delinquency or defaulters demographicaly. 
* **Loan Attributes**
  * Loan Ammount (loan_amt) 
  * Grade (grade)
  * Term (term)
  * Loan Date (issue_date)
  * Purpose of Loan (purpose)
  * Verification Status (verification_status)
  * Interest Rate (int_rate)
  * Installment (installment)
  * Public Records (public_rec) - Derogatory Public Records. The value adds to the risk to the loan. Higher the value, lower the success rate.
  * Public Records Bankruptcy  (public_rec_bankruptcy) - Number of bankruptcy records publocally available for the customer. Higher the value, lower is the success rate.
* **Customer Behaviour**
  * These attributes are generated once the loan is approved. Since these values are not available at the time of loan approval, they cannot be used to predict the loan pass or fail outcomes


### Ignored Columns
* The following types of columns will be ignored in the analysis. This is a generic categorization of the columns which will be ignored in our approach and not the full list.
   * **Null Columns** - The columns haveing consistent null values across the rows and will be ignored
   * **Constant Columns** - The columns having same values across the rows will be ignored as they wont contribute to the analysis
   * **Redundant Columns** - The columns which are redundant example the url is one on one derivation of the loan id
   * **ID Columns** - The columns which represent some ID of the row data and does not have any corellation with leading attribute(loan_status) will be ignored eg. loan_id, member_id etc.
   * **Name and Description Columns** - For the perspective of current case study, the name or description of the company will not contribute to analysis and will be ignored. In future, NLP can be applied to description to gain intent and attributes. For this case study, it will be out of scope.
   * **Customer Behaviour Columns** - Columns which describes customer behaviour will not contribute to the analysis. The current analysis is at the time of loan application but the customer behaviour variables generate post the approval of loan applications. Thus these attributes wil not be considered towards the loan approval/rejection process.
   * Granular Data - Columns which describe next level of details which may not be required for the analysis. For example grade may be relevant for creating business outcomes and visualizations, sub grade is be very granular and will not be used in the analysis

### Ignored Rows and Columns because of missing data
*  Columns with high percentage of missing values will be dropped (60% above for this case study)
*  Columns with less percentage of missing value will be imputed
*  Rows with high percentage of missing values will be removed (60% above for this case study)


### Approach / Workflow

### Decision Matrix
* *Loan Accepted* - Three Scenarios
    * *Fully Paid* -  Applicant has fully paid the loan (the principal and the interest rate)
    * *Current* - Applicant is in the process of paying the instalments, i.e. the tenure of the loan is not yet completed. These candidates are not labelled as 'defaulted'.
    * *Charged-off* - Applicant has not paid the instalments in due time for a long period of time, i.e. he/she has *defaulted* on the loan 
* *Loan Rejected* - The company had rejected the loan (because the candidate does not meet their requirements etc.). Since the loan was rejected, there is no transactional history of those applicants with the company and so this data is not available with the company (and thus in this dataset)



## General Information
- Provide general information about your project here.
- What is the background of your project?
- What is the business probem that your project is trying to solve?
- What is the dataset that is being used?

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions
- Conclusion 1 from the analysis
- Conclusion 2 from the analysis
- Conclusion 3 from the analysis
- Conclusion 4 from the analysis

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Technologies Used
- [Python - Version 3.8](https://www.python.org/download/releases/3.0/)
- [numpy - Version 1.22.3](https://github.com/numpy)
- [pandas - Version 1.4.2](https://github.com/pandas-dev/pandas)
- [matplotlib - Version 3.5.2](https://github.com/matplotlib)
- [seaborn - Version 0.11.2](https://github.com/seaborn)
- [Jupyter Notebook - Version 6.4.5]()
- [Anaconda - Version 2.1.4]()


## Acknowledgements and References
- The project references insights and inferences from live presentation given by [Aditya Bhattacharya](https://www.linkedin.com/in/aditya-bhattacharya-b59155b6/)
- The project reference course materieals from upGrads curriculm 
- [What is Exploratory Data Analysis? by Prasad Patil](https://towardsdatascience.com/exploratory-data-analysis-8fc1cb20fd15)
- [https://stackoverflow.com/questions/56611698/pandas-how-to-read-csv-file-from-google-drive-public]

## Glossary
- EDA - Exploratory Data Analytics

## Team
* [Manoj Kumar Shukla]()
* [Siddhartha Lahiri](https://www.linkedin.com/in/lahiris/)
