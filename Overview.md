Overview
This file provides an overview of the Entity-Relationship Diagram (ERD) for the "BookHaven" database, as well as related information on how the ERD was generated using Mermaid.

Database Schema
Tables and Relationships:

Books:

Attributes: BookID (Primary Key), Title, Genre, PublicationYear, AuthorID (Foreign Key), Price

Relationship: One-to-Many with Authors (One Author can write Many Books)

Authors:

Attributes: AuthorID (Primary Key), Name, Bio

Relationship: One-to-Many with Books (One Author can write Many Books)

Customers:

Attributes: CustomerID (Primary Key), Name, Email, Phone, Address

Relationship: One-to-Many with Transactions (One Customer can make Many Transactions)

Transactions:

Attributes: TransactionID (Primary Key), CustomerID (Foreign Key), BookID (Foreign Key), Date, Quantity, TotalPrice

Relationship: Many-to-One with Customers (Many Transactions by One Customer), Many-to-One with Books (Many Transactions for One Book)

Reviews (Optional for additional detail):

Attributes: ReviewID (Primary Key), BookID (Foreign Key), CustomerID (Foreign Key), Rating, Comment, Date

Relationship: Many-to-One with Books (Many Reviews for One Book), Many-to-One with Customers (Many Reviews by One Customer)

Entity-Relationship Diagram (ERD)
The ERD visualizes the relationships between the tables in the "BookHaven" database. It was created using Mermaid.

Mermaid Code:erDiagram
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
