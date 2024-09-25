# Stripe Integration with DezerX: Step-by-Step Guide

Integrating Stripe with DezerX is straightforward! Follow these steps for a seamless setup:

## Step 1: Create a Stripe Account
- Visit [Stripe's website](https://stripe.com) and sign up for an account if you don’t already have one.

## Step 2: Obtain API Keys
- After logging into your Stripe dashboard:
  1. Navigate to the **Developers** section in the left sidebar.
  2. Select **API keys**.
  3. Copy your **Publishable Key** and **Secret Key**. You will need these for configuration.

## Step 3: Locate the `.env` File
- Go to your DezerX directory and find the `.env` configuration file.

## Step 4: Add Your Stripe Keys
- Open the `.env` file in a text editor and add your Stripe keys as follows:

```bash
STRIPE_KEY=your_publishable_key_here
STRIPE_SECRET=your_secret_key_here
STRIPE_WEBHOOK_SECRET=your_webhook_secret_here


?>
Congrats! Stripe have been configured and should be functioning normally.
If you encounter any issues, please let us know on our [Discord](https://discord.gg/UN4VVc2hWJ).