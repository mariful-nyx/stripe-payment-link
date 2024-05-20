# NxtBn's Stripe Payment Link Plugin

NxtBn's Stripe Payment Link Plugin can be installed in NxtBn Ecom in two ways: one is via the NxtBn dashboard panel and another is manually by modifying the codebase.

## Installation

### Via NxtBn Dashboard

1. Go to the Plugins section in the dashboard: `Plugins > Upload Plugin`.
2. During the upload, select the plugin category as `"payment_processor"`.

### Manually

1. Download or clone this project.
2. Place the files in your NxtBn codebase at this location: `nxtbn/payment/plugin/`.

That's it! The plugin will automatically be recognized by the system.

## Configuration

The Stripe Payment Link Plugin requires the following environment variables to be set:

- `STRIPE_SUCCESS_URL=`
- `STRIPE_CANCEL_URL=`
- `STRIPE_WEBHOOK_KEY=`
- `STRIPE_SECRET_KEY=`

### Updating .env Variables

You can update these variables either via the NxtBn dashboard under `Settings` or directly in the codebase using:
```bash
nano .env


# Obtaining Stripe API Keys

To fully integrate the Stripe Payment Link Plugin with your NxtBn Ecom platform, you need to obtain a few specific API keys from Stripe: the Secret Key and the Webhook Key. Here's how you can retrieve these keys:

## Stripe Secret Key

The Stripe Secret Key is essential for server-side interactions with Stripe's API. Follow these steps to obtain your Secret Key:

1. Log in to your Stripe Dashboard.
2. Navigate to the **Developers** section in the sidebar.
3. Under **API keys**, you'll find your Secret Key. It's recommended to use the key in test mode first to ensure everything works as expected before switching to live mode.

## Stripe Webhook Key

The Webhook Key is necessary for receiving callbacks from Stripe to your server. Here's how to set it up:

1. In the Stripe Dashboard, go to **Developers** > **Webhooks**.
2. Click on **+ Add endpoint** and enter the URL where you want to receive the webhook events. If you use this plugin, your webhook endpoint is: `/payment/storefront/api/webhook-view/{payment_plugin_id}`
Here `{payment_plugin_id}` should be `stripe-payment-link` or the directory name you give inside the `nxtbn/payment/plugin` directory.
3. Select the events you want to listen to, for example, payment intents or charge completions.
4. After setting up the endpoint, Stripe will generate a Webhook Secret (your Webhook Key), which you will use to validate received events.

Ensure you store these keys securely and only in your environment variables to protect sensitive information.

