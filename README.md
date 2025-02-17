# Module 5 Lesson 1: Relational Database

## Overview
This project demonstrates the concepts and implementation of a relational database in Python. It includes examples of creating tables, inserting data, and performing queries using SQL.

## Features
- **Database Schema**: Definition of the relational database schema.
- **ERD**: Entity-Relationship Diagram (ERD) for visualizing the relationships between tables.
- **CRUD Operations**: Examples of Create, Read, Update, and Delete operations.
- **Sample Data**: Script to populate the database with sample data.
- **Query Examples**: Various SQL queries to interact with the database.

## Getting Started

### Prerequisites
- Python 3.x
- SQLite3

### Installation
1. Clone the repository:
   ```sh
Install required packages (if any):
pip install -r requirements.txt
Usage
python mod\ 5\ less\ 1\ database.py
Execute SQL queries to interact with the database using an SQLite client or through the provided scripts.

Entity-Relationship Diagram (ERD)
How to Generate the ERD
To generate the ERD using Mermaid:

Install Required Extension:

If using Visual Studio Code (VSCode), install the "Markdown Preview Mermaid Support" extension or any other relevant extension that supports Mermaid diagrams.
Add Mermaid Code:
Include the following Mermaid code in your Markdown file:The ERD visualizes the relationships between the tables in the "BookHaven" database. It was created using Mermaid.Run the database script to set up the schema and populate sample data:
```mermaid
erDiagram
    AUTHORS {
        int AuthorID
        string Name
        string Bio
    }
    BOOKS {
        int BookID
        string Title
        string Genre
        int PublicationYear
        int AuthorID
        float Price
    }
    CUSTOMERS {
        int CustomerID
        string Name
        string Email
        string Phone
        string Address
    }
    TRANSACTIONS {
        int TransactionID
        int CustomerID
        int BookID
        date Date
        int Quantity
        float TotalPrice
    }
    REVIEWS {
        int ReviewID
        int BookID
        int CustomerID
        int Rating
        string Comment
        date Date
    }

    AUTHORS ||--o{ BOOKS: "writes"
    CUSTOMERS ||--o{ TRANSACTIONS: "makes"
    BOOKS ||--o{ TRANSACTIONS: "includes"
    CUSTOMERS ||--o{ REVIEWS: "writes"
    BOOKS ||--o{ REVIEWS: "receives"
Preview the Diagram:

Save your Markdown file.

Open the Markdown preview to view the ERD.

The ERD accurately reflects the relationships within the database, highlighting key connections such as the link between Books and Authors, and Customers and Transactions.
