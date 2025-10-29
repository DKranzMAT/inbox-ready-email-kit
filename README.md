> **Inbox-Ready** is a lightweight, production-grade email kit built for real-world client testing — showcasing three responsive HTML templates (plus a donation appeal) that render consistently across Gmail, Outlook, and Apple Mail.

[![Live Preview](https://img.shields.io/badge/Live%20Demo-inbox--ready--email--kit-blue)](https://dkranzmat.github.io/inbox-ready-email-kit/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

# Inbox-Ready — Responsive Email Code Kit

Production-grade, table-based HTML email templates that render reliably across Gmail, Outlook (desktop/web), Apple Mail, and mobile clients. No build step required.

## What’s inside
- **4 templates**: Product Announcement, Newsletter, Transactional Receipt, Appeal
- **Shared partials**: header, footer, and a bulletproof button with VML fallback
- **/dist**: ready-to-send HTML plus an index page for local preview
- **Docs**: client quirks (Gmail clipping, Outlook gaps, dark mode) and fixes

## Quick start
1. Open any HTML in `/dist` to preview locally.
2. Customize content in `/src/templates` and copy changes into `/dist` when ready to send.
3. Keep CSS **inline**. Avoid `<style>` blocks except for dark-mode helpers.

> Keep total HTML under **100 KB** to avoid Gmail clipping.

---

## Client quirks & fixes (cheat sheet)

### Gmail clipping (“View entire message”)
- **Why**: message body over ~102KB.
- **Fix**: Minify markup, remove comments, trim tracking querystrings, split long modules.

### Outlook (Windows) alignment/gaps
- **Why**: Word rendering engine.
- **Fixes**: use table layout with explicit `width` + `align`, prefer `padding` over `margin`, add spacer rows. For buttons, include **VML** fallback.

### Image gaps / blue links
- Add `display:block` to `<img>` and `line-height:0` to container cells.
- Neutralize auto-link coloring with `x-apple-data-detectors`, `u ~ div .email-container a` overrides.

### iOS zoom
- Use a base body font-size ≥ 16px and design accordingly.

### Dark mode
- Inline explicit color on text and backgrounds.
- Provide a dark-mode helper span or conditional styles for Apple/Gmail where supported.

---

## Test checklist
- Gmail Web (Chrome), Gmail iOS/Android
- Outlook Desktop (Win), Outlook New/Legacy, Outlook Web
- Apple Mail (macOS), iOS Mail
- DPI scaling (Win @125%/150%), images on/off, link underlines, RTL sample

---

## Structure
```
/src
  /partials
    header.html
    footer.html
    button.html   (HTML + VML fallback)
  /templates
    product_announcement.html
    newsletter.html
    receipt.html
    appeal.html
/dist
  index.html
  product_announcement.html
  newsletter.html
  receipt.html
  appeal.html
```

---

## Credits
Adapted from years of client work and public learnings from the email community (e.g., Campaign Monitor, Litmus, MJML patterns). Licensed MIT.
