# MediCare Pro — Doctor Demo

**Demo:** [https://sakshsky.com/demo/doctor/](https://sakshsky.com/demo/doctor/)

**Repository:** [https://github.com/sakshsky/doctor-demo](https://github.com/sakshsky/doctor-demo)

---

A clean, modern, responsive landing page for a healthcare/clinic website built with Tailwind CSS and minimal vanilla JavaScript. This repository contains a static demo showcasing a hero, services, appointment booking (WhatsApp), testimonials, and a dark mode toggle.

## Table of contents

* [Features](#features)
* [Tech stack](#tech-stack)
* [Preview](#preview)
* [Local setup](#local-setup)
* [Development tips](#development-tips)
* [Deployment (GitHub Pages)](#deployment-github-pages)
* [Customizations](#customizations)
* [Accessibility & performance notes](#accessibility--performance-notes)
* [Contributing](#contributing)
* [Issues & support](#issues--support)
* [License](#license)

---

## Features

* Responsive landing page built with **Tailwind CSS**.
* Light / Dark theme toggle (uses `class`-based dark mode and `localStorage`).
* WhatsApp-based appointment booking with pre-filled message.
* Animated hero, service cards, counters, and testimonial slider.
* Simple, dependency-free JavaScript — no build step required.
* Clean, semantic HTML that’s easy to fork and customize.

## Tech stack

* HTML5
* Tailwind CSS (CDN)
* Font Awesome (CDN)
* Vanilla JavaScript (no frameworks)
* Google Fonts (Inter)

## Preview

Open the hosted demo: [https://sakshsky.com/demo/doctor/](https://sakshsky.com/demo/doctor/)

Screenshots and additional assets (if any) are available in the repository.

## Local setup

Clone the repo and open the demo locally:

```bash
# clone
git clone https://github.com/sakshsky/doctor-demo.git
cd doctor-demo

# Option A: open index.html directly
# - Double-click index.html or open it in the browser

# Option B: run a simple HTTP server (recommended to avoid some browser restrictions)
# Python 3.x
python -m http.server 8000
# then open http://localhost:8000 in your browser

# Option C: VS Code Live Server extension
# - Install Live Server and click "Go Live"
```

Because the project uses CDN links for Tailwind and Font Awesome, there is no build step required. If you prefer a build toolchain for Tailwind, you can integrate PostCSS / Tailwind CLI.

## Development tips

* To change the WhatsApp number used by the booking button, edit the `whatsappNumber` variable in the script near the top of the file (search for `const whatsappNumber`). Use the international format without the `+` (for example `15551234567`).
* The booking script constructs a pre-filled message using form inputs. If you want server-side booking, replace the `window.open` call with an API call to your backend.
* Tailwind is added via CDN for convenience. If you want smaller CSS files and purging, switch to a local Tailwind build using the official Tailwind CLI or PostCSS.
* Icons are provided by Font Awesome CDN — swap for local SVGs if you prefer.

## Deployment (GitHub Pages)

### Option 1 — Deploy `main` branch via GitHub Pages

1. Push your repository to GitHub (if not already):

```bash
git remote add origin git@github.com:sakshsky/doctor-demo.git
git push -u origin main
```

2. On GitHub, go to **Settings → Pages** (or **Pages** in the left sidebar for newer layouts).
3. Under **Source**, choose the `main` branch and root (`/`) folder (or `gh-pages` branch if you prefer) and click **Save**.
4. After a minute, your site will be available at `https://<your-username>.github.io/<repo-name>/` or a custom domain if configured.

### Option 2 — Use `gh-pages` branch (optional)

You can publish a static `gh-pages` branch using the `gh-pages` npm package or create the branch and push compiled assets there.

### Using a custom domain

If you want the demo to be served from `https://sakshsky.com/demo/doctor/` (like the current demo), configure the web server or CDN that hosts `sakshsky.com` to point the subpath to the repository’s `index.html`. GitHub Pages supports custom domains for an entire repository but not for subpaths — serving from a `/demo/doctor/` subpath likely requires a host-side configuration (e.g., upload static files to your web host under that subpath).

## Customizations

* **Branding colors:** adjust `:root` CSS variables at the top of the HTML to change primary/secondary colors and dark-theme colors.
* **Clinic info:** change phone numbers, address, email, open hours in the header/footer/announcement bar.
* **Form & booking flow:** the `appointmentForm` currently opens WhatsApp with a prefilled message. Replace or extend this logic to post to your backend for persistent booking.
* **Services & doctors:** update the markup inside the `#services` section and the floating doctor card in the hero.

## Accessibility & performance notes

* Test color contrast (especially for custom brand colors) to ensure accessibility.
* If you add heavy images, consider lazy-loading (`loading="lazy"`) to improve performance.
* Consider moving Tailwind to a build process for production to purge unused CSS and reduce file sizes.

## Contributing

Contributions are welcome! If you’d like to contribute:

1. Fork the repo
2. Create a feature branch: `git checkout -b feat/my-change`
3. Commit your changes: `git commit -m "feat: add ..."`
4. Push and open a pull request

Please open issues for bugs or feature requests.

## Issues & support

For bugs and feature requests, please use the repository issues page:

[https://github.com/sakshsky/doctor-demo/issues](https://github.com/sakshsky/doctor-demo/issues)

Or contact the maintainer directly via the email in the footer (if provided) or GitHub profile.

## License

This project is distributed under the **MIT License**. See `LICENSE` for details.

---

### Quick changelog / notes for maintainers

* The demo is intentionally dependency-light to make it easy to host and fork.
* If you want a scaffolding for a production-ready clinic site, consider adding a backend (Node/Express, Django, etc.) for bookings, validation, and user authentication.

---

> Built with ❤️ — feel free to fork and customize for your clinic or portfolio.
