# Doubts And Solutions Related to `WordPress` and `XAMPP` :

## Question 1

**i have installed and setup 'mysql server' seperatly on my windows machine with user id 'root' and password 'hameed48' and it's working properly but when i stop my seperatly installed 'mysql server' and start my 'mysql server' from the XAMPP software and try to login with the same user id and password then i am getting this error:** `ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: YES) , how can i fix this ?`

## 👉 Soultion:

This happens because the MySQL server in XAMPP uses a different authentication system and may not recognize the credentials from your separately installed MySQL. Try these solutions:

### 1. Use No Password:

```bash
mysql -u root
```

XAMPP's MySQL often has an empty root password by default.

### 2. Reset Root Password for XAMPP MySQL:

- Stop MySQL from XAMPP.
- Open `xampp/mysql/bin/my.ini` and add:

  ```sql
  skip-grant-tables
  ```

- Restart MySQL, login without a password, then reset it

  ```sql
  UPDATE mysql.user SET authentication_string=PASSWORD('hameed48') WHERE User='root';
  FLUSH PRIVILEGES;
  ```

- Remove skip-grant-tables and restart MySQL

### 3. Use the Correct MySQL Port:

Your separate MySQL might use 3306, while XAMPP's MySQL may use 3307. Try:

```bash
mysql -u root -p -P 3307
```

---

## Question 2

**suppose if i create a databsae for my 'WordPress website' form XAMPP softwar's 'mySQL server' and if i turn of 'mySQL sever' of XAMPP software and turn on my seperatly installed 'mySQL server, so will i still be able to access my wordpress website?**

## 👉 Solution 2:

No, your WordPress website will not work if you switch between MySQL servers because:

### 1. Different Data Directories:

- XAMPP's MySQL stores databases in `xampp/mysql/data/`.

- Your separately installed MySQL uses a different directory ( e.g., `C:\ProgramData\MySQL\MySQL Server X.X\Data\` ).

- When you switch servers, the new MySQL instance won't have the WordPress database.

### 2. Different User Permissions & Configurations:

- Each MySQL server has its own user accounts and privileges.

- Your separate MySQL may not have the same root user with access to the WordPress database.

## How to Make It Work on Both Servers?

### Option 1: Export & Import Database

- Export the WordPress database from XAMPP using phpMyAdmin or - mysqldump.

- Import it into your separate MySQL server.

### Option 2: Use the Same Data Directory

- Change XAMPP’s MySQL to use the same data folder as your separate MySQL server ( not recommended due to potential conflicts ).

### Option 3: Always Use One MySQL Server

- If you want stability, stick to one MySQL server ( either XAMPP’s or your separate installation ) and configure WordPress accordingly.

---

## Question 3

**how to check if WordPress is installed or not in my machine locally?**

## 👉 Solution:

You can check if WordPress is installed locally on your machine using these methods:

### 1. Check in the XAMPP `htdocs` Folder

- Open `C:\xampp\htdocs\` and look for a WordPress folder (e.g., `wordpress` ).

- If it exists, WordPress is likely installed.

### 2. Check Using a Web Browser

- Start XAMPP and run Apache & MySQL.
- Open a browser and go to:

  ```arduino
  http://localhost/wordpress/
  ```

- If you see a WordPress site or installation screen, it's installed.

### 3. Check via phpMyAdmin

- Open `http://localhost/phpmyadmin/`.
- Look for a database named `wordpress` (or similar).
- If it exists, WordPress is installed.

### 4. Check Installed Files in XAMPP

- Open `C:\xampp\htdocs\wordpress\wp-config.php`.
- If the file exists and contains database details, WordPress is installed.

---

## Question 4

**C:\>rmdir /s /q xampp**
`xampp\locale\en\LC_MES~1\delphi2006_de_en.mo - The process cannot access the file because it is being used by another process.
xampp\locale\en\LC_MES~1\xampp_control.mo - The process cannot access the file because it is being used by another process.
xampp\xampp-control.exe - Access is denied.
xampp\xampp-control.ini - Access is denied.
The process cannot access the file because it is being used by another process.` **How to fix this?**

## 👉 Solution:

The error occurs because some XAMPP files are still running in the background. Try these steps to fix it:

### 1. Stop XAMPP Processes

- Open **Task Manager** ( `Ctrl + Shift + Esc` ).

- Look for `xampp-control.exe`, `mysql.exe`, or `httpd.exe` under Processes.

- Right-click each and select **End Task**.

### 2. Stop XAMPP Services ( If Installed as a Service )

- Open Command Prompt as Administrator and run:

  ```bash
  net stop Apache2.4
  net stop MySQL
  ```

### 3. Run Delete Command as Administrator

- Open Command Prompt as Administrator (Win + R → type cmd→Ctrl + Shift + Enter`).
- Try deleting again:

  ```bash
  rmdir /s /q C:\xampp
  ```

### 4. Restart Your PC

If the files are still in use, restart your computer and try deleting again.
