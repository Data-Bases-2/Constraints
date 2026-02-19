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

# README

## Constraints

The exercise demonstrates the creation, configuration, and management of a **personnel database**, including table definitions, data types, constraints, and basic data manipulation.

---

## Table of Contents

| Section | Folder / File             | Description                                                      |
| ------: | ------------------------- | ---------------------------------------------------------------- |
|       1 | `assign/`                 | Laboratory / Assignment material                                 |
|     1.1 | `assign/laboratory_2.pdf` | Laboratory instructions (English)                                |
|     1.2 | `assign/εργαστήριο_2.pdf` | Laboratory instructions (Greek)                                  |
|       2 | `docs/`                   | Theoretical documentation                                        |
|     2.1 | `docs/Constraints.pdf`    | Constraints theory (English)                                     |
|     2.2 | `docs/Περιορισμοί.pdf`    | Constraints theory (Greek)                                       |
|       3 | `queries/`                | Visual query examples                                            |
|     3.1 | `queries/query*.png`      | Various SELECT, INSERT, UPDATE queries demonstrating constraints |
|     3.2 | `queries/query5_*.png`    | Queries specific to Department, Employee, Job constraints        |
|     3.3 | `queries/query6_*.png`    | Queries specific to Department, Employee, Job constraints        |
|     3.4 | `queries/query14_*.png`   | Complex queries on Dept / Emp / Job tables                       |
|     3.5 | `queries/query16_*.png`   | Multi-step queries / transactions                                |
|     3.6 | `queries/query18_*.png`   | Query examples with constraint validation                        |
|     3.7 | `queries/query20_*.png`   | Advanced constraint queries                                      |
|       4 | `src/`                    | SQL scripts and related images                                   |
|     4.1 | `src/personnel.sql`       | SQL script for personnel database with constraints               |
|     4.2 | `src/personnel.png`       | ER diagram / model image                                         |
|       5 | `README.md`               | Project documentation                                            |
|       6 | `INSTALL.md`              | Usage instructions                                               |

---

## 1. Database Structure

The database consists of three primary tables with the following initial configurations:

### 1.1 Tables and Data Types

| Table | Columns                          | Data Type                                                       |
| ----- | -------------------------------- | --------------------------------------------------------------- |
| DEPT  | DEPTNO, DNAME, LOC               | numeric(2), varchar(24), char(23)                               |
| JOB   | JOBCODE, JOB_DESCR, SAL          | numeric(3), varchar(24), numeric(10,2)                          |
| EMP   | EMPNO, NAME, JOBNO, DEPTNO, COMM | numeric(4), varchar(255), numeric(3), numeric(2), numeric(10,2) |

---

## 2. Key Activities

The exercise covers a comprehensive set of **SQL operations**:

### 2.1 Database Management

- Connecting to MySQL via CLI.
- Checking for existing databases.
- Creating the **personnel** database.

### 2.2 Table Operations

- Creating tables: `DEPT`, `JOB`, `EMP`.
- Populating tables with initial sample data.

### 2.3 Schema Modification

- Adding new columns (e.g., `HIREDATE`) and updating existing records.
- Modifying data types and renaming columns (e.g., `DNAME` → `DEPT_NAME`).

### 2.4 Constraints

- Adding and removing **Primary Keys** and **Foreign Keys**.
- Setting **DEFAULT** values.
- Implementing **AUTO_INCREMENT** on a new `PROJECT` table.

### 2.5 Audit

- Displaying the list of **limitations and constraints** applied to the database.

---

## 3. Environment

- **Server:** MySQL Community Server 8.0.35
- **Connection Method:** Command Line Interface (CLI) using the `root` user
