# 👔 Employee Management System

A GUI-based **Employee Management System** built with **Java**, using **JFrame** and **AWT** for the graphical interface. This application provides full CRUD (Create, Read, Update, Delete) functionality for managing employee records through an interactive desktop UI.

---

## 📋 Table of Contents

- [About the Project](#about-the-project)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running the Application](#running-the-application)
- [Screenshots](#screenshots)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

---

## 📌 About the Project

The **Employee Management System** is a Java desktop application that allows organizations to manage employee data through a user-friendly graphical interface. Built using **Java Swing (JFrame)** and **AWT**, it provides interactive forms, tables, and buttons to perform all employee management operations without needing a command-line interface.

---

## ✨ Features

- ➕ Add new employee records via GUI form
- 📄 View all employees in a structured table (JTable)
- 🔍 Search employee by ID or name
- ✏️ Update employee details through editable fields
- 🗑️ Delete employee records with confirmation dialog
- 🖥️ Fully interactive desktop window using JFrame & AWT
- 📊 Organized layout using panels, labels, and buttons
- ⚠️ Input validation with error dialog popups

---

## 🛠️ Technologies Used

| Technology        | Purpose                              |
|-------------------|--------------------------------------|
| **Java** (JDK 8+) | Core programming language            |
| **Java Swing**    | GUI components (JFrame, JPanel, etc.)|
| **Java AWT**      | Event handling, layouts, graphics    |
| **OOP Concepts**  | Encapsulation, Inheritance           |
| **Collections**   | ArrayList, HashMap for data handling |
| **File I/O / JDBC**| Data persistence                    |
| **MySQL** *(optional)* | Backend database storage        |

---

## 📁 Project Structure

EmployeeManagementSystem/
│
├── src/
│   └── employee/
│       └── management/
│           └── system/
│               ├── Splash.java            ← Entry point — animated splash screen
│               ├── Login.java             ← Login screen with username & password
│               ├── Main_class.java        ← Main dashboard with navigation buttons
│               ├── AddEmployee.java       ← Form to add a new employee
│               ├── View_Employee.java     ← Table view with search, update & print
│               ├── UpdateEmployee.java    ← Update existing employee details
│               ├── RemoveEmployee.java    ← Remove employee by ID
│               └── conn.java             ← MySQL JDBC connection handler
│
├── icons/
│   ├── front.gif       ← Splash screen animation
│   ├── bjn.jpg         ← Login background
│   ├── second.jpg      ← Login side image
│   ├── log1.jpg        ← Main dashboard background
│   ├── delete.png      ← Remove screen icon
│   └── remove.jpg      ← Remove screen background
│
├── README.md
└── .gitignore

-------

## 🗄️ Database Setup

1. Open **MySQL** and create the database:

```sql
CREATE DATABASE employeemanagement;
USE employeemanagement;
```

2. Create the **employee** table:

```sql
CREATE TABLE employee (
    name        VARCHAR(100),
    fname       VARCHAR(100),
    dob         VARCHAR(50),
    salary      VARCHAR(50),
    address     VARCHAR(200),
    phone       VARCHAR(15),
    email       VARCHAR(100),
    education   VARCHAR(50),
    designation VARCHAR(100),
    addhar      VARCHAR(20),
    empId       VARCHAR(10) PRIMARY KEY
);
```

3. Create the **login** table:

```sql
CREATE TABLE login (
    username VARCHAR(50),
    password VARCHAR(50)
);

-- Insert a default user
INSERT INTO login VALUES ('admin', 'admin123');
```

4. Update the database credentials in `conn.java` if needed:

```java
connection = DriverManager.getConnection(
    "jdbc:mysql://localhost:3306/employeemanagement", "root", "your_password"
);
```

---

## 🚀 Getting Started

### Prerequisites

- [Java JDK 8+](https://www.oracle.com/java/technologies/javase-downloads.html)
- [MySQL Server](https://www.mysql.com/)
- [MySQL Connector/J (JDBC Driver)](https://dev.mysql.com/downloads/connector/j/)
- `jcalendar.jar` — for `JDateChooser`
- `rs2xml.jar` — for `DbUtils.resultSetToTableModel()`
- Any Java IDE — [IntelliJ IDEA](https://www.jetbrains.com/idea/), [Eclipse](https://www.eclipse.org/), or [NetBeans](https://netbeans.apache.org/)

### Installation

1. **Clone the repository:**
```bash
   git clone https://github.com/your-username/employee-management-system.git
```

2. **Open the project** in your IDE.

3. **Add required JAR files** to your project build path:
   - `mysql-connector-j-x.x.x.jar`
   - `jcalendar-1.4.jar`
   - `rs2xml.jar`

4. **Set up the database** using the SQL scripts in the [Database Setup](#database-setup) section.

5. **Place all images** in the `icons/` folder at the root of your classpath.

### Running the Application

Run `Splash.java` as the main class:

```bash
javac -cp .;libs/* src/employee/management/system/*.java
java  -cp .;libs/* employee.management.system.Splash
```

Or simply right-click `Splash.java` in your IDE → **Run as Java Application**.

---

## 🔄 Application Flow
Splash.java  (5 sec animated intro)
↓
Login.java   (enter username & password → validated from DB)
↓
Main_class.java  (dashboard with 3 buttons)
├──→ AddEmployee.java     (fill form → save to DB)
├──→ View_Employee.java   (JTable → search / print / update)
│         └──→ UpdateEmployee.java  (edit & save changes)
└──→ RemoveEmployee.java  (select ID → delete from DB)




## 🤝 Contributing

Contributions are welcome! Follow these steps:

1. Fork the project
2. Create your feature branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

> Made with ❤️ using Java, Swing, AWT & MySQL
