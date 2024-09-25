# Updating DezerX

***

Updating DezerX keeps your system stable, secure and allows
your users/admins to experience new features quicker. Use
the following guide below as a reference for updating DezerX.

?>
Take a backup of your installation before continuing.

***

### Maintenance mode

Start by shutting down the Panel while we perform upgrades.

```bash
cd /var/www/dezerx 
php artisan down
```

### Download new version

Next, download the update to your local machine and upload it to the folder at /var/www/dezerx. Be sure to overwrite any existing files during this process.


### Update Composer packages

Due to DezerX staying up-to-date using the latest packages, you
will need to update the Composer dependencies which allow DezerX
to run properly on your machine.

```bash
composer install --no-dev --optimize-autoloader
```

### Sync database changes

You will need to migrate new database information into your
database in order to use the latest DezerX features.

```bash
php artisan migrate --seed --force
```

### Set webserver permissions

After changing the files, we must re-allow permissions for our
webserver so that DezerX can be hosted and accessed properly.

```bash
cd /var/www/dezerx

# ONLY RUN ONE OF THE FOLLOWING COMMANDS!

# If using NGINX or Apache (not on CentOS):
chown -R www-data:www-data *

# If using NGINX on CentOS:
chown -R nginx:nginx *

# If using Apache on CentOS
chown -R apache:apache *
```

?> Any issues? Please reach out to us on [Discord](https://discord.gg/UN4VVc2hWJ).
