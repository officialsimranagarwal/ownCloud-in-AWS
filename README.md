# Deploying ownCloud on AWS ☁️

![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)
![LAMP](https://img.shields.io/badge/Stack-LAMP-blue?style=for-the-badge)
![Security](https://img.shields.io/badge/Config-Trusted_Domains-red?style=for-the-badge)

## 📖 Overview

This repository provides a production-grade deployment guide for **ownCloud** on **AWS EC2**. It details the setup of a secure, scalable file hosting environment using the classic LAMP (Linux, Apache, MySQL/MariaDB, PHP) stack.

## 🏗️ Technical Stack & Configuration

### 1. Compute Layer (EC2)
-   **OS**: Ubuntu 20.04 LTS.
-   **Security Groups**: Inbound rules configured for SSH (22) and HTTP (80) access.

### 2. Web Server (Apache Integration)
-   **Service**: Apache2.
-   **Modules Enabled**: `libapache2-mod-php` for processing PHP files.
-   **Virtual Host**: Modified `000-default.conf` to point the DocumentRoot to `/var/www/owncloud`.
-   **Directory Configuration**: `DirectoryIndex` updated to prioritize `index.php`.

### 3. Database Layer (MariaDB)
-   **Service**: MariaDB Server.
-   **Security**: `mysql_secure_installation` script applied to remove anonymous users and disable remote root login.
-   **User Management**: Dedicated `owncloud` user created with specific privileges on the `owncloud` database, adhering to the principle of least privilege.

### 4. Application Logic (PHP & ownCloud)
-   **Dependencies**: Installed critical PHP extensions (`php-gd`, `php-mbstring`, `php-curl`, `php-zip`, `php-intl`) required for image processing and internationalization.
-   **Trusted Domains**: The `config.php` file is manually edited to whitelist the EC2 instance's Public IP, preventing HTTP Host header attacks.

## 📂 Contents

-   **`ownCloud Aws_compressed.pdf`**: Complete deployment pictorial guide.
-   **`installation of different files.`**: Bash command reference for the LAMP setup.

## 🚀 Getting Started

1.  Clone this repository.
2.  Follow the PDF guide to provision the EC2 instance and run the installation commands.

## 🤝 Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## 👤 Author

**Simran Agarwal**
-   [Profile](https://github.com/officialsimranagarwal)
-   [LinkedIn](https://linkedin.com/in/simran-agarwal-54751b191)

---
*Generated with ❤️ by Simran Agarwal*
