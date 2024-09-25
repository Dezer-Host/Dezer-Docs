# Environment Setup

***

### Create Configuration File

To set up DezerX, you'll need to create a configuration file based on the provided example. Follow these steps:

1. Copy the example configuration file:

```bash
cp .env.example .env
```

2. Open the `.env` file in your preferred text editor and update the following sections:

#### Database Configuration
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=DezerX
DB_USERNAME=root
DB_PASSWORD=your_password_here
```

#### Integration Settings
```
# Discord Webhook for notifications
DISCORD_WEBHOOK_URL=https://discord.com/api/webhooks/your_webhook_url

# ProxyCheck API for VPN detection
PROXYCHECK_API_KEY=your_proxycheck_api_key

# Cloudflare Turnstile for bot protection
TURNSTILE_SITE_KEY=your_turnstile_site_key
TURNSTILE_SECRET_KEY=your_turnstile_secret_key

# Discord OAuth for authentication
DISCORD_CLIENT_ID=your_discord_client_id
DISCORD_CLIENT_SECRET=your_discord_client_secret
DISCORD_REDIRECT_URI=https://your-domain.com/auth/discord/callback

# Pterodactyl Panel integration
PTERODACTYL_API_URL=https://panel.your-domain.com
PTERODACTYL_API_KEY=your_pterodactyl_api_key
PTERODACTYL_CLIENT_KEY=your_pterodactyl_client_key

# PayPal integration
PAYPAL_SELLER_EMAIL=your_paypal_email@example.com
```

Replace all placeholder values (like `your_password_here`, `your_webhook_url`, etc.) with your actual credentials and settings.

Make sure to keep your `.env` file secure and never share it publicly, as it contains sensitive information.
***

### Install Composer packages
After this, we'll need to install Composer dependencies - which will allow the PHP code in our project
(such as the backend and admin-side) to run properly.

```bash
composer install --no-dev --optimize-autoloader
```

Finally, we'll generate a random token which will be the encryption/app key for our project.

!> This encryption key is used to store important data (such as API keys).
Do NOT share this key with anyone - protect it like a password.
If you lose this key, all data is impossible to recover.

```bash
php artisan key:generate --force
```


### Database Migration
Now we need to set up all the base data for the Panel in the database you created earlier. The command below may take some time to run depending on your machine. Please **DO NOT exit the process** until it is completed!

```bash
php artisan migrate --seed --force
```

***

### Assign Permissions
In order for the webserver you're using to access the Panel files, we'll need to assign it permissions
with the `chown` command. Here's how to do this for all types of webservers:
```bash
# If using NGINX or Apache (not on CentOS):
chown -R www-data:www-data /var/www/dezerx/*

# If using NGINX on CentOS:
chown -R nginx:nginx /var/www/dezerx/*

# If using Apache on CentOS:
chown -R apache:apache /var/www/dezerx/*
```