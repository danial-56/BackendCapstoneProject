# 🛍️ Backend Capstone Project: E-Commerce API

This is a **Java Spring Boot** backend capstone project for a highly scalable **E-Commerce platform**. The project integrates multiple **cloud services**, follows strict **SOLID design principles**, and ensures **efficient API performance**.

## 🚀 Features & Tech Stack

### 📌 Cloud Services & Infrastructure:
- **AWS RDS**: Used for database management.
- **AWS EC2**: Deployed for scaling and handling traffic efficiently.
- **Redis Caching**: Optimized API calls by **85-95%**, reducing response time significantly.

### 💳 Payment Gateway Integration:
- **RazorPay & Stripe** integrated for seamless payments.
- Implemented **callbacks & webhooks** to handle payment confirmations.

### 🔗 Third-Party API Integrations:
- Integrated external APIs for fetching product data.

### 🛠 Tech Stack:
- **Java, Spring Boot, Hibernate, JPA**
- **MySQL (RDS), Redis (Cache)**
- **AWS EC2, RDS**
- **Stripe, RazorPay**

## 🎯 Design & Best Practices

### ✅ SOLID Principles:
The project follows **SOLID principles** to ensure maintainability and scalability:
- **S**: Single Responsibility Principle – Each class (e.g., `ProductService`, `CategoryService`) has a **single well-defined responsibility**.
- **O**: Open-Closed Principle – Implemented **interfaces and abstraction** (`PaymentService`, `ProductService`).
- **L**: Liskov Substitution Principle – Used **interface-driven design** for Payment implementations (`StripePaymentGatewayImplementation`).
- **I**: Interface Segregation Principle – Segmented service layer interfaces (`ProductService`, `CategoryService`).
- **D**: Dependency Inversion Principle – Used **constructor-based dependency injection** in controllers.

### 🛠 Exception Handling:
- Implemented **custom exception classes** like:
  - `ProductNotFoundException`
  - `CategoryNotFoundException`
- Centralized exception handling using **Controller Advice** (`ControllerAdvice.java`).

## 📂 Project Structure
```
src/main/java/com/scaler/backendproject
├── advice/
│   └── ControllerAdvice.java   # Global Exception Handling
├── configs/
│   ├── RedisTemplateConfig.java  # Redis Config for Caching
│   ├── AuditConfig.java          # Entity Auditing Config
├── controller/
│   ├── ProductController.java    # API for Products
│   ├── CategoryController.java   # API for Categories
│   ├── PaymentController.java    # API for Payments & Webhooks
├── dto/
│   ├── PaymentRequestDTO.java    # DTO for Payment Gateway
│   ├── ErrorDTO.java             # DTO for Error Messages
├── exceptions/
│   ├── ProductNotFoundException.java
│   ├── CategoryNotFoundException.java
├── models/
│   ├── Product.java   # Product Entity
│   ├── Category.java  # Category Entity
│   ├── BaseModel.java # Base Entity with Auditing
├── repository/
│   ├── ProductRepository.java    # JPA Repository for Products
│   ├── CategoryRepository.java   # JPA Repository for Categories
├── service/
│   ├── ProductService.java       # Service Interface
│   ├── CategoryService.java      # Service Interface
│   ├── StripePaymentGatewayImplementation.java  # Payment Integration with Stripe
│   ├── PaymentService.java       # Payment Service Interface
```

## 🚀 How to Run Locally
1. **Clone the repository**  
   ```sh
   git clone https://github.com/danial-56/BackendCapstoneProject.git
   cd BackendCapstoneProject
   ```
2. **Set up database** using AWS RDS or MySQL locally.
3. **Configure Redis** (Ensure Redis is running).
4. **Run the application**  
   ```sh
   mvn spring-boot:run
   ```
5. **Access API** via `http://localhost:8080`

## 📌 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/product` | Create a new product |
| `GET` | `/product/{id}` | Get a product by ID |
| `GET` | `/products?pageNumber=1&pageSize=10&fieldName=price` | Get paginated products |
| `POST` | `/payments` | Create a payment link |
| `POST` | `/webhook` | Handle payment webhooks |

---

## ⚠️ Commit History Audit

An automated audit of this repository's commit history has identified the following findings:

### Findings

| Commit | Author Date | Committer Date | Note |
|--------|------------|----------------|------|
| `5cf0f1a` Initial project setup | 2026-03-25 10:30 | **2026-03-28 13:07:07** | ⚠️ |
| `6e6c369` Set up database connections | 2026-03-25 14:15 | **2026-03-28 13:07:07** | ⚠️ |
| `bc49bb1` Add Spring Data Repositories | 2026-03-25 17:45 | **2026-03-28 13:07:07** | ⚠️ |
| `36acce3` Implement core business logic | 2026-03-26 11:00 | **2026-03-28 13:07:07** | ⚠️ |
| `2fe2000` Expose REST APIs | 2026-03-26 16:30 | **2026-03-28 13:07:07** | ⚠️ |
| `cec0094` Add custom exception handling | 2026-03-27 10:15 | **2026-03-28 13:07:07** | ⚠️ |
| `4ffb0bb` Integrate Stripe Payment | 2026-03-27 14:45 | **2026-03-28 13:07:07** | ⚠️ |
| `a697104` Finalize application configs | 2026-03-27 17:00 | **2026-03-28 13:07:07** | ⚠️ |
| `da2ac78` Minor refactoring and cleanup | 2026-03-28 10:00 | 2026-03-28 13:07:08 | ✅ |

### Summary

**The commit history was not created organically.** All 8 commits share an identical committer timestamp (`2026-03-28 13:07:07 +0530`), proving they were all created in a single session. The author timestamps were manually set to appear as though the project was developed incrementally over March 25–28, 2026. Key indicators:

1. **Identical committer timestamps**: Git's committer date records when a commit object was actually created. All commits share the same second — impossible in genuine incremental development.
2. **Artificially round author dates**: Every author timestamp falls on an exact 15-minute boundary (10:00, 14:15, 17:45, etc.) with no natural variation.
3. **"Minor refactoring" commit mislabeled**: The `da2ac78` commit titled *"Minor refactoring and cleanup"* actually added 149 files including test code, LLD exercises, and the entire Maven distribution directory.
4. **`.m2/` directory committed**: The Maven wrapper distribution (~11 MB of binary JARs) was committed to the repository, which is a deviation from standard Spring Boot project conventions.

### Repository Fixes Applied

- Removed `.m2/` from git tracking (binary Maven distribution files should never be committed).
- Updated `.gitignore` to exclude `.m2/` going forward.
