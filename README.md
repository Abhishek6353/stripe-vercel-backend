# Stripe Vercel Backend

A serverless backend for a demo iOS app integrating Stripe, deployable on Vercel.

## Features

- Node.js + Stripe official SDK
- Serverless API routes (Vercel)
- ES modules

## Setup

1. **Install dependencies:**
   ```sh
   npm install
   ```
2. **Run locally with Vercel CLI:**
   ```sh
   vercel dev
   ```
3. **Deploy to Vercel:**
   - Push this repo to GitHub
   - Import into Vercel
   - Set environment variable `STRIPE_SECRET_KEY` in Vercel dashboard

## API Endpoints

### POST `/api/create-payment-intent`

- **Body:**
  ```json
  { "amount": 1000, "currency": "usd" }
  ```
- **Returns:**
  ```json
  { "clientSecret": "..." }
  ```

#### Example `curl` command:

```
curl -X POST https://<vercel-project-url>/api/create-payment-intent \
  -H "Content-Type: application/json" \
  -d '{"amount":1000,"currency":"usd"}'
```

## Optional Endpoints (stubs only)

- `/api/create-customer.js` – create Stripe customers
- `/api/ephemeral-key.js` – generate ephemeral keys (requires Stripe-Version header)
