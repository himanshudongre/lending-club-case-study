# lending-club-case-study
## Problem Statement

### Business Understanding
You work for a consumer finance company which specialises in lending various types of loans to urban customers. When the company receives a loan application,
the company has to make a decision for loan approval based on the applicant’s profile. Two types of risks are associated with the bank’s decision:

- If the applicant is likely to repay the loan, then not approving the loan results in a loss of business to the company
- If the applicant is not likely to repay the loan, i.e. he/she is likely to default, then approving the loan may lead to a financial loss for the company

The data given below contains information about past loan applicants and whether they ‘defaulted’ or not. The aim is to identify patterns which indicate if a person is likely to default,
which may be used for taking actions such as denying the loan, reducing the amount of loan, lending (to risky applicants) at a higher interest rate, etc.

In this case study, we will use EDA to understand how consumer attributes and loan attributes influence the tendency of default.

When a person applies for a loan, there are two types of decisions that could be taken by the company:

1. Loan accepted: If the company approves the loan, there are 3 possible scenarios described below:

- Fully paid: Applicant has fully paid the loan (the principal and the interest rate)

- Current: Applicant is in the process of paying the instalments, i.e. the tenure of the loan is not yet completed. These candidates are not labelled as 'defaulted'.

- Charged-off: Applicant has not paid the instalments in due time for a long period of time, i.e. he/she has defaulted on the loan 

2. Loan rejected: The company had rejected the loan (because the candidate does not meet their requirements etc.). Since the loan was rejected, there is no transactional history of those applicants with the company and so this data is not available with the company (and thus in this dataset)

### Business Objectives
This company is the largest online loan marketplace, facilitating personal loans, business loans, and financing of medical procedures. Borrowers can easily access lower interest rate loans through a fast online interface. 

Like most other lending companies, lending loans to 'risky' applicants is the largest source of financial loss (called credit loss). Credit loss is the amount of money lost by the lender when the borrower refuses to pay or runs away with the money owed. In other words, borrowers who default cause the largest amount of loss to the lenders. In this case, the customers labelled as 'charged-off' are the 'defaulters'. 

If one is able to identify these risky loan applicants, then such loans can be reduced thereby cutting down the amount of credit loss. Identification of such applicants using EDA is the aim of this case study.

In other words, the company wants to understand the driving factors (or driver variables) behind loan default, i.e. the variables which are strong indicators of default.  The company can utilise this knowledge for its portfolio and risk assessment.

### Conclusion from Analysis
Based on the above analysis below is the list of primary features which should be used to predict default for loan applications:

| Features    | Description | Effect on Default Rate    |
| :---        | :----   | :--- |
| loan_amnt   | The listed amount of the loan applied for by the borrower.       | loan amount above median leads to more default   |
| pub_rec_bankruptcies  | Number of public record bankruptcies        | if any public record bankrupcies are present then there is a strong chance of default       |
| grade  | LC assigned loan grade        | grade C and below have higher chances of defaults      |
| annual_inc  | The self-reported annual income provided by the borrower during registration.        |annual income in the lower 25% quartile have more chances of defaults      |
| loan_income_ratio  | Loan to income Ratio        | loan income ratio above 20 have high chances of default       |
| int_rate  | Interest Rate on the loan        | int rate above median have higher chances of default      |

Apart from these primary features below are few more features which have some co-relation with default:
- People taking loan for small business purpose have a high tendency of defaulting
- Applicants from certain states like WY seem to have high default rates
- Applicants with dti greater than 20 have higher chances of defaults

### Recommendations

- **Stop approving loans where loan amount to income ratio is greater than 20.**
- **Reduce number of loan approvals to small businesses in general.**
- **Reduce approvals to applicants with grade C and below for high risk states like WY and grade D and below for everyone else.**
- **Stop approving loans to applicants with existing public record bankruptcies.**
- **Start charging more interest rate to applicants with dti greater than 20.**
