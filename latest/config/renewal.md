# 🚀 **Enabling Renewals for DezerX: Simplified Guide**

## To enable monthly renewals:

1. **Open the crontab editor** by running the following command:

    ```bash
    crontab -e
    ```

    - If you're prompted to choose an editor, select option `1` (typically `nano` or `vi`).
    - If you're unfamiliar with editors, `nano` is recommended for its simplicity.

2. **Add the following line** to the crontab file to schedule the renewal process every 2 hours:

    ```bash
    0 */2 * * * cd /path/to/dezerx && php artisan monthly:start
    ```

    - Make sure to replace `/path/to/dezerx` with the actual path to your DezerX project directory.

3. **Save and exit the crontab editor**:
    - In `nano`, press `Ctrl + O` to save, then `Ctrl + X` to exit.
    - In `vi`/`vim`, type `:wq` and press `Enter` to save and exit.

---

🎉 **Congratulations!** Renewals have been successfully configured and should now be running every 2 hours. You’re all set!

If you encounter any issues, feel free to reach out to us on our [Discord](https://discord.gg/UN4VVc2hWJ).
