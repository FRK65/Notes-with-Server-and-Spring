# Types of files used in java spring boot projects
Java Spring Boot projects typically involve a variety of file types that serve different purposes. Here's an overview of the main types:

# 1. Source Files

**Java Files (.java)**: These files contain the source code of the application. 
They define classes, interfaces, and methods that make up the application's functionality.
~~~
Example:
src/main/java/com/example/demo/DemoApplication.java
~~~

# 2.1 Configuration Files

**Application Properties/YAML (.properties / .yaml):** 
Configuration settings for the Spring Boot application.
~~~
Example: 
src/main/resources/application.properties 
or
src/main/resources/application.yml
~~~

**Log Configuration (logback.xml, log4j2.xml):** 
Settings for logging frameworks used in the project.
~~~
Example: 
src/main/resources/logback.xml
~~~

# 3.1 Resource Files

**Static Files (.html, .css, .js):** 
Front-end files served by the application, such as HTML, CSS, and JavaScript files.
~~~
Example: 
src/main/resources/static/index.html
~~~

**Template Files (.html, .ftl, .jsp):** 
Templates for generating dynamic content, typically used with Thymeleaf, Freemarker, or JSP.
~~~
Example: 
src/main/resources/templates/home.html
~~~

# 3.4 Dependency Management Files

**Maven (pom.xml):** Defines project dependencies, plugins, and other 
configurations for projects using Maven as a build tool.
~~~
Example: pom.xml
~~~

**Gradle (build.gradle):** 
Defines project dependencies, plugins, and other configurations for projects 
using Gradle as a build tool.
~~~
Example: build.gradle
~~~

# 4. Test Files
**Test Java Files (.java):** Source files for unit tests and integration tests.
~~~
Example: 
src/test/java/com/example/demo/DemoApplicationTests.java
~~~

# 5. Meta-Inf Files

**Manifest Files (MANIFEST.MF):** 
Metadata about the project, including version information and main class for executable JARs.
~~~
Example: src/main/resources/META-INF/MANIFEST.MF
~~~

# 6. Security Files

**KeyStore/TrustStore Files (.jks, .p12):** 
Used for SSL/TLS configurations.

~~~
Example: src/main/resources/keystore.jks
~~~
# 7. Docker and Cloud Configuration Files

**Dockerfiles (Dockerfile):** Defines the instructions to build a Docker image for the application.
~~~
Example: Dockerfile
~~~
**Kubernetes YAML Files (.yaml):** Configuration files for deploying the application to Kubernetes.
~~~
Example: deployment.yaml
~~~


# HTTP methods used in web APIs for different types of operations.

| Method | Purpose             | Idempotent | Safe | Example            |
|--------|---------------------|------------|------|--------------------|
| GET    | Retrieve data       | Yes        | Yes  | GET /users/123     |
| POST   | Create new resource | No         | No   | POST /users        |
| PUT    | Update or create    | Yes        | No   | PUT /users/123     |
| DELETE | Delete a resource   | Yes        | No   | DELETE /users/123  |
| PATCH  | Partially update    | Yes        | No   | PATCH /users/123   |


