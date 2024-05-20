# nxtbn Stripe Payment Link Plugin

nxtbn's Stripe Payment Link Plugin can be installed in nxtbn ecom in two ways: via the nxtbn dashboard panel or manually by codebase.

## Installation Methods

### Via nxtbn Dashboard

1. Go to **Plugins**.
2. Click on the **Upload Plugin** button.
3. During the upload process, choose the plugin category **payment_processor**.

### Manually by Codebase

1. Download or clone this project.
2. Place the files in your nxtbn codebase at the following location: `nxtbn/payment/plugin/`.

That's it! The plugin will automatically be integrated.

## Configuration

The Stripe Payment Link Plugin requires the following `.env` variables:

```
STRIPE_SUCCESS_URL=
STRIPE_CANCEL_URL=
STRIPE_WEBHOOK_KEY=
STRIPE_SECRET_KEY=
```


### Updating `.env`

You can update the `.env` file either via:

- nxtbn dashboard: **Settings**
- Codebase: 
  ```sh
  nano .env
and then update the .env file with the required variables.
