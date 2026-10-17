# CODEX MASTER PROMPT — BULSHO CAR RENTAL INTERACTIVE SALES DEMO

You are a senior full-stack engineer, product designer, and QA lead. Transform the included working static HTML proof-of-concept into a premium, fully interactive, deployable sales demonstration for **Bulsho Car Rental**, commissioned by **Daljir Technology**. This is a SINGLE-COMPANY deployment, NOT a multi-tenant SaaS.

## Objective
Build a polished, fast, mobile-first, client-facing demonstration that allows Bulsho Car Rental management to explore the end-to-end rental business journey without a production backend. Every screen must have useful interactions and believable **clearly fictional** sample data. Keep the existing demo working while upgrading it.

## Technology
- Next.js App Router, TypeScript strict mode, Tailwind CSS, shadcn/ui, Lucide, React Hook Form, Zod, Recharts.
- Feature-based architecture, typed repositories, reusable components, accessible design.
- Seed deterministic mock data; use browser-local persistence (localStorage or IndexedDB) with migration/version handling. Never expose or require real customer information.
- Use Next.js standalone output or a tested Dockerfile with production health check; deploy to Coolify on Hostinger VPS.
- No Supabase, external production API, paid payment gateway, actual WhatsApp messages, or real GPS tracking in this demo.

## Product and brand
- Name: Bulsho Car Rental. Logo must be replaceable from configuration; do not claim the screenshot logo is a usable high-resolution original asset.
- Visual direction: premium automotive brand, navy #0D1B4B, blue #0874C9, amber #F59E0B, white/slate; Space Grotesk headings and Inter body.
- Support Somali/English translations, light/dark themes, keyboard navigation, mobile-first responsive layouts, skeletons, empty states, success/error feedback.
- Persistent, obvious `DEMO — SAMPLE DATA` indicator on all interfaces.

## Interfaces and routes
1. Public website: /, /fleet, /fleet/[id], /search, /book/[id], /about, /services, /corporate, /offers, /contact, /faq.
2. Admin: /admin, /admin/vehicles, /admin/vehicles/[id], /admin/bookings, /admin/calendar, /admin/customers, /admin/drivers, /admin/inspections, /admin/maintenance, /admin/payments, /admin/invoices, /admin/expenses, /admin/contracts, /admin/reports, /admin/content, /admin/settings.
3. Customer portal: /portal, /portal/bookings, /portal/invoices, /portal/contracts, /portal/profile, /portal/support.
4. Driver portal: /driver, /driver/trips, /driver/inspections, /driver/schedule, /driver/profile.
5. /demo-guide: guided presentation walkthrough for a business prospect.

## Mandatory functional flows
- Vehicle search with category, transmission, price, seats, and date filters; interactive detail pages with image galleries.
- Reservation wizard: vehicle -> pickup/return date/time -> customer -> extras -> pricing -> review -> demo confirmation.
- Simulated availability: prevent overlapping active/pending reservations and maintenance blocks; explain date logic and conflicts; include booking extension/cancellation and correct status transitions.
- Bookings created on the public site must immediately appear in admin bookings and in the mock customer portal (within the same browser demo state).
- Admin CRUD for vehicles, mock customers, drivers, bookings, maintenance logs, expense entries; provide form validation, confirmation dialogs, and undo/reset where appropriate.
- Vehicle check-in/check-out inspection demo with condition checklist, fuel, odometer, mock damage notes, and generated preview contract.
- Simulated invoice, partial payment, deposit and refund statuses; NEVER request real card credentials or process real payments.
- Driver trip assignment, mock pickup/return flow, completion status.
- Dashboard with reactive KPIs, utilization, reservations, revenue and costs; charts and CSV export based on current demo state. No static numbers presented as actual business results.
- Language switch, dark mode, responsive mobile navigation, accessible controls.
- Reset Demo and optional predefined scenarios (busy fleet, new booking, maintenance incident, overdue return).
- Explicit demo notices for WhatsApp, EVC Plus, Zaad, Sahal, GPS and AI: only illustrative previews, no live integrations.

## Data model (typed mock repositories)
Vehicle, VehicleCategory, VehicleRate, VehicleBlock, Branch, Customer, Driver, Booking, BookingItem, BookingStatusHistory, Invoice, Payment, Deposit, Expense, MaintenanceRecord, Inspection, DamageReport, RentalAgreement, Notification, UserRole, AuditEvent. Use integer minor units or decimal-safe currency helpers, UTC timestamps, timezone-aware date display. Enforce foreign key-like consistency in mock state.

## Engineering quality
- Build real navigable screens, not screenshots or dead buttons.
- Isolate mock data service from UI so it can later be replaced by NestJS + PostgreSQL + Prisma.
- Use atomic booking updates; define booking state machine; model vehicle operational status separately from date-based availability.
- Avoid unsafe HTML injection, validate all user input, do not persist sensitive ID or license scans in the demo.
- Unit tests for availability conflicts, date calculations, currency, booking transitions and persistence.
- Component tests for filters, forms, navigation, theme and language.
- E2E Playwright tests for public booking -> admin appearance, vehicle status, reset, mobile layout, dark mode, CSV export.
- Run lint, typecheck, tests, production build; fix all failures before completion.

## Deliverables
1. Complete source code in a clean repository.
2. Responsive public site + all three portals.
3. Functional sample dataset and interactive demo workflows.
4. Dockerfile, .dockerignore, .env.example (only non-secret demo config), Coolify deployment instructions.
5. README with architecture, features, commands, screenshots, test evidence, limitations.
6. Business-facing guided presentation script in Somali and English.
7. Final report listing implemented features, tests run, deployment status, known limitations.

## Execution instructions
First inspect the existing files and working demo. Create a clear implementation plan, then implement each phase end-to-end without silently dropping features. Run and verify the application locally. If a tool, external asset, domain or deployment credential is unavailable, clearly state what remains blocked rather than inventing completion or URLs. Never deploy publicly without explicit approval. Do not use real Bulsho Car Rental prices, fleet size, revenue, or customer identities unless provided and authorized. The demo must look professional enough to present to company leadership.
