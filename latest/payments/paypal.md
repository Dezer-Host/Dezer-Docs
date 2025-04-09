# 💳 **PayPal Integration with DezerX: Simplified!**

Integrating PayPal with DezerX is a breeze! Just follow these easy steps:

---

## Step 1: Locate the `.env` File

Navigate to your DezerX directory and find the `.env` configuration file.

---

## Step 2: Add PayPal Configuration

Open the `.env` file and add the following PayPal configuration. Replace the placeholders with your actual PayPal credentials.

```bash
# PAYPAL Configuration
PAYPAL_SANDBOX=true  # Set to 'false' for live environment
PAYPAL_CLIENT=your_paypal_client_id
PAYPAL_SECRET=your_paypal_secret_key
```

- **`PAYPAL_SANDBOX`**: Set this to `true` if you're using the sandbox (test) environment for PayPal. Set it to `false` when you're ready for live transactions.
- **`PAYPAL_CLIENT`**: Replace this with your PayPal **Client ID**.
- **`PAYPAL_SECRET`**: Replace this with your PayPal **Secret Key**.

---

## Step 3: Save the File

Once you've added the correct details, save the `.env` file.

---

🎉 **Congrats!** PayPal has been configured and should now be functioning normally.

If you encounter any issues, feel free to reach out to us on our [Discord](https://discord.gg/UN4VVc2hWJ).
