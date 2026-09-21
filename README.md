
# Binance Market API + Dashboard

A small Node service that pulls live ticker data from the public Binance API,
ranks trading pairs by their ask/bid ratio and serves the result to a React
dashboard.

## Stack
Node.js · Express · Axios · React

## How it works
- `dataService.js` calls Binance `/api/v3/ticker/bookTicker`, calculates the
  ask/bid ratio for every pair, drops invalid rows and returns the top of the
  sorted list.
- `server.js` exposes it as `GET /api/data` with CORS enabled, so the browser
  app can read it.
- The React app renders the ranked pairs.

## Run locally
```bash
npm install
node server.js   # API on http://localhost:5000
npm start        # React app
```
