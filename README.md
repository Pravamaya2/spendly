Initiaaly project set up and description

● Spendly is a lightweight personal expense tracker designed as an
  educational project to demonstrate the fundamentals of web
  development using a minimal, "no-framework" tech stack.

  🚀 Core Technology Stack

  The project adheres to strict constraints to keep the
  architecture simple and transparent:
  - Backend: Flask (Python) — used for routing and request
    handling.
  - Database: SQLite — a serverless, file-based database for
    storing users and expenses.
  - Frontend: Vanilla JavaScript, HTML (Jinja2 templates), and CSS
    — no modern JS frameworks (like React or Vue) are used.
  - Styling: Pure CSS with a separation between global styles
    (style.css) and page-specific styles (e.g., landing.css).

  🏗️  Architecture

  The project follows a clean, single-responsibility structure:
  - app.py: The central hub containing all application routes.
  - database/db.py: The dedicated layer for all SQLite
    interactions. No database logic is permitted inside the route
    functions.
  - templates/: A collection of HTML files that extend a common
    base.html layout for visual consistency.
  - static/: Houses all CSS and JavaScript assets.

  🛠️  Current Status

  The project is currently in an iterative implementation phase.
  Some core pages are functional, while others are placeholders
  ("stubs") waiting to be developed:


  ┌───────────────────┬────────────────┐
  │      Feature      │     Status     │
  ├───────────────────┼────────────────┤
  │ Landing Page      │ ✅ Implemented │

  ┌───────────────────┬────────────────┐
  │      Feature      │     Status     │
  ├───────────────────┼────────────────┤
  │ Landing Page      │ ✅ Implemented │

  ┌───────────────────┬────────────────┐
  │      Feature      │     Status     │
  ├───────────────────┼────────────────┤
  ┌───────────────────┬────────────────┐
  │      Feature      │     Status     │
  ├───────────────────┼────────────────┤
  │ Landing Page      │ ✅ Implemented │
  ├───────────────────┼────────────────┤
  │ User Registration │ ✅ Implemented │
  ├───────────────────┼────────────────┤
  │ User Login        │ ✅ Implemented │
  ├───────────────────┼────────────────┤
  │ Logout            │ ⏳ Stub        │
  ├───────────────────┼────────────────┤
  │ User Profile      │ ⏳ Stub        │
  ├───────────────────┼────────────────┤
  │ Add Expense       │ ⏳ Stub        │
  ├───────────────────┼────────────────┤
  │ Edit Expense      │ ⏳ Stub        │
  ├───────────────────┼────────────────┤
  │ Delete Expense    │ ⏳ Stub        │
  └───────────────────┴────────────────┘

  📐 Key Development Rules

  To maintain the project's educational goals, it follows several
  strict guidelines:
  - Security: Always uses parameterized queries to prevent SQL
    injection.
  - Routing: Uses Flask's url_for() for all internal links to avoid
    hardcoded URLs.
  - Database: Manual enforcement of Foreign Keys (using PRAGMA
    foreign_keys = ON).
  - Environment: Runs on port 5001 by default.

