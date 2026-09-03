# Helping Hand — interactive app mockup

A clickable, nine-screen mockup of **Helping Hand**, the transparency-first global giving and
volunteering platform described in the 2026 seed case study.

Two builds, both single self-contained files — no build step, no dependencies, no network calls.

| File | What it is |
|---|---|
| [`index.html`](index.html) | **The app prototype.** Just the phone. Goes full-bleed on mobile, so it demos like a real app on a handset. This is what GitHub Pages serves. |
| [`case-study-board.html`](case-study-board.html) | **The annotated board.** The same nine screens on a presentation canvas, each paired with a handoff panel listing its purpose, its features, the backend it needs, and the phase KPIs — all drawn from the case study. Use this one for the spec. |

Open either in any browser.

## Screens

| # | Screen | What it shows |
|---|---|---|
| 01 | Impact home | Points, Advocate rank, 7-day streak, daily mission — Phase 1 gamification |
| 02 | Profile | Passions, Traveling Mode toggle, payment methods, per-setting privacy |
| 03 | Local events | Beach Clean Up with instant RSVP, attendees, host EIN + program ratio |
| 04 | Travel Mode | Destination, dates, and selectable cause filters against matched programs |
| 05 | Charity spotlight | Build Water Wells in Kenya, with a line-item cost breakdown |
| 06 | Scan a charity | Camera viewfinder with three real scan verdicts (green / amber / red) |
| 07 | State of emergency | Live totals, hour-by-hour fund releases, volunteer site capacity |
| 08 | The Bank | Disbursement ledger with recipients and clearing dates, tax receipt |
| 09 | Impact Passport | Stamps, leaderboard, squad goal, CSR reward — Phases 2–5 |

### What's interactive

In both builds: the bottom tab bar, the in-app links between screens, the Traveling Mode switch,
the cause tags, the Bank's traced / pending / receipts segments, and the three scan targets in the
viewfinder. The board additionally carries a flow rail for jumping straight to any screen.

## Design notes

- The verification scale (green / amber / red) is a **separate palette from the brand accent**, so
  colour only ever means one thing: program expense ratio. An active 501(c)(3) can still read red.
- Type is Newsreader for money figures and headings, Libre Franklin for UI, IBM Plex Mono for EINs
  and ledger rows — the product's thesis is that giving should read like a receipt.
- Light and dark themes are both defined at token level, including the viewer's default
  "system" state.

## The Beach Clean Up scene loop

`assets/beach-loop.mp4` is a 3-second, 1280×720 motion-graphics loop that animates the Beach Clean
Up card. It is generated with **Kling 3.0 Turbo** (image-to-video) from
`assets/beach-start-frame.png`, which is itself a rasterization of `assets/beach-scene.svg` — the
card's own scene art, rebuilt at 16:9. Animating the app's real artwork keeps the clip on-palette
instead of drifting photoreal, and meant one generation did the whole job.

Waves, foam, gulls and a sun shimmer move; the volunteer silhouettes and the camera stay locked.
Mean per-pixel difference between the first and last frame is 3.62/255, so it loops with no visible
seam.

In both builds the clip is inlined as a data URI and shared by both the card and the event hero.
The static SVG scene sits underneath as a fallback, and the video is skipped entirely under
`prefers-reduced-motion`.

## A note on the figures

Every number in this mockup comes from the case study. The charity program-expense ratios shown in
the scanner are **estimates** drawn from public IRS Form 990 filings, IRS Pub 78, Charity Navigator,
and investigative reporting, and the app labels them as such on screen. A verified EIN is a
statement about registration status, not an endorsement.

This is a design mockup. Nothing here processes real money.
