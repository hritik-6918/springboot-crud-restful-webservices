# Spring Boot CRUD RESTful Web Services

A complete Spring Boot application that exposes a set of RESTful APIs for managing users. It provides functionality to **Create**, **Read**, **Update**, and **Delete** (CRUD) `User` entities with integration to a **MySQL** database.

---

## ✨ Features

* RESTful API endpoints using Spring Boot
* CRUD operations for `User` entity
* MySQL database integration
* Exception handling with custom exception class
* Maven-based project structure

---

## 📊 Technologies Used

* Java 17
* Spring Boot 3.5.0
* Spring Data JPA
* MySQL
* Maven

---

## 📦 Project Structure

```bash
hritik-6918-springboot-crud-restful-webservices/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── net/springboot/springboot/
│   │   │       ├── SpringbootCrudRestfulWebservicesApplication.java
│   │   │       ├── controller/
│   │   │       │   └── UserController.java
│   │   │       ├── entity/
│   │   │       │   └── User.java
│   │   │       ├── exception/
│   │   │       │   └── ResourceNotFoundException.java
│   │   │       └── repository/
│   │   │           └── UserRepository.java
│   │   └── resources/
│   │       └── application.properties
│   └── test/
│       └── java/
│           └── net/springboot/springboot/
│               └── SpringbootCrudRestfulWebservicesApplicationTests.java
├── pom.xml
├── mvnw / mvnw.cmd
└── .mvn/
```

---

## ⚙️ Setup & Configuration

### Prerequisites

* Java 17+
* Maven 3.6+
* MySQL Server

### Application Properties

Configure your `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/usersDB?useSSL=false
spring.datasource.username=your_mysql_username
spring.datasource.password=your_mysql_password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect
```

> Replace `your_mysql_username` and `your_mysql_password` with actual MySQL credentials.

### Build & Run

```bash
# Build the project
./mvnw clean install

# Run the application
./mvnw spring-boot:run
```

Application will start at: `http://localhost:8080`

---

## 🔧 API Endpoints

| Method | Endpoint          | Description           |
| ------ | ----------------- | --------------------- |
| GET    | `/api/users`      | Retrieve all users    |
| GET    | `/api/users/{id}` | Retrieve a user by ID |
| POST   | `/api/users`      | Create a new user     |
| PUT    | `/api/users/{id}` | Update a user by ID   |
| DELETE | `/api/users/{id}` | Delete a user by ID   |

### Example JSON Payload for Create/Update:

```json
{
  "firstName": "John",
  "lastName": "Doe",
  "email": "john.doe@example.com"
}
```

---

## 🚫 Exception Handling

Custom exception `ResourceNotFoundException` is used to handle cases where a user with a given ID does not exist. It returns HTTP 404 with appropriate error messages.

---

## 📊 Testing

Unit test class: `SpringbootCrudRestfulWebservicesApplicationTests.java`

Run tests using Maven:

```bash
./mvnw test
```

---

## 🚀 Future Enhancements

* Swagger/OpenAPI integration for API docs
* User input validation (using `javax.validation`)
* Pagination and filtering support
* Docker containerization

---

## 🙏 Acknowledgments

This is a learning project built with Spring Boot to demonstrate building REST APIs with full CRUD capabilities.

---
