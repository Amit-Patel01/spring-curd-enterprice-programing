# Spring CRUD Operation Project

<p align="center">
  <img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExeTY1cWI1MHkybmJpbWthNGl6cTMycms4NHlpeW9ycmh0bmNidGs5YiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/scZPhLqaVOM1qG4lT9/giphy.gif" width="400"/>
</p>

This is an **Enterprise Programming project built using Spring Framework** that demonstrates basic **CRUD (Create, Read, Update, Delete)** operations with a database using **RESTful APIs**.

---

## 🚀 Features

- Create new records
- Read all records
- Update existing records
- Delete records
- REST API architecture
- Database integration

---

## 🛠 Tech Stack

- Java
- Spring Framework / Spring Boot
- Maven
- MySQL
- REST API
- Eclipse IDE

# ⚙️ Eclipse Me Spring CRUD Project Banane Ke Steps

## 1️⃣ Eclipse Open Kare

Open **Eclipse IDE for Enterprise Java Developers**

---

## 2️⃣ New Spring Project Banaye


File → New → Spring Starter Project


Fill details:


Name: spring-crud-project
Type: Maven
Packaging: Jar
Java Version: 17
Group: com.example
Artifact: crud


---

## 3️⃣ Dependencies Select Kare

Select these:


Spring Web
Spring Data JPA
MySQL Driver
Lombok (optional)
Spring Boot DevTools


Click **Finish**

---

## 4️⃣ Model Class Banaye


model → User.java


```java
@Entity
public class User {

@Id
@GeneratedValue(strategy = GenerationType.IDENTITY)
private Long id;

private String name;
private String email;

}
5️⃣ Repository Banaye
repository → UserRepository.java
@Repository
public interface UserRepository extends JpaRepository<User, Long> {

}
6️⃣ Service Layer
service → UserService.java
@Service
public class UserService {

@Autowired
private UserRepository repo;

public List<User> getAllUsers(){
return repo.findAll();
}

}
7️⃣ Controller Banaye
controller → UserController.java
@RestController
@RequestMapping("/users")
public class UserController {

@Autowired
private UserService service;

@GetMapping
public List<User> getUsers(){
return service.getAllUsers();
}

}
8️⃣ Database Configuration
application.properties
spring.datasource.url=jdbc:mysql://localhost:3306/testdb
spring.datasource.username=root
spring.datasource.password=1234

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
9️⃣ Project Run Kare
Right Click Project
Run As → Spring Boot App
🔗 API Example
GET http://localhost:8080/users
POST http://localhost:8080/users
PUT http://localhost:8080/users/{id}
DELETE http://localhost:8080/users/{id}
