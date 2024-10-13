# Email Service

This project is the **Email Service** component of the **Voters Voice Amendment (VVA)** system. It provides functionality for managing contact requests submitted by users, allowing them to reach out to VVA for inquiries or feedback.

## Features

- **Email Form Submission**:
    - Users can submit a email form with their name, email, and message.
    - The service validates the form and stores the email requests in a database for further processing.

- **Email Notification**:
    - Send email notifications to administrators when a new email form submission is received.

## Technologies Used

- **Spring Boot** 3.3.4 (Java 23)
    - **Spring Web**: For building RESTful APIs.
    - **Spring Data JPA**: For interacting with the PostgreSQL database.
    - **PostgreSQL**: As the relational database to store email form submissions.

## Project Setup

### Prerequisites

Before running this project, ensure you have the following installed:

- **Java 17 or higher**
- **Maven**
- **PostgreSQL** (If running locally)

### Build and Run the Project

1. **Clone the repository**:
    ```bash
    git clone https://github.com/votersvoiceamendment/emailservice.git
    cd emailservice
    ```

2. **Build the project**:
    ```bash
    mvn clean package
    ```

3. **Run the application**:
    ```bash
    mvn spring-boot:run
    ```

The application will start on [http://localhost:8080](http://localhost:8080) by default.

### Dockerization

This service is containerized using Docker. You can build and run the Docker container as follows:

1. **Build the Docker image**:
    ```bash
    docker build -t emailservice .
    ```

2. **Run the Docker container**:
    ```bash
    docker run -p 8080:8080 emailservice
    ```

### Database Configuration

The project is configured to use **PostgreSQL**. You can set the database credentials in the `application.properties` or use environment variables to override them.

**Example properties**:
```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/email_service
spring.datasource.username=your_username
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=update
