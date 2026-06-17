Oracle Library Management System

-> Project Overview

The Oracle Library Management System is a database-driven application developed using Oracle Database 12c, SQL and PL/SQL. The project demonstrates Oracle DBA concepts along with database design, automation and reporting functionalities.

The system manages books, members, book copies, issue transactions and return transactions while maintaining data integrity through constraints, sequences, triggers, views and stored procedures.

---

Technologies Used

* Oracle Database 12c
* SQL
* PL/SQL
* Oracle Linux
* SQL*Plus

---

Oracle DBA Concepts Implemented

-> Storage Management

* Tablespace Creation
* User Quotas

-> Security Management

* Role Creation
* Profile Creation
* User Creation
* Privilege Management

-> Database Objects

* Tables
* Constraints
* Sequences
* Triggers
* Views
* Stored Procedures

---

Database Schema

Tables

-> BOOKS

Stores book information.

Columns:

* BOOK_ID
* TITLE
* AUTHOR
* ISBN
* CATEGORY
* PUBLISHER
* CREATE_DATE

-> MEMBERS

Stores member information.

Columns:

* MEMBER_ID
* MEMBER_NAME
* PHONE
* JOIN_DATE

-> BOOK_COPIES

Stores physical copies of books.

Columns:

* COPY_ID
* BOOK_ID
* STATUS

-> ISSUES

Stores book issue transactions.

Columns:

* ISSUE_ID
* COPY_ID
* MEMBER_ID
* ISSUE_DATE
* DUE_DATE

-> RETURNS

Stores returned book transactions.

Columns:

* RETURN_ID
* ISSUE_ID
* RETURN_DATE
* FINE

---

Sequences

* SEQ_BOOK_ID
* SEQ_MEMBER_ID
* SEQ_COPY_ID
* SEQ_ISSUE_ID
* SEQ_RETURN_ID

---

Triggers

Auto-ID Generation

* TRG_BOOK_ID
* TRG_MEMBER_ID
* TRG_COPY_ID
* TRG_ISSUE_ID
* TRG_RETURN_ID

Business Logic Automation

TRG_ISSUE_BOOK

Automatically updates book copy status from AVAILABLE to ISSUED when a book is issued.

TRG_RETURN_BOOK

Automatically updates book copy status from ISSUED to AVAILABLE when a book is returned.

---

Views

-> VW_AVAILABLE_BOOKS

Displays currently available books.

-> VW_ISSUED_BOOKS

Displays issued books along with member information.

-> VW_CURRENT_ISSUES

Displays books that are currently issued and not yet returned.

---

Stored Procedure

ISSUE_BOOK_PROC

Issues a book copy to a member and automatically creates an issue transaction.

Example:

EXEC ISSUE_BOOK_PROC(3,2);

---

Project Workflow

BOOKS
↓
BOOK_COPIES
↓
ISSUES
↓
RETURNS

Automation:

Issue Book
↓
TRG_ISSUE_BOOK
↓
STATUS = ISSUED

Return Book
↓
TRG_RETURN_BOOK
↓
STATUS = AVAILABLE

---

Repository Structure

oracle-library-management-system

├── README.md

├── scripts

│   ├── 01_tablespace.sql

│   ├── 02_security_setup.sql

│   ├── 03_books.sql

│   ├── 04_members.sql

│   ├── 05_book_copies.sql

│   ├── 06_issues.sql

│   ├── 07_returns.sql

│   ├── 08_views.sql

│   └── 09_procedures.sql

└── screenshots

```
├── 01_tables.png

├── 02_books.png

├── 03_members.png

├── 04_book_copies.png

├── 05_issues.png

├── 06_returns.png

├── 07_available_books_view.png

├── 08_issued_books_view.png

├── 09_current_issues_view.png

├── 10_procedure_execution.png

├── 11_triggers.png

└── 12_sequences.png
```

---

Key Learning Outcomes

* Oracle Database Administration
* User and Security Management
* SQL and PL/SQL Development
* Database Design
* Data Integrity using Constraints
* Automation using Triggers
* Reporting using Views
* Stored Procedure Development

---

Author
Bhargav Chaitanya.

