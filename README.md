# Shubham Bansode — Portfolio

Personal portfolio website built with static **HTML/CSS/JavaScript**. It presents a single-page layout (scroll sections) with interactive UI behaviors (active nav highlighting, typing headline, orbiting tech icons) and a working contact form powered by **EmailJS** (no backend required).

**Live URL:** https://shubham-bansode.netlify.app/

---

## Project Overview (Analysis)

### Pages / Layout

- **Single-page application style (no routing):** one `index.html` with multiple sections.
- **Sections present in the UI:** Home, About, Projects, Experience, Education, Contact.

### Key UI/UX Behaviors

- **Responsive navigation**
  - Desktop: horizontal nav.
  - Mobile: hamburger toggles the menu open/close.
- **Active section highlighting (scroll spy)**
  - Uses `IntersectionObserver` to detect the section in view and apply `.active` to the matching nav link.
- **Typing headline effect**
  - Rotates phrases (e.g., “Web Developer”, “Front-End”, etc.) and simulates typing/deleting.
- **Orbiting tech icons around the profile image**
  - Orbit icons get randomly generated keyframes and orbit radii.
  - Hover pauses an icon’s animation.
- **Smooth scrolling**
  - Clicking nav links scrolls to the section with an offset so content isn’t hidden under the fixed navbar.
- **Scroll-in reveal animations**
  - Elements with `.slide-in-left`, `.slide-in-right`, `.slide-in-up` fade/translate into view when intersecting.

### Contact Form (EmailJS)

- **No backend required:** the form submits using EmailJS via CDN.
- The form is identified by `#contact-form` and uses these field names:
  - `user_name`
  - `user_email`
  - `message`
- Submit UX:
  - Disables the button and shows “Sending...” while sending.
  - Shows success/failure alerts and resets the form on success.

### Notes / Current Implementation Details

- `script.js` includes a `initSunPhotoModal()` feature, but the current `index.html` does not include the modal markup (`#photo-modal`, `.close`, `#random-photo`). Because the JS checks for elements first, it fails safely (no runtime crash) and simply doesn’t activate.

---

## Tech Stack

- **HTML5** (semantic sections)
- **CSS3** (responsive layout, animations)
- **Vanilla JavaScript** (DOM + observers + animations)
- **EmailJS (CDN)** for contact form email delivery

---

## Project Structure

```text
.
├─ index.html
├─ style.css
├─ script.js
├─ img.jpg
├─ SHUBHAM BANSODE (2).pdf
└─ Pictures/
	 ├─ icon.jpg
	 └─ (project images)
```

---

## Run Locally

This is a static website (no build step).

### Option 1: Open directly

1. Download/clone the repository
2. Open `index.html` in your browser

### Option 2: VS Code Live Server (recommended)

1. Open the folder in VS Code
2. Install the **Live Server** extension
3. Right-click `index.html` → **Open with Live Server**

---

## Configuration / Customization

### Update your links

- Social links are in `index.html` (GitHub, LinkedIn, Instagram, WhatsApp).
- Project buttons (Live Demo / GitHub) are inside the Projects section.

### Update projects

- Edit the project cards inside the `#projects` section in `index.html`.
- Replace placeholder values like `href="#"` and missing images (`src="#"`).

### Configure EmailJS (for forks)

EmailJS is loaded via:

- CDN script in `index.html`

EmailJS is configured in `script.js`:

- `emailjs.init('<PUBLIC_KEY>')`
- `emailjs.sendForm('<SERVICE_ID>', '<TEMPLATE_ID>', form)`

If you fork this repo and want the contact form to work for your own EmailJS account:

1. Create an account at https://www.emailjs.com/
2. Create an Email Service + Email Template
3. Replace the **public key**, **service id**, and **template id** inside `script.js`

---

## Deployment

This project is deployed on **Netlify**.

- **Live URL:** https://shubham-bansode.netlify.app/

To deploy your fork:

1. Push your code to GitHub
2. In Netlify: **Add new site** → **Import an existing project**
3. Build settings:
   - Build command: _(none)_
   - Publish directory: `/` (project root)

---

## License

This project is for personal portfolio use. If you reuse the layout/design, please give credit.
