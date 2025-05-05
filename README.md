# 🏠 Airbnb Clone Project

## 🚀 Overview

The **Airbnb Clone Project** is a backend system designed to replicate the core functionalities of Airbnb. It provides a robust, scalable foundation for managing users, property listings, bookings, payments, and reviews. The system supports modern API standards and integrates advanced backend technologies to deliver a seamless experience for both hosts and guests.

## 🎯 Project Goals

- **User Management:** Secure user registration, authentication, and profile management.
- **Property Listings:** Create, update, retrieve, and manage property listings.
- **Booking System:** Allow users to book properties and manage their reservations.
- **Payment Integration:** Process and record payments securely.
- **Review System:** Enable users to post and manage property reviews.
- **Performance Optimization:** Implement database indexing and caching for efficient data handling.

## 🛠️ Technology Stack

A combination of modern tools and frameworks were used to build a robust, scalable, and maintainable backend system for the Airbnb Clone project.

### ⚙️ Django
A high-level Python web framework that simplifies building secure and maintainable web applications. Used for handling the core logic, URL routing, middleware, and views.

### 🌐 Django REST Framework (DRF)
A powerful and flexible toolkit for building Web APIs on top of Django. Used to create RESTful endpoints for CRUD operations.

### 🐘 PostgreSQL
A reliable and advanced open-source relational database system. Chosen for its performance, scalability, and support for complex queries and data relationships.

### 🔍 GraphQL
A query language for APIs that allows clients to request exactly the data they need. Integrated to provide a flexible and efficient alternative to REST endpoints.

### ⏱️ Celery
An asynchronous task queue used to run background jobs (e.g., sending confirmation emails, processing payments) outside the request-response cycle.

### 🧠 Redis
An in-memory data store used for caching and managing Celery task queues, helping improve performance and reduce database load.

### 📦 Docker
A containerization platform used to package the application and its dependencies into containers, ensuring consistency across development, testing, and production environments.

### 🔁 CI/CD Pipelines
Automated processes that handle building, testing, and deploying the application. Helps maintain code quality and streamline deployments.

## 🗄️ Database Design

The database schema is structured to support all core Airbnb functionalities such as user registration, property listings, bookings, payments, and reviews.

### 📘 Entities and Relationships

#### 1. **Users**
- `id`: Unique identifier for the user
- `name`: Full name of the user
- `email`: Email address (used for login)
- `password`: Hashed password
- `is_host`: Boolean flag to differentiate between guests and hosts  
🔗 **Relationships**: A user can own multiple properties, create bookings, and leave reviews.

#### 2. **Properties**
- `id`: Unique identifier for the property
- `owner_id`: Foreign key linking to the User who owns the property
- `title`: Property title or headline
- `description`: Details about the property
- `price_per_night`: Cost to book per night  
🔗 **Relationships**: A property belongs to one user (host), can have multiple bookings and reviews.

#### 3. **Bookings**
- `id`: Unique booking identifier
- `user_id`: Foreign key referencing the guest who made the booking
- `property_id`: Foreign key referencing the property
- `check_in_date`: Booking start date
- `check_out_date`: Booking end date  
🔗 **Relationships**: A booking is made by a user for a specific property.

#### 4. **Payments**
- `id`: Unique payment identifier
- `booking_id`: Foreign key linking the payment to a booking
- `amount`: Total amount paid
- `payment_method`: e.g., credit card, PayPal
- `status`: Payment status (pending, completed, failed)  
🔗 **Relationships**: Each payment is associated with one booking.

#### 5. **Reviews**
- `id`: Unique review identifier
- `user_id`: Foreign key linking to the reviewer
- `property_id`: Foreign key referencing the reviewed property
- `rating`: Numerical rating (e.g., 1–5)
- `comment`: Text feedback  
🔗 **Relationships**: A user can leave a review for a property after booking it.

### 🔗 Entity Relationship Summary
- A **User** can:
  - own multiple **Properties**
  - make multiple **Bookings**
  - write multiple **Reviews**

- A **Property**:
  - belongs to one **User**
  - can have multiple **Bookings** and **Reviews**

- A **Booking**:
  - belongs to one **User** and one **Property**
  - has one associated **Payment**

- A **Review**:
  - belongs to one **User** and one **Property**

## 👥 Team Roles

This project is a collaborative effort involving specialists with distinct responsibilities to ensure development, deployment, and maintenance of a high-quality backend system.

### 🧠 Backend Developer
Responsible for implementing the core business logic, API endpoints, authentication, and system integrations using Django and Django REST Framework. Works closely with other team members to translate functional requirements into technical solutions.

### 🗃️ Database Administrator (DBA)
Manages the design, implementation, and optimization of the PostgreSQL database. Responsible for indexing, query performance, data integrity, and backup strategies.

### ⚙️ DevOps Engineer
Handles environment setup, continuous integration/continuous deployment (CI/CD), containerization with Docker, and ensures system scalability, availability, and monitoring in production.

### 🧪 QA Engineer
Designs and executes test cases to validate system functionality, reliability, and performance. Works to identify bugs and edge cases before deployment, ensuring high-quality releases.

### 📡 API Architect (optional but recommended)
Designs API structures (REST and GraphQL) for consistency and scalability. Defines communication protocols and documentation standards for frontend-backend integration.

---


---

> 📁 **Repository:** [`airbnb-clone-project`](https://github.com/matidzatshepo/airbnb-clone-project)

