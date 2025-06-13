### DezerX Subscriptions and Cron Jobs Setup Guide

Here's your complete guide for setting up cron jobs and queue workers for your Laravel application, with an important notice about directory paths:

## Important Notice ⚠️

**Before proceeding, verify your correct application directory path!**

- Some systems may use `/var/www/DezerX` (capital D, capital X)
- Others may use `/var/www/dezerx` (all lowercase)

Please check your actual directory structure and replace all instances of the path in the commands below with your correct path.

## 1. Setting Up Cron Job

First, open your crontab file for editing:

```shellscript
crontab -e
```

Add the following line to run Laravel's scheduler every minute:

```shellscript
* * * * * cd /path/to/your/DezerX && php artisan schedule:run >> /dev/null 2>&1
```

Save and exit the editor.

## 2. Creating a Systemd Service for Queue Worker

Create a systemd service file:

```shellscript
sudo nano /etc/systemd/system/dezerx.service
```

Add the following content:

```plaintext
[Unit]
Description=Laravel Queue Worker for DezerX
After=network.target

[Service]
User=www-data
Group=www-data
WorkingDirectory=/path/to/your/DezerX
ExecStart=/usr/bin/php /path/to/your/DezerX/artisan queue:work --queue=critical,high,medium,default,low --sleep=3 --tries=3
Restart=always
RestartSec=5
StartLimitBurst=3
StartLimitIntervalSec=60
StandardOutput=syslog
StandardError=syslog
SyslogIdentifier=dezerx-worker

[Install]
WantedBy=multi-user.target
```

Save and exit the editor.

## 3. Enable and Start the Service

Reload systemd to recognize the new service:

```shellscript
sudo systemctl daemon-reload
```

Enable the service to start on boot:

```shellscript
sudo systemctl enable dezerx.service
```

Start the service:

```shellscript
sudo systemctl start dezerx.service
```

## 4. Check Service Status

Verify that the service is running correctly:

```shellscript
sudo systemctl status dezerx.service
```

This should show you the status of the service, including whether it's active (running) and any recent log entries.
