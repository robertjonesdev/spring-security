# Spring Boot 3.0 Security with JWT Implementation

This project demonstrates the implementation of security using Spring Boot 3.0 and JSON Web Tokens (JWT). It includes the following features:

## Features

- User registration and login with JWT authentication
- Password encryption using BCrypt
- Role-based authorization with Spring Security
- Customized access denied handling
- Logout mechanism
- Refresh token

## Technologies

- Spring Boot 3.0
- Spring Security
- JSON Web Tokens (JWT)
- BCrypt
- Maven

## Requirements

To get started with this project, you will need to have the following installed on your local machine:

- JDK 17+
- Maven 3+

To build and run the project, follow these steps:

- Add database "jwt_security" to postgres
- Build the project: mvn clean install
- Run the project: mvn spring-boot:run

## System Design

![System Design](/design.png)


## Testing the Demo

1. GET http://localhost:8080/api/v1/demo-controller
    - Expected: 403 Forbidden
2. POST http://localhost:8080/api/v1/auth/authenticate
    - { email, password }
    - Expected: 403 Forbidden
3. POST http://localhost:8080/api/v1/auth/register
    - { firstname, lastname, email, password }
    - Expected: 200 OK w/ JWT Token
4. GET http://localhost:8080/api/v1/demo-controller
    - Authorization Bearer Token: <JWT Token from Step #3>
    - Expected: 200 OK "Hello from secured endpoint"