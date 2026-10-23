---
name: frontend-design
description: Maintains and improves the UI/UX for Spendly, a personal expense tracker. Focuses on preserving the original project aesthetic while adding functional polish, real-time validation, and data-driven insights.
disable-model-invocation: true
---

# Spendly UI & Logic Maintainer

You are maintaining the frontend and interaction logic for **Spendly**. The goal is to keep the app lightweight and consistent with the original design while ensuring the user experience is robust and error-free.

## Tech Stack
- **Backend:** Flask (`app.py`), SQLite (`database/`)
- **Templates:** Jinja2 in `templates/`
- **Styles:** vanilla CSS in `static/css/`
- **Scripts:** vanilla JS in `static/js/` for real-time validation and interactions.
- **Icons:** Lucide icons loaded via CDN.

## Design Principles (The "Preserve & Polish" approach)
- **Consistency:** Do not introduce drastic new design systems (e.g., avoid sudden shifts to "fintech" or "modernist" styles unless explicitly asked). Match the existing spacing, colors, and typography.
- **Functional UI:** UI changes should solve a problem. If adding a new feature (like Analytics), design the layout to fit the existing page style.
- **Surgical Edits:** Improve components individually (e.g., better buttons, clearer labels) rather than rewriting entire pages.

## Functional Standards
Whenever implementing or updating pages, adhere to these project rules:

### 1. Validation Logic (Crucial)
All financial inputs must follow these rules:
- **Amount:** Must be a positive float (`> 0`).
- **Date:** Must be a valid date and **cannot be in the future**.
- **Feedback:** Provide both frontend (immediate JS feedback) and backend (Flask flash messages) validation.
- **Confirmation:** Destructive actions (like deleting an expense) must have a browser confirmation dialog.

### 2. Interaction Logic
- **Auto-Redirect:** Logged-in users visiting the landing page (`/`) must be automatically redirected to the profile page.
- **Real-time Validation:** Use `static/js/validation.js` to highlight invalid fields and disable submit buttons before the form is sent.

### 3. Data Mapping (Analytics & Profile)
When working with `get_category_breakdown`, expect a list of dictionaries:
`[{ "name": "Food", "amount": "500.00", "percent": 25 }, ...]`
Always access these via `.name`, `.amount`, and `.percent` in Jinja2 templates.

## Output Structure
When making changes, provide:
1. **Logic Plan:** 2-3 bullets on what is being improved and why.
2. **The Code:** 
   - Template updates (Jinja2).
   - CSS updates (scoped to the specific page/component).
   - JS updates (vanilla JS only).
3. **Verification Step:** How to test that the validation or logic is working as expected.

## What to Avoid
- **Drastic Redesigns:** Do not change the core "look and feel" without explicit permission.
- **External Libraries:** No React, Tailwind, or Bootstrap.
- **Hardcoded URLs:** Always use `url_for()`.
- **Inline Styles:** Keep CSS in separate files.
