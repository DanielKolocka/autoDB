# WA4E Assignment: Automobiles, Sessions, and POST-Redirect

A PHP-based web application to track automobile data using a MySQL database. This project implements the **POST-Redirect-GET-Flash** pattern to manage user sessions and data validation.

## Features
- **Session Management:** Uses PHP `$_SESSION` to track logged-in users and pass "Flash" messages.
- **POST-Redirect-GET:** Prevents double-submission by redirecting after every POST request.
- **Security:**
  - **SQL Injection Protection:** Uses PDO prepared statements.
- **Data Validation:** - Login requires a valid email (must contain `@`).
  - Automobile "Year" and "Mileage" must be numeric.
  - "Make" is a required field.

## Project Structure
- `index.php`: The landing page for the application.
- `login.php`: Handles user authentication and error logging.
- `view.php`: Displays the list of automobiles stored in the database.
- `add.php`: Provides a form to add new automobile records.
- `logout.php`: Destroys the session and redirects to index.
- `pdo.php`: Contains the database connection logic.

## Database Setup
This project requires a table named `autos` in a MySQL database.
```sql
CREATE TABLE autos (
  auto_id INT UNSIGNED NOT NULL AUTO_INCREMENT KEY,
  make VARCHAR(128),
  year INT,
  mileage INT
);
