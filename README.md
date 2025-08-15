# Library Management System

A modern JavaFX-based Library Management System that connects to a MySQL database. This project demonstrates robust CRUD operations (Create, Read, Update, Delete) and sorting for managing books in a library.

## Features
- View all books in the library
- Add new books
- Update existing book details
- Delete books
- Search for books by title or author
- **Sort books by any column (title, author, availability, etc.)**

## Technologies Used
- Java 17+
- JavaFX
- MySQL
- JDBC
- Maven

## Getting Started

### Prerequisites
- Java 17 or higher
- Maven
- MySQL Server

### Database Setup
1. **Create the Database:**
   ```sql
   CREATE DATABASE library_db;
   USE library_db;
   ```
2. **Create the Books Table:**
   ```sql
   CREATE TABLE Books (
     book_id INT AUTO_INCREMENT PRIMARY KEY,
     title VARCHAR(255) NOT NULL,
     author VARCHAR(255) NOT NULL,
     available BOOLEAN DEFAULT TRUE
   );
   ```

### Configuration
1. **Database Credentials:**
   - Copy `src/main/resources/db.properties.example` to `src/main/resources/db.properties`.
   - Edit `db.properties` with your MySQL credentials:
     ```properties
     db.url=jdbc:mysql://localhost:3306/library_db
     db.user=YOUR_USERNAME
     db.password=YOUR_PASSWORD
     ```
   - **Note:** `db.properties` is in `.gitignore` and should not be committed.

### Build & Run
1. **Build the project:**
   ```sh
   mvn clean install
   ```
2. **Run the application:**
   ```sh
   mvn javafx:run
   ```

## Sorting Functionality
- You can sort the books in the table by clicking on any column header (e.g., Title, Author, Availability).
- Sorting is handled automatically by JavaFX TableView, providing a seamless and interactive user experience.

## Project Structure
```
LibrarySystem/
├── src/
│   ├── main/
│   │   ├── java/com/mylibrary/
│   │   │   ├── Book.java
│   │   │   ├── DatabaseConnection.java
│   │   │   └── LibraryUI.java
│   │   └── resources/
│   │       ├── db.properties.example
│   │       └── com/mylibrary/primary.fxml
│   │       └── com/mylibrary/secondary.fxml
├── pom.xml
└── ...
```

## Security
- **Never commit your real database credentials!**
- The `db.properties` file is ignored by Git. Use the provided `db.properties.example` as a template.

## License
This project is for educational purposes only.
