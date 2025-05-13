# Mankind Matrix Product Service

A microservice for managing products, using MySQL as the database.

## Overview

This service provides REST API endpoints to manage product data with full CRUD operations.

## Setup Guide

### Prerequisites

- **Java**: JDK 17
- **MySQL**: 8.0 or newer
- **Git**: For cloning the repository

### Installation Steps

#### 1. Install Java (JDK 17)

<details>
<summary><b>macOS</b></summary>

1. Install Homebrew (if not installed)
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

2. Install Java with Homebrew
```bash
brew install openjdk@17
```

3. Link Java
```bash
sudo ln -sfn $(brew --prefix)/opt/openjdk@17/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-17.jdk
```
</details>

<details>
<summary><b>Windows</b></summary>

1. Download OpenJDK 17 from [Adoptium](https://adoptium.net/)
2. Run the installer
3. Add to PATH: Set JAVA_HOME in Environment Variables
</details>

<details>
<summary><b>Linux (Ubuntu/Debian)</b></summary>

1. Update Linux
```bash
sudo apt update
```

2. Install Java
```bash
sudo apt install openjdk-17-jdk
```
</details>

#### 2. Install MySQL

<details>
<summary><b>macOS</b></summary>

1. Install MySQL
```bash
brew install mysql
```

2. Start MySQL service
```bash
brew services start mysql
```
</details>

<details>
<summary><b>Windows</b></summary>

1. Download MySQL Installer from [MySQL Website](https://dev.mysql.com/downloads/installer/)
2. Select "Server only" or "Custom" installation
3. Complete the setup wizard (note your root password)
</details>

<details>
<summary><b>Linux (Ubuntu/Debian)</b></summary>

```bash
sudo apt install mysql-server
```
</details>

#### 3. Verify Instalation

<details>

```bash
# Check Java version (should show version 17.x)
java --version

# Check MySQL version
mysql --version
```
</details>

## Project Setup

### 1. Clone the Repository

```bash
git clone https://github.com/rebeccayilma/Mankind_Matrix_Product_Service.git
```
```bash
cd Mankind_Matrix_Product_Service
```
### 2. Create .env file

1. Duplicate the file '.env.example'
2. Rename for .env

### 3. Connect to Database

This step has to be done when a database is setup. If it not yet, please, follow the guidance here.

- Replace the enviroment variable with the database connection
```bash
# Database Configuration
DB_HOST=mankind-matrix-db.cd0qkick6gy2.us-west-1.rds.amazonaws.com
DB_PORT=3306
DB_NAME=mankind_matrix_db
DB_USERNAME=matrix_user
DB_PASSWORD=matrix_pass

# Database Connection Properties
DB_CONNECT_TIMEOUT=60000
DB_SOCKET_TIMEOUT=60000
DB_USE_SSL=false
DB_ALLOW_PUBLIC_KEY_RETRIEVAL=true
DB_SERVER_TIMEZONE=UTC
DB_AUTO_RECONNECT=true
DB_FAIL_OVER_READ_ONLY=false

# Hikari Connection Pool Settings
DB_HIKARI_MAX_POOL_SIZE=10
DB_HIKARI_MIN_IDLE=5
DB_HIKARI_CONNECTION_TIMEOUT=60000
DB_HIKARI_IDLE_TIMEOUT=300000
DB_HIKARI_MAX_LIFETIME=1200000

```

### 4. Run the Application

- Run the command to start application

```bash
./mvnw spring-boot:run
```

### 5. Testing the API

The service will be available at `http://localhost:8080`

Check API application at `http://localhost:8080`

## Additional Resources

- [Spring Boot Documentation](https://docs.spring.io/spring-boot/docs/current/reference/html/)
- [MySQL Documentation](https://dev.mysql.com/doc/)