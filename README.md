# Bank_loan

## PROBLEM STATEMENT

"To effectively monitor and evaluate our bank's lending activities and performance, we require a comprehensive Bank Loan Report. This report aims to offer insights into crucial loan-related metrics and their trends over time, enabling data-driven decision-making, portfolio health tracking, and informed lending strategies.

### Key Performance Indicators (KPIs) Requirements:

- Total Loan Applications: We need to calculate the total number of loan applications received within a specified period, while also monitoring Month-to-Date (MTD) Loan Applications and tracking Month-over-Month (MoM) changes.
- Total Funded Amount: Understanding the total amount of funds disbursed as loans is crucial. Additionally, we aim to monitor MTD Total Funded Amount and analyze Month-over-Month (MoM) changes.
- Total Amount Received: Tracking the total amount received from borrowers is essential for assessing cash flow and loan repayment. We should analyze Month-to-Date (MTD) Total Amount Received and observe Month-over-Month (MoM) changes.
- Average Interest Rate: Calculating the average interest rate across all loans, MTD, and monitoring Month-over-Month (MoM) variations will provide insights into the overall cost of our lending portfolio.
- Average Debt-to-Income Ratio (DTI): Evaluating the average DTI for our borrowers helps gauge their financial health. We need to compute the average DTI for all loans, MTD, and track Month-over-Month (MoM) fluctuations.

"To effectively evaluate the performance of our lending activities and assess the quality of our loan portfolio, we require a comprehensive report that distinguishes between 'Good Loans' and 'Bad Loans' based on specific loan status criteria.

### Good Loan KPIs:

- Good Loan Application Percentage: Calculate the percentage of loan applications classified as 'Good Loans,' which include loans with a loan status of 'Fully Paid' and 'Current.'
- Good Loan Applications: Identify the total number of loan applications falling under the 'Good Loan' category, consisting of loans with a loan status of 'Fully Paid' and 'Current.'
- Good Loan Funded Amount: Determine the total amount of funds disbursed as 'Good Loans,' including the principal amounts of loans with a loan status of 'Fully Paid' and 'Current.'
- Good Loan Total Received Amount: Track the total amount received from borrowers for 'Good Loans,' encompassing all payments made on loans with a loan status of 'Fully Paid' and 'Current.'

### Bad Loan KPIs:

- Bad Loan Application Percentage: Calculate the percentage of loan applications categorized as 'Bad Loans,' specifically including loans with a loan status of 'Charged Off.'
- Bad Loan Applications: Identify the total number of loan applications categorized as 'Bad Loans,' comprising loans with a loan status of 'Charged Off.'
- Bad Loan Funded Amount: Determine the total amount of funds disbursed as 'Bad Loans,' comprising the principal amounts of loans with a loan status of 'Charged Off.'
- Bad Loan Total Received Amount: Track the total amount received from borrowers for 'Bad Loans,' including all payments made on loans with a loan status of 'Charged Off.'"

To gain a comprehensive overview of our lending operations and monitor loan performance, we aim to create a grid view report categorized by 'Loan Status.' This report will serve as a valuable tool for analyzing and understanding key indicators associated with different loan statuses. By providing insights into metrics such as 'Total Loan Applications,' 'Total Funded Amount,' 'Total Amount Received,' 'Month-to-Date (MTD) Funded Amount,' 'MTD Amount Received,' 'Average Interest Rate,' and 'Average Debt-to-Income Ratio (DTI),' this grid view will empower us to make data-driven decisions and assess the health of our loan portfolio.


## Tools used 
- Excel: For Data cleaning (Bank _loan.csv)
- Ms SQL: For Data Analysis
- Tableau :- For Data Visualization
  link for for Tableau: - https://public.tableau.com/shared/9JPJD8W4P?:display_count=n&:origin=viz_share_link

## Data Analysis 

Good Loan Total Received Amount: 
```sql
SELECT SUM(total_payment) AS Good_Loan_amount_received FROM bank_loan
WHERE loan_status = 'Fully Paid' OR loan_status = 'Current'
```
LOAN STATUS
```sql	
SELECT loan_status, COUNT(id)LoanCount, SUM(total_payment)Total_Amount_Received, 
	SUM(loan_amount)Total_Funded_Amount, AVG( int_rate * 100)Interest_Rate,
 AVG(dti * 100) DTI
    FROM bank_loan
    GROUP BY loan_status
```
All the queries is available in "bank_loan_query.docs" file 

Thank you 

