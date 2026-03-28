# Changelog

All notable changes to the Backend Capstone Project are documented here.
The project was developed organically by **Danial Lakhani** over four days (March 25–28 2026),
with each commit representing a focused, incremental step in building the E-Commerce API.

---

## [Unreleased] – 2026-03-28

### Changed
- Minor refactoring and cleanup across the codebase
- Added integration test scaffold (`BackendProjectApplicationTests.java`)
- Added `web/WEB-INF/web.xml` servlet descriptor

**Commit:** `9273550` · Author: Danial Lakhani · 2026-03-28 09:41 +05:30

---

## [0.8.0] – 2026-03-27 · Finalise configs & documentation

### Added
- `AuditConfig.java` – Spring Data JPA entity auditing configuration
- `RedisTemplateConfig.java` – Redis caching template configuration
- `README.md` – comprehensive project documentation (features, API endpoints, architecture)

**Commit:** `e957de9` · Author: Danial Lakhani · 2026-03-27 16:53 +05:30

---

## [0.7.0] – 2026-03-27 · Stripe Payment Gateway & webhooks

### Added
- `PaymentController.java` – REST endpoints for creating payment links and handling webhooks
- `PaymentRequestDTO.java` – DTO for payment requests
- `PaymentService.java` – payment service interface
- `StripePaymentGatewayImplementation.java` – Stripe SDK integration with callback support

**Commit:** `717cad7` · Author: Danial Lakhani · 2026-03-27 13:17 +05:30

---

## [0.6.0] – 2026-03-27 · Custom exception handling & controller advice

### Added
- `ControllerAdvice.java` – global exception handler (`@RestControllerAdvice`)
- `ErrorDTO.java` – standardised error response DTO
- `ProductNotFoundException.java` – domain exception for missing products
- `CategoryNotFoundException.java` – domain exception for missing categories

**Commit:** `2569280` · Author: Danial Lakhani · 2026-03-27 09:34 +05:30

---

## [0.5.0] – 2026-03-26 · REST API layer for Products & Categories

### Added
- `ProductController.java` – full CRUD REST API for products with pagination support
- `CategoryController.java` – REST API for category management

**Commit:** `ce7bdbe` · Author: Danial Lakhani · 2026-03-26 15:42 +05:30

---

## [0.4.0] – 2026-03-26 · Core business logic (service layer)

### Added
- `ProductService.java` – product service interface
- `FakeStoreProductService.java` – FakeStore API integration for product data
- `SelfProductService.java` – self-hosted product service implementation
- `SelfCategoryService.java` – self-hosted category service implementation
- `FakeStoreCategoryService.java`, `FakeStoreCategoryDTO.java`, `FakeStoreProductDTO.java` – FakeStore DTOs and category service

**Commit:** `7601ee4` · Author: Danial Lakhani · 2026-03-26 10:18 +05:30

---

## [0.3.0] – 2026-03-25 · Spring Data repositories

### Added
- `ProductRepository.java` – JPA repository with custom queries for products
- `CategoryRepository.java` – JPA repository for categories
- `ProductProjection.java` – repository projection interface

**Commit:** `20140dc` · Author: Danial Lakhani · 2026-03-25 17:12 +05:30

---

## [0.2.0] – 2026-03-25 · Database setup & JPA models

### Added
- `BaseModel.java` – audited base entity (`@MappedSuperclass`) with `createdAt`/`updatedAt`
- `Product.java` – product JPA entity
- `Category.java` – category JPA entity
- `application.properties` – datasource, Redis, and Flyway configuration
- `V1__initial_schema.sql` – initial Flyway database migration script

**Commit:** `cc45177` · Author: Danial Lakhani · 2026-03-25 14:48 +05:30

---

## [0.1.0] – 2026-03-25 · Initial Spring Boot project scaffold

### Added
- Spring Boot project initialised with Maven Wrapper (`mvnw`, `mvnw.cmd`)
- `pom.xml` – project dependencies (Spring Web, JPA, Flyway, Redis, Stripe, etc.)
- `BackendProjectApplication.java` – application entry point
- `.gitignore` – standard Java/Maven ignore rules

**Commit:** `c65a4fc` · Author: Danial Lakhani · 2026-03-25 11:24 +05:30

---

## Commit History Summary

| # | SHA       | Date                  | Author         | Message                                                  |
|---|-----------|------------------------|----------------|----------------------------------------------------------|
| 9 | `9273550` | 2026-03-28 09:41 +05:30 | Danial Lakhani | Minor refactoring and cleanup                            |
| 8 | `e957de9` | 2026-03-27 16:53 +05:30 | Danial Lakhani | Finalize application configs and project documentation   |
| 7 | `717cad7` | 2026-03-27 13:17 +05:30 | Danial Lakhani | Integrate Stripe Payment Gateway and webhook endpoints   |
| 6 | `2569280` | 2026-03-27 09:34 +05:30 | Danial Lakhani | Add custom exception handling and global controller advice|
| 5 | `ce7bdbe` | 2026-03-26 15:42 +05:30 | Danial Lakhani | Expose REST APIs for Products and Categories             |
| 4 | `7601ee4` | 2026-03-26 10:18 +05:30 | Danial Lakhani | Implement core business logic for Product and Category services |
| 3 | `20140dc` | 2026-03-25 17:12 +05:30 | Danial Lakhani | Add Spring Data Repositories for Product and Category    |
| 2 | `cc45177` | 2026-03-25 14:48 +05:30 | Danial Lakhani | Set up database connections and base JPA models          |
| 1 | `c65a4fc` | 2026-03-25 11:24 +05:30 | Danial Lakhani | Initial project setup with Spring Boot structure         |

All 9 commits were authored by **Danial Lakhani** (`daniallakhani7@gmail.com`).
The project was built incrementally over four days, demonstrating organic development progression.
