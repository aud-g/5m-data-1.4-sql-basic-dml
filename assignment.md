# Assignment

## Brief

Write the SQL DML statements for the following questions.

## Instructions

Paste the answer as SQL in the answer code section below each question.

### Question 1

Select the minimum and maximum price per sqm of all the flats.

```sql
select 
      MIN(resale_price / floor_area_sqm) AS min_price_per_sqm,
      MAX(resale_price / floor_area_sqm) AS max_price_per_sqm
from resale_flat_prices_2017;

```

### Question 2

Select the average price per sqm for flats in each town.

```sql
SELECT 
      town,
      ROUND(AVG(resale_price / floor_area_sqm), 2) AS avg_price_per_sqm
from resale_flat_prices_2017
GROUP BY town
ORDER BY avg_price_per_sqm DESC;

```

### Question 3

Categorize flats into price ranges and count how many flats fall into each category:

- Under $400,000: 'Budget'
- $400,000 to $700,000: 'Mid-Range'
- Above $700,000: 'Premium'
  Show the counts in descending order.

```sql
select * from resale_flat_prices_2017;
select CASE
	
   	   WHEN price < 400000 THEN 'Budget'
   	   WHEN price >= 400000 AND price <= 700000 THEN 'Mid-Range'
   	   WHEN price > 700000 THEN 'Premium'
   END AS price category
   COUNT(*) AS flat_count

   Select * from resale_flat_prices_2017
   
   FROM flat_type
GROUP BY price_category
ORDER BY flat_count DESC;
```

### Question 4

Count the number of flats sold in each town during the first quarter of 2017 (January to March).

```sql
select
   town,
   count(*) AS units_sold
FROM resale_flat_prices_2017 
WHERE month in ('2017-01', '2017-02', '2017-03')
GROUP BY town
ORDER BY town DESC;

```

## Submission

- Submit the URL of the GitHub Repository that contains your work to NTU black board.
- Should you reference the work of your classmate(s) or online resources, give them credit by adding either the name of your classmate or URL.
