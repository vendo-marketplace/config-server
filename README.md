# Config Server

The **Config Server** is the **Centralized Configuration Management** component for the Vendo platform.

It provides HTTP, resource-based API for external configuration in a distributed system. By using this service, you have one central place to manage external properties for applications across all environments. It fetches configuration files from a remote Git repository and serves them to all other microservices upon startup.

---
# Tech Stack

* Java 17
* Spring Boot
* Maven

---

# Architecture

The Config Server is a foundational **Infrastructure Component**. It does not contain domain business logic, Hexagonal Architecture, or CQRS patterns.

# Project Structure

```
src
 └── main
     └── java
         └── com.vendo.config_server
             └── config
```

---

# Prerequisites

This is typically the **very first service** that must be started in the Vendo platform ecosystem, as all other services depend on it to load their configurations.

## Dependencies

- **Git Repository:** A remote Git repository containing the configuration files

---

# Running the Service

---

## Run application

Or build and run:

```
mvn clean package
java -jar target/config_server.jar
```

---

# Environment Variables

| Variable          | Description                                | Default |
|-------------------|--------------------------------------------|---------|
| SERVER_PORT       | Port on which the config server runs       | 8010    |
| GIT_CONFIGS_URL   | URI of the Git repository with configs     | -       |
| GIT_USERNAME      | Username for Git repository authentication | -       |
| GIT_PASSWORD      | Password/Token for Git authentication      | -       |

---

# Code Style

The project follows standard **Java code conventions**.

Key principles:

* Clean Architecture
* SOLID principles
* Immutable DTOs
* Constructor injection
* Clear separation between layers

---

# Contributing

1. Create feature branch
2. Write tests
3. Ensure tests pass
4. Create pull request