# Spec: Login and Logout

## Overview
This feature enables users to securely access their personal expense data and end their sessions. It involves verifying user credentials against the stored password hashes in the database and managing user state via Flask sessions.

## Depends on
- 01-database-setup
- 02-registration

## Routes
- `GET /login` — Displays the login form — public
- `POST /login` — Authenticates user and starts session — public
- `GET /logout` — Clears session and redirects to landing — logged-in

## Database changes
No database changes. Uses the existing `users` table and `get_user_by_email` helper.

## Templates
- **Create:** `templates/login.html`
- **Modify:** `templates/base.html` (ensure navigation links for login/logout are correctly handled)

## Files to change
- `app.py` (implement `/login` and `/logout` route logic)
- `database/db.py` (ensure `get_user_by_email` is robust)

## Files to create
- `templates/login.html`
- `static/css/login.css` (for page-specific styling)

## New dependencies
No new dependencies.

## Rules for implementation
- No SQLAlchemy or ORMs
- Parameterised queries only
- Passwords verified with `werkzeug.security.check_password_hash`
- Use CSS variables — never hardcode hex values
- All templates extend `base.html`
- Session must store `user_id` and `user_name` upon successful login
- Logout must completely clear the Flask session

## Definition of done
- [ ] `GET /login` renders the login page.
- [ ] `POST /login` with correct credentials starts a session and redirects to `/profile`.
- [ ] `POST /login` with incorrect credentials shows an "Invalid email or password" error.
- [ ] `GET /logout` clears the session and redirects to the landing page.
- [ ] Protected routes (e.g., `/profile`) are inaccessible without an active session.
