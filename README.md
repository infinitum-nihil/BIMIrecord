# BIMI record repo

https://github.com/infinitum-nihil/BIMIrecord

This repo hosts the BIMI assets for the mail services of infinitum-nihil.com

last updated 2apr2026 by NT

---

## Status: FULLY DEPLOYED

| Component | Status | Detail |
|-----------|--------|--------|
| DMARC | ✅ Live | `p=reject` / `pct=100` |
| BIMI DNS record | ✅ Live | `default._bimi.infinitum-nihil.com` |
| SVG logo (`l=`) | ✅ Live | `https://bimi.infinitum-nihil.com/image/logo.svg` |
| VMC certificate (`a=`) | ✅ Live | `https://bimi.infinitum-nihil.com/image/vmc.pem` |
| US Trademark | ✅ Registered | Reg. No. 8145923, February 17, 2026 |

### DNS Record

```
default._bimi.infinitum-nihil.com TXT "v=BIMI1; l=https://bimi.infinitum-nihil.com/image/logo.svg; a=https://bimi.infinitum-nihil.com/image/vmc.pem"
```

### VMC Certificate

- **Issuer:** GlobalSign GCC R42 Verified Mark CA 2023
- **Subject:** INFINITUM NIHIL (Private Organization, CA, US)
- **Trademark:** USPTO Reg. No. 8145923
- **Valid:** April 2, 2026 — May 4, 2027
- **File:** `image/vmc.pem`

---

## History

**March 14, 2026:** Original `logo.svg` was a base64-encoded PNG wrapped in an SVG shell — not BIMI-compliant. Discovered during VMC cert validation. Logo rebuilt as true vector SVG using potrace from brand source PNG. BIMI DNS record set with `l=` only. VMC cert ordered from PrimeSSL/ssl2buy.

**April 2, 2026:** VMC certificate delivered by GlobalSign. PEM uploaded to `image/vmc.pem`. DNS record updated with `a=` parameter. BIMI fully operational.

---

## Relevant specs

- [IETF BIMI Draft](https://datatracker.ietf.org/doc/draft-brand-indicators-for-message-identification/)
- [BIMI Group](https://bimigroup.org/)
- [What is a VMC?](https://www.digicert.com/faq/email-trust/what-is-a-verified-mark-certificate/)
- [BIMI in Gmail](https://cloud.google.com/blog/products/identity-security/bringing-bimi-to-gmail-in-google-workspace)

---

[![Better Stack Badge](https://uptime.betterstack.com/status-badges/v1/monitor/1re8n.svg)](https://uptime.betterstack.com/?utm_source=status_badge)
