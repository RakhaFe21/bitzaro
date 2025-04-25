  

# Documentation Cloning WordPress Website on aaPanel

  

This document outlines the step-by-step process of cloning a WordPress website from one domain to another using **aaPanel**. The cloning process includes duplicating website files and transferring the database to ensure that the new domain mirrors the original WordPress site.

  

---

  

## Prerequisites

Before starting, ensure you have:

-  **Domain pointed to aaPanel** (e.g., `bitzaro.solutions`).

  


  

---

  

## Step 1: Create a New Website and Database

  

### Create a New Website:

1. Navigate to the **"Website"** section in aaPanel.

2. Click **"Add site"** and create a new website for `bitzaro.solutions`.
![enter image description here](https://private-user-images.githubusercontent.com/135587083/437513441-8972495b-7969-436e-8356-07c8068260be.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDU1OTU4OTAsIm5iZiI6MTc0NTU5NTU5MCwicGF0aCI6Ii8xMzU1ODcwODMvNDM3NTEzNDQxLTg5NzI0OTViLTc5NjktNDM2ZS04MzU2LTA3YzgwNjgyNjBiZS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNDI1JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDQyNVQxNTM5NTBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1mNjg5NzQyYjczM2JhMTA2YTVhZDk5ZTA1ZDFjNzA1N2U4NjIwNGNkMDdjOTQxMjdiMjU5MTFlYzVkZjk0ZjI4JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.Gj1d1pSE8Vnf_MZBxmWX2Uh6KgfNycFKF6vuoq-tSYs)
4. Set the **Document Root** in the Website Path column to the appropriate directory where you'll place the cloned files.
![enter image description here](https://private-user-images.githubusercontent.com/135587083/437513871-9fb019cb-9903-42b3-ab4e-42c6f94897e9.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDU1OTU5NjksIm5iZiI6MTc0NTU5NTY2OSwicGF0aCI6Ii8xMzU1ODcwODMvNDM3NTEzODcxLTlmYjAxOWNiLTk5MDMtNDJiMy1hYjRlLTQyYzZmOTQ4OTdlOS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNDI1JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDQyNVQxNTQxMDlaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0xMzAyODdhMjZjNGRiZTZhNzg0NDFhOWIwZDgzYzZhMmFiYWZjMjRlZmFiNDc0M2FlYmYzYmM0ODgxOWFjYTVhJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.wxHpI5Id-0EbsoVNGWjCSC7Br-9ixJ-RgXt9P_gQoZg)
5. Ensure that the **domain** is pointing correctly to your aaPanel server.

  

### Create a New Database:

1. Go to the **"Database"** section in aaPanel.

2. Click **"Add DB"** and create a new database for `bitzaro.solutions`.
![enter image description here](https://private-user-images.githubusercontent.com/135587083/437515150-3202b68e-a2f8-460c-8a74-52c1430e6312.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDU1OTYxOTcsIm5iZiI6MTc0NTU5NTg5NywicGF0aCI6Ii8xMzU1ODcwODMvNDM3NTE1MTUwLTMyMDJiNjhlLWEyZjgtNDYwYy04YTc0LTUyYzE0MzBlNjMxMi5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNDI1JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDQyNVQxNTQ0NTdaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1kM2JlODdkM2Y3YmIzNjI1ZDhiMTYwNWY2NjcxMGUxNmVmOWM0ODkxNGJlNWQ4MWFkOTc0NjU2MWNmYzM3OWE2JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.bpd1rfzoUVxrzEK6b_YKcMkQvQNyDrqrNVInP3rJffE)

4. Note the **database name**, **username**, and **password** for later use.


---

  

## Step 2: Upload Website Files to the New Domain

  

1. Go to the **"File"** section in aaPanel.
2. Navigate to the **Document Root** folder of `blog.bitzaro.com`, select all and then copy.
![enter image description here](https://private-user-images.githubusercontent.com/135587083/437515990-07e8d302-cb12-43a0-b15a-19fd44c74dc5.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDU1OTYzNTAsIm5iZiI6MTc0NTU5NjA1MCwicGF0aCI6Ii8xMzU1ODcwODMvNDM3NTE1OTkwLTA3ZThkMzAyLWNiMTItNDNhMC1iMTVhLTE5ZmQ0NGM3NGRjNS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNDI1JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDQyNVQxNTQ3MzBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT04NGFmMjU2ZTY0MDk0NDMyOWU3YWY5MTZiY2U5NzBmYmNkZjVmOGFjN2Q2NTA3NTA2YzM5MDQzZThhMDM1NjM3JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.tFXt0zbBC2p1WqNJFkRa6DaHSf2wMEKI5L3wU1NEyF8)
4. Go to the **Document Root** folder of `bitzaro.solutions`.

5. **Paste all files** that you previously copied from `blog.bitzaro.com`.
![enter image description here](https://private-user-images.githubusercontent.com/135587083/437517141-bb290966-6c00-4711-b1ac-9834aa69fdb5.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDU1OTY1NTIsIm5iZiI6MTc0NTU5NjI1MiwicGF0aCI6Ii8xMzU1ODcwODMvNDM3NTE3MTQxLWJiMjkwOTY2LTZjMDAtNDcxMS1iMWFjLTk4MzRhYTY5ZmRiNS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNDI1JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDQyNVQxNTUwNTJaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT04YmY0MzU1N2JiNDRiODZkZTU2ZjJhMjI5MmI5MjkxYjlmZmUxM2FmZTRjOWJiZTMyMTBkMmRjZWM3ZWY4OWNlJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.H29Cpj53PAJC5kKAEKVfRBDALZ6mUg-VKxPdvdqZkqg)

  

---

  

## Step 3: Import the Database

  

1. Go to Databases section in aaPanel.
2. Select database `sql_blog_bitzaro` and download file to your computer.
3. Click on new database which is `sql_bitzaro_solutions` and upload file that previously downloaded. If file database have been successful uploaded, then import
![enter image description here](https://private-user-images.githubusercontent.com/135587083/437520211-41f47a65-d4db-4aa7-b0cf-7134d927485a.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDU1OTcxMDQsIm5iZiI6MTc0NTU5NjgwNCwicGF0aCI6Ii8xMzU1ODcwODMvNDM3NTIwMjExLTQxZjQ3YTY1LWQ0ZGItNGFhNy1iMGNmLTcxMzRkOTI3NDg1YS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNDI1JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDQyNVQxNjAwMDRaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT01ZThmNTZkZjRlOTIzZDIzMTZlMGFiM2FhZGUxNmJjNzIxNTFkODM5NWJiMzZkNWE2MmYyNTI3MmIzNDIwOGQwJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.dNlXC0DyymT8yCu8yMWWxyfP54I2Uv0F-ULTEFpzjno)
  

---

  

## Step 4: Update the `wp-config.php` File

  

1. In the **File Manager**, open the `wp-config.php` file located in the `bitzaro.solutions` root directory.

2. Update the following lines to reflect the new database name, username, and password:

  

```php

define('DB_NAME', 'bitzaro_solutions_db'); // New database name

define('DB_USER', 'bitzaro_user'); // New database username

define('DB_PASSWORD', 'new_password'); // New database password

define('DB_HOST', 'localhost'); // Database host (usually localhost)

```

  

3. Save the file after making the necessary changes.

 

---

  

## Step 5: Update `siteurl` and `home` in the Database

  

1. Go to Database section then click **phpMyAdmin** button and open the `wp_options` table within the new database (`bitzaro_solutions_db`).

2. Locate the `siteurl` and `home` entries.

3. **Edit** both to replace the old URL (`https://blog.bitzaro.com`) with the new one (`https://bitzaro.solutions`):

  

```sql

UPDATE wp_options SET option_value = 'https://bitzaro.solutions' WHERE option_name = 'siteurl';

UPDATE wp_options SET option_value = 'https://bitzaro.solutions' WHERE option_name = 'home';

```
![enter image description here](https://private-user-images.githubusercontent.com/135587083/437521194-573cc801-7196-4405-8f17-194c0996c324.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDU1OTcyODcsIm5iZiI6MTc0NTU5Njk4NywicGF0aCI6Ii8xMzU1ODcwODMvNDM3NTIxMTk0LTU3M2NjODAxLTcxOTYtNDQwNS04ZjE3LTE5NGMwOTk2YzMyNC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNDI1JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDQyNVQxNjAzMDdaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1jMDU3YjZjYTQzODVkYzk0ZTBhMGI5YmJlNDQ1NGE5YzlhOTBmYThiNTIwOTkzZDRjNTYzMmUwNWE1MzYwNzM1JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.hNQljixNsGq6AMBX6RysSiVaeWYdR4o1DM-BCfpD6F4)
  
  

---

  

## Step 6: Test the Website

  

1. After all the changes are made, access `https://bitzaro.solutions` in your browser.

2. Verify that the website is properly cloned and running as expected.


---

  

## Step 7: Finalize and Clean Up

  

1. Verify that all links, images, and media are correctly linked to the new domain.

2. Clear any browser cache to ensure that no redirects or old data are affecting the site.

3. Regularly back up the new site and monitor its performance.

  

---

  

### **Conclusion**

  

By following the steps above, you can successfully clone a WordPress website from one domain to another using **aaPanel**. The process includes copying the website files, importing the database, updating the configuration file, and ensuring everything works properly with the new domain.

  

---

  

### Notes:

- Always take a full **backup** of your website and database before making any changes.

- Ensure that **DNS settings** for the new domain (`bitzaro.solutions`) are correctly configured to point to your aaPanel server.

  

---
