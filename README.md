# Task 3 - Login Page UI

This is my submission for Task 3 of the Synent Technologies internship assessment. The goal was to build a clean, functional login page using only HTML and CSS — no frameworks allowed.

---

## What I Built

A login page with a centered card layout. Kept the design minimal but tried to make it look like something you'd actually use, not just a plain form thrown on a white background.

The page has:
- Email and password input fields with icons inside them
- A show/hide toggle on the password field
- A "Forgot password?" link
- A login button with a hover effect and a loading spinner when clicked
- A small toast notification that pops up for success and error messages
- Responsive layout that works on mobile too

---

## Files

```
task3-login-page/
├── login.html       — main HTML file with structure and JS
├── style.css        — all the styling
```

---

## How to Run

No setup needed. Just download both files, keep them in the same folder, and open `login.html` in any browser. That's it.

---

## Design Decisions

I went with a warm off-white background (`#f5f0e8`). The accent color is a terracotta (`#c4623a`) with sage green (`#5a7a5e`) for the links. I picked these because they felt more personal."

For fonts I used Fraunces (a serif with a nice italic) for the heading and DM Sans for the form — wanted the heading to have some character without going overboard.

The card has a slight offset shadow (`5px 5px 0px`) which gives it a grounded, slightly editorial feel rather than the floating glassmorphism look everyone uses.

---

## Tech Used

- HTML5 (semantic tags — `<main>`, `<header>`, `<form>`, `<footer>`)
- CSS3 (Flexbox, custom properties, transitions, keyframe animations)
- Vanilla JavaScript (form validation, DOM manipulation, no libraries)

---

## What the JS Does

- Stops the form from refreshing the page on submit (`e.preventDefault()`)
- Checks that both fields are filled before proceeding
- Shows a loading spinner on the button for 1.8 seconds to simulate a real login request
- Toggles the password field between `type="password"` and `type="text"`
- Shows a toast message at the top of the screen for both success and error states
- The "Forgot password?" link also triggers a toast instead of navigating away

---

## Commits

This repo has few commits showing how the project was built step by step:

- Added base HTML structure and login form layout
- Added CSS reset, custom properties, and card styles
- Styled input fields, labels, and focus states
- Added submit button hover effects and loading spinner
- Added JS for form validation, toast notifications, and password toggle

---

## Notes

The login doesn't connect to any backend — it's purely a frontend UI task. The form simulates a login with a short delay and then resets. To hook it up to a real server you'd replace the `setTimeout` block with a `fetch()` call to your API endpoint.
