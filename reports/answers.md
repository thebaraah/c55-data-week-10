# Business Question Answers

Queries run against `dev_baraah.fct_daily_borough_stats`.

## Q1: Highest total `total_fare` across the whole loaded dataset

**SQL:**

```sql
-- TODO: query fct_daily_borough_stats grouped by pickup_borough, sum total_fare, order DESC
```
SELECT
    pickup_borough,
    SUM(total_fare) AS total_revenue
FROM dev_baraah.fct_daily_borough_stats
GROUP BY pickup_borough
ORDER BY total_revenue DESC
LIMIT 1;
**Result:** TODO

**Interpretation:** The borough with the highest total fare revenue across the loaded dataset was

---

## Q2: Day with the highest overall `trip_count`

**SQL:**

```sql
-- TODO: query fct_daily_borough_stats grouped by pickup_date, sum trip_count, order DESC LIMIT 1
```
SELECT
    pickup_date,
    SUM(trip_count) AS total_trips
FROM dev_baraah.fct_daily_borough_stats
GROUP BY pickup_date
ORDER BY total_trips DESC
LIMIT 1;
**Result:** TODO

**Interpretation:** The busiest day in the dataset was

---

## Q3: Highest `avg_tip_pct` for any (borough, day) combination

**SQL:**

```sql
-- TODO: query fct_daily_borough_stats order by avg_tip_pct DESC LIMIT 5
```
SELECT
    pickup_borough,
    pickup_date,
    avg_tip_pct
FROM dev_baraah.fct_daily_borough_stats
ORDER BY avg_tip_pct DESC
LIMIT 5;

**Result:** TODO

**Interpretation:** The highest average tip percentage occurred in

---

## Q4: Median daily `trip_count` for Manhattan vs Brooklyn

**SQL:**

```sql
-- TODO: use percentile_cont(0.5) WITHIN GROUP (ORDER BY trip_count) filtered by borough
```
SELECT
    pickup_borough,
    percentile_cont(0.5) WITHIN GROUP (ORDER BY trip_count) AS median_trip_count
FROM dev_baraah.fct_daily_borough_stats
WHERE pickup_borough IN ('Manhattan', 'Brooklyn')
GROUP BY pickup_borough;

**Result:** TODO

**Interpretation:** TODO (one sentence on the ratio)
