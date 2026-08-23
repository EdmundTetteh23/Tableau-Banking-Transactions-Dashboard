# Banking Transactions and Customer Analytics
A multi-view Tableau business intelligence project evaluating customer demographics, account portfolio distribution, loan performance, transaction and card transaction velocity, and customer support efficiency across SBI branch operations to streamline branch performance and enhance service delivery.

## Table of Contents
- [Overview](#overview)
- [Project Brief and Problem Statement](#Project-Brief-and-Problem-Statement)
- [Data Pipeline and Architecture](#Data-Pipeline-and-Architecture)
- [Data Model and Relationships](#Data-Model-and-Relationships)
- [Tableau Calculations and Business Logic](#Tableau-Calculations-and-Business-Logic)
- [Dashboards and Visualizations](#Dashboards-and-Visualizations)
- [Key Business Insights](#Key-Business-Insights)
- [Strategic Recommendations](#Strategic-Recommendations)
- [Tech Stack](#Tech-Stack)


## Overview
State Bank of India required a unified operational analytics workspace to connect fragmented transactional databases across branches, card processing units, loan origination desks, and customer support centers. This project structures core banking data into a relational Tableau model, delivering an executive analytics suite that enables the bank's leadership to isolate operational bottlenecks, track fraud patterns, evaluate credit portfolio risk, and monitor customer service resolution performance in real time.

## Project Brief and Problem Statement
### Project Brief
SBI required a unified operational intelligence platform to consolidate fragmented data across physical branches, card processing units, credit desks, and support centers. This project delivers an interactive 5-sheet Tableau workbook that connects core banking entities into a relational model, equipping branch managers and executive leadership with real-time visibility into customer demographics, account activation health, loan portfolio risk, card fraud velocity, and customer service resolution cycles.

### Project Objectives
- Customer Demographic Profiling: Evaluate customer wealth distribution, creditworthiness, and branch usage patterns across occupations, income brackets, and age cohorts.
- Account Portfolio & Footprint Optimization: Monitor account activation status, account types, and regional branch density across states and cities to identify growth opportunities and reduce account dormancy.
- Credit Portfolio Risk Analysis: Track loan origination trends, repayment metrics, default rates, and interest earnings across diverse loan categories to safeguard credit quality.
- Card Velocity & Fraud Monitoring: Analyze card transaction volumes, merchant spending patterns, and monthly fraud occurrences across card tiers (Debit, Classic, Gold, Platinum).
- Support Service Efficiency: Measure support ticket resolution times, escalation rates, and customer satisfaction scores across issue types to optimize service workflows.

## Data Pipeline and Architecture
[Raw Operational Dataset] ➔ [Data Standardization & Relational Modeling] ➔ [Calculated Fields & Dynamic Parameters] ➔ [Tableau Dashboard]

## Data Model and Relationships
The data architecture utilizes a multi-fact relational model built inside Tableau’s logical layer, connecting customer records with operational financial activities:
<img width="1097" height="504" alt="Tableau DM" src="https://github.com/user-attachments/assets/0fe7b688-4757-4f44-a115-882847d598ca" />


- dim_customers: Central customer hub capturing personal attributes (customer_id, name, email, phone, gender, date_of_birth, occupation, annual_income, credit_score, city, state, join_date).

- fact_accounts: Operational account directory (account_id, customer_id, branch_id, account_type, balance, open_date, status).

- dim_account_id: Intermediary bridge table linking bank accounts data to operational core transactions.

- fact_transactions: General account transaction log (transaction_id, account_id, txn_date, txn_type, amount, channel, merchant_category).

- dim_cards: Card metadata lookup (card_id, customer_id, account_id, card_type, credit_limit, issue_date, expiry_date, status).

- fact_card_transactions: Card payment log capturing transaction details (card_txn_id, card_id, amount, txn_date, merchant_category, is_fraud).

- fact_loans: Loan account records (loan_id, customer_id, branch_id, loan_type, loan_amount, interest_rate, term_months, start_date, status).

- dim_loan_id: Intermediary bridge table connecting main loans to granular repayment schedules.

- fact_loan_payments: Amortization tracking table for loan payments (payment_id, loan_id, payment_date, amount_paid, principal_component, interest_component, late_payment_flag).

- fact_support_tickets: Customer service activity log (ticket_id, customer_id, date_opened, date_resolved, issue_type, status, satisfaction_score, Resolution Time Day).

- dim_branches: Branch lookup (branch_id, branch_name, city, state, ifsc_code, opened_date).

- dim_employees: Branch staffing directory (employee_id, branch_id, name, role, salary, hire_date).

## Dashboards and Visualizations
- Dashboard 1 — Customer Demographics Analysis: Executive overview displaying core customer metrics (60.0K Total Customers, 22.0K Customers with Loans, ₹1.8M Avg Income, 600 Avg Credit Score, 49 Avg Age), state map distributions, gender split (52% Male, 46% Female, 2% Other), age bracket breakdowns, occupation density, and branch customer counts.

- Dashboard 2 — Account Analysis: Portfolio management view tracking account volume (95.0K Total Accounts, 80.7K Active Accounts across 12 States, 15 Cities, and 93 Branches), account type distributions (Savings, Current, Salary, Fixed Deposit, NRI), account status breakdowns (85% Active, 10% Dormant, 5% Closed), regional state/city maps, and branch-level filters.

- Dashboard 3 — Transaction Analysis: Core banking transactional view monitoring general account throughput, transaction channel preferences (Mobile Banking, Internet Banking, ATM, Branch, UPI), transaction type splits (Credit vs. Debit), high-volume transaction categories, and monthly flow trends across regional branch networks.

- Dashboard 4 — Card Transaction Analysis: Payment processing view equipped with an Amount / Transactions dynamic parameter toggle, displaying card metrics (65.0K Cards, 57.2K Active Cards, 1.05M Card Txns, ₹1.9B Txn Amount, 5.2K Fraud Txns), monthly transaction trends, card tier volume (Debit, Classic, Gold, Platinum), top merchant spending categories, monthly fraud volume trends, and merchant fraud distributions.

Dashboard 5 — Loan Analysis: Credit portfolio workspace featuring an Amount / Loans metric switcher and Principal / Interest view controls, tracking total loan volume (₹9.2B Total Amount, 22.0K Loans, ₹6.2B Paid, ₹5.1B Principal Paid, ₹1.1B Interest Paid), monthly issuance trends, loan status distributions (65% Active, 25% Closed, 7% Defaulted, 3% Written Off), product distributions (Home, Personal, Business, Gold, Auto, Education), average interest rates (~11.4% - 11.6%), and term lengths (~92 - 97 months).

Dashboard 6 — Customer Support Analysis: Operational service view tracking ticket throughput (25.0K Total Tickets, 20.1K Resolved, 3.0K Open, 9 Days Avg Resolution Time, 3 Avg CSAT), ticket trend lines, status mix (80% Resolved, 12% Open, 8% Escalated), volume by issue type (Card Blocked, Fraud Report, Net Banking, Cheque Bounce, Loan Query), resolution cycle times, and customer satisfaction scores by issue type.

## Key Business Insights

## Strategic Recommendations

## Tech Stack
