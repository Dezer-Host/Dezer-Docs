# DezerX Subscriptions and cron jobs

## 1. Setting Up Cron Job

First, open your crontab file for editing:

```bash
crontab -e
```

Add the following line to run Laravel's scheduler every minute:

```bash
* * * * * cd /var/www/DezerX && php artisan schedule:run >> /dev/null 2>&1
```

Save and exit the editor.

## 2. Creating a Systemd Service for Queue Worker

Create a systemd service file:

```bash
sudo nano /etc/systemd/system/dezerx.service
```

Add the following content:

```
[Unit]
Description=Laravel Queue Worker for DezerX
After=network.target

[Service]
User=www-data
Group=www-data
WorkingDirectory=/var/www/DezerX
ExecStart=/usr/bin/php /var/www/DezerX/artisan queue:work --queue=high,medium,default,low --sleep=3 --tries=3 --timeout=300
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

```bash
sudo systemctl daemon-reload
```

Enable the service to start on boot:

```bash
sudo systemctl enable dezerx.service
```

Start the service:

```bash
sudo systemctl start dezerx.service
```

## 4. Check Service Status

Verify that the service is running correctly:

```bash
sudo systemctl status dezerx.service
```

This should show you the status of the service, including whether it's active (running) and any recent log entries.
