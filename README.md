# NearDoc — Campus Printing, Reinvented

> Skip the queue. Print smarter.

**NearDoc** is a campus-focused document printing web application that lets students upload documents, configure print settings, choose a nearby campus print shop, pay online, and track their order in real time — all without waiting in line.

Built as a complete, fully functional **static web app** — no backend, no build step, no installation required. Runs entirely in the browser.

---

## Overview

Campus printing is a daily friction point for students: physical queues, no visibility on order status, and zero payment flexibility. NearDoc solves this by bringing the entire print workflow online — from document upload to OTP-based pickup.

The platform serves three user types:
- **Students** — place and track print orders
- **Shop Owners** — manage incoming orders and shop settings
- **Admins** — verify shops and monitor the platform

---

## Features

### Student App (`NearDoc.html`)
- **Document Upload** — Drag & drop or browse to upload PDF, DOC, DOCX, PNG, or JPG files
- **PDF Preview** — Client-side PDF rendering using PDF.js (CDN)
- **Print Configuration** — Choose copies, color mode (B&W / Color), paper size (A4 / A3 / Letter), single/double-sided, and binding
- **Live Price Calculation** — Instant cost estimate based on selected options and shop pricing
- **Nearby Shop Selection** — View available campus print shops with distance, rating, pricing, and open/closed status
- **Promo Code Support** — Apply promo codes at checkout (`PRINT10`, `SAVE5`, `DOC15`, `CAMPUS20`, `WELCOME7`)
- **Payment Options** — UPI, Card, or Pay at Shop
- **Live Order Tracking** — Real-time status: Confirmed → Printing → Ready → Collected
- **OTP Pickup** — Unique 4-digit OTP generated per order for counter verification
- **Order History** — View all active and past orders with summary statistics
- **User Profile** — Edit name, phone, college; change password; delete account

### Shop Owner Dashboard (`NearDoc-shop.html`)
- Register and manage a campus print shop
- Accept, print, and mark orders as ready or collected
- Configure pricing (B&W and Color per page), ETA, working hours
- View order queue with real-time updates
- Shop profile management and password change

### Admin Panel (`NearDoc-admin.html`)
- Secure login (demo credentials)
- Approve, suspend, or delete print shops
- View all registered users and their orders
- Platform-wide order monitoring with live stats
- Real-time dashboard synced across browser tabs via `storage` events

### Authentication (`NearDoc-auth.html`)
- Student and Shop Owner sign-up / sign-in flows
- Password strength indicator
- Session management via `localStorage`
- Forgot password flow

---

## Tech Stack

| Layer | Technology |
|---|---|
| Structure | HTML5 |
| Styling | Vanilla CSS (custom design system, no frameworks) |
| Logic | Vanilla JavaScript (ES6+) |
| PDF Parsing | [PDF.js](https://mozilla.github.io/pdf.js/) via CDN |
| Data Storage | Browser `localStorage` |
| Fonts | Google Fonts — [Fraunces](https://fonts.google.com/specimen/Fraunces), [DM Sans](https://fonts.google.com/specimen/DM+Sans) |

> ⚡ **No framework. No server. No build step.** Runs entirely in the browser.

---

## Project Structure

```
NearDoc/
├── NearDoc.html           # Main student-facing app
├── NearDoc-auth.html      # Login & registration page
├── NearDoc-shop.html      # Shop owner dashboard
├── NearDoc-admin.html     # Admin control panel
├── .gitignore             # Git ignore rules
├── PROJECT_INFO.txt       # Repository preparation notes
└── README.md              # This file
```

> **Note:** The `presentation/` directory is excluded from this repository. It contains internal project documentation not intended for public publication.

---

## How to Run

NearDoc is a **pure static web app**. No Node.js, Python, server, or installation is required.

### Option 1 — Open directly in browser

```bash
# 1. Clone the repository
git clone https://github.com/your-username/neardoc.git

# 2. Open the entry point in your browser
# Navigate to NearDoc-auth.html in Chrome / Edge / Firefox
```

Simply double-click `NearDoc-auth.html` or drag it into a browser window.

### Option 2 — VS Code Live Server

1. Install the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension
2. Right-click `NearDoc-auth.html` → **Open with Live Server**

### Recommended Browser

Chrome or Edge (for best compatibility with PDF.js and `localStorage`).

---

## Demo / Test Data

| Role | Access |
|---|---|
| Student | Sign up on `NearDoc-auth.html` with any email & password |
| Shop Owner | Open `NearDoc-shop.html` directly and register a shop |
| Admin | Open `NearDoc-admin.html` — use `admin@neardoc.local` / `admin123` |

**Test promo codes:** `PRINT10`, `SAVE5`, `DOC15`, `CAMPUS20`, `WELCOME7`

> All data is stored in your browser's `localStorage`. No external database or server is involved.
> Clearing browser data will reset the app to its initial state.

---

## App Flow

```
Sign In / Sign Up (NearDoc-auth.html)
          ↓
Upload Document (PDF / DOC / Image)
          ↓
Configure Print Options (copies, color, size, sides, binding)
          ↓
Choose Nearby Campus Print Shop
          ↓
Apply Promo Code (optional) → Review Total
          ↓
Pay (UPI / Card / Pay at Shop)
          ↓
Track Order in Real Time (Printing → Ready → Collected)
          ↓
Show 4-digit OTP at Counter → Collect Printout 🎉
```

---

## Limitations

Since this is a frontend-only prototype:

- **Data does not persist across devices or browsers** — `localStorage` is device-local
- **Payments are simulated** — no real payment gateway is integrated
- **Real-time tracking is simulated** — order status updates are triggered manually or via UI
- **OTP is display-only** — there is no server-side OTP validation
- **No push notifications** — status changes are visible only when the app is open

These are intentional scope decisions for a browser-based prototype. A production version would require a backend (e.g., Node.js + MongoDB), real payment gateway integration (e.g., Razorpay), and WebSocket-based real-time updates.

---

## Current Status

**✅ Completed — v1.0 (April 2026)**

All core features are implemented and functional. The app is a complete, working prototype demonstrating the full student printing workflow end-to-end.

---

## Future Improvements

- **Backend integration** — Replace `localStorage` with a real database (e.g., MongoDB, PostgreSQL) for multi-device persistence
- **Payment gateway** — Integrate Razorpay or Stripe for real UPI / card payments
- **Real-time updates** — WebSocket or SSE for live order status without page refresh
- **Mobile app** — React Native or Flutter version for native mobile experience
- **Maps integration** — Google Maps API for real shop distance and directions
- **SMS/Email notifications** — Order confirmations and OTP delivery via Twilio / SendGrid
- **PWA support** — Installable progressive web app with offline capability

---

## Author

**Made by Jaydip Modasiya**

- GitHub: [s`github.com/jaydipmodasiya](https://github.com/jaydipmodasiya)
- Built: April 2026

---

## License

No license has been specified for this project.

If you wish to use, fork, or contribute to this project, please contact the author first.

---

> *NearDoc — Because your time at campus shouldn't be spent waiting in line.*
