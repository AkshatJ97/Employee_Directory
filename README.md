# Employee Directory

**Employee Directory** is a web-based application built with Spring Boot, Thymeleaf, and MySQL that allows users to manage a list of employees. Users can view, add, update, and delete employee records through a simple and responsive web interface.

---

## What the Project Does

This project serves as an **employee management system** with CRUD (Create, Read, Update, Delete) functionality:
- **List all employees** in a sortable table.
- **Add a new employee** via a web form.
- **Update existing employee details**.
- **Delete employees** from the directory.

---

## How It Works (Main Logic)

The core logic follows the **Spring MVC pattern** integrated with Thymeleaf for server-side rendering:
- **Controllers** handle HTTP requests for listing, creating, updating, and deleting employees.
- **Service Layer** abstracts business logic and interacts with the data access layer.
- **Spring Data JPA** manages database interactions using the `EmployeeRepository`, which interfaces with a MySQL database.
- **Thymeleaf templates** render dynamic HTML pages for user interaction.

**Key Flow:**
1. User accesses `/employees/list` to view all employees.
2. Add or update forms are served at `/employees/showFormForAdd` and `/employees/showFormForUpdate`.
3. Form submissions POST to `/employees/save`, which persists data via the service and repository layers.
4. Deletions are handled via `/employees/delete?employeeId={id}` with confirmation prompts.

---

## Project Structure

```plaintext
Employee_Directory/
├── src/
│   ├── main/
│   │   ├── java/com/springboot/thymeleafdemo/
│   │   │   ├── ThymeleafdemoApplication.java   # Main Spring Boot entry point
│   │   │   ├── controller/
│   │   │   │   ├── DemoController.java         # "Hello World" demo endpoint
│   │   │   │   └── EmployeeController.java     # Handles employee CRUD requests
│   │   │   ├── entity/
│   │   │   │   └── Employee.java               # Employee JPA entity
│   │   │   ├── dao/
│   │   │   │   └── EmployeeRepository.java     # Spring Data JPA repository
│   │   │   ├── service/
│   │   │   │   ├── EmployeeService.java        # Service interface
│   │   │   │   └── EmployeeServiceImpl.java    # Service implementation
│   │   ├── resources/
│   │   │   ├── application.properties          # DB connection settings
│   │   │   ├── static/index.html               # Redirects to /employees/list
│   │   │   └── templates/
│   │   │       ├── employees/
│   │   │       │   ├── employee-form.html      # Form for add/update employee
│   │   │       │   └── list-employees.html     # List view for all employees
│   │   │       └── helloworld.html             # Demo template
├── pom.xml                                    # Maven build and dependencies
└── README.md                                  # Project overview and instructions
```

---

## Tech Stack

- **Java 17+**
- **Spring Boot 3**
- **Spring MVC & Thymeleaf** for web and view rendering
- **Spring Data JPA** for ORM and database operations
- **MySQL** for persistent storage
- **Maven** for build and dependency management
- **Bootstrap** for UI styling (via CDN)
- **JUnit 5** for testing

---

## Usage Instructions

### Prerequisites

- **Java 17** or higher
- **Maven 3.6+**
- **MySQL database** running locally (or update `application.properties` for your environment)

### Setup

1. **Clone the repository:**
   ```sh
   git clone <repo-url>
   cd Employee_Directory
   ```

2. **Configure the database:**
   - Create a database named `employee_directory`.
   - Update `src/main/resources/application.properties` with your MySQL username and password.

   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/employee_directory
   spring.datasource.username=YOUR_USERNAME
   spring.datasource.password=YOUR_PASSWORD
   ```

3. **Build and run the application:**
   ```sh
   mvn spring-boot:run
   ```

4. **Access the application:**
   - Open [http://localhost:8080/](http://localhost:8080/) in your browser.
   - You will be redirected to `/employees/list` where you can view and manage employees.

---

## Main Features

- **List employees**: See all employees, sorted by last name.
- **Add employees**: Fill a web form to add new entries.
- **Edit employee**: Update employee information via pre-populated form.
- **Delete employee**: Remove any employee after confirmation.
- **Responsive UI**: Clean, mobile-friendly interface using Bootstrap.
- **MVC Best Practices**: Clear separation of concerns.

---

