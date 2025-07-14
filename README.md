
### **1. What is PostgreSQL?**

**PostgreSQL** is an **open-source, object-relational database management system (ORDBMS)** known for its stability, advanced features, and standards compliance. It supports:

* SQL & NoSQL queries
* ACID transactions
* Extensibility (custom data types, functions)
* Complex joins, indexing, concurrency control
  It’s widely used in web development, data analysis, and enterprise systems for storing and managing structured data efficiently.

---

### **2. What is the purpose of a database schema in PostgreSQL?**

In PostgreSQL, a **schema** is a **namespace** within a database that groups together related tables, views, indexes, functions, etc.
Purpose:

* Organize objects logically
* Avoid naming conflicts (e.g., two tables with the same name in different schemas)
* Manage permissions more easily
* Enable modular design (e.g., separating app, auth, and log tables)

---

### **3. Explain the Primary Key and Foreign Key concepts in PostgreSQL.**

* **Primary Key**: A column (or group of columns) that **uniquely identifies each row** in a table. It **cannot contain NULLs** and must be **unique**.

  ```sql
  ranger_id SERIAL PRIMARY KEY
  ```

* **Foreign Key**: A column that creates a **link to the primary key** in another table. It enforces **referential integrity**.

  ```sql
  ranger_id INT REFERENCES rangers(ranger_id)
  ```

---


### **4. What are the `LIMIT` and `OFFSET` clauses used for?**

* **`LIMIT`**: Restricts the number of rows returned.
* **`OFFSET`**: Skips a specific number of rows before starting to return results.

```sql
SELECT * FROM sightings ORDER BY sighting_time DESC LIMIT 5 OFFSET 10;
```

This fetches the 11th to 15th most recent sightings (for pagination).

---

### **5. How can you modify data using `UPDATE` statements?**

The `UPDATE` statement modifies existing rows in a table.

```sql
UPDATE species
SET conservation_status = 'Historic'
WHERE discovery_date < '1800-01-01';
```

It updates only rows that match the `WHERE` condition.
Be careful: Omitting `WHERE` updates **all rows**.

---



