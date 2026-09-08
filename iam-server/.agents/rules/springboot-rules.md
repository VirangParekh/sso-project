---
trigger: manual
---

# Spring Boot Server Rules

## Coding Instructions
- Language Stack: Modern Java (Java 21+ features like Records, Virtual Threads, and Pattern Matching), Spring Boot 3.x, Gradle (Kotlin DSL).
- Architecture: Hexagonal / Ports & Adapters architecture. The Core Domain layer must have zero dependencies on `org.springframework.*` or database drivers.
- Dependencies: Use pure constructor injection. Ban `@Autowired` annotations entirely.
- Data Flow: Enforce rigid boundaries using separate JPA Entities, Domain Objects, and REST/GraphQL DTOs. Provide explicit mapper utilities.

## TDD & Testing Rules
- Red-Green-Refactor: When writing a backend feature, generate the test suite FIRST.
- Architecture Testing: Always include `ArchUnit` rules to programmatically enforce that infrastructure packages cannot import domain packages.
- Test Stack: Use JUnit 5, AssertJ, and Mockito. Implement slicing with `@WebMvcTest` and `@DataJpaTest` instead of spinning up heavy `@SpringBootTest` environments unless doing end-to-end integration tests.

## Response Style & Output Optimization
- Format: Present database schema/migration scripts first, followed by Unit Tests, Domain Interfaces, and finally implementation code.
- Strict Anti-Truncation: Do not abbreviate Spring configuration classes, controller mappings, or complex database queries with comments like `// TODO: implement logic`. Generate production-ready, compileable boilerplate.
