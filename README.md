# QR Maker

**Turn any link into a QR code, and any number into a WhatsApp link.**

A one-page tool with two jobs that belong together: paste a link or any text and get a downloadable QR code, and type a phone number + message and get a wa.me WhatsApp chat link — with a button that turns that link straight into a QR code too.

## What it does

- **QR maker** — type or paste any link or text; the code draws live as you type. Size slider (256–1024 px), one-tap PNG download. Preset chips for the Bangees portfolio (Agent Roll Call, Agent Cards, Name Atlas, Naira Lens, Claim Checker, Discaro) — the Roll Call preset doubles as hackathon outreach: print it, stick it on a flyer, share it.
- **WhatsApp link maker** — country code defaults to +234; accepts 0803…, +234803… or 803… and normalises to international format. Optional pre-written message, then Copy link, Open in WhatsApp, or "Make a QR of this link".
- **Fully client-side** — the QR code is drawn on your device with the vendored `qrcode-generator` library (MIT, `site/qrcode.min.js`); nothing typed is uploaded anywhere, no backend, no tracking, no accounts. Works offline once loaded.

## Honesty notes

- QR codes are black on white with a quiet zone on purpose — that is what phone cameras read most reliably, so the colours are fixed.
- A very long link still scans, but a short link scans faster; the presets use short portfolio links for that reason.
- The page says so on the page: if text is too long for one QR code, it says so instead of drawing a broken one.

## Tech

One static page (`site/index.html`) plus the vendored QR library, a PIL-drawn banner and letter-mark icons, a PWA manifest + service worker (installable via "Add to Home screen", same pattern as the rest of the portfolio) and the navy "More from Bangees" footer. No build step. Published via GitHub Pages from the `site/` folder.

## Status

Built locally and tested (QR generation + phone normalisation + all assets serving) on 2026-11-21. **Not published yet** — needs an empty GitHub repo named `qr-maker`, then push + verify live, same as the other ten sites. When it goes live, add its link to the "More from Bangees" footer on the other ten sites.
