# Enabling Renewals for DezerX: Simplified Guide

## To enable monthly renewals:

1. Open the crontab editor by running:

    ```bash
    crontab -e
    ```

    - If prompted to choose an editor, select option `1`.

3. Add the following line to the crontab file:

    ```bash
0 */2 * * * cd /path/to/dezerx && php artisan monthly:start
    ```

4. Save the file (Ctrl + S) and exit the editor.

---

🎉 **Congrats!** Renewals have been configured and should be functioning normally.

If you encounter any issues, please let us know on our [Discord](https://discord.gg/UN4VVc2hWJ).
