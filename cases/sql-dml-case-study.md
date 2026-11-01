# Case Study: SQL Data Manipulation (DML) & Data Retrieval

**Project:** `hillel-qauto` Database (Educational Project)\
**Task:** Write SQL queries to extract specific data from the database
using `SELECT`, `JOIN`, aggregate functions, and `GROUP BY`. The goal
was to answer specific business questions and simulate real-world data
verification tasks.\
**Tools Used:** MySQL / SQL (DML) / MySQL Workbench\
**Date Completed:** 25.10.2026

------------------------------------------------------------------------

## 📝 Project Context & Overview

After creating the database schema in the previous task, the next
logical step was to practice data retrieval. This assignment focused on
writing queries to answer specific business questions, such as finding
users by name, calculating maximum expenses, and counting owners by car
brand and model. A key requirement was to use proper filtering,
aggregation, and grouping to ensure accurate results.

## 🛠 My Approach & Deliverables

I approached this by breaking down each business question into a
specific SQL query. I used `WHERE` for filtering, `JOIN` for combining
related tables, and aggregate functions (`COUNT`, `MAX`) with `GROUP BY`
for summarizing data.

### 🔄 1. End-to-End Query Flow

The assignment covered five distinct business questions, all implemented
in a single SQL script:

1.  **Search by Name:** Found users whose names contain the sequence
    `"am"`.
2.  **Max Expense:** Identified the highest expense among Audi cars.
3.  **Count Models:** Counted the number of models for Audi and BMW
    brands.
4.  **Count Owners:** Calculated the number of owners by car brand and
    model.
5.  **Users with Cars:** Retrieved names of users who have at least one
    car.

### ⚙️ 2. Technical Implementation (Key SQL Concepts)

**Filtering with LIKE**

Used the `%` wildcard to find names containing `"am"` anywhere in the
string.

``` sql
SELECT name
FROM user_profiles
WHERE name LIKE '%am%';
```

**Aggregation with MAX and JOIN**

Combined three tables (`expenses`, `cars`, `car_brands`) to filter by
brand and find the maximum expense.

``` sql
SELECT MAX(expenses.totalCost) AS max_audi_expense
FROM expenses
JOIN cars ON expenses.carId = cars.id
JOIN car_brands ON cars.carBrandId = car_brands.id
WHERE car_brands.title = 'Audi';
```

**Grouping with COUNT and GROUP BY**

Used `COUNT()` with `GROUP BY` to aggregate data per brand/model. For
counting owners, I used `COUNT(DISTINCT cars.userId)` to ensure each
owner is counted only once, even if they own multiple cars of the same
model.

``` sql
SELECT
    COUNT(car_models.id) AS count_models,
    car_brands.id AS car_id
FROM car_brands
JOIN car_models ON car_brands.id = car_models.carBrandId
WHERE car_brands.title IN ('Audi', 'BMW')
GROUP BY car_brands.id;
```

``` sql
SELECT
    car_models.title AS car_model,
    car_brands.title AS car_brand,
    COUNT(DISTINCT cars.userId) AS user_count
FROM cars
JOIN car_models ON cars.carModelId = car_models.id
JOIN car_brands ON car_models.carBrandId = car_brands.id
GROUP BY car_models.title, car_brands.title;
```

**INNER JOIN for Filtering**

Used `INNER JOIN` to return only users who have a matching record in the
`cars` table.

``` sql
SELECT DISTINCT user_profiles.name
FROM user_profiles
INNER JOIN cars ON user_profiles.userId = cars.userId;
```

### ✅ 3. Assertions & Validation

For each query, I verified the results by:

-   Checking that the output matches the expected business logic (e.g.,
    only Audi expenses were considered).
-   Ensuring no duplicate rows appeared (using `DISTINCT` where
    necessary).
-   Confirming that aggregate functions returned the correct counts and
    maximum values.

## 🐞 Examples of Implemented Queries (from Script)

**1. Search by Name (Task 1)**

-   **Query:** `SELECT name FROM user_profiles WHERE name LIKE '%am%';`
-   **Test:** Checks if the output contains names with `"am"`.

**2. Max Expense (Task 2)**

-   **Query:**
    `SELECT MAX(expenses.totalCost) AS max_audi_expense FROM expenses JOIN cars ... WHERE car_brands.title = 'Audi';`
-   **Test:** Returns a single numeric value representing the highest
    expense.

**3. Count Owners (Task 4)**

-   **Query:**
    `SELECT car_models.title AS car_model, car_brands.title AS car_brand, COUNT(DISTINCT cars.userId) AS user_count FROM cars ... GROUP BY ...;`
-   **Test:** Returns aggregated counts per model and brand.

## 📸 Proof of Work

*(Screenshots of the successfully executed SQL queries and their
results)*

**Query Results Overview:**

[SQL query results screenshot](./images/proof-sql-query-results-max-expense-total-cost.png)
[SQL query results screenshot](./images/proof-sql-query-results-name-car-etc.png)


## 💡 Conclusion

This task reinforced my understanding of SQL DML. I practiced using
`LIKE` for pattern matching, `JOIN` for combining tables, `GROUP BY` for
aggregation, and `DISTINCT` for removing duplicates. The most valuable
takeaway was learning how to translate business questions into efficient
SQL queries and validate the results for accuracy.

*(Screenshot of the completed assignment and feedback)*

[Completed assignment and feedback
screenshot](./images/proof-sql-score-dml.png)
