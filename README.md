# Create-and-Host-Wordpress-Website-on-AWS-EC2

## Summary
Learn how to create and deploy a WordPress website on the AWS platform step by step, including setting up a virtual computer, installing Apache web server, MySQL database, and WordPress, assigning a domain name, and securing the website with an SSL certificate.

## Highlights
🚀 Deploy a WordPress website on AWS EC2 using the traditional method instead of one-click installation.
🖥️ Rent a virtual computer on AWS EC2 and install Apache web server and MySQL database.
🌐 Install WordPress, a popular content management system, on the web server.
🔐 Assign a domain name and secure the website with an SSL certificate.

## Key Insights
💻 Creating a virtual computer on AWS EC2 allows you to have full control over your website and customize it as per your needs.
🌐 Installing Apache web server enables the handling of HTTP requests and serving appropriate responses for your website.
🗃️ Setting up a MySQL database provides a reliable and efficient way to store and manage data for your WordPress website.
📝 WordPress, written in PHP, is a powerful content management system that allows you to create and customize your website without the need for coding.
🌐 Assigning a domain name to your website makes it easily accessible to users and enhances its professional appearance.
🔒 Securing your website with an SSL certificate ensures the protection of user data and builds trust among visitors.
💡 By following the traditional method, you gain a deeper understanding of the components and processes involved in hosting a website on the cloud.

## Step-by-Step-Script

1. Install Apache server on Ubuntu
sudo apt install apache2

2. Install php runtime and php mysql connector
sudo apt install php libapache2-mod-php php-mysql

3. Install MySQL server
sudo apt install mysql-server 

4. Login to MySQL server
sudo mysql -u root

5. Change authentication plugin to mysql_native_password (change the password to something strong)
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password by 'Testpassword@123';

6. Create a new database user for wordpress (change the password to something strong)
CREATE USER 'wp_user'@localhost IDENTIFIED BY 'Testpassword@123';

7. Create a database for wordpress
CREATE DATABASE wp;

8. Grant all privilges on the database 'wp' to the newly created user
GRANT ALL PRIVILEGES ON wp.* TO 'wp_user'@localhost;

9. Download wordpress
cd /tmp
wget https://wordpress.org/latest.tar.gz

10. Unzip
tar -xvf latest.tar.gz

11. Move wordpress folder to apache document root
sudo mv wordpress/ /var/www/html

12. Command to restart/reload apache server
sudo systemctl restart apache2
OR
sudo systemctl reload apache2

13. Install certbot
sudo apt-get update
sudo apt install certbot python3-certbot-apache

14. Request and install ssl on your site with certbot
sudo certbot --apache

## Output - Screenshots 

### AWS Console (Instance Running) 
![1](https://github.com/prajwalchapke055/Create-and-Host-Wordpress-Website-on-AWS-EC2/assets/122814333/0a66186d-e24f-4bf4-a162-d0c159ad06bc)

### Apache2 Default Page 
![2](https://github.com/prajwalchapke055/Create-and-Host-Wordpress-Website-on-AWS-EC2/assets/122814333/b1d7537f-a282-404c-a1ec-f28ff12d415d)

### MobaXterm (Commands)
![3](https://github.com/prajwalchapke055/Create-and-Host-Wordpress-Website-on-AWS-EC2/assets/122814333/7cc3746c-897f-4d47-8f12-4dd7d7862e77)

### Wordpress Download Page / Link
![4](https://github.com/prajwalchapke055/Create-and-Host-Wordpress-Website-on-AWS-EC2/assets/122814333/2544ab79-389e-4100-a155-1f5a66297814)

### Setup Wordpress
![5](https://github.com/prajwalchapke055/Create-and-Host-Wordpress-Website-on-AWS-EC2/assets/122814333/2a8d5fc9-b576-42f8-854c-55bd2886ac88)

### Login Wordpress
![6](https://github.com/prajwalchapke055/Create-and-Host-Wordpress-Website-on-AWS-EC2/assets/122814333/4d16fece-cfce-4ac1-88bf-6f71da4167b1)

### Hostinger Login 
![8](https://github.com/prajwalchapke055/Create-and-Host-Wordpress-Website-on-AWS-EC2/assets/122814333/b1436081-34d3-418f-b3d6-5b5dbb1ce61e)

### Sample Wordpress
![7](https://github.com/prajwalchapke055/Create-and-Host-Wordpress-Website-on-AWS-EC2/assets/122814333/f907b798-4ba5-4842-8e29-a536d29bc590)

### YouTube Reference 
![9](https://github.com/prajwalchapke055/Create-and-Host-Wordpress-Website-on-AWS-EC2/assets/122814333/1f4d6257-20c7-40ca-a567-614991bf19aa)
