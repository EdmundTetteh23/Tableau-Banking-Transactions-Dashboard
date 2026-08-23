# Banking Transactions and Customer Analytics
A multi-view Tableau business intelligence project evaluating customer demographics, account portfolio distribution, loan performance, card transaction velocity, and customer support efficiency across SBI branch operations to streamline branch performance and enhance service delivery.

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
State Bank of India required a unified operational analytics workspace to connect fragmented transactional databases across physical branches, card processing units, loan origination desks, and customer support centers. This project structures core banking data into a relational Tableau model, delivering an executive analytics suite that enables branch managers and bank leadership to isolate operational bottlenecks, track fraud patterns, evaluate credit portfolio risk, and monitor customer service resolution performance in real time.

## Project Brief and Problem Statement
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

## Key Business Insights

## Strategic Recommendations

## Tech Stack
