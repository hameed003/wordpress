# A: Install wordpress on local machine.

## Step 1: Download & Install XAMPP

1. Download latest version of XAMPP according to your Operating System from the official `XAMPP` website [Download XAMPP](https://www.apachefriends.org/download.html)

2. Once the XAMPP is downloaded Run the installer and install it in `C:\xampp`.

3. Open **XAMPP Control Panel** and **Start**:
   - Apache ( for the web server )
   - MySQL ( for the database )

## Step 2: Download & Extract WordPress

1. Now download the latest version of wordpress from the official `wordpress.org` website [Download Wordpress](https://wordpress.org/download/)

2. Once the `wordpress` is downloaded, `Extract` the downloaded `.zip` file it in the download folder.

3. Move the extracted `wordpress` folder to `C:\xampp\htdocs\`.

   - You can rename the folder `wordpress` (e.g., `mywebsite`).

4. Now go to `C:\xampp\htdocs\wordpress\wp-config-sample.php` and make a copy of `wp-config-sample.php` and rename it to `wp-config.php` and make the necessary changes as shown below.

![image 1](https://github.com/hameed003/wordpress/blob/main/images/image%201.png)

![image 2](https://github.com/hameed003/wordpress/blob/main/images/image%202.png)

### wp-config-sample.php file ( before rename )

![wp-config-sample.php file](https://github.com/hameed003/wordpress/blob/main/images/image%203.png)

### wp-config.php file ( after rename )

**Set or Change `DB_NAME to wordpress_db`, `DB_USER to root`, `DB_PASSWORD to "" ( empty by default in XAMPP )`**
![wp-config.php file](https://github.com/hameed003/wordpress/blob/main/images/image%204.png)

## Step 3: Create a MySQL Database for WordPress

1. Open **phpMyAdmin** in a browser:

```arduino
http://localhost/phpmyadmin/
```

2. Click **Databases** → Enter a database name (e.g., `wordpress_db`) → Click Create.

**Note:** the database name in `wp-config.php` must match exactly with the database name created in http://localhost/phpmyadmin/ like `wordpress_db` in this case.

## Step 4: Configure WordPress

1. Open a browser and visit:

```arduino
http://localhost/wordpress/
```

( or _`http://localhost/mywebsite/`_ if renamed )

2. Select a language → Click **Continue.**

![Select-language](https://github.com/hameed003/wordpress/blob/main/images/image%205.png)

3. Enter database details ( if asked or else setup manually as we setup above in `C:\xampp\htdocs\wordpress\wp-config.php` ):
   - **Database Name:** `wordpress_db` (the one you created)
   - **Username:** `root`
   - **Password:** ( _leave empty, default for XAMPP_ )
   - **Database Host:** `localhost`
4. Click **Submit** → Click **Run the Installation**.

5. Fill in WordPress site details ( username, password, email ) and click **Install WordPress**.

![Install-WordPres](https://github.com/hameed003/wordpress/blob/main/images/image%206.png)

![WordPress-Installed-Success](https://github.com/hameed003/wordpress/blob/main/images/image%207.png)

## Step 5: Login to WordPress Admin Panel

- Go to:

```ruby
http://localhost/wordpress/wp-admin/
```

- Enter your credentials and start using WordPress!

![WordPress-Credentail](https://github.com/hameed003/wordpress/blob/main/images/image%208.png)

**Wordpress Dashboard or Admin Pannel**

![Wordpress-Dashboard](https://github.com/hameed003/wordpress/blob/main/images/image%209.png)
