# Problem-Set-3-Econ_3916_PS3.ipynb
# ECON 3916 – Problem Set 3: The Number Nobody Can Reproduce

## Project Overview
This project investigates why two SQL queries using the same database produce different average revenue figures. It explores common problems in data analysis, including SQL join errors, missing values, and misleading conclusions about cause and effect.

The project also uses AI to develop a SQL query reviewer that identifies potential issues before results are presented.

## Tools Used
- Python and Google Colab
- DuckDB for SQL queries
- Pandas for data analysis
- AI assistance for Phase 4

## Project Findings

**Phase 1: SQL Joins and Fan-Out**

The average revenue per West-region customer was $814.43 when calculated correctly, compared with $1,250.67 after joining the customers and orders tables. The difference occurred because customers with more orders appeared multiple times in the joined data, giving them greater weight in the average.

**Phase 2: Missing Data**

Approximately 15% of customer region values were set to NULL. A standard SQL filter unintentionally excluded 439 customers with unknown regions. The project also used a window function to calculate regional average revenue without changing the number of rows.

**Phase 3: Causal Analysis**

The project simulated an account-management programme with a true revenue effect of $50. The initial comparison estimated an effect of $363.30, but controlling for existing account size reduced the estimate to $48.30. Adding support tickets as another control made the estimate less accurate, reducing it to $10.30.

**Phase 4: AI Query Reviewer**

AI was used to help create a Python function called `review_query()` that checks SQL queries for potential problems, including joins that duplicate rows, filters that exclude missing values, and averages calculated from duplicated records. The function was evaluated against queries from the earlier phases, with its successes and limitations documented.

## Conclusion

This project demonstrates why analysts should verify SQL joins, account for missing data, and consider other explanations before claiming that a programme caused higher revenue. These checks help ensure that business decisions are based on accurate and reliable information.

## Project File
`Econ_3916_PS3.ipynb` — Google Colab notebook containing the SQL queries, Python code, results, explanations, and AI transcript.
