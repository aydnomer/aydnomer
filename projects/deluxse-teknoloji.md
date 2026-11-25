<div align="center">

# 🔌 DELUXSE Teknoloji

**E-commerce website, dealer (B2B) portal and installable admin app for a phone-accessories brand**

[![Live](https://img.shields.io/badge/Live-deluxseteknoloji.com.tr-111111?style=for-the-badge&logo=googlechrome&logoColor=white)](https://deluxseteknoloji.com.tr)
![PHP](https://img.shields.io/badge/PHP_8.3-777BB4?style=for-the-badge&logo=php&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![nginx](https://img.shields.io/badge/nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)
![PWA](https://img.shields.io/badge/PWA-installable-5A0FC8?style=for-the-badge&logo=pwa&logoColor=white)

</div>

> The source code is private. This page describes what was built.

---

## About the project

DELUXSE is a brand selling chargers, cables, power banks, headphones, speakers, car accessories and phone cases. I designed, built and deployed the whole system end to end: a storefront for retail customers, a separate portal for business customers (phone shops and wholesalers), and an admin panel the store owner and staff use every day, installable on the phone as an app.

| | |
|---|---|
| **Role** | Design, frontend, backend, database, server setup, deployment and SEO (solo) |
| **Type** | E-commerce site + B2B portal + admin PWA |
| **Status** | Live in production at [deluxseteknoloji.com.tr](https://deluxseteknoloji.com.tr) |

## What was built

### Storefront

- **Mobile-first, Apple-style design** with light/dark theme and Turkish/English language support.
- **Product catalog** of 120+ products with categories, sub-groups, filters (color, connector, power), sorting and in-category search.
- **Instant search** by product code or name, with keyboard shortcuts (`Ctrl+K` or `/`).
- **"Find a compatible product"**: the customer picks their phone's port (USB-C, Lightning, MagSafe, Micro USB, 3.5 mm) and only matching products are listed. Compatibility is derived automatically from each product's data.
- **Product pages** with large images, color and capacity options with a photo per color, highlights, technical specs, videos, related and recently viewed products, and share / ask on WhatsApp.
- **Cart and checkout**: slide-out cart, address and billing details, order confirmation. Totals and stock are always recalculated on the server, never trusted from the browser.
- **Order tracking** by order number and phone, with carrier and tracking number.
- **Newsletter** sign-up with consent text stored alongside it.
- **Legal and info pages** (about, contact, returns, shipping, FAQ, privacy, cookies, distance sales). Company details come from the admin panel, and empty fields are hidden automatically.
- **Cookie consent** banner; visitor analytics work without cookies.

### Dealer (B2B) portal

- Three customer types: retail, phone shop and wholesaler.
- **Dealer application** form that lands in the admin panel for approval.
- **Dealer login** with a forced password change on first login.
- **Quick order screen**: all products in one table, search, category tabs, **paste "code quantity" lines straight from Excel**, live totals and one-click ordering.
- **Order history and reorder**: a past order goes back into the table with one tap.
- **Dealer-only data never ships in static files.** It is served from the server only to an approved, logged-in dealer, and only their own.

### Admin panel (PWA)

- **Dashboard**: live visitors, today's orders, a to-do list (new orders, pending dealers, products missing photos or data) and low-stock alerts.
- **Orders**: status, shipping details, internal notes, printable receipt, WhatsApp message to the customer, Excel export.
- **Products**: add, edit, duplicate, hide; photo upload with automatic square WebP conversion; color/capacity variants with stock per color; video links; labels (New, Featured, Deal); bulk updates by pasting from Excel with a preview before saving.
- **Categories**: create, rename, delete and choose which appear in the top menu.
- **Dealers**: approve/reject, temporary passwords with a ready-made WhatsApp message, password reset, account closing.
- **Analytics**: daily chart, traffic source (Instagram, TikTok, Facebook, YouTube, Google, WhatsApp), sales funnel, most viewed and most added-to-cart products, and trackable links per platform.
- **Audit log**: who changed what, and when.
- **Settings**: payment, company and shipping details, exchange rate (automatic from the Central Bank or manual), staff accounts, database backup download.
- **Roles**: the owner sees everything; staff accounts cannot see sensitive business data or dealer accounts.
- **Installable on iPhone and Android** with its own manifest, icons and service worker.

## Security

- Passwords stored with `password_hash`; login attempt limits; **CSRF protection**; sessions expire after inactivity.
- **Rate limiting per IP** on orders, newsletter, tracking and dealer endpoints.
- Uploaded images are **re-encoded** before saving, and no scripts can run in the upload folder.
- Database, config file, scripts and docs are **not reachable from the web**.
- **Content Security Policy** and security headers; the site cannot be embedded in other sites.
- Privacy-friendly analytics: no cookies, IP addresses or device IDs stored.
- Server with automatic security updates; PHP 8.3 patched against known vulnerabilities, plus an **integrity check on every deployment**.
- No secrets in the code: server credentials live in GitHub Secrets, live config is never committed.

## SEO

- Schema.org `Store` structured data (business details, opening hours, map, social links).
- Separate, fast-loading contact page for local search.
- Share page for every product with a rich preview on WhatsApp and Instagram.
- Auto-generated sitemap, `robots.txt`, admin and API excluded from indexing.
- Logo and site icons in the sizes Google expects.

## Deployment and DevOps

- **One-click deploy with GitHub Actions**, with a **rollback** option to the previous version.
- Each deploy keeps the database, uploads and live config, then writes a report: PHP version and security patch, file integrity, whether pages respond, whether the data folder is closed, and store health checks.
- Server provisioning scripts for **Ubuntu 24.04 + nginx + php-fpm**; `.htaccess` included for Apache/LiteSpeed.
- Python scripts to generate product data, convert 130+ product photos to WebP and split color variants automatically.

## Technical decisions

| Decision | Why |
|---|---|
| **No framework, no build step, zero dependencies** (no npm, no Composer) | Easy to maintain for years and no supply-chain risk from third-party packages. |
| **PHP + SQLite** | Runs on any low-cost server, single-file database, created automatically on first run, easy to back up. |
| **Everything sensitive computed on the server** | Totals, stock and dealer data can never be changed or seen from the browser. |
| **Admin panel as a PWA** | The owner manages orders and stock from the phone without an App Store release. |
| **Cookie-less analytics** | Useful traffic and funnel data without a cookie banner burden or personal data. |

## Tech stack

**Frontend:** HTML5 · CSS (design tokens) · Vanilla JavaScript
**Backend:** PHP 8.3 · PDO · SQLite · GD (WebP)
**Server:** Ubuntu 24.04 · nginx · php-fpm
**DevOps:** GitHub Actions (deploy + rollback) · Bash · PowerShell · Python scripts
**PWA:** Web App Manifest · Service Worker
**SEO:** Schema.org JSON-LD · sitemap · Open Graph

## Timeline

Built in about four weeks (October 2026) and delivered in early November 2026: design and storefront → backend and admin panel → deployment pipeline → branding and security hardening → SEO and final checks.

---

<div align="center">

Designed and developed by **[Ömer Faruk Aydın](https://github.com/aydnomer)**

</div>
