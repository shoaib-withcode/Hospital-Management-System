# Hospital Management System

A desktop Hospital Management System built with **Java Swing**, **Java 17**, **Maven**, and **MySQL**. This project is intended for college learning and demonstration.

## Features

- Role-based login for Admin, Receptionist, and Viewer
- Add and view patient records
- View doctor details
- Book appointments
- Prevent booking the same doctor on the same date
- View a patient's appointment history
- Allow only Admin users to remove patients

## Technologies Used

- Java 17+
- Java Swing (desktop interface)
- MySQL
- JDBC / MySQL Connector/J
- Apache Maven

## Requirements

Before running the project, install:

1. **JDK 17 or newer**
2. **Apache Maven**, available in your system `PATH`
3. **MySQL Server** and MySQL Workbench (or another MySQL client)

## Setup and Run on Windows

### 1. Extract the project

Extract the ZIP file and open the `HospitalManagementSystem_Simple` folder.

### 2. Create the database

1. Start MySQL Server.
2. Open MySQL Workbench.
3. Open `database/schema.sql` from the project.
4. Execute the complete script.

The script creates the `hospital` database and its tables, and inserts demo users and doctors. **If you already have important data in a database named `hospital`, back it up before running SQL scripts.**

### 3. Start the application

Double-click **`RUN_PROJECT.bat`**.

If the batch file asks for your MySQL password, enter the password for the MySQL `root` account. The application expects MySQL to be running locally at:

`jdbc:mysql://localhost:3306/hospital`

If your MySQL username or password is different, configure the environment variables `HMS_DB_URL`, `HMS_DB_USER`, and `HMS_DB_PASSWORD` before starting the app.

### Alternative: Run with Maven

Open PowerShell in the project folder and run:

```powershell
$env:HMS_DB_URL="jdbc:mysql://localhost:3306/hospital"
$env:HMS_DB_USER="root"
$env:HMS_DB_PASSWORD="YOUR_MYSQL_PASSWORD"
mvn clean compile exec:java
```

Replace `YOUR_MYSQL_PASSWORD` with your own MySQL password. Do not publish it or commit it to GitHub.

## Demo Login Accounts

| Role | Username | Password |
|---|---|---|
| Admin | `admin` | `admin123` |
| Receptionist | `reception` | `reception123` |
| Viewer | `viewer` | `viewer123` |

These are demo credentials for local testing only. Change or remove them before any real deployment.

## Project Structure

```text
HospitalManagementSystem_Simple/
├── database/
│   └── schema.sql
├── src/main/java/com/ims/hms/
│   ├── Database.java
│   └── HospitalManagementSystemGUI.java
├── pom.xml
├── RUN_PROJECT.bat
└── README.md
```

## Troubleshooting

- **Database connection failed:** Make sure MySQL Server is running and the database script has been executed.
- **Access denied for user:** Check `HMS_DB_USER` and `HMS_DB_PASSWORD`.
- **`mvn` is not recognized:** Install Maven and add its `bin` folder to your system `PATH`.
- **Java version error:** Check that JDK 17 or newer is installed using `java -version`.

## Disclaimer

This is an educational college project. Do not use it to store real patient information or rely on its demo accounts for production use.
