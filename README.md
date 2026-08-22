# Deal Flow

An infinite-scroll feed of machine-generated modern business pitches — a new venture name, one-line pitch, wedge, and momentum score on every card, forever.

Single self-contained `index.html`, no build step, no backend, no external requests at runtime (fonts are subsetted and embedded as base64 WOFF2).

## How it works

Each card is generated from a large combinatorial word bank (industries × business models × mechanisms × audiences × differentiators × name fragments × sentence templates — well over a billion possible pitches) using a seeded PRNG, so the feed is deterministic-but-varied and never runs out. Scrolling near the bottom triggers `IntersectionObserver` to generate and append the next batch. A shuffle button re-rolls the session seed for an entirely fresh run.

## Run locally

```
python3 -m http.server 8000
```

then open `http://localhost:8000`.
