# Spec: Registration

## Overview
This feature allows new users to create an account in Spendly. It provides a registration form where users can enter their name, email, and password. The system will validate the input, hash the password for security, and store the user in the database.

## Depends on
- 01-database-setup

## Routes
- `GET /register` — Displays the registration form — public
- `POST /register` — Processes registration form and creates user account — public

## Database changes
No database changes. The `users` table already exists with the required columns (`name`, `email`, `password_hash`).

## Templates
- **Create:** `templates/register.html`
- **Modify:** `templates/base.html` (ensure navigation link to registration exists)

## Files to change
- `app.py` (implemented the `/register` route logic)
- `database/db.py` (utilize `create_user` function)

## Files to create
- `templates/register.html`
- `static/css/register.css` (for page-specific styling)

## New dependencies
No new dependencies.

## Rules for implementation
- No SQLAlchemy or ORMs
- Parameterised queries only
- Passwords hashed with werkzeug
- Use CSS variables — never hardcode hex values
- All templates extend `base.html`
- Email must be unique (handled by database UNIQUE constraint)
- Password and confirm password must match

## Definition of done
- [ ] `GET /register` renders the registration page with a form.
- [ ] `POST /register` successfully creates a user in the database with a hashed password.
- [ ] Registration fails and shows an error if any field is empty.
- [ ] Registration fails and shows an error if passwords do not match.
- [ ] Registration fails and shows an error if the email is already taken.
- [ ] Successful registration redirects to the login page with a success message.
