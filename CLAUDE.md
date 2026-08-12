# jajehfamilyoffice.com

Flagship static site for the Jajeh Family Office — ultra-high-net-worth, white-glove,
one-stop family office (accounting, investments, legal, business interests).
Hosted on GitHub Pages (repo: overtaxedgoose/jajehfamilyoffice.com). Built August 2026.

## Design intent — protect this
- Quiet luxury: near-black charcoal (--night), warm ivory, hairline brass (--brass) accents.
  The green sail mark is deliberately the ONLY color. Do not add photos, icons, or bright colors.
- Type: Cormorant Garamond (display) + Lato 300/400 (text). Logo font (Flama Condensed) is
  reserved for logo artwork per the brand designer — never use it in site text.
- Single page, restrained copy, no prices, no testimonials, no hype. Tone: discreet, assured.
- Contact is intentionally minimal: "Request an Introduction" mailto patrick@jajehgroup.com.

## Structure
- Plain HTML/CSS + ~6 lines of JS (IntersectionObserver reveal; respects prefers-reduced-motion).
- index.html, 404.html, assets/css/style.css, assets/img (marks from the Jajeh Logos kit).

## Domain — DIFFERENT REGISTRAR than the other Jajeh sites
- jajehfamilyoffice.com is registered at NAMECHEAP (not GoDaddy), DNS on
  dns1/dns2.namecheaphosting.com, MX on Namecheap Private Email (jellyfish.systems).
- Cutover (in Namecheap dashboard): apex A records → 185.199.108.153/.109/.110/.111,
  www CNAME → overtaxedgoose.github.io. Do NOT touch MX/TXT until confirming whether
  email @jajehfamilyoffice.com is in use.
