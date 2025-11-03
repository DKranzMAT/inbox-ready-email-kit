# Inbox-Ready — Responsive Email Code Kit

> **Inbox-Ready** is a lightweight, production-grade email kit built for real-world client testing — showcasing four responsive HTML templates (Product Announcement, Newsletter, Transactional Receipt, and Appeal) that render consistently across Gmail, Outlook, and Apple Mail.

[![Live Preview](https://img.shields.io/badge/Live%20Demo-inbox--ready--email--kit-blue)](https://dkranzmat.github.io/inbox-ready-email-kit/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

<p align="center">
  <img src="inbox-ready.png" alt="Responsive Email Code Kit" width="800"/>
</p>

## 🧠 Tech Stack

**Core:**  
- Hand-coded responsive **HTML + table layouts** (no frameworks)  
- **Inline CSS** with VML button fallbacks for Outlook  
- **Modular partials:** header, footer, and reusable button block  

**Tooling:**  
- Built and tested locally — no build step required  
- GitHub Pages for live preview  
- Compatible with ESP imports (Campaign Monitor, Mailchimp, HubSpot, etc.)

**Rendering targets:**  
- Gmail Web + Mobile  
- Outlook (Desktop + New Web)  
- Apple Mail / iOS Mail  
- Dark-Mode adjustments where supported  

---

## ⚙️ Usage

1. **Preview online:**  
   [Live Demo →](https://dkranzmat.github.io/inbox-ready-email-kit/)

2. **Use locally:**
   ```bash
   git clone https://github.com/DKranzMAT/inbox-ready-email-kit.git
   cd inbox-ready-email-kit
   open index.html
   ```

3. **Customize content:**
   - Edit any template in `/src/templates/`
   - Copy updated HTML into `/dist/` before sending
   - Keep CSS inline and total file size under **100 KB** to avoid Gmail clipping

4. **Test before launch:**
   - Gmail Web + Mobile
   - Outlook (Windows, Mac, New Web)
   - Apple Mail / iOS
   - Optional: Litmus or Email on Acid for full previews

---

## 💬 Client Quirks & Fixes

### Gmail clipping (“View entire message”)  
- **Why:** message body over ~102 KB  
- **Fix:** minify markup, remove comments, shorten tracking URLs, split long sections

### Outlook (Windows) alignment & gaps  
- **Why:** Word rendering engine  
- **Fix:** table layout with explicit widths, use padding not margin, include VML button fallback

### Image gaps / blue link styling  
- Add `display:block` to images  
- Use `line-height:0` on container cells  
- Override auto-link colors with `x-apple-data-detectors` and Gmail dark-mode resets  

---

## 📂 Structure

```
/src
  /partials
    header.html
    footer.html
    button.html
  /templates
    product_announcement.html
    newsletter.html
    receipt.html
    appeal.html
/dist
  index.html
  (ready-to-send templates)
```

---

## 🧾 License
MIT © 2025 — see [LICENSE](LICENSE)

---

## 👤 Author
**David Kranz** — Front-End Developer  
[Portfolio](https://davidkranzwordpress.com) · [GitHub](https://github.com/DKranzMAT) · Chicago, IL

---
