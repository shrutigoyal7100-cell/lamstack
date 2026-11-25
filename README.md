# ☁️ CloudCraft – Two-Tier WordPress Architecture on AWS

<p align="center">
  <b>A Cloud-Based WordPress Application Using Amazon EC2 and Amazon RDS</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/AWS-Cloud-orange?logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/OS-Amazon%20Linux%202023-blue" />
  <img src="https://img.shields.io/badge/Web%20Server-Apache-red?logo=apache" />
  <img src="https://img.shields.io/badge/Database-MySQL%208.4-blue?logo=mysql" />
  <img src="https://img.shields.io/badge/CMS-WordPress-21759B?logo=wordpress" />
</p>

## 📌 Project Overview

**CloudCraft** is a two-tier WordPress application deployed on Amazon Web Services (AWS). The project demonstrates how to host a WordPress website using Amazon EC2 as the web/application server and Amazon RDS as the managed database service.

The application tier runs on Amazon Linux 2023 with Apache, PHP, and WordPress, while the database tier uses Amazon RDS with MySQL 8.4.

This project focuses on cloud infrastructure deployment, database connectivity, Linux administration, security group configuration, and application troubleshooting.

## 🏗️ Architecture

The project follows a two-tier architecture:

**User → Amazon EC2 → Amazon RDS**

- **Web/Application Tier:** Amazon EC2 running Amazon Linux 2023, Apache, PHP, and WordPress.
- **Database Tier:** Amazon RDS running MySQL 8.4.
- **Communication:** WordPress connects to the RDS database through MySQL TCP port 3306.
- **Security:** Security groups restrict database connectivity to the EC2 application server.

![CloudCraft Architecture](screenshots/architecture.png)

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| AWS EC2 | Application hosting |
| Amazon Linux 2023 | Operating system |
| Apache HTTP Server | Web server |
| PHP | Application runtime |
| WordPress | Content Management System |
| Amazon RDS | Managed database service |
| MySQL 8.4 | Relational database |
| AWS Security Groups | Network access control |

## ✨ Project Objectives

- Deploy WordPress on Amazon EC2.
- Configure Apache and PHP.
- Create and configure an Amazon RDS MySQL database.
- Establish secure EC2-to-RDS connectivity.
- Configure WordPress database settings.
- Understand AWS networking and security groups.
- Practice Linux administration and SQL commands.
- Troubleshoot common application and database errors.

## 🚀 Deployment Workflow

### 1. Launch EC2 Instance
- Create an EC2 instance using Amazon Linux 2023.
- Configure the required security group.
- Allow SSH access from a trusted IP.
- Allow HTTP traffic on port 80 when required.

### 2. Install Required Packages

```bash
sudo dnf update -y
sudo dnf install -y httpd php php-mysqlnd php-fpm mariadb105
```

### 3. Start Apache and PHP-FPM

```bash
sudo systemctl enable --now httpd
sudo systemctl enable --now php-fpm
```

### 4. Configure Amazon RDS
- Create an Amazon RDS MySQL 8.4 database.
- Configure the database identifier and credentials.
- Set up the VPC and DB subnet group.
- Configure database connectivity.

### 5. Configure Security Groups

Allow MySQL traffic on port `3306` from the EC2 security group only.

**Important:** Never expose the database port publicly using `0.0.0.0/0`.

### 6. Configure WordPress

Download and install WordPress on the EC2 instance.

Configure the database connection in `wp-config.php` using the RDS endpoint and database credentials.

### 7. Verify Application

Access the WordPress website through the EC2 public IPv4 address and complete the WordPress installation wizard.

## 📸 Project Screenshots

### 1. AWS Architecture
![Architecture](screenshots/architecture.png)

### 2. AWS EC2 Console
![EC2 Console](screenshots/aws-console.png)

### 3. RDS Database Console
![RDS Console](screenshots/rds-console.png)

### 4. Database Terminal
![Database Terminal](screenshots/terminal-db.png)

### 5. Live WordPress Website
![CloudCraft Website](screenshots/live-site.png)

## 🔧 Troubleshooting & Challenges

During implementation, several common configuration issues were explored:

- **MySQL Error 1045:** Database authentication and access denied issues.
- **MySQL Error 1396:** Handling an already existing database user.
- **PHP HTTP 500 Error:** Identifying and correcting PHP configuration syntax errors.
- **Database Connectivity:** Verifying RDS endpoints, security groups, and port configuration.
- **Linux Package Management:** Using `dnf` on Amazon Linux 2023.

These troubleshooting exercises helped develop practical cloud administration and debugging skills.

## 🔐 Security Best Practices

- Restrict SSH access to trusted IP addresses.
- Keep the RDS database private.
- Allow database traffic only from the EC2 security group.
- Never upload AWS credentials, passwords, private keys, or sensitive configuration files to GitHub.
- Keep `wp-config.php` out of public repositories.
- Follow the principle of least privilege.
- Use HTTPS for production deployments.
- Regularly update system packages and WordPress.

## 💰 Cost Optimization

After testing the application and verifying EC2-to-RDS connectivity, the EC2 instances were terminated to reduce ongoing compute costs.

Unused AWS resources should also be reviewed to avoid unnecessary charges, including:

- EBS volumes
- Snapshots
- Elastic IP addresses
- Amazon RDS instances

## 🎯 Key Learning Outcomes

Through this project, I gained practical experience in:

- AWS EC2 provisioning and management.
- Amazon Linux 2023 administration.
- Apache and PHP configuration.
- WordPress deployment.
- Amazon RDS MySQL database management.
- SQL user and database administration.
- AWS Security Group configuration.
- Cloud networking and database connectivity.
- Linux and application troubleshooting.
- Cloud security and cost optimization.

## 👩‍💻 Author

**Shruti Goyal**

Cloud & DevOps Enthusiast

**Project:** CloudCraft – Two-Tier WordPress Architecture on AWS

**GitHub:** [Your GitHub Profile](https://github.com/your-username)

---

<p align="center">
  <b>Built with AWS, Linux, Apache, PHP, MySQL & WordPress.</b>
  <br/>
  Learning Cloud Computing & DevOps Through Hands-On Projects.
</p>
