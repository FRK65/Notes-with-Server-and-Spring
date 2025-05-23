
## 🔹 **Core Spring**

1. **What is Spring Framework?**

   * A lightweight open-source framework for developing Java applications, especially for building web apps and microservices.

2. **What are the main features of Spring?**

   * Inversion of Control (IoC)
   * Dependency Injection (DI)
   * Aspect-Oriented Programming (AOP)
   * Transaction Management
   * Modular Architecture

3. **What is Dependency Injection in Spring?**

   * It's a design pattern where objects are injected into a class rather than created within it.

4. **What are the types of Dependency Injection in Spring?**

   * Constructor Injection
   * Setter Injection
   * Field Injection (not recommended)

5. **What is a Spring Bean?**

   * Any object managed by the Spring IoC container.

6. **What is the Spring Bean lifecycle?**

   * Instantiate → Populate properties → `BeanNameAware` → `BeanFactoryAware` → `ApplicationContextAware` → `@PostConstruct` → `InitializingBean` → Custom init-method → Use → `@PreDestroy` → `DisposableBean` → Custom destroy-method

---

## 🔹 **Spring Annotations**

7. **What is `@Component` vs `@Bean`?**

   * `@Component`: Marks a class as a Spring-managed component (auto-detected via component scanning).
   * `@Bean`: Declares a bean explicitly in a `@Configuration` class.

8. **What are `@Autowired`, `@Qualifier`, and `@Primary`?**

   * `@Autowired`: Injects bean automatically.
   * `@Qualifier`: Helps resolve ambiguity when multiple beans of the same type exist.
   * `@Primary`: Marks a bean as default when multiple candidates are available.

---

## 🔹 **Spring Boot**

9. **What is Spring Boot?**

   * A Spring module that simplifies the setup of new Spring applications using auto-configuration, embedded servers, and starter dependencies.

10. **What is Spring Boot Starter?**

    * A set of convenient dependency descriptors you can include in your application.

11. **What is `application.properties` or `application.yml`?**

    * Used for externalizing configuration in Spring Boot applications.

12. **What is Spring Boot auto-configuration?**

    * Automatically configures your application based on the libraries on the classpath.

13. **How do you disable a specific auto-configuration class?**

    * Use `@EnableAutoConfiguration(exclude = {ClassName.class})` or `spring.autoconfigure.exclude` in properties.

---

## 🔹 **Spring MVC**

14. **What is DispatcherServlet?**

    * The front controller in Spring MVC that handles all HTTP requests and dispatches them to appropriate handlers.

15. **What are `@Controller` and `@RestController`?**

    * `@Controller`: Returns views.
    * `@RestController`: Returns JSON/XML directly (combines `@Controller` + `@ResponseBody`).

16. **What is `@RequestMapping`, `@GetMapping`, `@PostMapping`?**

    * Used to map HTTP requests to handler methods.

17. **How does Spring MVC handle exceptions?**

    * Using `@ExceptionHandler`, `@ControllerAdvice`, or `ResponseStatusException`.

---

## 🔹 **Spring Data / JPA**

18. **What is Spring Data JPA?**

    * A part of Spring Data project to simplify JPA-based repository development.

19. **What is `CrudRepository` and `JpaRepository`?**

    * Interfaces that provide basic CRUD and JPA-related operations for an entity.

20. **What is the difference between `@Entity` and `@Table`?**

    * `@Entity`: Marks a class as a JPA entity.
    * `@Table`: Maps the entity to a specific table name.

21. **What are lazy and eager loading?**

    * Lazy: Fetch only when accessed.
    * Eager: Fetch immediately with parent entity.

22. **What is `@Transactional` and when is it used?**

    * Manages transaction boundaries in a declarative way.

---

## 🔹 **Advanced / Practical**

23. **How do you secure a Spring Boot application?**

    * Use Spring Security with annotations like `@EnableWebSecurity`, `@PreAuthorize`.

24. **What is Spring AOP?**

    * Aspect-Oriented Programming: Separates cross-cutting concerns like logging, transactions.

25. **What is the use of `@Configuration` and `@EnableAutoConfiguration`?**

    * `@Configuration`: Marks class as source of bean definitions.
    * `@EnableAutoConfiguration`: Tells Spring Boot to guess and configure beans automatically.

---
