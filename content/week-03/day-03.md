+++
title = "Day 03 - 30/09/2026 (Remote)"
weight = 3
+++

## Started Coding the Login Page

Started implementation based on yesterday's UI design, beginning with the Login page.

- Set up the `auth` module/feature folder following the repo's existing conventions.
- Built the Login page layout in React/Next.js from the approved design: logo, email/username field, password field, submit button, and error message area.
- Added form validation (required fields, email format) before calling the API.
- Wired the login form to the Auth API endpoint provided in the repo and handled the loading/error/success states.
- Stored the returned auth token and redirected to the Dashboard on successful login.
- Tested the login flow locally with valid and invalid credentials to confirm error handling works as expected.
