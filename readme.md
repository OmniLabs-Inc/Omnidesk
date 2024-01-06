# OmniDesk Laravel Application

Welcome to OmniDesk, a powerful Laravel-based help desk application. This README provides essential information to get you started with the installation and configuration process.

## Installation

### cPanel Installation

# Copy Files to Server:

Locate the "Omni" Application folder in your local development environment.
Connect to your cPanel hosting account using an FTP client or cPanel File Manager.
Navigate to the root directory or public_html directory of your server.
Upload all files and folders from the "OmniSupportApplication" folder to the server.

# Visit Your Website: 

Open a web browser and visit your website's domain.
Follow the on-screen instructions to initiate the installation process.
Ensure you have the necessary database credentials ready for configuration.

# Complete Installation:

Provide the required information during the installation, including database connection details.
Complete the installation wizard, and the application will set up the necessary tables and configurations.
You may be prompted to create an admin account or configure other settings during this process.

### NGinx Installation

# Copy Files to Server:

Locate the "Omni" Application folder in your local development environment.
Connect to your server using SSH or your preferred method.
Copy the entire "OmniSupportApplication" folder to the desired location on your server.
Configure NGinx Document Root:

Open your NGinx server configuration file (commonly found at /etc/nginx/nginx.conf or /etc/nginx/sites-available/default).
Locate the server block corresponding to your domain or create a new one.
Set the root directive to point to the directory where you copied the "OmniSupportApplication" folder. For example:
nginx
Copy code

```bash
server {
    listen 80;
    server_name your_domain.com;
    root /path/to/your/OmniSupportApplication;
    index index.php index.html index.htm;
    # Other NGinx configurations...
}
```
Reload NGinx:

Save the configuration file and reload NGinx to apply the changes. Run the following command:

```bash
sudo service nginx reload
```
Visit Your Website:

Open a web browser and visit your website's domain.
Follow the on-screen instructions to initiate the installation process.
Ensure you have the necessary database credentials ready for configuration.

# Complete Installation:

Provide the required information during the installation, including database connection details.
Complete the installation wizard, and the application will set up the necessary tables and configurations.
You may be prompted to create an admin account or configure other settings during this process.


## Clear All Cache

To clear all caches, run the following command in your Laravel application:

```bash
php artisan optimize && php artisan cache:clear && php artisan route:cache && php artisan view:clear && php artisan config:cache && php artisan route:clear
```

## Running a Queue Cron Job on Shared Hosting

If you are using shared hosting, you can set up a queue Cron job with the following command:

```bash
php /path/to/application/artisan queue:work --queue=high,default --stop-when-empty
```

Make sure to replace "/path/to/application/" with the actual path to your Laravel application.

---
