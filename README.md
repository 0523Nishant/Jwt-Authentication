# Spring Boot JWT Authentication 🚀

Welcome to the Spring Boot JWT Authentication project! This project demonstrates how to implement JWT (JSON Web Token) authentication in a Spring Boot application.

## Table of Contents 📚

- [Features ✨](#features)
- [Technologies Used 💻](#technologies-used)
- [Getting Started 🚀](#getting-started)
  - [Prerequisites ⚙️](#prerequisites)
  - [Setup 🛠️](#setup)
- [Database Setup 📊](#database-setup)
- [Endpoints 🏗️](#endpoints)
- [Project Structure 📂](#project-structure)
- [SQL Scripts 🧑‍💻](#sql-scripts)

## Features ✨

- JWT Authentication for secure login
- User and Role-based Authorization
- Secure password handling with bcrypt
- API endpoints for login and user management

## Technologies Used 💻

- Spring Boot
- Spring Security
- JWT (JSON Web Token)
- H2 Database (or replace with your preferred DB)
- Maven
- JPA (Hibernate)

## Getting Started 🚀

Follow these instructions to get your project up and running.

### Prerequisites ⚙️

Before you begin, ensure you have the following installed:

- **Java 11 or higher** (for Spring Boot)
- **Maven** (for managing dependencies)
- **IDE** (IntelliJ IDEA, Eclipse, or your favorite Java IDE)

### Setup 🛠️

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/jwt-authentication-springboot.git

### Project Structure 📂
 ```bash
src/
 ├── main/
 │    ├── java/
 │    │    └── com/
 │    │         └── example/
 │    │             ├── config/          # Security & JWT configuration
 │    │             ├── controller/      # API Controllers
 │    │             ├── model/           # User, Role, and other models
 │    │             ├── repository/      # JPA Repositories
 │    │             └── service/         # Business logic for JWT & user management
 │    └── resources/
 │         └── application.properties    # Application configurations
 └── test/
      └── java/                         # Unit and integration tests

### SQL ⚙️
 ```bash

CREATE TABLE roles (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(20) NOT NULL
);

 ```bash
CREATE TABLE users (
    id BIGINT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(20) NOT NULL,
    email VARCHAR(50) NOT NULL,
    password VARCHAR(120) NOT NULL,
    CONSTRAINT unique_username UNIQUE (username),
    CONSTRAINT unique_email UNIQUE (email)
);
 ```bash

CREATE TABLE user_roles (
    user_id BIGINT NOT NULL,
    role_id INT NOT NULL,
    PRIMARY KEY (user_id, role_id),
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE,
    FOREIGN KEY (role_id) REFERENCES roles(id) ON DELETE CASCADE
);

Endpoints 🏗️
 ```bash

{
  "username": "your-username",
  "password": "your-password"
}
