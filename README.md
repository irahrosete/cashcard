# Spring Cash Card
Spring Academy <br>
### [Building a REST API with Spring Boot](https://spring.academy/courses/building-a-rest-api-with-spring-boot)

### Module 1: 
- Spring vs Spring Boot
- Inversion of Control and Dependency Injection
- API Contracts & JSON
- The Testing Pyramid
  - unit tests
  - integration tests
  - E2E tests
- Test-Driven Development (Red, Green, Refactor Loop)
  - JUnit
  - AssertJ
- REST: Representational State Transfer
  - a way to manage the state (value) of resource representations (objects)
  - CRUD
  - HTTP
- Spring Bean, Annotations and Component Scan
  - One of the main things Spring does is to configure and instantiate objects. These objects are called Spring Beans, and are usually created by Spring (as opposed to using the Java new keyword).

| Operation | API Endpoint    | HTTP Method | Response Status |
|-----------|-----------------|-------------|-----------------|
| Create    | /cashcards      | POST        | 201 (CREATED)   |
| Read      | /cashcards/{id} | GET         | 200 (OK)        |
| Update    | /cashcards/{id} | PUT         | 204 (NO DATA)   |
| Delete    | /cashcards/{id} | DELETE      | 204 (NO DATA)   |

- Repositories & Spring Data
  - JBDC
    - ORM: object-relational mapping
  - H2

### Module 2:
- Idempotent
  - results in the same outcome if performed more than once
- HTTP response for `201 CREATED` must contain the header `location` containing the URI of the created resource
  - Location=/cashcards/42
- 