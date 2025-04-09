# 🚀 **Enabling Console for DezerX: Simplified Guide**

## Step 1: Edit Pterodactyl Configuration

1. **Open the Pterodactyl configuration file** by running the following command:

    ```bash
    sudo nano /etc/pterodactyl/config.yml
    ```

    - If you're using a different text editor (e.g., `vi` or `vim`), replace `nano` with your preferred editor.

2. **Scroll down** until you find the following line in the configuration file:

    ```bash
    allowed_origins: []
    ```

3. **Modify it** to include the allowed origins for your DezerX dashboard:

    ```bash
    allowed_origins:
    - https://dash.example.com
    - http://dash.example.com
    ```

    - Replace `https://dash.example.com` and `http://dash.example.com` with your actual dashboard URLs.

---

## Step 2: Restart Wings

After saving the configuration changes, you need to **restart the Wings service** to apply them. Run:

```bash
sudo systemctl restart wings
```

---

🎉 **Done!** The console for DezerX should now be enabled and ready to use!

If you encounter any issues, feel free to reach out to us on our [Discord](https://discord.gg/UN4VVc2hWJ).
