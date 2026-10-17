# Bulsho Car Rental — Interactive Demo

A standalone, responsive interactive demo with browser-local mock data. No production backend, real payment processing, or real booking availability.

## Run locally

Open `index.html` in a browser, or run `python3 -m http.server 8080` and visit http://localhost:8080.

## Deploy on Coolify

1. Push this folder to a private GitHub repository.
2. In Coolify, create an Application from the repository using **Dockerfile** build pack.
3. Expose container port `80` and set a demo domain with HTTPS.
4. Protect access using Coolify/edge basic authentication or Cloudflare Access before sharing.
5. Validate mobile, navigation, booking flow, and reset behavior.

## Data handling

All data is fictional, demo-only and stored in browser `localStorage`. Each browser has its own state. No credentials or real identity documents should be entered. Reset Demo clears the demo state. Payment simulation never charges money.

## Screens

Public website, vehicle fleet and filters, booking wizard, customer portal, admin overview, fleet management, reservations, customers, drivers, finance, maintenance, reports, and driver portal.
