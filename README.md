# Inventory Management System (ASP.NET Core + Tailwind CSS)

## Overview

This project is a **production-grade, scalable, and maintainable Inventory Management System** built with **ASP.NET Core** and styled using **Tailwind CSS**. It follows **clean architecture principles**, strict **separation of concerns**, and is fully **mobile-responsive**.

The system is suitable for real-world business use and also designed to demonstrate **enterprise-level backend and full‑stack engineering skills** for job applications.

---

## Key Objectives

* Clean, modular, and testable architecture
* Scalable backend using ASP.NET Core
* Secure authentication and authorization
* Mobile‑responsive UI with Tailwind CSS
* Easy to extend for ERP / CRM use cases

---

## Technology Stack

### Backend

* **ASP.NET Core 8 (Web API + MVC)**
* **Entity Framework Core** (Code‑First)
* **SQL Server** (PostgreSQL compatible)
* **ASP.NET Identity + JWT Authentication**
* **AutoMapper**
* **FluentValidation**

### Frontend

* **Razor Pages / MVC Views**
* **Tailwind CSS**
* **Alpine.js** (lightweight interactivity)

### DevOps & Tooling

* Docker (optional)
* Swagger / OpenAPI
* Serilog (logging)
* xUnit (testing)

---

## System Features

### Core Modules

* Authentication & Role‑Based Authorization
* Product Management
* Category Management
* Supplier Management
* Stock In / Stock Out
* Inventory Tracking
* Low‑Stock Alerts
* User Management (Admin)

### Advanced Features

* Audit Logs
* Pagination & Search
* Soft Deletes
* Server‑side Validation
* RESTful API support

---

## Architecture

This project follows **Clean Architecture**:

```
InventorySystem
│
├── src
│   ├── Inventory.API          # API Layer
│   ├── Inventory.Web          # MVC / Razor UI
│   ├── Inventory.Application  # Business Logic
│   ├── Inventory.Domain       # Core Entities
│   └── Inventory.Infrastructure # DB, Auth, External Services
│
└── tests
    └── Inventory.Tests
```

### Layer Responsibilities

#### Domain

* Entities
* Enums
* Domain rules

#### Application

* Use Cases
* DTOs
* Interfaces
* Validators

#### Infrastructure

* EF Core DbContext
* Repositories
* Authentication
* External services

#### Web / API

* Controllers
* UI Views
* API Endpoints

---

## Database Design (Sample)

* Users
* Roles
* Products
* Categories
* Suppliers
* StockTransactions
* AuditLogs

All tables use **GUID primary keys** and **soft deletes**.

---

## UI & Responsiveness

* Tailwind CSS utility‑first design
* Fully responsive (mobile, tablet, desktop)
* Accessible and clean UI
* Component‑based layout

---

## How to Build This Application (Step‑by‑Step)

### 1. Create Solution

```bash
dotnet new sln -n InventorySystem
```

### 2. Create Projects

```bash
dotnet new webapi -n Inventory.API
dotnet new mvc -n Inventory.Web
dotnet new classlib -n Inventory.Domain
dotnet new classlib -n Inventory.Application
dotnet new classlib -n Inventory.Infrastructure
```

### 3. Add Project References

```bash
dotnet add Inventory.Application reference Inventory.Domain
dotnet add Inventory.Infrastructure reference Inventory.Application
dotnet add Inventory.API reference Inventory.Application
dotnet add Inventory.Web reference Inventory.Application
```

### 4. Configure Entity Framework Core

* Add DbContext in Infrastructure
* Configure migrations
* Use Code‑First approach

```bash
dotnet ef migrations add InitialCreate
dotnet ef database update
```

### 5. Authentication & Authorization

* ASP.NET Identity
* JWT Tokens
* Role‑based access control

### 6. Business Logic

* Use CQRS‑style services
* Validation via FluentValidation
* Mapping via AutoMapper

### 7. API Layer

* RESTful endpoints
* Swagger documentation
* DTO‑based communication

### 8. UI with Tailwind CSS

```bash
npm install -D tailwindcss
npx tailwindcss init
```

* Configure Tailwind in wwwroot
* Use utility classes in Razor views

### 9. Logging & Error Handling

* Serilog
* Global exception middleware

### 10. Testing

* Unit tests for services
* Integration tests for API

---

## Running the Project

```bash
dotnet run --project Inventory.API
dotnet run --project Inventory.Web
```

Navigate to:

* API: `https://localhost:5001/swagger`
* Web: `https://localhost:5000`

---

## Security Considerations

* JWT expiration & refresh tokens
* Password hashing
* Input validation
* SQL injection protection

---

## Scalability & Maintainability

* Stateless APIs
* Dependency Injection
* Clear layer boundaries
* Easily extendable modules

---

## Future Enhancements

* Multi‑warehouse support
* Barcode scanning
* Reporting & analytics
* Microservices split
* Cloud deployment (Azure/AWS)

---

## License

MIT License

---

## Author

**Bilal Hassan**
Full‑Stack / Backend Engineer

This project is designed for **real‑world usage and senior‑level job applications**.
