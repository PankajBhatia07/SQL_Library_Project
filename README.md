# 📚 Library Management System (SQL Project)

## 📌 Project Overview

This project focuses on designing and analyzing a Library Management System using SQL (MySQL).

It includes multiple tables such as branches, employees, books, members, issued status, and return status to manage library operations efficiently.

The goal of this project is to manage library data, maintain relationships between tables, and perform data analysis using SQL queries to generate meaningful insights.

---

## 🛠️ Tools & Technologies

* SQL (MySQL)
* MySQL Workbench
* Database Design
* Data Analysis

---

## 🗂️ Database Structure

### 1. Branch Table

* Stores library branch details such as branch ID, manager ID, address, and contact number.

### 2. Employees Table

* Stores employee information including employee name, position, salary, and branch ID.

### 3. Books Table

* Stores book details such as ISBN, title, category, rental price, status, author, and publisher.

### 4. Members Table

* Stores library member information including member ID, name, address, and registration date.

### 5. Issued Status Table

* Stores information about books issued to members, including issue ID, member ID, book name, issue date, ISBN, and employee ID.

### 6. Return Status Table

* Stores information about returned books including return ID, issue ID, return date, and book ISBN.

---

## 🔗 Entity Relationship

* Branches are connected with employees through `branch_id`.
* Members are connected with issued books through `member_id`.
* Books are connected with issued records through `ISBN`.
* Employees are connected with issued records through `emp_id`.
* Issued records are connected with return records through `issued_id`.

### Main Flow

Branch → Employees → Issued Books → Return Status

Members → Issued Books

Books → Issued Books

---

## 🔑 Database Constraints

The project uses:

* Primary Keys to uniquely identify records.
* Foreign Keys to establish relationships between tables.
* Referential integrity to ensure related records exist.

### Foreign Key Relationships

* `issued_member_id` → `members.member_id`
* `issued_book_isbn` → `books.isbn`
* `issued_emp_id` → `employees.emp_id`
* `employees.branch_id` → `branch.branch_id`
* `return_status.issued_id` → `issued_status.issued_id`

---

## 📊 Key SQL Queries

### ✔ Basic Queries

* Count total records in each table.
* Retrieve all books, members, employees, and issued records.
* Insert new books, issued records, and return records.
* Update an existing member's address.
* Delete a specific issued-book record.

### ✔ Data Validation Queries

* Find issued records whose ISBN does not exist in the books table.
* Validate relationships between issued books and books.
* Identify records that can cause Foreign Key constraint errors.

### ✔ Intermediate Queries

* Retrieve books issued by a specific employee.
* Find books belonging to a specific category.
* Find members registered within the last 180 days.
* Calculate rental income by book category.
* Find books that have not yet been returned.

### ✔ Advanced Queries

* Use `GROUP BY` and `HAVING` to analyze multiple issued records.
* Use `JOIN` to combine books and issued-status data.
* Use `LEFT JOIN` to identify books that have not been returned.
* Use CTAS to create summary tables.
* Use Self Join to display employees with their branch manager.

---

## 🧮 Important SQL Functions & Concepts

### `COUNT()`

Used to count the number of records.

### `SUM()`

Used to calculate total rental income.

### `GROUP BY`

Used to group records based on a column.

### `HAVING`

Used to filter grouped results.

### `JOIN`

Used to combine related records from multiple tables.

### `LEFT JOIN`

Used to keep all records from the left table and find unmatched records.

### `IS NULL`

Used to identify records where matching data does not exist.

### `CTAS`

Create Table As Select is used to create a new table from the result of a query.

### `CURRENT_DATE`

Used to get the current date.

### `INTERVAL`

Used for date-based calculations such as finding members registered in the last 180 days.

---

## 📈 Key Analysis & Findings

* Identified issued records with missing or unmatched ISBNs.
* Analyzed books issued by specific employees.
* Identified books belonging to specific categories.
* Calculated rental income by category.
* Identified members registered within the last 180 days.
* Analyzed employee and branch-manager relationships.
* Created a summary table showing the number of times each book was issued.
* Identified books that have been issued but not yet returned.
* Created a separate table for books with rental prices above 7.00.

---

## 📝 Project Tasks

### Task 1 — Create a New Book Record

Added a new book:

* ISBN: `978-1-60129-456-2`
* Title: `To Kill a Mockingbird`
* Category: `Classic`
* Rental Price: `6.00`
* Author: `Harper Lee`

### Task 2 — Update Member Address

Updated the address of member `C102`.

### Task 3 — Delete Issued Record

Deleted the issued record with:

`issued_id = IS121`

### Task 4 — Books Issued by Employee

Retrieved all books issued by employee:

`E101`

### Task 5 — Multiple Issued Records

Used `GROUP BY`, `COUNT()`, and `HAVING` to identify employees with more than one issued record.

### Task 6 — Book Issue Summary

Created `book_issued_cnt` using CTAS to calculate how many times each book was issued.

### Task 7 — Books by Category

Retrieved books belonging to the `Classic` category.

### Task 8 — Rental Income Analysis

Calculated total rental income and issue count by category.

### Task 9 — Recent Members

Retrieved members who registered within the last 180 days.

### Task 10 — Employee & Manager Analysis

Retrieved employee information along with branch and branch-manager details using JOINs and a Self Join.

### Task 11 — Expensive Books

Created `expensive_books` containing books with rental prices greater than `7.00`.

### Task 12 — Books Not Yet Returned

Used `LEFT JOIN` and `IS NULL` to identify books that were issued but have not yet been returned.

---

## 📂 Project Structure

```text
Library-Management-System/
│
├── ERR-Diagram
├── Library_Project.sql
├── README.md
├── DATA
    └── books.csv
    └── employees.csv
    └── issued_status.csv
    └── members.csv
    └── return_status.csv

```
---

## 🚀 How to Run
1. Open MySQL or MySQL Workbench.
2. Create and select the Library_Project database.
3. Create the required tables.
4. Insert the library data.
5. Create the required Primary Key and Foreign Key relationships.
6. Run the analysis queries to generate results.
---

## 💡 Future Improvements
- Add a separate table for book reservations.
- Add a fine/penalty system for late returns.
- Create a dashboard using Power BI.
- Add monthly and yearly library performance analysis.
- Analyze most frequently issued books.
- Add member-wise borrowing analysis.
---

## 👨‍💻 Author
Pankaj Bhatia

## ⭐ If you like this project

Give it a ⭐ on GitHub!
