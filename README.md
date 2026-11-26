# Java Spring Boot REST APIs

![Java](https://img.shields.io/badge/Java-21-orange)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-REST%20API-6DB33F)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-database-336791)
![Maven](https://img.shields.io/badge/build-Maven-C71A36)

A hands-on backend development project demonstrating RESTful API development using Java, Spring Boot, and Spring MVC.

The application implements Student management APIs using a layered architecture, integrating Spring Data JPA for database persistence and PostgreSQL as the relational database.

The project focuses on understanding how modern Java backend applications handle HTTP requests, business logic, data persistence, request validation, and object mapping.

In simple terms, A Student REST API built with Spring Boot, using a layered architecture (Controller, Service, Repository), Spring Data JPA, PostgreSQL, DTOs and ModelMapper.

## Tech Stack

| Technology | Purpose |
|---|---|
| Java 21 | Programming language |
| Spring Boot 4.1.2 | Application framework |
| Spring MVC | REST API development |
| Spring Data JPA | Database persistence |
| Hibernate | ORM implementation |
| PostgreSQL | Relational database |
| Jakarta Validation | Request validation |
| ModelMapper | DTO and entity mapping |
| Lombok | Boilerplate code reduction |
| Maven | Dependency management |

## Architecture

The application follows a layered architecture that separates HTTP request handling, business logic, and database operations.

```text
                 Client
                   |
                   v
          Spring MVC Controller
                   |
                   v
              Service Layer
                   |
                   v
            Repository Layer
                   |
                   v
             Spring Data JPA
                   |
                   v
              PostgreSQL
```

## Table of Contents
 
- [Application Layers](#application-layers)
- [Project Structure](#project-structure)
- [Features and Concepts](#features-and-concepts)
- [Getting Started](#getting-started)
- [API Development and Testing](#api-development-and-testing)
- [Build and Test](#build-and-test)
- [Learning Objectives](#learning-objectives)

## Application Layers
 
### 1. Controller Layer
 
- Handles incoming HTTP requests.
- Defines REST API endpoints.
- Processes request parameters, path variables, and request bodies.
- Returns appropriate HTTP responses.
### 2. Service Layer
 
- Contains application business logic.
- Coordinates operations between controllers and repositories.
- Separates business logic from HTTP request handling.
### 3. Repository Layer
 
- Handles database interactions.
- Uses Spring Data JPA for persistence operations.
- Provides data access abstractions.
### 4. Entity Layer
 
- Defines the `Student` domain entity.
- Maps Java objects to database tables using JPA annotations.
### 5. DTO Layer
 
- Separates API request and response models from persistence entities.
- Uses ModelMapper for object conversion.
### 6. Configuration Layer
 
- Contains application-level configuration.
- Defines the ModelMapper bean for dependency injection.
## Project Structure
 
```text
LearningRESTAPIs/
│
├── .mvn/
│   └── wrapper/
│
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/springboot/mvc/LearningRESTAPIs/
│   │   │       │
│   │   │       ├── config/
│   │   │       │   └── MapperConfig.java
│   │   │       │
│   │   │       ├── controller/
│   │   │       │   └── StudentController.java
│   │   │       │
│   │   │       ├── DTO/
│   │   │       │   ├── AddStudentRequestDto.java
│   │   │       │   └── StudentDto.java
│   │   │       │
│   │   │       ├── entity/
│   │   │       │   └── Student.java
│   │   │       │
│   │   │       ├── repository/
│   │   │       │   └── StudentRepository.java
│   │   │       │
│   │   │       ├── service/
│   │   │       │   ├── StudentService.java
│   │   │       │   └── impl/
│   │   │       │       └── StudentServiceImplementation.java
│   │   │       │
│   │   │       └── LearningRestapIsApplication.java
│   │   │
│   │   └── resources/
│   │       └── application.properties
│   │
│   └── test/
│
├── .gitignore
├── mvnw
├── mvnw.cmd
├── pom.xml
├── README.md
└── LICENSE
```
 
## Features and Concepts
 
This project demonstrates:
 
- RESTful API development using Spring MVC.
- Layered backend architecture.
- Controller-Service-Repository separation.
- Dependency Injection and Spring Beans.
- Entity modelling using JPA.
- Database integration using PostgreSQL.
- Data persistence using Spring Data JPA.
- DTO-based request and response handling.
- Entity-to-DTO mapping using ModelMapper.
- Request validation using Jakarta Validation.
- Dependency management using Maven.
## Getting Started
 
### Prerequisites
 
Make sure the following are installed:
 
- JDK 21
- PostgreSQL
- Git
- Maven (optional when using the Maven Wrapper)
Verify Java:
 
```bash
java -version
```
 
### 1. Clone the repository
 
```bash
git clone https://github.com/Mdsid7/Java-Spring-boot-REST-APIS.git
```
 
### 2. Navigate to the project
 
```bash
cd Java-Spring-boot-REST-APIS
```
 
### 3. Configure PostgreSQL
 
Create a PostgreSQL database for the application, then update the connection settings in:
 
`src/main/resources/application.properties`
 
Example configuration:
 
```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/your_database
spring.datasource.username=${DB_USERNAME}
spring.datasource.password=${DB_PASSWORD}
 
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```
 
Set the environment variables before running the application:
 
```bash
# macOS / Linux
export DB_USERNAME=your_username
export DB_PASSWORD=your_password
```
 
```powershell
# Windows (PowerShell)
$env:DB_USERNAME="your_username"
$env:DB_PASSWORD="your_password"
```
 
> **Warning:** Do not commit database credentials or other secrets.
 
### 4. Run the application
 
Using the Maven Wrapper:
 
```bash
./mvnw spring-boot:run
```
 
Or with Maven installed:
 
```bash
mvn spring-boot:run
```
 
The application starts on the configured Spring Boot server port (`8080` by default).
 
## API Development and Testing
 
`StudentController` exposes the application's Student REST API operations. It uses Spring MVC annotations for request mapping and delegates application operations to the service layer.
 
Use [Postman](https://www.postman.com/) or another REST client to interact with the endpoints.
 
Refer to `StudentController.java` for the exact endpoint paths, HTTP methods, request formats, and response structures.
 
## Build and Test
 
Build the application:
 
```bash
./mvnw clean package
```
 
Run automated tests:
 
```bash
./mvnw test
```
 
## Learning Objectives
 
This project provides practical exposure to:
 
- Java backend development.
- Spring Boot application fundamentals.
- Spring MVC request processing.
- REST API design and implementation.
- Layered architecture and separation of concerns.
- Dependency Injection and configuration.
- Spring Data JPA and Hibernate.
- PostgreSQL integration.
- DTO and Entity separation.
- Object mapping and request validation.
- Maven-based application development.
