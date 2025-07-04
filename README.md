# 🐬 Installing MySQL on Ubuntu

This guide covers the steps to install **MySQL Server** on Ubuntu (20.04, 22.04 or similar).

---

## 🛠️ Prerequisites

* Ubuntu 20.04 or newer
* A user with **sudo** privileges
* Internet connection

---

## 📦 Step 1: Update Your Package Index

```bash
sudo apt update -y
```

## 📦 Step 2: Install MySQL Server
```bash
sudo apt install mysql-server -y
```

## 🔐 Step 3: Secure the Installation
```bash
sudo mysql_secure_installation
```

You will be asked to:
* Set the root password
* Remove anonymous users
* Disallow remote root login
* Remove test database
* Reload privilege tables

Choose `Y` for all to improve security (unless you have specific needs).

## ✅ Check installation and Service Status
```bash
mysql --version
```
or
```bash
sudo systemctl status mysql.service
```

## ▶️ Step 4: Do these if necessary (normally not necessary):
```bash
sudo systemctl start mysql
sudo systemctl enable mysql

