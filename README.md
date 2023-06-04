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
- Pagination and Sorting
  - Page
  - Pageable
  - PageAndSortingRepository
- [JsonPath](https://github.com/json-path/JsonPath)
- Security
  - Spring Security implements authentication in the Filter Chain
  - Spring Security provides authorisation via Role-Based Access Control
  - Same Origin Policy (SOP)
    - Cross-Origin Request Sharing (CORS) @CrossOrigin
  - Common web exploits:
    - Cross-Site Request Forgery (CSRF) "sea-surf"
    - Cross-Site Scripting (XSS)

## Module 3:
- POST, PUT, PATCH

  | HTTP Method | Operation | Definition                       | Response Code    | Response Body        | What does it do?                                                                  |
  |-------------|-----------|----------------------------------|------------------|----------------------|-----------------------------------------------------------------------------------|
  | POST        | Create    | Server generates and returns URI | 201 (CREATED)    | The created resource | Creates a sub-resource ("under" or "within" the passed URI)                       | 
  | PUT         | Create    | Client supplies URI              | 201 (CREATED)    | The created resource | Creates a resource (at the Request URI)                                           |
  | PUT         | Update    | Client supplies URI              | 204 (NO CONTENT) | (empty)              | Replaces the resource: The entire record is replaced by the object in the Request |
  | PATCH       | Update    | Client supplies URI              | 200 (OK)         | The updated resource | Partial Update: modify only fields included in the request on the existing record |

- DELETE
  - Soft delete, hard delete