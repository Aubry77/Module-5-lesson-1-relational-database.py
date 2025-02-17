# BookHaven Database ERD

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
