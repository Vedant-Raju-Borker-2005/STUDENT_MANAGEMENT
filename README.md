# Java Student Management System

A desktop Student Management application built with JavaFX and MySQL.

This project includes:
- Login screen
- Student dashboard with table view
- Add, update, and delete student records
- Search/filter students by name, email, or course
- Logout flow back to the login screen

## Project Structure

- `src/Main.java` - JavaFX entry point; opens login screen
- `src/LoginController.java` - handles login and dashboard navigation
- `src/DashboardController.java` - handles student CRUD, search, and logout
- `src/DataStore.java` - JDBC database operations (users + students)
- `src/Student.java` - student model class
- `src/login.fxml` - login UI
- `src/dashboard.fxml` - dashboard UI
- `database.sql` - database and table creation script

## Tech Stack

- Java 17+
- JavaFX 17
- MySQL
- JDBC (MySQL Connector/J)

## Prerequisites

Before running the project, install:
- JDK 17 or later
- JavaFX SDK 17 (or compatible)
- MySQL Server
- MySQL Connector/J JAR (jdbc driver)
- An IDE (recommended): IntelliJ IDEA / Eclipse / NetBeans

## Database Setup

1. Open MySQL and run the SQL script from `database.sql`.
2. Insert at least one user record (required for login):

```sql
INSERT INTO users (username, password) VALUES ('admin', 'admin123');
```

3. Verify the database name is `studentdb`.

## Configure DB Credentials

Open `src/DataStore.java` and check these values:

```java
private static final String URL = "jdbc:mysql://localhost:3306/studentdb";
private static final String USER = "root";
private static final String PASSWORD = "Swayam@123";
```

Update `USER` and `PASSWORD` to match your local MySQL setup.

## Add External Libraries

Add these to your project classpath/module path:
- JavaFX libraries
- MySQL Connector/J JAR

If your IDE asks for VM options for JavaFX, use:

```bash
--module-path "<path-to-javafx-lib>" --add-modules javafx.controls,javafx.fxml
```

## Run the Application

1. Import/open the folder in your Java IDE.
2. Ensure JavaFX and MySQL connector dependencies are configured.
3. Run `Main.java`.
4. Log in using a user from the `users` table.

## Usage

After login:
- Add a student using Name, Email, Course fields
- Select a table row, edit fields, then click Update Student
- Select a row and click Delete Student
- Use the search box to filter records live
- Click Logout to return to login screen

## Notes

- Passwords are stored as plain text in the current implementation.
- The DB password is hardcoded in code and should be externalized for production use.
- Add validation (email format, duplicate checks, etc.) if extending this project.

## Future Improvements

- Hash passwords (BCrypt/Argon2)
- Move DB credentials to environment variables or config files
- Add input validation and user feedback messages
- Add unit tests for database and controller logic
- Add role-based users (admin/staff)

XYZ
