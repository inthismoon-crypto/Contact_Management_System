Contact Management System (DBMS Lab Project)

A single-page Contact Management System built for the Database Management System (DBMS) Lab course. It runs a real in-browser SQLite engine via SQL.js (WebAssembly) to execute live SQL queries (CREATE, INSERT, SELECT, UPDATE, DELETE, WHERE, INNER JOIN, and aggregate functions) without requiring external server setup.

Live Demo

Once you enable GitHub Pages, paste your live site link here:

https://<your-username>.github.io/<your-repository-name>/

Features

Single-Page CRUD Operations: Add, view, search, filter, update, and delete contacts seamlessly on one page.

Relational Database Schema: Uses two normalized SQL tables linked by a Foreign Key (contacts.group_id $\rightarrow$ contact_groups.group_id).

Live SQL Execution Log: Displays every SQL statement executed in real time at the bottom of the interface.

SQL Aggregate Summaries: Dynamically calculates COUNT(*), SUM(is_favorite), AVG(priority_score), and MAX(priority_score).

One-Click .SQL Export: Export the full schema and current records as contact_management_system.sql for lab submission.

Persistent Storage: Automatically saves database changes in browser localStorage, with a one-click reset to restore the 12 initial sample records.

Database Schema

1. contact_groups (Parent Table)

Column

Data Type

Constraint

Description

group_id

VARCHAR(10)

PRIMARY KEY

Unique group code (e.g., FAM, WRK)

group_name

VARCHAR(50)

NOT NULL

Name of the contact category

description

VARCHAR(150)

—

Brief description of the group

2. contacts (Child Table)

Column

Data Type

Constraint

Description

contact_id

VARCHAR(20)

PRIMARY KEY

Unique contact identifier (e.g., CNT-1001)

full_name

VARCHAR(100)

NOT NULL

Contact's full name

phone

VARCHAR(30)

NOT NULL

Phone number

email

VARCHAR(100)

NOT NULL, UNIQUE

Email address

city

VARCHAR(60)

NOT NULL

City or location

group_id

VARCHAR(10)

FOREIGN KEY

References contact_groups(group_id)

priority_score

INT

CHECK (1..100)

Priority rating between 1 and 100

is_favorite

INTEGER

DEFAULT 0

1 for Favorite, 0 for Standard

Technologies Used

Frontend: HTML5, Tailwind CSS, Vanilla JavaScript, Lucide Icons

Database Engine: SQLite via SQL.js (WebAssembly)

How to Run Locally

Download or clone this repository.

Open index.html (or contact_management.html) directly in any modern web browser.
