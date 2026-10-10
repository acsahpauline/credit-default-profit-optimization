# Credit Card Default: Profit-Optimizing Approval Policy

## Business question
A bank must decide which credit card applicants to approve and what
credit limit to offer. Approving too many risky customers creates
losses from defaults; approving too few leaves profit on the table.
This project finds the policy that maximizes expected profit.

## Data
- Source: UCI Machine Learning Repository, "Default of Credit Card
  Clients" (Yeh, I-Cheng)
- 30,000 credit card clients in Taiwan (2005), with credit limit,
  demographics, 6 months of repayment status, bills and payments,
  and whether the client defaulted the next month
- License: CC BY 4.0
- Citation: Yeh, I. C., & Lien, C. H. (2009). The comparisons of data
  mining techniques for the predictive accuracy of probability of
  default of credit card clients. Expert Systems with Applications,
  36(2), 2473-2480.

## Approach
1. Clean data with Power Query
2. Split into train (70%) and test (30%) sets
3. Build risk segments and estimate default rates (train set)
4. Validate on the test set
5. Model expected profit under stated assumptions
6. Use Excel Solver to find the optimal approval and limit policy
7. Test how the result changes under different assumptions

## Tools
Excel (Power Query, formulas, Solver, Data Tables)

## Key assumptions
[Fill in once decided: revenue per customer, loss on default, etc.]

## Data cleaning log
- Loaded 30,000 rows and 25 columns (header was in row 2 of the source file)
- Renamed PAY_0 to PAY_1 and "default payment next month" to DEFAULT
- Checks: 0 blank cells, 0 duplicate IDs (IDs 1 to 30,000, sum verified)
- EDUCATION: codes 0, 5, 6 were not in the documented categories
  ([x] rows total), grouped into 4 (others); code 4 now has 468 rows
- MARRIAGE: code 0 was undocumented ([x] rows), grouped into 3
  (others); code 3 now has 377 rows
- Negative bill amounts kept (could be credit balances)
- Final: 30,000 rows

## Results
[Fill in after analysis]

## Limitations
- Profit inputs are assumptions, not values from the data
- Data is from Taiwan, 2005, so the method transfers but the exact
  default rates may not
- Sex, marital status, and age are not used in scoring, in line with
  responsible-lending practice

## Status
In progress