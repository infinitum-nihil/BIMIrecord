# BIMI record repo

https://github.com/infinitum-nihil/BIMIrecord

This repo hosts the BIMI assets for the mail services of infinitum-nihil.com

last updated 14mar2026 by NT

---

## Status

| Component | Status |
|-----------|--------|
| DMARC | `p=reject` / `pct=100` ✅ |
| BIMI DNS record | Live at `bimi.infinitum-nihil.com` ✅ |
| SVG logo (`l=`) | True vector, BIMI SVG Tiny 1.2 PS compliant ✅ |
| US Trademark | Reg. No. 8145923, registered February 17, 2026 ✅ |
| VMC cert | In validation — PrimeSSL ⏳ |
| `a=` field | Pending PEM delivery from PrimeSSL ⏳ |

---

## What happened

The original `logo.svg` was a base64-encoded PNG wrapped in an SVG shell — technically not a vector file and not BIMI-compliant. This was discovered when ssl2buy flagged it during VMC cert validation.

The logo was rebuilt as a true vector SVG using potrace, traced directly from the brand source PNG, preserving the original mark's character and edges. The file at `image/logo.svg` is now a proper SVG Tiny 1.2 PS document with no embedded raster content.

The VMC cert was purchased from PrimeSSL on March 14, 2026 ($810/year). Once the PEM is delivered, the final step is adding the `a=` field to the existing BIMI DNS record pointing to the cert URL.

---

## Relevant specs

- [IETF BIMI Draft](https://datatracker.ietf.org/doc/draft-brand-indicators-for-message-identification/)
- [BIMI Group](https://bimigroup.org/)
- [What is a VMC?](https://www.digicert.com/faq/email-trust/what-is-a-verified-mark-certificate/)
- [BIMI in Gmail](https://cloud.google.com/blog/products/identity-security/bringing-bimi-to-gmail-in-google-workspace)

---

[![Better Stack Badge](https://uptime.betterstack.com/status-badges/v1/monitor/1re8n.svg)](https://uptime.betterstack.com/?utm_source=status_badge)
