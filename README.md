# MySQL on Ubuntu

🛠 Step 2: Install MySQL Server
bash
Copy
Edit
sudo apt install mysql-server
This installs the latest MySQL version available in Ubuntu's official repositories.

🔒 Step 3: Secure the Installation
bash
Copy
Edit
sudo mysql_secure_installation
You’ll be prompted to:

Set up root password (if not using auth_socket)

Remove anonymous users

Disallow root login remotely

Remove test database

Reload privilege tables

🚦 Step 4: Check MySQL Service Status
bash
Copy
Edit
sudo systemctl status mysql
Basic service commands:

bash
Copy
Edit
sudo systemctl start mysql
sudo systemctl stop mysql
sudo systemctl restart mysql
🔑 Step 5: Log Into MySQL
Option 1: Using sudo (default)
bash
Copy
Edit
sudo mysql
Option 2: Using Password (manual setup required)
bash
Copy
Edit
sudo mysql
Then inside the MySQL shell:

sql
Copy
Edit
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'your_password';
FLUSH PRIVILEGES;
EXIT;
Now you can log in using:

bash
Copy
Edit
mysql -u root -p
🌐 Optional: Enable Remote Connections
Open the MySQL config file:

bash
Copy
Edit
sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
Change the bind address:

ini
Copy
Edit
bind-address = 127.0.0.1
to

ini
Copy
Edit
bind-address = 0.0.0.0
Restart MySQL:

bash
Copy
Edit
sudo systemctl restart mysql
⚠️ Be sure to secure your remote connections (firewall, SSL, and user permissions).

✅ Done!
You now have MySQL installed and running on your Ubuntu machine. 🎉

Feel free to contribute or open an issue if you have improvements or questions!
