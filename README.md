# Task 3 - Login Page UI

This is my submission for Task 3 of the Synent Technologies internship assessment. The goal was to build a clean, functional login page using only HTML and CSS — no frameworks allowed.

---

## What I Built

A login page with a centered card layout. Kept the design minimal but tried to make it look like something you'd actually use, not just a plain form thrown on a white background.

The page has:
- Email and password input fields with icons inside them
- Real-time email format validation with error messages shown under the field
- Strong password enforcement — must include uppercase, lowercase, a number, and a symbol
- A live password strength bar that updates as you type (Weak / Medium / Strong)
- A show/hide toggle on the password field
- A "Forgot Password?" link that opens a modal popup with its own email field and validation
- An "Apply Here" link that opens a full internship application form in a modal
- A login button with a hover effect and a loading spinner when clicked
- Toast notifications that slide in at the top for success and error states
- Responsive layout that works on mobile and desktop

---

task3-login-page/
├── login.html
├── style.css
├── README.md
├── screenshots/
│   ├── 01-login-page-desktop.png
│   ├── 02-validation-errors.png
│   ├── 03-password-strength.png
│   ├── 04-forgot-password-modal.png
│   ├── 05-apply-form-modal.png
│   └── 06-mobile-view.png
└── report/
    └── task3-report
```

---

## How to Run

No setup needed. Just download both files, keep them in the same folder, and open `login.html` in any browser. That's it.

---

## Design Decisions

I went with a warm off-white background (`#f5f0e8`) instead of the typical white or dark navy that most login pages use. The accent color is a terracotta (`#c4623a`) with sage green (`#5a7a5e`) for the links. I picked these because they felt more personal and less like a template.

For fonts I used Fraunces (a serif with a nice italic) for the heading and DM Sans for the form — wanted the heading to have some character without going overboard.

The card has a slight offset shadow (`5px 5px 0px`) which gives it a grounded feel rather than the floating glassmorphism look everyone uses. Modals follow the same style — white box, same border radius, same shadow logic.

---

## Tech Used

- HTML5 (semantic tags — `<main>`, `<header>`, `<form>`, `<footer>`)
- CSS3 (Flexbox, CSS custom properties, transitions, keyframe animations, Grid for the two-column name fields)
- Vanilla JavaScript (form validation, modal control, DOM manipulation — no libraries at all)

---

## What the JS Does

**Login form:**
- Stops the page from refreshing on submit (`e.preventDefault()`)
- Validates email format using a regex check — flags empty fields and invalid formats separately
- Validates password against 5 rules: minimum 8 characters, one uppercase, one lowercase, one number, one symbol
- Shows specific error messages under each field with a red border highlight
- Shows a loading spinner on the button for 1.8 seconds to simulate a real login request
- Resets the form and clears the strength bar after successful login

**Password field:**
- Toggles between `type="password"` and `type="text"` with the eye icon
- Live strength bar calculates how many of the 5 rules are met and colours accordingly

**Forgot Password modal:**
- Opens as an overlay when the link is clicked
- Has its own email field with validation
- Closes on X button or clicking outside the modal
- Shows a toast on successful submission

**Apply Here modal:**
- Opens a full application form with first name, last name, email, role, and a message field
- All fields are validated before submission
- Message must be at least 20 characters
- Closes and shows a success toast when submitted correctly

---

## Commits

This repo has 5 commits showing how the project was built step by step:

1. Added base HTML structure and login form layout
2. Added CSS reset, custom properties, and card styles
3. Styled input fields, labels, focus states, and responsive breakpoints
4. Added submit button hover effects and loading spinner
5. Added JS validation, password strength bar, toast notifications, forgot password modal, and apply form modal

---

## Notes

The login doesn't connect to any backend — it's purely a frontend UI task. The form simulates a login with a short delay and then resets. To hook it up to a real server you'd replace the `setTimeout` block with a `fetch()` call to your API endpoint, pass the email and password in the request body, and handle the response from there.

Both modals (forgot password and apply form) also simulate submission — in a real app these would POST to a backend route.
