
# Enabling AFK for DezerX: Simplified Guide

## Step 1: Setup WebSocket URL

DezerX uses its own WebSocket to connect to AFK using `wss`.

- In the `.env` file, make sure you have set up the `VITE_WEBSOCKET_URL`, which should start with:

    ```bash
    VITE_WEBSOCKET_URL=wss://afk.example.com
    ```

## Step 2: Create NGINX Configuration

Next, create a new NGINX configuration file and add the following settings:

```bash
server {
    listen 80;
    server_name afk.example.com;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl;
    server_name afk.dezerx.com;

    ssl_certificate /etc/letsencrypt/live/afk.example.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/afk.example.com/privkey.pem;

    location / {
        proxy_pass http://localhost:3000;  
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_read_timeout 86400;
    }
}
```

Make sure to replace `afk.example.com` with your actual domain name.

## Step 3: Create a Symlink and Restart NGINX

After configuring NGINX, create a symlink for the configuration and restart the NGINX service to apply changes.

## Step 4: Setup Cron Job

To ensure the WebSocket server runs continuously, set up a cron job:

1. Run `crontab -e`
2. Add the following line:

    ```bash
    php /var/www/DezerX/artisan websocket:serve 2>&1
    ```

3. Save the file (Ctrl + S) and exit the editor.

---

🎉 **Congrats!** You have fully set up DezerX.

If you encounter any issues, please let us know on our [Discord](https://discord.gg/UN4VVc2hWJ).
```

This Markdown version is clean and well-formatted for readability.
