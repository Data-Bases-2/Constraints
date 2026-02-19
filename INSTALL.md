<p align="center">
  <img src="https://www.especial.gr/wp-content/uploads/2019/03/panepisthmio-dut-attikhs.png" alt="UNIWA" width="150"/>
</p>

<p align="center">
  <strong>UNIVERSITY OF WEST ATTICA</strong><br>
  SCHOOL OF ENGINEERING<br>
  DEPARTMENT OF COMPUTER ENGINEERING AND INFORMATICS
</p>

<p align="center">
  <a href="https://www.uniwa.gr" target="_blank">University of West Attica</a> ·
  <a href="https://ice.uniwa.gr" target="_blank">Department of Computer Engineering and Informatics</a>
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

<hr>

<p align="center">
  <strong>Supervision</strong>
</p>

<p align="center">
  Supervisor: Periklis Andritsos, Associate Professor
</p>
<p align="center">
  <a href="https://ice.uniwa.gr/en/emd_person/periklis-andritsos/" target="_blank">UNIWA Profile</a> ·
  <a href="https://www.linkedin.com/in/periklisandritsos/" target="_blank">LinkedIn</a>
</p>

<p align="center">
  Co-supervisor: Rania Garofalaki, Laboratory Teaching Staff<br>
</p>

<p align="center">
  <a href="https://ice.uniwa.gr/en/emd_person/zacharenia-garofalaki/" target="_blank">UNIWA Profile</a> ·
  <a href="https://www.linkedin.com/in/rania-garofalaki-4761b071/" target="_blank">LinkedIn</a>
</p>

</hr>

---

<p align="center">
  Athens, December 2023
</p>

---

<p align="center">
  <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRPpVviZDCutOfiXZhHFqb0EIk94aiNKA-psg&s" width="250"/>
</p>

---

# INSTALL

## Constraints

This repository contains a **personnel database project with constraints** developed for the **Databases II** course at the **University of West Attica (UNIWA)**.  
It demonstrates **table creation, data types, constraints, data manipulation, and schema modification** for a sample personnel database.

---

## 1. Prerequisites

Before using this project, ensure you have the following installed:

### 1.1 Database Management System (DBMS)

- **MySQL 8.0** (recommended)
- Compatible alternatives:
  - MariaDB
  - PostgreSQL _(minor syntax adjustments may be required)_

### 1.2 SQL Client / Interface

A tool to execute `.sql` scripts:

- **MySQL Workbench** (recommended)
- phpMyAdmin
- DBeaver
- Command-line MySQL client

### 1.3 Knowledge Requirements

- SQL basics: `CREATE DATABASE`, `CREATE TABLE`, `INSERT`, `SELECT`, `UPDATE`
- Understanding of **primary keys, foreign keys, default values, and auto-increment**
- Familiarity with table modification commands: `ALTER TABLE`

---

## 2. Installation

### 2.1 Clone the Repository

Open a terminal/command prompt and run:

```bash
git clone https://github.com/Data-Bases-2/Constraints.git
```

### 2.2 Alternative (Without Git)

- Open the repository URL in your browser
- Click Code → Download ZIP
- Extract the ZIP file to a local directory

### 2.3 Open SQL Client

- Launch your preferred SQL client (e.g., MySQL Workbench)
- Connect to your local or remote MySQL server

### 2.4 Create the Database

- Execute the following SQL command if the database does not exist:

```sql
CREATE DATABASE IF NOT EXISTS personnel;
USE personnel;
```

### 2.5 Create Tables

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

### 2.6 Insert Sample Data

Populate tables using the `INSERT INTO` statements included in the script.
Refer to `queries/` for visual examples of correct data insertion.

### 2.7 Verify Tables and Constraints

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

## 3. Open the Documentation

1. Navigate to the `docs/` directory
2. Open the report corresponding to your preferred language:
   - English: `Constraints.pdf`
   - Greek: `Περιορισμοί.pdf`
