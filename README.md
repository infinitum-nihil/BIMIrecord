# BIMI — infinitum-nihil.com

BIMI (Brand Indicators for Message Identification) assets for `infinitum-nihil.com` mail services.

**Live site:** https://bimi.infinitum-nihil.com

## Architecture

```
GitHub repo (source of truth)
  ↓ push to main
GitHub Actions (rclone sync)
  ↓
Cloudflare R2 bucket (bimi-assets)
  ↓ custom domain
https://bimi.infinitum-nihil.com
```

Push to `main` triggers rclone sync of all servable files to the `bimi-assets` R2 bucket. R2 serves directly via custom domain — no Worker, no GitHub Pages.

## DNS Record

```
default._bimi.infinitum-nihil.com TXT "v=BIMI1; l=https://bimi.infinitum-nihil.com/image/logo.svg; a=https://bimi.infinitum-nihil.com/image/vmc.pem"
```

## Files

| Path | Purpose |
|------|---------|
| `image/logo.svg` | BIMI logo served at `l=` URL — SVG Tiny 1.2 PS compliant |
| `image/mark-bimi-brand.svg` | Same file, canonical name for reference |
| `image/vmc.pem` | VMC certificate chain served at `a=` URL |
| `index.html` | Status page at site root |
| `robots.txt` | Crawl policy |

## Logo

Traced from `Logoblackbackground.psd` master via potrace. Brand red (#EF3340) on white background. Square 981×981 viewBox, 192×192 declared pixels. Validated against `draft-svg-tiny-ps-abrotman-11` and Google Workspace BIMI requirements via [bimi-svg-worker](https://bimi-svg-worker.infinitumnihil.workers.dev/).

**SHA-256:** `8cb4f2b5783d3cb4bc72673f49fe611bae8342466355ac4eb1c437d1d928ea98`

## VMC Certificate

- **Issuer:** GlobalSign GCC R42 Verified Mark CA 2023
- **Subject:** INFINITUM NIHIL (Private Organization, CA, US)
- **Trademark:** USPTO Reg. No. 8145923 (Serial 97981054)
- **Status:** Reissuance pending — original cert embedded SVG with `width="100%"` (non-compliant)

## GitHub Actions Secrets Required

| Secret | Purpose |
|--------|---------|
| `CF_ACCOUNT_ID` | Cloudflare account ID |
| `R2_ACCESS_KEY_ID` | R2 API token access key |
| `R2_SECRET_ACCESS_KEY` | R2 API token secret key |

## Relevant Specs

- [IETF BIMI Draft](https://datatracker.ietf.org/doc/draft-brand-indicators-for-message-identification/)
- [SVG Tiny Portable/Secure](https://datatracker.ietf.org/doc/draft-svg-tiny-ps-abrotman/)
- [BIMI Group](https://bimigroup.org/)
- [Google Workspace — Create a BIMI SVG](https://support.google.com/a/answer/10911027)
