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
You should see the following information:  
  
● mysql.service - MySQL Community Server  
     Loaded: loaded (/lib/systemd/system/mysql.service; enabled; vendor preset: enabled)  
     Active: active (running) since Fri 2025-07-04 15:58:51 WIB; 21s ago  
    Process: 3899 ExecStartPre=/usr/share/mysql/mysql-systemd-start pre (code=exited, status=0/SUCCESS)  
   Main PID: 3907 (mysqld)  
     Status: "Server is operational"  
      Tasks: 38 (limit: 9376)  
     Memory: 364.4M  
        CPU: 666ms  
     CGroup: /system.slice/mysql.service  
             └─3907 /usr/sbin/mysqld  


## ▶️ Step 4: Do these if necessary (normally not necessary):
```bash
sudo systemctl start mysql
sudo systemctl enable mysql

