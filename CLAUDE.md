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
- One frozen backdrop (Nov 2026): the first screen's scene (charcoal, brass radial glow, ghost
  mark bottom-right) is a fixed layer behind everything and never moves. Panels have NO
  background of their own — no ivory sections — only words that rise over the backdrop.
- One panel at a time. Each section is a full-screen panel. Only the panel in view keeps its
  words; the others fade with their distance from the screen. Do not let two panels' copy be
  readable at once.
- The page moves only by script ("sailing"), never by native scroll: `html { overflow: hidden }`
  and a handler reads wheel, swipe and keys, then glides one panel per gesture over ~1.6 s with a
  cubic ease (longer across several panels). It must feel slow and silken — never snap. Keep the
  duration; do not reintroduce scroll-snap or native smooth scrolling.
- No header bar. Navigation is the "horizon": a fixed hairline across the top with the sail mark
  riding it. No tick marks on the line (PK removed them). The sail moves along the line with
  progress, heels 8° in the direction of travel, rocks gently at rest, and sails in from the left
  on load. Clicking the sail sails on to the next panel (and home from the last). The ports are
  unmarked; they exist only for keyboard users (tab shows a port's name).
- Services: each card shows only numeral + name; the subtext appears on hover/focus. On touch
  screens (hover: none) the subtext is folded and a tap unfolds it.
- "How We Work" heading is "Quietly, completely, and in person." (PK rejected "White glove is
  not a promise. It is a procedure." — wrong rhythm, "procedure" sounds medical.) The third
  principle is "With Discretion".
- Contact is intentionally minimal: both "Request an Introduction" CTAs are silent email captures.
  They POST emailAddress to the private Google Form "Jajeh Family Office — Introductions"
  (published id 1FAIpQLSd0ztOChg3y5w_Arq-iIMRdTEIeVY3SpkFD3GVt9qiEcRy_QA, owner
  patrick@jajehgroup.com, notifications on). On submit the form dissolves into a thank-you and
  localStorage key `jfo-introduction-requested` limits each browser to one request — this
  one-shot "we'll contact you" behavior is deliberate; do not add a normal contact form.
- The gold mark (assets/img/mark-gold.png) is generated from the brand kit's BoatOnly logo,
  recolored to brass #ad9161 — regenerate from the kit rather than editing pixels.

## Structure
- Plain HTML/CSS + ~110 lines of JS in index.html: `paint()` runs per scroll frame (sail position,
  `.is-active`, per-panel `--words` opacity, heading); `sailTo(k)` animates `window.scrollTo` with
  the cubic ease; wheel/touch/key handlers call it one panel per gesture (`innerRoom()` lets a
  panel whose words overflow — small screens only — scroll inside its `.wrap` first). The email
  capture is the other half. prefers-reduced-motion: instant moves, no heel/rock/sail-in.
- Panels are exactly one screen tall (`height: 100svh`); the footer lives inside the last panel so
  the page never rests on a footer-only screen.
- index.html, 404.html, assets/css/style.css, assets/img (marks from the Jajeh Logos kit).
- Local preview: `python -m http.server 8765` from the repo root (absolute /assets paths need a server).

## Domain — DIFFERENT REGISTRAR than the other Jajeh sites
- jajehfamilyoffice.com is registered at NAMECHEAP (not GoDaddy), DNS on
  dns1/dns2.namecheaphosting.com, MX on Namecheap Private Email (jellyfish.systems).
- Cutover (in Namecheap dashboard): apex A records → 185.199.108.153/.109/.110/.111,
  www CNAME → overtaxedgoose.github.io. Do NOT touch MX/TXT until confirming whether
  email @jajehfamilyoffice.com is in use.
