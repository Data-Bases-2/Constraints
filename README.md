<p align="center">
  <img src="https://www.especial.gr/wp-content/uploads/2019/03/panepisthmio-dut-attikhs.png" alt="UNIWA" width="150"/>
</p>

<p align="center">
  <strong>UNIVERSITY OF WEST ATTICA</strong><br>
  SCHOOL OF ENGINEERING<br>
  DEPARTMENT OF COMPUTER ENGINEERING AND INFORMATICS
</p>

---

<p align="center">
  <strong>Databases II</strong>
</p>

<h1 align="center">
  Constraints
</h1>

<p align="center">
  <strong>Vasileios Evangelos Athanasiou</strong><br>
  Student ID: 19390005
</p>

<p align="center">
  <a href="https://github.com/Ath21" target="_blank">GitHub</a> ·
  <a href="https://www.linkedin.com/in/vasilis-athanasiou-7036b53a4/" target="_blank">LinkedIn</a>
</p>

<p align="center">
  Supervisor: Rania Garofalaki, Laboratory Teaching Staff<br>
</p>

<p align="center">
  <a href="https://ice.uniwa.gr/en/emd_person/zacharenia-garofalaki/" target="_blank">UNIWA Profile</a> ·
  <a href="https://www.linkedin.com/in/rania-garofalaki-4761b071/" target="_blank">LinkedIn</a>
</p>

<p align="center">
  Athens, December 2023
</p>

---

# Project Overview

The exercise demonstrates the creation, configuration, and management of a **personnel database**, including table definitions, data types, constraints, and basic data manipulation.


---

## Table of Contents


| Section | Folder / File | Description |
|------:|---------------|-------------|
| 1 | `assign/` | Laboratory / Assignment material |
| 1.1 | `assign/laboratory_2.pdf` | Laboratory instructions (English) |
| 1.2 | `assign/εργαστήριο_2.pdf` | Laboratory instructions (Greek) |
| 2 | `docs/` | Theoretical documentation |
| 2.1 | `docs/Constraints.pdf` | Constraints theory (English) |
| 2.2 | `docs/Περιορισμοί.pdf` | Constraints theory (Greek) |
| 3 | `queries/` | Visual query examples |
| 3.1 | `queries/query*.png` | Various SELECT, INSERT, UPDATE queries demonstrating constraints |
| 3.2 | `queries/query5_*.png` | Queries specific to Department, Employee, Job constraints |
| 3.3 | `queries/query6_*.png` | Queries specific to Department, Employee, Job constraints |
| 3.4 | `queries/query14_*.png` | Complex queries on Dept / Emp / Job tables |
| 3.5 | `queries/query16_*.png` | Multi-step queries / transactions |
| 3.6 | `queries/query18_*.png` | Query examples with constraint validation |
| 3.7 | `queries/query20_*.png` | Advanced constraint queries |
| 4 | `src/` | SQL scripts and related images |
| 4.1 | `src/personnel.sql` | SQL script for personnel database with constraints |
| 4.2 | `src/personnel.png` | ER diagram / model image |
| 5 | `README.md` | Repository overview and instructions |

---

## Database Structure

The database consists of three primary tables with the following initial configurations:

### Tables and Data Types

| Table | Columns | Data Type |
|-------|---------|-----------|
| DEPT  | DEPTNO, DNAME, LOC | numeric(2), varchar(24), char(23) |
| JOB   | JOBCODE, JOB_DESCR, SAL | numeric(3), varchar(24), numeric(10,2) |
| EMP   | EMPNO, NAME, JOBNO, DEPTNO, COMM | numeric(4), varchar(255), numeric(3), numeric(2), numeric(10,2) |

---

## Key Activities

The exercise covers a comprehensive set of **SQL operations**:

### Database Management
- Connecting to MySQL via CLI.
- Checking for existing databases.
- Creating the **personnel** database.

### Table Operations
- Creating tables: `DEPT`, `JOB`, `EMP`.
- Populating tables with initial sample data.

