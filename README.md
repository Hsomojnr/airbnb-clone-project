# AirBnB Clone Project

## Overview

This project is a clone of the AirBnB web application. The goal is to understand and build a simplified version of the AirBnB platform, including features such as user registration, listing creation, booking functionality, and a review system.

## Project Goals

- Learn and implement full-stack web development.
- Build and deploy a dynamic web application.
- Work with backend APIs, databases, and frontend frameworks.

## Tech Stack

- **Frontend**: HTML, CSS, JavaScript
- **Backend**: Python (Django)
- **Database**:  PostgreSQL
- **Version Control**: Git and GitHub
- **Deployment**: Heroku, Render, or AWS

### 1. Django
A high-level Python web framework used to build the backend and RESTful APIs. It handles routing, business logic, authentication, and server-side rendering.

### 2. PostgreSQL
An open-source relational database used to store structured data such as users, bookings, listings, and reviews. Chosen for its reliability, scalability, and support for advanced querying.

### 3. HTML/CSS
The fundamental technologies for building and styling the structure of web pages. HTML provides the content structure, while CSS handles layout and visual design.

### 4. JavaScript
Adds interactivity to the frontend, enabling dynamic content updates, client-side validations, and improved user experience.

### 5. GraphQL
A query language for APIs that allows clients to request exactly the data they need. It provides more flexibility than REST and can optimize data fetching.

### 6. Git
A version control system to track changes in source code and collaborate with team members effectively.

### 7. GitHub
A cloud-based platform to host the Git repository, manage code reviews, track issues, and collaborate in a team setting.

### 8. Docker
Used to containerize the application, making it easier to develop, test, and deploy in consistent environments.

### 9. CI/CD Tools (GitHub Actions, Jenkins)
Automate testing, building, and deployment processes to ensure fast and reliable software delivery.

### 10. Deployment Platforms (Heroku, AWS, Render)
Used to host the live version of the application for end-users. Handles scalability, performance, and availability.



## Team Roles

The success of this project depends on collaboration between several roles, each contributing specific skills and responsibilities.

### 1. Frontend Developer
Responsible for creating the user interface and ensuring a smooth user experience. Works with HTML, CSS, and JavaScript to build responsive pages and connect them to backend APIs.

### 2. Backend Developer
Builds and maintains the server-side logic, API endpoints, and application workflows. Handles user authentication, data processing, and integrations with external services.

### 3. Database Administrator (DBA)
Designs and manages the project’s database schema. Ensures data consistency, performance optimization, and backup strategies for secure data storage.

### 4. DevOps Engineer
Manages code deployment, CI/CD pipelines, cloud infrastructure, and monitoring tools. Ensures smooth development-to-production transitions and uptime.

### 5. UX/UI Designer
Designs the visual look and feel of the platform, ensuring intuitive interfaces and positive user experience. Provides wireframes and mockups for frontend developers.

### 6. Project Manager
Coordinates the team, sets milestones, and ensures the project stays on schedule. Facilitates communication, task tracking, and risk management.

### 7. QA Engineer
Responsible for testing the application to ensure it works as expected. Writes test cases, performs manual and automated testing, and reports bugs.

## Database Design

The database will store all the essential data for users, listings, bookings, reviews, and payments. Below are the key entities and their relationships.

### 1. Users

Represents users of the platform (guests and hosts).

**Fields:**
- `id` (Primary Key)
- `name`
- `email`
- `password_hash`
- `user_type` (guest or host)

### 2. Properties

Represents listings created by hosts.

**Fields:**
- `id` (Primary Key)
- `user_id` (Foreign Key to Users)
- `title`
- `description`
- `location`
- `price_per_night`

**Relationship:**
- A **user** (host) can have **many properties**

### 3. Bookings

Represents reservations made by guests.

**Fields:**
- `id` (Primary Key)
- `user_id` (Foreign Key to Users)
- `property_id` (Foreign Key to Properties)
- `start_date`
- `end_date`
- `total_price`

**Relationship:**
- A **user** (guest) can have **many bookings**
- A **property** can have **many bookings**

### 4. Reviews

Represents feedback left by guests for a property.

**Fields:**
- `id` (Primary Key)
- `user_id` (Foreign Key to Users)
- `property_id` (Foreign Key to Properties)
- `rating` (1–5)
- `comment`

**Relationship:**
- A **user** can leave **many reviews**
- A **property** can have **many reviews**

### 5. Payments

Represents payment records for completed bookings.

**Fields:**
- `id` (Primary Key)
- `booking_id` (Foreign Key to Bookings)
- `amount`
- `payment_date`
- `payment_status` (paid, failed, refunded)

**Relationship:**
- Each **booking** has **one payment**

