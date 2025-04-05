# Aggregation using Window Functions

📚 **Author**: Ibrahim Ambale | ExploreAI Academy  
⚠️ **Note**: This notebook will **not** run on Google Colab because it requires a connection to a **local MySQL database** (`united_nations`). Please run it on the same machine where **MySQL Workbench** and the **united_nations** database are installed.

---

## 📌 Learning Objectives

- Understand the concept of **window functions** in SQL.
- Use **window functions** for **data aggregation**.
- Learn how to **partition** data using SQL.
- Solve **complex problems** using window functions.

---

## 🗂 Overview

In this notebook, we explore how to use **window functions** in SQL to perform calculations across rows that are related to the current row. Unlike regular aggregate functions, window functions do **not collapse rows**—they allow you to retain row-level data while still applying calculations.

We’ll be working with the `Access_to_Basic_Services` table from the `united_nations` database, which includes:

- Country information  
- GDP figures  
- Access to basic services  
- Subregional classifications  

---

## 🧪 Exercise Highlight

The exercise includes:

✅ Calculating **land cover as a percentage per subregion** for the year 2020  
✅ Using `PARTITION BY` and `OVER()` clauses  
✅ Exploring `ROW_NUMBER()`, `RANK()`, and `DENSE_RANK()`  
✅ Comparing results with regular aggregation for deeper insight  

---

## 🛠 Prerequisites

- MySQL installed and running locally  
- MySQL Workbench setup with `united_nations` database  
- Python libraries:
  - `mysql.connector` or `pymysql`
  - `pandas`
  - `sqlalchemy` (optional)

---

## 🔗 Sample Query Using Window Function

```sql
SELECT 
    Country, 
    Subregion,
    Land_Cover,
    SUM(Land_Cover) OVER (PARTITION BY Subregion) AS Subregion_Total
FROM Access_to_Basic_Services
WHERE Year = 2020;
```

🧠 Final Thoughts
Window functions are incredibly useful for analytical queries and solving problems that go beyond simple aggregation. This notebook helps you get hands-on with them in a structured, practical way.

Happy querying! 🚀
