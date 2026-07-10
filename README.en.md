<!-- LANG_START -->
🇷🇺 [Русская версия](README.md)
<!-- LANG_END -->

<div align="center">

<img src="resources/header.svg" alt="SupportChat" width="900"/>

</div>





<!-- STATS_START -->
<!-- auto-updated by GitHub Actions · 2026-07-10 09:01 UTC -->

[![Views local](https://img.shields.io/badge/Views_local-69-ff6900?style=for-the-badge&logo=github)](https://github.com/gooog1111/SupportChat)
[![Views GitHub](https://img.shields.io/badge/Views_GitHub-0-ff6900?style=for-the-badge&logo=github)](https://github.com/gooog1111/SupportChat)
[![Unique visitors](https://img.shields.io/badge/Unique-0-blue?style=for-the-badge&logo=github)](https://github.com/gooog1111/SupportChat)
[![Clones](https://img.shields.io/badge/Clones-1806-purple?style=for-the-badge&logo=github)](https://github.com/gooog1111/SupportChat)
[![Stars](https://img.shields.io/badge/Stars-1-yellow?style=for-the-badge&logo=github)](https://github.com/gooog1111/SupportChat/stargazers)
[![Forks](https://img.shields.io/badge/Forks-0-green?style=for-the-badge&logo=github)](https://github.com/gooog1111/SupportChat/network/members)
[![Downloads latest release](https://img.shields.io/badge/Downloads_latest_release-0-brightgreen?style=for-the-badge)](https://github.com/gooog1111/SupportChat/releases/latest)
[![Downloads total assets](https://img.shields.io/badge/Downloads_total_assets-0-brightgreen?style=for-the-badge)](https://github.com/gooog1111/SupportChat/releases)

<!-- STATS_END -->









<!-- GRAPH_START -->
<p align="center">
  <img src="./traffic-views.png" width="100%" alt="GitHub Traffic">
</p>
<!-- GRAPH_END -->










<!-- ISSUES_START -->
<!-- auto-updated by GitHub Actions · 2026-07-10 09:01 UTC -->

## Issues

<p>
  <a href="https://github.com/gooog1111/SupportChat/issues">
    <img alt="Open issues" src="https://img.shields.io/badge/Open_issues-0-blue?style=for-the-badge&logo=github">
  </a>
  <a href="https://github.com/gooog1111/SupportChat/issues/new/choose">
    <img alt="Create issue" src="https://img.shields.io/badge/Create_issue-new-success?style=for-the-badge&logo=github">
  </a>
</p>

<details open>
<summary><b>Open issues</b></summary>


<p align="center">
  <b>No open issues.</b><br>
  <sub>The service issue <code>views-counter</code> is hidden from the list.</sub>
</p>


</details>

<p>
  <a href="https://github.com/gooog1111/SupportChat/issues/new/choose">Create new issue</a> ·
  <a href="https://github.com/gooog1111/SupportChat/issues">All issues</a>
</p>

<!-- ISSUES_END -->




## Technical support chat

## ⚠️ Attention  
This file has been automatically edited.

---

A simple and (not very) secure chat for organizing technical support, divided into client and administrative interfaces. Runs on Apache, Nginx or IIS without using a database or Node.js.

![Пример интерфейса поьзователя](https://github.com/gooog1111/supportchat/blob/main/chat/assets/images/client.png)

---

![Пример интерфейса администратора](https://github.com/gooog1111/supportchat/blob/main/chat/assets/images/admin.png)

---

## 🚀 Features
- **Client part**  
  - 📤 Send text and images (up to 5 MB)
  - 📅 Correspondence history
  - 🕒 Group messages by time (2 minute intervals)
  - 🔄 Automatic session recovery  
  - 👤 Unique session ID for each client
- **Administrative panel**
  - 🎯 Dynamic chat updates (every 10 sec)
  - 🚦 Status system:
    - `🟢 Открыт` 
    - `🟡 В работе (Имя админа)`
    - `🔴 Закрыт`
  - 🛠 Chat management (open/close/clear)  
  - 🔍 View client metadata (IP, PC name)  
  - 📊 Chat statuses (Open, In progress, Closed)  
  - 🔄 Automatic update of chat list
- **Safety**  
  - 🔒 XSS and CSRF protection  
  - 🔑 Session and authorization system  
  - 📁 Storing data in JSON files  
  - 🔄 Regular cleaning of inactive sessions
- **Adaptability**  
  - 📱 Optimized for mobile devices

## ⚙️ Server requirements
## # Required components
| Component | Minimum version | 
|----------------|--------------------|
| PHP | 7.4+ |
| Web server | Apache/Nginx/IIS | 

## # Required PHP modules
```bash
sudo apt install php7.4-fileinfo php7.4-json php7.4-session  # Для Linux
```
- **Web server**: Apache, Nginx or IIS  
- **Write permissions** for folders: `uploads/`, `chats/`, `clients/`, `logs/`  

---

## ⚙️ Installation

## # 🪟Windows  
## ## For IIS:  
1. Set [PHP для Windows](https://windows.php.net/download/) and add the PHP path to the `PATH` variable.  
2. In **IIS Manager**:  
   - Create a website with a project root folder.  
   - Set the `*.php` handler to `php-cgi.exe`.  
3. Set up permissions:  
   ```powershell  
   icacls "C:\путь_к_проекту" /grant IIS_IUSRS:(OI)(CI)F  
   ```
## ## For Apache (via XAMPP/WAMP):  
1. Copy the `chat` folder to `htdocs/`.  
2. Add a virtual host:  
   ```apache  
   <VirtualHost *:80>  
       DocumentRoot "C:/xampp/htdocs/chat"  
       ServerName chat.local  
       <Directory "C:/xampp/htdocs/chat">  
           AllowOverride All  
           Require all granted  
       </Directory>  
   </VirtualHost>  
   ```
3. Restart Apache.

---

## # 🐧 Linux  
## ## Apache:  
1. Install packages:  
   ```bash  
   sudo apt install apache2 php libapache2-mod-php php-fileinfo  
   ```
2. Place the project in `/var/www/html/chat`.  
3. Set up a virtual host:  
   ```apache  
   <VirtualHost *:80>  
       DocumentRoot /var/www/html/chat  
       ServerName chat.local  
       <Directory "/var/www/html/chat">  
           Options FollowSymLinks  
           AllowOverride All  
           Require all granted  
       </Directory>  
   </VirtualHost>
   
4. Настройте права:  
   ```bash  
   sudo chown -R www-data:www-data /var/www/html/chat/  
   ```
## ## Nginx:  
1. Установите пакеты:  
   ```bash  
   sudo apt install nginx php-fpm php-fileinfo
   ```
2. Добавьте конфигурацию:  
   ```nginx  
   server {  
       listen 80;  
       root /var/www/html/chat;  
       index index.php;  
       
       location/{  
           try_files $uri $uri/ /index.php?$args;  
       }       location ~ \.php$ {  
           include snippets/fastcgi-php.conf;  
           fastcgi_pass unix:/run/php/php7.4-fpm.sock;  
       }  
   }  
   ```
---

## 🔍 Проверка работоспособности  
1. Создайте файл `info.php` в корне проекта:  
   
   ```php
   <?php phpinfo(); ?>
   ```
   
2. Откройте его в браузере. Убедитесь, что активны модули:  
   - fileinfo  
   - json  
   - session  

---

## 🔑 Настройка администраторов

Отредактируйте файл `includes/admins.php`:

```php
<?php $ADMINS = array (
  'admin' => 
  array (
    'password' => '$2y$10$DCjIXIdp9qF.HwZAQhkH8OUMtGuKcAyYjFDxSWPyn4OhkecGFCo4S',
    'name' => 'admin1',
  ),
  'admin1' => 
  array (
    'password' => '$2y$10$DCjIXIdp9qF.HwZAQhkH8OUMtGuKcAyYjFDxSWPyn4OhkecGFCo4S',
    'name' => 'admin2',
  ),
); ?>
```
```
Дефолтный логин/пароль
admin/password
```
---
## 🛡️ Рекомендации по безопасности
## # Критически важные меры
1. **HTTPS** (настройка для Apache)
```apache
<VirtualHost *:443>
    SSLEngine on
    SSLCertificateFile /etc/ssl/certs/chat.crt
    SSLCertificateKeyFile /etc/ssl/private/chat.key
</VirtualHost>
```
3. **Очистка неактивных сессий** (Cron):
```bash
0 3 * * * find /path/to/clients/ -type f -mtime +1 -delete
```
5. **Резервное копирование**:
```bash
tar -czvf chat_backup_$(date +\%F).tar.gz chats/ clients/ uploads/
```
---
## 🖥 Использование
- **Клиентская часть**: http://ваш-сервер/chat/client/
- **Административная панель**: http://ваш-сервер/chat/admin/

## 📂 Структура проекта
```
chat/
├── admin/               # Панель администратора
│   ├── clear_chat.php   # Очистка чата
│   ├── close_chat.php   # Закрытие чата
│   ├── dashboard.php    # Основная панель управления
│   ├── get_chat_list.php# Получение списка чатов
│   ├── get_messages.php # Получение сообщений чата
│   ├── index.php        # Перенаправление на страницу входа
│   ├── login.php        # Страница входа для администратора
│   ├── logout.php       # Выход из системы
│   ├── send_message.php # Отправка сообщений от администратора
│   ├── update_chat_status.php # Обновление статуса чата
│   ├── update_hostnames.php   # Обновление имен ПК клиентов
│   └── update_profile.php     # Обновление профиля администратора
├── admin_online/        # Файлы для отслеживания онлайн-статуса администраторов
    ├── index.php        # Защита от прямого доступа
├── assets/              # Ресурсы проекта (стили, скрипты, изображения)
│   ├── css/             # Стили
│   │   ├── admin.css    # Стили для административной панели
│   │   ├── all.min.css  # Минифицированные стили (например, FontAwesome)
│   │   ├── index.php    # Защита от прямого доступа
│   │   └── styles.css   # Основные стили для клиентской части
│   ├── images/          # Изображения
│   │   └── index.php    # Защита от прямого доступа
│   ├── js/              # JavaScript-скрипты
│   │   ├── admin.js     # Скрипты для административной панели
│   │   ├── index.php    # Защита от прямого доступа
│   │   └── script.js    # Скрипты для клиентской части
│   ├── webfonts/        # Шрифты
│   │   └── index.php    # Защита от прямого доступа
│   └── index.php        # Защита от прямого доступа
├── chats/               # История сообщений (JSON-файлы)
│   └── index.php        # Защита от прямого доступа
├── client/              # Клиентская часть
│   ├── get_messages.php # Получение сообщений для клиента
│ ├── get_online_admins.php # Getting the number of online administrators
│ ├── index.php # Main client interface
│ ├── restore_session.php # Restoring a client session
│ └── send_message.php # Sending messages from the client
├── clients/ # Client data (JSON files)
│ └── index.php # Protection against direct access
├── includes/ # System scripts and configurations
│ ├── admins.php # Administrator data (logins, passwords, names)
│ ├── config.php # Basic project settings
│ ├── functions.php # Auxiliary functions (sanitization, CSRF tokens)
│ ├── index.php # Protection against direct access
│ ├── session.php # Session management
│ ├── storage.php # Functions for working with data (saving, updating)
│ └── upload_functions.php # Functions for uploading files
├── logs/ # Error logs
│ ├── error.log # Log file
│ └── index.php # Protection against direct access
├── uploads/ # Uploaded files (images)
│ └── index.php # Protection against direct access
└── index.php # Main file for redirecting to the client side
```

---

> ⚠️ **Important!** Before using in production, conduct a security audit and configure HTTPS.