### Schema Modification
- Adding new columns (e.g., `HIREDATE`) and updating existing records.
- Modifying data types and renaming columns (e.g., `DNAME` → `DEPT_NAME`).

### Constraints
- Adding and removing **Primary Keys** and **Foreign Keys**.
- Setting **DEFAULT** values.
- Implementing **AUTO_INCREMENT** on a new `PROJECT` table.

### Audit
- Displaying the list of **limitations and constraints** applied to the database.

---

## Environment

- **Server:** MySQL Community Server 8.0.35  
- **Connection Method:** Command Line Interface (CLI) using the `root` user

---

# Installation & Setup Guide

This repository contains a **personnel database project with constraints** developed for the **Databases II** course at the **University of West Attica (UNIWA)**.  
It demonstrates **table creation, data types, constraints, data manipulation, and schema modification** for a sample personnel database.

---

## Prerequisites

Before using this project, ensure you have the following installed:

### 1. Database Management System (DBMS)
- **MySQL 8.0** (recommended)
- Compatible alternatives:
  - MariaDB
  - PostgreSQL *(minor syntax adjustments may be required)*

### 2. SQL Client / Interface
A tool to execute `.sql` scripts:
- **MySQL Workbench** (recommended)
- phpMyAdmin
- DBeaver
- Command-line MySQL client

### 3. Knowledge Requirements
- SQL basics: `CREATE DATABASE`, `CREATE TABLE`, `INSERT`, `SELECT`, `UPDATE`
- Understanding of **primary keys, foreign keys, default values, and auto-increment**
- Familiarity with table modification commands: `ALTER TABLE`

---

## Installation

### 1. Clone the Repository

Open a terminal/command prompt and run:

```bash
git clone https://github.com/Data-Bases-2/Constraints.git
```

#### Alternative (Without Git)

- Open the repository URL in your browser
- Click Code → Download ZIP
- Extract the ZIP file to a local directory

### 2. Open SQL Client
- Launch your preferred SQL client (e.g., MySQL Workbench)
- Connect to your local or remote MySQL server

### 3. Create the Database
- Execute the following SQL command if the database does not exist:
```sql
CREATE DATABASE IF NOT EXISTS personnel;
USE personnel;
```

### 4. Create Tables
Run the provided SQL script `src/personnel.sql`. This script includes:
- `DEPT` Table
- `JOB` Table
- `EMP` Table
- Column data types, primary keys, foreign keys, default values, and auto-increment where required
Example:
```sql
CREATE TABLE DEPT (
    DEPTNO NUMERIC(2) PRIMARY KEY,
    DNAME VARCHAR(24),
    LOC CHAR(23)
);

CREATE TABLE JOB (
    JOBCODE NUMERIC(3) PRIMARY KEY,
    JOB_DESCR VARCHAR(24),
    SAL NUMERIC(10,2)
);

CREATE TABLE EMP (
    EMPNO NUMERIC(4) PRIMARY KEY,
    NAME VARCHAR(255),
    JOBNO NUMERIC(3),
    DEPTNO NUMERIC(2),
    COMM NUMERIC(10,2),
    FOREIGN KEY (DEPTNO) REFERENCES DEPT(DEPTNO),
    FOREIGN KEY (JOBNO) REFERENCES JOB(JOBCODE)
);
```
> Tip: Execute the full `personnel.sql` file in one step to ensure all constraints and sample data are applied.

### 5. Insert Sample Data
Populate tables using the `INSERT INTO` statements included in the script.
Refer to `queries/` for visual examples of correct data insertion.

### 6. Verify Tables and Constraints
Check that tables exist and constraints are applied:
```sql
USE personnel;
SHOW TABLES;

SELECT * FROM DEPT;
SELECT * FROM JOB;
SELECT * FROM EMP;

-- Check constraints
SHOW CREATE TABLE EMP;
SHOW CREATE TABLE DEPT;
SHOW CREATE TABLE JOB;
```

---

## Open the Documentation
1. Navigate to the `docs/` directory
2. Open the report corresponding to your preferred language:
    - English: `Constraints.pdf`
    - Greek: `Περιορισμοί.pdf`