# A: Install wordpress on local machine.

## Step 1: Download & Install XAMPP

1. Download latest version of **XAMPP** according to your **Operating System** from the official **XAMPP** website. [Download XAMPP](https://www.apachefriends.org/download.html)

2. Once the **XAMPP** is downloaded Run the `installer` and install it in `C:\xampp`.

3. Open **XAMPP Control Panel** and **Start**:
   - Apache ( for the web server to run `PHP` )
   - MySQL ( for the database to run `mySQL` )

## Step 2: Download & Extract WordPress

1. Now download the latest version of **WordPress** from the official `wordpress.org` website. [Download Wordpress](https://wordpress.org/download/)

2. Once the `wordpress` is downloaded, `Extract` the downloaded `.zip` file it in the download folder.

3. Move the extracted `wordpress` folder to `C:\xampp\htdocs\`.

   - You can rename the `wordpress` folder ( e.g., `mywebsite`).

4. Now go to `C:\xampp\htdocs\wordpress\wp-config-sample.php` and make a copy of `wp-config-sample.php` and rename it to `wp-config.php` and make the necessary changes as shown below.

### wp-config-sample.php file ( before rename )

![wp-config-sample.php-file-image-1](https://github.com/hameed003/wordpress/blob/main/images/01%20image.png)

![wp-config-sample.php-file-image-2](https://github.com/hameed003/wordpress/blob/main/images/03%20image.png)

### wp-config.php file ( after rename )

![wp-config.php file-image-1](https://github.com/hameed003/wordpress/blob/main/images/02%20image.png)

Set or Change **DB_NAME** to `wordpress_db`, **DB_USER** to `root` and **DB_PASSWORD** to `" "` ( empty, default in XAMPP )

![wp-config.php file-image-2](https://github.com/hameed003/wordpress/blob/main/images/image%204.png)

## Step 3: Create a MySQL Database for WordPress

1. Open **phpMyAdmin** in a browser:

```arduino
http://localhost/phpmyadmin/
```

2. Click **Databases** → Enter a database name (e.g., `wordpress_db`) → Click Create.

![mySQL-database-dashboard-image](https://github.com/hameed003/wordpress/blob/main/images/image%204.png)

**Note:** the database name in `wp-config.php` must match exactly with the database name created in http://localhost/phpmyadmin/ like `wordpress_db` in this case.

## Step 4: Configure WordPress

1. Open a browser and visit:

```arduino
http://localhost/wordpress/
```

( or _`http://localhost/mywebsite/`_ if renamed )

2. Select a language → Click **Continue.**

![Select-wordpress-language-image](https://github.com/hameed003/wordpress/blob/main/images/image%205.png)

3. Enter database details ( if asked or else setup manually as we setup above in `C:\xampp\htdocs\wordpress\wp-config.php` ):
   - **Database Name:** `wordpress_db` (the one you created)
   - **Username:** `root`
   - **Password:** ( _leave empty, default for XAMPP_ )
   - **Database Host:** `localhost`
4. Click **Submit** → Click **Run the Installation**.

5. Fill in WordPress site details ( username, password, email ) and click **Install WordPress**.

![Setupt-WordPres-credential-image](https://github.com/hameed003/wordpress/blob/main/images/image%206.png)

![WordPress-Installation-Success-image](https://github.com/hameed003/wordpress/blob/main/images/image%207.png)

## Step 5: Login to WordPress Admin Panel

- Go to:

```ruby
http://localhost/wordpress/wp-admin/
```

- Enter your credentials and start using WordPress!

![WordPress-login-page-image](https://github.com/hameed003/wordpress/blob/main/images/image%208.png)

**Wordpress Dashboard or Admin Pannel**

![Wordpress-Dashboard-image](https://github.com/hameed003/wordpress/blob/main/images/image%209.png)
