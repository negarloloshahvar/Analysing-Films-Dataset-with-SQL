# Analysing-Films-Dataset-with-SQL

## Project Description
In this project we have a dataset called films, which contains data about 4968 
films including the title, release_year, country, duration, language, certification, gross, and budget.

We want to write a SQL query that returns the average budget and gross earnings for films each year after 1990 if the average budget is greater than 60 million.

## Solution
First, we select the release_year for each film in the films table, filter for records released after 1990, and group by release_year.

Then, we modify the query to include the average budget aliased as avg_budget and average gross aliased as avg_gross for the results we have so far.

After that, we modify the query once more so that only years with an average budget of greater than 60 million are included.

Finally, we order the results from the highest average gross and limit to one.

## Final SQL Query
SELECT release_year, AVG(budget) AS avg_budget, AVG(gross) AS avg_gross

FROM films

WHERE release_year > 1990

GROUP BY release_year
HAVING AVG(budget) > 60000000

ORDER BY avg_gross DESC

LIMIT 1;