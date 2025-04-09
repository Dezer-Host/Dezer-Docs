# Enabling Console for DezerX: Simplified Guide

## Step 1: Edit Pterodactyl Configuration

1. Open the Pterodactyl configuration file by running:

    ```bash
    nano /etc/pterodactyl/config.yml
    ```

2. Scroll down until you find the following line:

    ```bash
    allowed_origins: []
    ```

3. Modify it to:

    ```bash
    allowed_origins:
    - https://dash.example.com
    - http://dash.example.com
    ```

## Step 2: Restart Wings

After making the changes, restart the wings service:

```bash
systemctl restart wings
