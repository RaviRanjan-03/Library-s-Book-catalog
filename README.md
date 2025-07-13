# **Library's-Book-Catalog API**

This is a Java-based RESTful API built with Spring Boot for managing a library’s book catalog.  
It supports operations like adding, listing, deleting, and updating book availability, and stores data in a MySQL database.

  ##  How to Run the Project (Using IntelliJ IDEA)
  - Java 8 or above
  - IntelliJ IDEA installed
  - Maven (bundled with IntelliJ)
  - MySQL server running
  - Postman (for API testing)

  ###  Configure MySQL Database
  1. Open MySQL and create a database:
     ```sql
     CREATE DATABASE library_db;



 2.Update your application.properties (or application.yml) in src/main/resources:

      spring.datasource.url=jdbc:mysql://localhost:3306/library_db
      spring.datasource.username=your_mysql_username
      spring.datasource.password=your_mysql_password
    
      spring.jpa.hibernate.ddl-auto=update
      spring.jpa.show-sql=true
      spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect


### ▶️Run the App in IntelliJ
     i Open IntelliJ and load the project.
     ii Wait for Maven dependencies to load (check bottom bar).
     iii Open LibraryApplication.java.
     iv Right-click the file and select Run 'LibraryApplication'.
     v The app should start at:
       - http://localhost:8080

### API Endpoints (Test with Postman)
  1. Add a New Book:
     
     POST /api/books
     
       Body:
     
           {
            "title": "Effective Java",
            "author": "Joshua Bloch",
            "isbn": "9780134685991",
            "available": true
           }
     Response:
     
           {
            "id": 1,
            "title": "Effective Java",
            "author": "Joshua Bloch",
            "isbn": "9780134685991",
            "available": true
           }

3. Get All Books:
   
   GET /api/books
   
     Response:
   
         [
            {
              "id": 1,
              "title": "Effective Java",
              "author": "Joshua Bloch",
              "isbn": "9780134685991",
              "available": true
            }
        ]

5. Get Book by ID:
   
   GET /api/books/1
   
    Response:
   
       {
        "id": 1,
        "title": "Effective Java",
        "author": "Joshua Bloch",
        "isbn": "9780134685991",
        "available": true
       }

7. Delete a Book:
   
   DELETE /api/books/1
   
      Response:
   
         Book deleted

9. Update Book Availability:
    
   PUT /api/books/1/availability?available=false
   
        Response:
   
           {
              "id": 1,
              "title": "Effective Java",
              "author": "Joshua Bloch",
              "isbn": "9780134685991",
              "available": false
           }

Tools Used:
 - Java 8+
 - Spring Boot (REST, JPA, Web)
 - MySQL 8
 - IntelliJ IDEA
 - Postman (for API testing)

Features:
 - REST-style CRUD operations
 - Persistent storage with MySQL
 - Input validation (title cannot be empty)
 - Modular and testable service architecture
