subject:: [[cs]]
parents:: [[data engineering]]
source:: [[original]]
status:: active

- This page captures common query patterns that I've found useful in my experience working with data.
- A side note on CTEs
	- CTEs (common table expressions) are named subqueries that can be reused multiple times within the query. I find them way nicer to use in terms of readability of the  query than nested `SELECT`s, and they're usually worth the tradeoff in terms of query performance.
- Common Patterns
	- Finding rows with duplicate IDs
	  logseq.order-list-type:: number
		- Example use case: Running data quality checks for columns that should only have unique values.
		  logseq.order-list-type:: number
		- logseq.order-list-type:: number
		  ```sql
		  SELECT
		  	
		  ```