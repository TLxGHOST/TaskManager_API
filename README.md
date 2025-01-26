# Task Manager API

This is a simple Task Manager API built with **Spring Boot** that allows users to create, read, update, and delete tasks. It uses **Spring Data JPA** to interact with a **MySQL** database and exposes a RESTful interface to manage tasks.

## Features

- Create a new task
- View all tasks
- View a task by ID
- Update an existing task
- Delete a task

## Requirements

- **Java 17** or higher
- **Maven** for dependency management
- **MySQL** (or PostgreSQL) for database storage

## Setup

### 1. Clone the repository
```bash
git clone https://github.com/your-username/task-manager-api.git
cd task-manager-api
```

### 2. Configure the database
- Create a new database in MySQL
- Update the database connection details in `src/main/resources/application.properties`
```bash
spring.datasource.url=jdbc:mysql://localhost:3306/task_manager
spring.datasource.username=root
spring.datasource.password=password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
spring.jpa.show-sql=true
```
### 3. Run the application
```bash
mvn spring-boot:run
```

### 4. API Endpoints
- The API exposes the following endpoints:

- GET all tasks
- Retrieve a list of all tasks.

- URL: /api/tasks
- Method: GET
```bash
curl -X GET http://localhost:8080/api/tasks
```
- GET a task by ID
- Retrieve a task by its ID.

- URL: /api/tasks/{id}
- Method: GET
```bash
curl -X GET http://localhost:8080/api/tasks/1
```
- POST a new task
- Create a new task.

- URL: /api/tasks
- Method: POST
- Body:
```json
{
  "title": "New Task",
  "description": "This is a new task",
  "completed": false
}
```

```bash
curl -X POST http://localhost:8080/api/tasks \
-H "Content-Type: application/json" \
-d '{"title": "New Task", "description": "This is a new task", "completed": false}'
```

- PUT update a task
- Update an existing task by its ID.

- URL: /api/tasks/{id}
- Method: PUT
- Body:
``` json
{
  "title": "Updated Task",
  "description": "Updated description",
  "completed": true
}
```
```bash
curl -X PUT http://localhost:8080/api/tasks/1 \
-H "Content-Type: application/json" \
-d '{"title": "Updated Task", "description": "Updated description", "completed": true}'
```
- DELETE a task
- Delete a task by its ID.

- URL: /api/tasks/{id}
- Method: DELETE
```bash
curl -X DELETE http://localhost:8080/api/tasks/1
```

### Technologies Used
- Spring Boot: Backend framework for building the REST API
- Spring Data JPA: For interacting with the database
- MySQL: Database to store task data
- Maven: Dependency management and build tool









