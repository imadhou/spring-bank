# Bank Simulation System  

## **Overview**  
This project is a **Spring-based Bank Simulation System** that models banking operations, including customer service, cashier management, and client satisfaction tracking. The system allows users to configure simulations and view real-time results through a web interface.  

### **Key Technologies**  
- **Spring Framework** (Dependency Injection, AOP, Transaction Management)  
- **Hibernate (JPA)** for ORM-based database interaction  
- **JDBC** for raw SQL queries  
- **JSF + PrimeFaces** for the frontend UI  
- **MySQL** for database storage  
- **Apache Tomcat** as the web server  

---

## **Architecture**  

The project follows a **layered architecture**, ensuring modularity and scalability:  

1. **Presentation Layer (JSF + PrimeFaces)**  
   - Handles user interactions through a web-based UI.  
   - Uses **Managed Beans** (`@ManagedBean` or `@Controller`) to communicate with the business logic.  

2. **Business Layer (Spring Services)**  
   - Contains the core logic for simulation processes.  
   - Uses **Spring Services (`@Service`)** for business rules and simulation management.  

3. **Data Access Layer (Spring + Hibernate/JDBC)**  
   - Uses **Spring Data JPA + Hibernate** for ORM.  
   - Implements the **DAO (Data Access Object) pattern** to separate persistence logic.  

4. **Database Layer (MySQL)**  
   - Stores simulation configurations and results in a relational database.  

---

## **Design Patterns Used**  

### **1. Singleton Pattern**  
- Used in **Spring Beans**, ensuring only one instance of each service is created and managed by the Spring IoC container.  

### **2. Factory Pattern**  
- Implemented through **Spring’s IoC Container**, which automatically creates and injects dependencies instead of manual instantiation.  

### **3. DAO (Data Access Object) Pattern**  
- Separates database logic from business logic, providing structured data access via repository classes.  

### **4. Observer Pattern**  
- Used for **real-time simulation tracking** where clients notify the system when served or leave due to impatience. Implemented using **Spring Events (`@EventListener`)**.  

### **5. MVC (Model-View-Controller) Pattern**  
- **Model:** Hibernate Entities (`Client`, `Cashier`, etc.).  
- **View:** JSF + PrimeFaces UI components.  
- **Controller:** Managed Beans (`@ManagedBean` or `@RestController`).  

### **6. Strategy Pattern**  
- Allows dynamic selection of **different simulation algorithms** by defining multiple strategies (e.g., basic vs. advanced simulation models).  

### **7. Template Method Pattern**  
- Defines the **general process of a simulation**, allowing variations in specific steps while maintaining a common structure.  

### **8. Dependency Injection Pattern**  
- Used throughout **Spring Framework**, where dependencies are injected rather than instantiated manually.  

### **9. Proxy Pattern**  
- Utilized in **Hibernate lazy-loading**, deferring object loading until required, improving performance.  

### **10. Command Pattern**  
- Encapsulates user actions (e.g., starting or stopping a simulation) as command objects for better flexibility.  

### **11. Builder Pattern**  
- Used for constructing **complex simulation configurations** in a readable and scalable way.  

---
