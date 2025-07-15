# Assignment

## Brief

Write the SQL DML statements for the following questions.

## Instructions

Paste the answer as SQL in the answer code section below each question.

### Question 1

Select the minimum and maximum price per sqm of all the flats.

```sql
SELECT min(resale_price/floor_area_sqm) as min_price_per_sqm , max(resale_price/floor_area_sqm) as max_price_per_sqm
FROM 
resale_flat_prices_2017;
```

### Question 2

Select the average price per sqm for flats in each town.

```sql
SELECT min(resale_price/floor_area_sqm) as min_price_per_sqm , max(resale_price/floor_area_sqm) as max_price_per_sqm
FROM 
resale_flat_prices_2017;
```

### Question 3

Categorize flats into price ranges and count how many flats fall into each category:

- Under $400,000: 'Budget'
- $400,000 to $700,000: 'Mid-Range'
- Above $700,000: 'Premium'
  Show the counts in descending order.

```sql
select count(flat_type) as num_of_flats, 
	CASE 
		WHEN resale_price < 400000 THEN 'Budget'
		WHEN resale_price between 400000 and 700000 THEN 'Mid-Range'
		ELSE 'Premium'
	END AS price_ranges
FROM 
resale_flat_prices_2017
group by price_ranges
order by num_of_flats desc;
```

### Question 4

Count the number of flats sold in each town during the first quarter of 2017 (January to March).

```sql
SELECT COUNT(*)as flats_sold, town
FROM 
resale_flat_prices_2017
WHERE
month between '2017-01' and '2017-03'
group by town
order by flats_sold desc;
```

## Submission

- Submit the URL of the GitHub Repository that contains your work to NTU black board.
- Should you reference the work of your classmate(s) or online resources, give them credit by adding either the name of your classmate or URL.
