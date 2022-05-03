# Lending Club Case Study

## Table of Contents
* [Problem Statement](#problem-statement)
* [Objectives](#objectives)
* [Data Set](#dat-aset)
* [General Info](#general-information)
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

## Data Set
The data given below contains the information about past loan applicants and whether they ‘defaulted’ or not. The aim is to identify patterns which indicate if a person is likely to default, which may be used for taking actions such as denying the loan, reducing the amount of loan, lending (to risky applicants) at a higher interest rate, etc.

* The dataset reflects loans post approval, thus does not represent any information on the rejection criteria process
* Overall objective will be to observe key leading indicaters (driver variables) in the dataset, which contribute to defaulters 
* Use the analysis as a the foundation of the hypothesis
* The overall loan process is represented by three steps
   * Potential borrower requests for loan amount (loan_amnt)
   * The approver approves/rejects an amount based on past history/risk (funded_amnt)
   * The final amount offered as loan by the investor (funded_amnt_inv )

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


## Acknowledgements
- The project references insights and inferences from live presentation given by [Aditya Bhattacharya](https://www.linkedin.com/in/aditya-bhattacharya-b59155b6/)
- The project reference course materieals from upGrads curriculm 

## Glossary
- EDA - Exploratory Data Analytics

## Team
* [Manoj Kumar Shukla]()
* [Siddhartha Lahiri](https://www.linkedin.com/in/lahiris/)
