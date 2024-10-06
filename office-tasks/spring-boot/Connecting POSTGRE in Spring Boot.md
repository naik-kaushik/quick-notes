## **To use Postgres, you need to:**

1. Add dependencies to your build tool.
2. Create a new Postgres database with `psql`.
3. Connect Spring Boot to your Postgres database.
4. Create a Java entity with Hibernate.
5. Create a repository with Spring Data JPA.
6. Create a controller that uses your repository.

### 1.  Add dependencies to your build tool

There are two dependencies to be added:
1. Spring Boot Starter Data JPA
2. PostgreSQL JDBC Driver

The method to add these dependencies differ based on what build tool you are using.

#### 1. Gradle

add following lines to your `build.gradle`

```gradle
dependencies { 
// ... 
implementation 'org.springframework.boot:spring-boot-starter-data-jpa' 
implementation 'org.postgresql:postgresql' 
}
```

#### 2. Maven

add following to your `pom.xml`

```xml
<dependencies>
  <dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-jpa</artifactId>
  </dependency>
  <dependency>
    <groupId>org.postgresql</groupId>
    <artifactId>postgresql</artifactId>
  </dependency>
</dependencies>
```


### 2. Create A New Postgres Database With `psql`

