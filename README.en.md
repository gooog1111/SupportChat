<!-- LANG_START -->
🇷🇺 [Русская версия](README.md)
<!-- LANG_END -->

<div align="center">

<img src="resources/header.svg" alt="SupportChat" width="900"/>

</div>





<!-- STATS_START -->
<!-- auto-updated by GitHub Actions · 2026-07-10 07:01 UTC -->

[![Views local](https://img.shields.io/badge/Views_local-67-ff6900?style=for-the-badge&logo=github)](https://github.com/gooog1111/SupportChat)
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
<!-- auto-updated by GitHub Actions · 2026-07-10 07:01 UTC -->

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




## Чат технической поддержки

## ⚠️ Внимание  
Этот файл прошел автоматическую редактуру.

---

Простой и (не очень) безопасный чат для организации технической поддержки с разделением на клиентский и административный интерфейсы. Работает на Apache, Nginx или IIS без использования БД и Node.js.

![Пример интерфейса поьзователя](https://github.com/gooog1111/supportchat/blob/main/chat/assets/images/client.png)

---

![Пример интерфейса администратора](https://github.com/gooog1111/supportchat/blob/main/chat/assets/images/admin.png)

---

## 🚀 Особенности
- **Клиентская часть**  
  - 📤 Отправка текста и изображений (до 5 МБ)
  - 📅 История переписки
  - 🕒 Группировка сообщений по времени (интервал 2 минуты)
  - 🔄 Автоматическое восстановление сессии  
  - 👤 Уникальный идентификатор сессии для каждого клиента
- **Административная панель**
  - 🎯 Динамическое обновление чатов (каждые 10 сек)
  - 🚦 Система статусов:
    - `🟢 Открыт` 
    - `🟡 В работе (Имя админа)`
    - `🔴 Закрыт`
  - 🛠 Управление чатами (открытие/закрытие/очистка)  
  - 🔍 Просмотр метаданных клиентов (IP, имя ПК)  
  - 📊 Статусы чатов (Открыт, В работе, Закрыт)  
  - 🔄 Автоматическое обновление списка чатов
- **Безопасность**  
  - 🔒 Защита от XSS и CSRF  
  - 🔑 Система сессий и авторизации  
  - 📁 Хранение данных в JSON-файлах  
  - 🔄 Регулярная очистка неактивных сессий
- **Адаптивность**  
  - 📱 Оптимизирован для мобильных устройств

## ⚙️ Требования к серверу
## # Обязательные компоненты
| Компонент       | Минимальная версия | 
|-----------------|--------------------|
| PHP             | 7.4+              |
| Веб-сервер      | Apache/Nginx/IIS  | 

## # Необходимые модули PHP
```bash
sudo apt install php7.4-fileinfo php7.4-json php7.4-session  # Для Linux
```
- **Веб-сервер**: Apache, Nginx или IIS  
- **Права на запись** для папок: `uploads/`, `chats/`, `clients/`, `logs/`  

---

## ⚙️ Установка

## # 🪟 Windows  
## ## Для IIS:  
1. Установите [PHP для Windows](https://windows.php.net/download/) и добавьте путь к PHP в переменную `PATH`.  
2. В **Диспетчере IIS**:  
   - Создайте сайт с корневой папкой проекта.  
   - Настройте обработчик `*.php` на `php-cgi.exe`.  
3. Настройте права:  
   ```powershell  
   icacls "C:\путь_к_проекту" /grant IIS_IUSRS:(OI)(CI)F  
   ```
## ## Для Apache (через XAMPP/WAMP):  
1. Скопируйте папку `chat` в `htdocs/`.  
2. Добавьте виртуальный хост:  
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
3. Перезапустите Apache.

---

## # 🐧 Linux  
## ## Apache:  
1. Установите пакеты:  
   ```bash  
   sudo apt install apache2 php libapache2-mod-php php-fileinfo  
   ```
2. Разместите проект в `/var/www/html/chat`.  
3. Настройте виртуальный хост:  
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
       
       location / {  
           try_files $uri $uri/ /index.php?$args;  
       }  
       
location ~ \.php$ {  
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
Default login/password
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
├── admin/ # Administrator panel
│ ├── clear_chat.php # Clearing chat
│ ├── close_chat.php # Closing the chat
│ ├── dashboard.php # Main control panel
│ ├── get_chat_list.php# Getting a list of chats
│ ├── get_messages.php # Receive chat messages
│ ├── index.php # Redirect to login page
│ ├── login.php # Login page for administrator
│ ├── logout.php # Logout
│ ├── send_message.php # Sending messages from the administrator
│ ├── update_chat_status.php # Update chat status
│ ├── update_hostnames.php # Update client PC names
│ └── update_profile.php # Update the administrator profile
├── admin_online/ # Files for tracking the online status of administrators
    ├── index.php # Protection against direct access
├── assets/ # Project resources (styles, scripts, images)
│ ├── css/ # Styles
│ │ ├── admin.css # Styles for the admin panel
│ │ ├── all.min.css # Minified styles (for example, FontAwesome)
│ │ ├── index.php # Protection against direct access
│ │ └── styles.css # Basic styles for the client side
│ ├── images/ # Images
│ │ └── index.php # Protection against direct access
│ ├── js/ # JavaScript scripts
│ │ ├── admin.js # Scripts for the administrative panel
│ │ ├── index.php # Protection against direct access
│ │ └── script.js # Scripts for the client side
│ ├── webfonts/ # Fonts
│ │ └── index.php # Protection against direct access
│ └── index.php # Protection against direct access
├── chats/ # Message history (JSON files)
│ └── index.php # Protection against direct access
├── client/ # Client part
│ ├── get_messages.php # Receiving messages for the client│   ├── get_online_admins.php # Получение количества онлайн-администраторов
│   ├── index.php        # Основной интерфейс клиента
│   ├── restore_session.php # Восстановление сессии клиента
│   └── send_message.php # Отправка сообщений от клиента
├── clients/             # Данные о клиентах (JSON-файлы)
│   └── index.php        # Защита от прямого доступа
├── includes/            # Системные скрипты и конфигурации
│   ├── admins.php       # Данные администраторов (логины, пароли, имена)
│   ├── config.php       # Основные настройки проекта
│   ├── functions.php    # Вспомогательные функции (санитизация, CSRF-токены)
│   ├── index.php        # Защита от прямого доступа
│   ├── session.php      # Управление сессиями
│   ├── storage.php      # Функции для работы с данными (сохранение, обновление)
│   └── upload_functions.php # Функции для загрузки файлов
├── logs/                # Логи ошибок
│   ├── error.log        # Файл логов
│   └── index.php        # Защита от прямого доступа
├── uploads/             # Загруженные файлы (изображения)
│   └── index.php        # Защита от прямого доступа
└── index.php            # Главный файл для перенаправления на клиентскую часть
```

---

> ⚠️ **Важно!** Перед использованием в продакшене проведите аудит безопасности и настройте HTTPS.
