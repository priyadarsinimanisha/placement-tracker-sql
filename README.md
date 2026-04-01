# 🎯 Placement Tracker System (SQL + Dashboard)

## 🚀 Overview

A **Placement Tracker System** built using SQL to manage and analyze student placement data.
This project tracks **students, companies, applications, and job offers**, and provides insights through SQL queries and a dashboard.

---

## 🧩 Features

* 📌 Track student applications to companies
* 📊 Analyze placement statistics (selection rate, highest package)
* 🧠 Identify top-performing students
* 📈 Visualize insights using Power BI dashboard

---

## 🧱 Database Schema

### 📂 Tables

* **Students** → Stores student details
* **Companies** → Stores company details
* **Applications** → Tracks job applications
* **Offers** → Stores placement offers

---

## 🔗 ER Diagram

![ER Diagram](screenshots/er-diagram.png)

---

## 📊 Dashboard Preview

![Dashboard](screenshots/dashboard.png)

---

## 🛠️ Tech Stack

* 🗄️ SQL (MySQL)
* 📊 Power BI
* 📁 GitHub for version control

---

## 🔍 Key SQL Queries

### 1. Students Placed

```sql
SELECT DISTINCT s.name
FROM Students s
JOIN Offers o ON s.student_id = o.student_id;
```

### 2. Highest Package Company

```sql
SELECT company_name, package
FROM Companies
ORDER BY package DESC
LIMIT 1;
```

### 3. Selection Rate per Company

```sql
SELECT c.company_name,
COUNT(CASE WHEN a.status = 'Selected' THEN 1 END) * 100.0 / COUNT(*) AS selection_rate
FROM Companies c
JOIN Applications a ON c.company_id = a.company_id
GROUP BY c.company_name;
```

---

## 📁 Project Structure

```
Placement-Tracker-SQL/
│
├── schema.sql
├── data.sql
├── queries.sql
├── README.md
│
├── screenshots/
│   ├── er-diagram.png
│   ├── dashboard.png
│
├── dashboard/
│   ├── placement_dashboard.pbix
```

---

## ▶️ How to Run

1. Install MySQL and open SQL editor
2. Run `schema.sql`
3. Run `data.sql`
4. Execute queries from `queries.sql`

---

## 💡 Key Concepts Used

* Joins (INNER, LEFT)
* Aggregations (SUM, COUNT, AVG)
* GROUP BY & HAVING
* Subqueries
* Data visualization

---

## 🎯 Use Case

This system helps colleges and students:

* Track placement progress
* Analyze company performance
* Monitor student success

---

## 🧠 What I Learned

* Designing relational databases
* Writing optimized SQL queries
* Building real-world analytics dashboards

---

## 📬 Contact

Feel free to connect for feedback or collaboration!

---

⭐ If you like this project, give it a **star** on GitHub!
