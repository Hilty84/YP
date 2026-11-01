# Yhoo Pay — Complete Frontend Prototype

## Included pages
- index.html — public homepage
- dashboard.html — dashboard
- industry-list.html — industry directory
- trade-list.html — trade directory with filtering
- day-rate-index.html — sample day-rate index
- market-insights.html — sample market insights
- calculator.html — interactive day-rate calculator
- set-day-rate.html — add sample rate entries
- job-records.html — create and view demo job records
- job-issues.html — issue register
- payment-summary.html — payment totals
- payment-history.html — searchable payment history
- worker-profile.html — worker profile
- employer-profile.html — employer profile
- login.html — login interface placeholder
- register.html — registration interface placeholder

## Run it
1. Extract the ZIP.
2. Open `index.html` in a browser, or run a local static server from this folder:
   `python -m http.server 5500`
3. Visit `http://localhost:5500`.

## Demo limitations
- Data is stored in browser localStorage on the current device/browser.
- Demo data is not shared between users or devices.
- Login and registration do not authenticate users.
- No real payment is initiated, held, transferred, or verified.
- Example rates and market indicators are illustrative only.
- This is a frontend prototype, not a production-ready financial platform.

## Python backend integration
The shared JavaScript contains:
- `YHOO_CONFIG.API_BASE_URL`
- `api(path, options)` helper
- Example route structure and comments

When your Python API is ready, set `API_BASE_URL` in `assets/app.js` to your API base URL and implement the corresponding endpoints. Suggested initial endpoints:
- `GET /api/trades`
- `GET /api/rates`
- `GET /api/market-index`
- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/jobs`
- `POST /api/jobs`
- `GET /api/payments`
- `POST /api/payment-requests`

Security requirements:
- Validate all data and permissions on the server.
- Store passwords using a modern password-hashing algorithm; never store plain-text passwords.
- Keep payment-provider secret keys only on the server.
- Verify payment-provider webhooks server-to-server before changing payment status.
- Use HTTPS in production, secure sessions/tokens, CSRF protection where applicable, rate limiting, audit logs and role-based access control.
- Do not describe a payment as escrow or funds held by Yhoo Pay unless the legal, regulatory and provider model supports that.
