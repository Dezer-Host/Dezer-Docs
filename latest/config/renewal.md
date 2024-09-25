# Enabling Renewals for DezerX: Simplified Guide

Enabling renewals in DezerX is straightforward. Follow these easy steps to set up automatic renewals for your system.

## Steps to Enable Renewals

### 1. Navigate to the DezerX Directory

Open your terminal and change to the DezerX directory:

```bash
cd /var/www/DezerX
```

### 2. Create the Renewal Script

Use a text editor to create and edit the renewal script:

```bash
nano renewal.sh
```

Add the following script to `renewal.sh`:

```bash
#!/bin/bash
for i in {1..60}
do
    /usr/bin/php /var/www/DezerX/artisan servers:suspend-expired
    sleep 1
done
```

Save and exit the text editor (for nano, press CTRL + X, then Y, and Enter).

### 3. Make the Script Executable

Change the permissions of the `renewal.sh` script to make it executable:

```bash
chmod +x renewal.sh
```

### 4. Schedule the Script with Cron

Open the crontab file for editing:

```bash
crontab -e
```

Add the following line to run the renewal script every minute:

```bash
* * * * * /var/www/DezerX/renewal.sh
```

Save and exit the crontab editor.

## Disabling Renewals

To disable the renewals:
1. Go to the admin area of your application
2. Set the duration to 0

## Notes

- The renewal script runs every second, checking for expired servers to suspend.

?>
Congrats! Renewals have been configured and should be functioning normally.
If you encounter any issues, please let us know on our [Discord](https://discord.gg/UN4VVc2hWJ).