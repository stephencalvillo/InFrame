# Open Items & Pre-Launch Checklist

Tasks and decisions flagged in the draft or inferred from review.

## Assets

- [x] **Extract embedded assets** — Logo, favicon, and mark moved to `/assets/`
- [x] **Logo SVG files** — Wordmark, condensed mark, footer logo, favicon, skewed mark in `/assets/`
- [ ] **Hero photography** — `hero_01.jpeg` in place; confirm final brand-approved hero image
- [ ] **Gallery photography** — Confirm all four site images are approved for web use

## Content & compliance

- [ ] **Coverage lines** — Confirm list only includes lines InFrame can bind today (per HTML comment)
- [ ] **"Hundreds of markets" claim** — Substantiate or soften copy
- [ ] **Legal disclaimer** — Replace `[________]` NPN and `[states]` placeholders in footer
- [ ] **Entity names** — Align InFrame Insurance Services LLC vs InFrame Risk Inc. usage
- [ ] **Footer links** — Privacy, Terms, Licenses pages don't exist yet (`href="#"`)
- [ ] **Founder credibility line** — Optional one-liner in contact section (noted in HTML comment)

## Functionality

- [ ] **Contact form backend** — Wire to Formspree, HubSpot, Framer/Webflow form action, or custom API
- [ ] **Form success flow** — Decide if inline message is enough or if redirect/thank-you page is needed
- [ ] **Analytics** — Add tracking if required (not present in draft)

## Design polish (optional)

- [ ] **Hero eyebrow** — CSS exists; decide if label (e.g. "Specialist brokerage") should appear above headline
- [ ] **Nav expansion** — Add links to #work / #coverage / #gallery if client wants in-page nav beyond Contact
- [ ] **Mobile nav** — Not needed at current link count; revisit if nav grows
- [ ] **Open Graph / social meta** — No OG tags in current `<head>`

## Technical

- [ ] **Hosting target** — Static HTML, or migrate to Next.js / CMS / Webflow?
- [ ] **Domain** — Confirm production URL and email domain alignment (inframerisk.com)
- [ ] **Documentation sync** — Keep `docs/` updated when section styling or interactions change

## What we still need from the client

| Item | Why |
|------|-----|
| Brand book / official color specs | Validate tokens match print and other materials |
| Final hero and gallery photography | Replace or confirm current assets |
| Legal review of disclaimer + coverage claims | Compliance |
| NPN, licensed states, correct legal entity names | Footer accuracy |
| Form submission destination | Make contact form functional |
| Founder/team bio (optional) | Credibility in contact section |
| Priority tweaks list | What to change first |
