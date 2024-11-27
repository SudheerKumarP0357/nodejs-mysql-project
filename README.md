# NodeJS & MySQL Project
## Setup Instructions

### 1. Setting Up MySQL Server

First, you need to set up a MySQL server on your local machine.

1. **Update the package index:**

   ```bash
   sudo apt update
   ```

2. **Install the MySQL server:**

   ```bash
   sudo apt install mysql-server
   ```

3. **Log in to the MySQL shell as root:**

   ```bash
   sudo mysql -u root
   ```

4. **Set a password for the root user and update the authentication method:**

   ```sql
   ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
   FLUSH PRIVILEGES;
   ```

   Replace `'password'` with a secure password of your choice.

5. **Exit the MySQL shell:**

   ```sql
   exit;
   ```

6. **Log in to the MySQL shell again with the new password:**

   ```bash
   sudo mysql -u root -p
   ```

   Enter the password you set in the previous step.

7. **Create a new database:**

   ```sql
   CREATE DATABASE test_db;
   ```

8. **Switch to the new database:**

   ```sql
   USE test_db;
   ```

9. **Create the `users` table:**

   ```sql
   CREATE TABLE users (
       id INT AUTO_INCREMENT PRIMARY KEY,
       name VARCHAR(255) NOT NULL,
       email VARCHAR(255) NOT NULL UNIQUE,
       role ENUM('Admin', 'User') NOT NULL
   );
   ```

   This table will store user information, including their name, email, and role.

### 2. Configuring and Running the Client
Clone the project into your local machine.
```bash
git clone https://github.com/SudheerKumarP0357/nodejs-mysql-project.git
```

The client side of the application is built using modern JavaScript, HTML, and CSS. To configure and run the client:

1. **Navigate to the client folder:**

   ```bash
   cd client
   ```

2. **Install the required dependencies:**

   ```bash
   npm install
   ```

3. **Build the client application:**

   ```bash
   npm run build
   ```

   This will create a production build of the client application, which will be served by the Express server.

### 3. Configuring and Running the Server

The server side is built using Node.js and Express and connects to the MySQL database to manage user data.

1. **Navigate to the server folder:**

   ```bash
   cd server
   ```

2. **Install the required dependencies:**

   ```bash
   npm install
   ```

3. **Start the server:**

   ```bash
   npm start
   ```

   The server will run on `http://localhost:5000` by default.

## Usage

After following the setup instructions, you can access the application by navigating to `http://localhost:5000` in your web browser.

