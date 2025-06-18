# airbnb-clone-project
An Airbnb Clone backend project built with Django, GraphQL, MySQL, and Docker. Implements core booking, user management, reviews, and payment systems with CI/CD and API security.


# Airbnb Clone Project

## Project Overview
StayBackend is a backend-focused Airbnb clone designed to replicate the functionalities of a modern booking platform. The goal is to simulate real-world backend development practices including API design, secure user authentication, property booking, payment handling, and CI/CD pipeline integration.

---

## Project Goals

- Implement user authentication, authorization, and profile management.
- Enable hosts to create, manage, and delete property listings.
- Allow users to book, review, and pay for properties.
- Use Django and GraphQL for scalable and flexible backend development.
- Integrate CI/CD pipelines for efficient deployment.
- Ensure secure, maintainable, and production-ready backend systems.

---

## Team Roles

| Role | Description |
|------|-------------|
| **Backend Developer** | Designs and implements APIs, handles authentication, and ensures business logic consistency. |
| **Database Administrator (DBA)** | Structures relational databases, defines entity relationships, and implements indexing for optimization. |
| **DevOps Engineer** | Manages deployment pipelines, monitors uptime, configures Docker containers, and maintains CI/CD pipelines. |
| **QA Engineer** | Ensures that all backend features are tested, validates API functionality, and identifies defects early in development. |

---

## Technology Stack

| Technology | Purpose |
|------------|---------|
| **Django** | A high-level Python web framework for building secure, scalable APIs. |
| **Django REST Framework** | Enables the creation of robust RESTful APIs for user and property data. |
| **GraphQL** | Provides flexible query access to nested backend data. |
| **MySQL** | A relational database for structured and transactional data. |
| **Celery** | Used for handling background tasks like sending confirmation emails or payment processing. |
| **Redis** | In-memory store for caching and Celery broker. |
| **Docker** | Containerization platform for consistent development and deployment environments. |
| **GitHub Actions** | CI/CD tool to automate testing and deployment workflows. |

---

## Database Design

### Key Entities and Fields

1. **User**
   - `id`, `username`, `email`, `password`, `is_host`

2. **Property**
   - `id`, `title`, `description`, `location`, `price_per_night`, `host_id (FK → User)`

3. **Booking**
   - `id`, `user_id (FK → User)`, `property_id (FK → Property)`, `check_in`, `check_out`, `status`

4. **Payment**
   - `id`, `booking_id (FK → Booking)`, `amount`, `payment_method`, `status`

5. **Review**
   - `id`, `user_id (FK → User)`, `property_id (FK → Property)`, `rating`, `comment`

### Relationships

- A **User** can list many **Properties**.
- A **User** can make many **Bookings**.
- A **Booking** is linked to one **Payment**.
- A **Property** can have many **Reviews** from different **Users**.

---

## Feature Breakdown

1. **User Management**
   - Secure registration and login system with profile editing. Handles host/user role differentiation.

2. **Property Management**
   - Hosts can create, update, or remove listings. Includes pricing, descriptions, and location tagging.

3. **Booking System**
   - Enables users to select dates and reserve properties. Supports real-time availability checking.

4. **Payment Processing**
   - Integrates a mock or real payment gateway to handle booking payments and receipts.

5. **Review System**
   - Users can post ratings and feedback after stays, enhancing transparency and property quality.

6. **GraphQL API**
   - Provides efficient and customizable queries to fetch deeply nested property, booking, and review data.

---

## API Security

Key Security Measures:

- **Authentication**: Only verified users can log in and access their data using JWT or session-based auth.
- **Authorization**: Role-based access control — only hosts can manage listings; users can only access their bookings.
- **Rate Limiting**: Prevent brute-force attacks and abuse using throttling middleware.
- **Data Validation**: Input sanitization to prevent injection attacks and data corruption.
- **Secure Payments**: Ensures financial data is handled via secure, tokenized APIs.
- **HTTPS**: All traffic will be encrypted during production deployment.

Security is essential to protect:
- **User privacy and credentials**
- **Booking and payment integrity**
- **System availability from abuse**

---

## CI/CD Pipeline

### What is CI/CD?
CI/CD stands for **Continuous Integration** and **Continuous Deployment** — practices that ensure frequent, reliable delivery of software changes through automation.

### Pipeline Features:

- **Code Quality Checks** (Linting, Formatting)
- **Automated Testing** on push/pull requests
- **Docker Builds** for environment consistency
- **Automatic Deployments** on merge to main branch

### Tools Used:
- **GitHub Actions**: Automates testing, build, and deployment workflows.
- **Docker**: Packages the backend app into reproducible containers.
- *(Optionally)* **Heroku / AWS / Render**: For backend hosting

---

## Timeline
- **Project Start**: June 16, 2025
- **Deadline**: June 23, 2025

---

## Submission
Once all tasks are complete:
1. Push this README to the `airbnb-clone-project` repository.
2. Notify the manual reviewer to begin QA.

---
