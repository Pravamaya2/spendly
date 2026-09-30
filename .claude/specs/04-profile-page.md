# Spec: Profile Page Design

## Overview
The Profile Page is the central hub for the logged-in user. It provides a comprehensive overview of their spending habits, including total expenses, transaction count, the top spending category, and a detailed list of recent transactions. This page transforms raw database records into a meaningful financial dashboard.

## Depends on
- 01-database-setup
- 03-login-and-logout

## Routes
- `GET /profile` — Displays the user dashboard — logged-in

## Database changes
No database changes. Relies on `users` and `expenses` tables.

## Templates
- **Create:** `templates/profile.html`
- **Modify:** `templates/base.html` (ensure navigation links reflect logged-in state)

## Files to change
- `app.py` (route logic to fetch user stats and recent transactions)
- `database/queries.py` (implement business logic for summary stats, category breakdown, and transaction listing)

## Files to create
- `templates/profile.html`
- `static/css/profile.css`

## New dependencies
No new dependencies.

## Rules for implementation
- No SQLAlchemy or ORMs
- Parameterised queries only
- Use CSS variables — never hardcode hex values
- All templates extend `base.html`
- Use clear, readable formatting for currency (₹) and dates (e.g., 28 Sep 2026)

## Definition of done
- [ ] `GET /profile` renders the dashboard for logged-in users.
- [ ] Page displays the correct user name and "Member since" date.
- [ ] Summary stats (Total Spent, Total Transactions, Top Category) are correctly calculated.
- [ ] Recent transactions are listed in descending order of date.
- [ ] The layout is responsive and follows the project's design system.
- [ ] Unauthorized users are redirected to `/login`.
