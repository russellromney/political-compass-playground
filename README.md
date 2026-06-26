# 2020s Political Compass — Playground

A tiny single-page toy for the [BritMonkey "2020s Political Compass" test](https://britmonkey.com/2020s-political-compass/).

Drag four sliders and watch your **cluster** of nearest public figures update live. No build step, no dependencies — just `index.html`.

👉 **[Open the playground](https://russellromney.github.io/political-compass-playground/)** (GitHub Pages)

## How the original model works

The BritMonkey quiz isn't a 2-axis compass — it's **4 independent axes**, each scored from **−32 to +32** (16 questions × answer −2…+2 × weight ±1):

| Axis | + pole | − pole |
|------|--------|--------|
| `prog_cons` | Woke | Chud |
| `tech_ludd` | Techbro | Neo-Luddite |
| `mod_nihil` | Hopepilled | Doomer |
| `dav_dub` | Davos | Dubai |

Your result is simply the **single nearest figure by Euclidean distance** in that 4-D space. That's it — no quadrants, no weighting.

### Why "everyone gets Rishi Sunak"

The 30 figures in the original quiz are mostly *extremists* — loud on at least one axis. Sunak is one of the only **moderate** figures, sitting at `(−10, +12, +12, +12)`: mildly chud, mildly pro-tech, mildly optimistic, mildly globalist. That's exactly where a normal, mildly-online person lands — so most real respondents collapse onto him. Sampling the realistic "normie zone" sends **~44%** of it to Sunak. The quiz has no anchor at the true centre, so the nearest moderate wins by default.

This playground adds **110 US figures** (politicians, Twitter/X commentators, tech & business) so there's something to match other than four British politicians and a pope.

## The data

`figures.js` (and `figures.json`) holds every figure as 4-axis coordinates.

- **30 BritMonkey figures** use the site's **exact** coordinates, scraped from the page.
- **110 US figures** (politics / business / media & X commentators) are **subjective estimates** by the author. They're meant to start arguments — open a PR and fight about them.

```js
{ "name": "Marc Andreessen", "group": "US Business",
  "description": "VC, Andreessen Horowitz",
  "scores": { "prog_cons": -20, "tech_ludd": 32, "mod_nihil": 6, "dav_dub": -10 } }
```

## Run locally

Just open `index.html` in a browser. (Data is embedded in `figures.js`, so it works over `file://` — no server needed.)

## Credits

Model and the original 30 figures © [BritMonkey](https://britmonkey.com/2020s-political-compass/). This repo is an unaffiliated fan toy for poking at the model.
