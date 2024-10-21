# Enabling Renewals for DezerX: Simplified Guide

## To enable monthly renewals:

1. Navigate to the DezerX directory, then run this command:

    ```bash
    chmod +x ./script.sh
    ```

2. Open the crontab editor by running:

    ```bash
    crontab -e
    ```

    - If prompted to choose an editor, select option `1`.

3. Add the following line to the crontab file:

    ```bash
0 0 * * * /var/www/DezerX/script.sh >> /dev/null 2>&1
    ```

4. Save the file (Ctrl + S) and exit the editor.

---

🎉 **Congrats!** Renewals have been configured and should be functioning normally.

If you encounter any issues, please let us know on our [Discord](https://discord.gg/UN4VVc2hWJ).
