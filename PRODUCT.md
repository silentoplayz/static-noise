# Static as a product

An honest plan. The code can be made product-grade in a repo; worth is decided
by people finding it, using it, and paying for it. This file separates the two.

## What "product-grade" means here, and what is done

| Need | Why it matters for a noise product | Status |
|---|---|---|
| Stereo output | Mono noise sounds like a point source; decorrelated stereo sounds like a room. | Done: two independent, deterministic phase sets. |
| No interface stalls | Rendering a 5 s loop is heavy; users drag sliders constantly. | Done: DSP runs in a Web Worker, requests coalesce, main-thread fallback. |
| Sleep timer | The main use of noise apps is falling asleep. | Done: 15–90 min, 20 s fade, restores volume after. |
| Shareable links | Distribution comes from people sending "hear this". | Done: URL hash restores colour, blackbody, source or a drawn spectrum. |
| Export | People want the sound in their own player or DAW. | Done: one-minute 48 kHz 16-bit stereo WAV, tiled from the seamless loop. |
| Installable, offline | Bedside use, flights, no dependence on the host. | Done: web app manifest, service worker, icons. |
| Lock-screen controls | Playing in the background on a phone. | Done: Media Session metadata and play/pause handlers. |
| Social previews | A link with a card gets clicked; a bare link does not. | Done: Open Graph and Twitter tags with a 1200×630 card. |
| Privacy | A selling point against ad-funded competitors. | Done by construction: no network requests, no analytics, no accounts. |

## What the code cannot do

- **Reach.** Nobody will find this without distribution. The audiences that fit:
  science communicators and physics teachers ("hear a candle", "hear hydrogen"),
  sleep and focus communities, generative audio and synth forums, Hacker News
  and Product Hunt for the launch day.
- **Trust.** A name, a domain, a short explainer video and a clear "what it does
  and doesn't do" page matter more than any feature.
- **Money.** Options, cheapest first: a tip link (GitHub Sponsors, Ko-fi);
  a paid "pro" tier with longer exports, custom presets sync and higher sample
  rates; a native wrapper on the app stores at a one-off price, which is where
  noise apps actually get paid. Each needs accounts and decisions only the
  owner can make.

## Suggested next steps, in order

1. Register a domain and point GitHub Pages at it. Add the domain to the
   manifest and Open Graph tags.
2. Record a 40-second screen capture: pick a colour, switch to spectrum, press
   the candle, press hydrogen. Post it with the link.
3. Add a tip link once an account exists; keep it to one line in the footer.
4. Collect the ten most-shared links (the hash encodes them) and publish them
   as named presets.
5. Only then decide about a paid tier or a store wrapper, based on who showed up.

## Honest valuation reminders

- A tool with no users is worth its replacement cost to the owner and roughly
  nothing to a buyer.
- A tool with a few thousand monthly users and a tip link is worth a modest
  side income.
- A store app in the sleep category with good ratings can earn real money, but
  that is a marketing and support business, not a code business.
