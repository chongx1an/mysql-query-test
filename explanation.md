# Result
In my local MySQL database with dummy data:
|   | Original query  | Enhanced query |
|---|---|---|
| Execution time  | 33.21188807s  | 0.00333309s  |
| Row examined  | 40,828,756  | 209  |
| Query cost  | 208,212,221,850.32+  | 200+  |


# Explanation
1. Use inner join instead of left join
    - Inner join is faster than left join, left join will format and return more data
    - More data will increase the cost of processing the rows


2. Create proper indexing
    - Implement index to commonly used column like name, deleted, sort_order, etc


3. Do not join too many tables
    - Joinning too much tables will increase the cost of the query
    - I use subquery and union the subqueries result to prevent join too many tables


## *Note
Not sure the original query is correct or not as it return empty result while my enhanced query will return result. However, I think they does the same things which act as a search query across multiple tables.