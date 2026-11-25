# DELUXSE Teknoloji · Full-stack e-commerce project

**Live:** [deluxseteknoloji.com.tr](https://deluxseteknoloji.com.tr) · **Code:** private (client project) · **Built:** October 2026, solo

A production e-commerce system I built alone, from design to server: a storefront, a login-protected portal for business customers and an admin panel that installs on a phone as an app.

## What I did

- **Designed and built the whole product** on my own: UI, frontend, backend, database, server setup, deployment and SEO.
- **Designed the database and REST-style API** in PHP + SQLite for products, orders, users and roles.
- **Implemented authentication and role-based access**: customers, business customers and staff each see only what they are allowed to; sensitive data is computed and filtered on the server, never trusted from the browser.
- **Built a CI/CD pipeline with GitHub Actions**: one-click deploy, one-click rollback and an automatic health report after each release.
- **Set up and secured a Linux server** (Ubuntu, nginx, php-fpm) with provisioning scripts and automatic security updates.
- **Built an installable admin app (PWA)** so the client manages the store from their phone.
- **Wrote Python scripts** to generate catalog data and batch-convert 130+ images to WebP.
- **Delivered on time to a real client** and wrote the documentation they use to run the system.

## Engineering highlights

- **Security:** password hashing, CSRF protection, login and per-IP rate limiting, session timeouts, Content Security Policy, safe image uploads (re-encoded, no script execution), private folders closed to the web, no secrets in the repository.
- **Privacy-friendly analytics** without cookies or personal data: traffic sources, funnel and popular products.
- **Bulk workflows:** pasting data from Excel with a preview before saving.
- **Zero dependencies:** no framework, npm or Composer. Simple to maintain and no third-party package risk.
- **SEO:** structured data, sitemap, share previews and a mobile-first, fast-loading site.

## Skills used

`PHP` `SQL / SQLite` `JavaScript` `HTML/CSS` `REST APIs` `Authentication & authorization` `Web security (OWASP basics)` `Linux` `nginx` `GitHub Actions CI/CD` `Bash` `Python` `PWA` `SEO`

## What I learned

- Owning a project end to end, from client requirements to production and support.
- Designing for security from the start instead of adding it later.
- Making deployments safe and reversible, so releasing is routine instead of risky.

---

[← Back to profile](https://github.com/aydnomer)
