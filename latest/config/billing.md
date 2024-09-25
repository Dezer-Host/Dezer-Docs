# for the billing:
```bash
crontab -e
```
***
## If needed, always choose option 1
```bash
* * * * * cd /var/www/DezerX && php artisan schedule:run >> /dev/null 2>&1
```
?>
Congrats! Billing have been configured and should be functioning normally.
If you encounter any issues, please let us know on our [Discord](https://discord.gg/UN4VVc2hWJ).