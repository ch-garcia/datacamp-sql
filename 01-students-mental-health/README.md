# Analyzing Student's Mental Health  

## Contents

- `students.csv` - The dataset used for this analysis.

- `notebook.ipynb` - My completed notebook from DataCamp.

## Project Instructions

Explore and analyze the `students` data to see how the length of stay (`stay`) impacts the average mental health diagnostic scores of the **international** students present in the study.

- Return a table with **nine** rows and **five** columns.

- The five columns should be aliased as: `stay`, `count_int`, `average_phq`, `average_scs`, and `average_as`, **in that order**.

- The average columns should contain the average of the `todep` (PHQ-9 test), `tosc` (SCS test), and `toas` (ASISS test) columns for each length of stay, **rounded to two decimal places**.

- The `count_int` column should be the number of international students for each length of stay.

- Sort the results by the length of stay in **descending order**.

**Note**: Creating new cells in the workbook will rename the DataFrame. Make sure that your final solution uses the name `df`.

## Code Snippet

```sql
-- Start coding here...
SELECT
	stay,
	COUNT(inter_dom) AS count_int,
	ROUND(AVG(todep), 2) AS average_phq,
	ROUND(AVG(tosc), 2) AS average_scs,
	ROUND(AVG(toas), 2) AS average_as
FROM students
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC;
```
