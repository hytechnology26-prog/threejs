# The One Who Didn't Come Back

A short, cinematic 3D scene built entirely in the browser with [Three.js](https://threejs.org) — one continuous, unbroken camera shot moving through a single night, from warm midnight to cold dawn. No character. No 3D modeling. Just light, time, and an empty room.

**🔗 Walk through it yourself:** https://threejs-psi-orcin.vercel.app

**🎥 Watch the full video** (how it was made, step by step, including everything that broke):
[Link to YouTube video]

---

## What this is

A room. A desk. A lamp still on. A cup of coffee going cold. A chair pushed back, like someone just left. The camera drifts through the space for about 80 seconds, and the light shifts from warm night to cold morning — the person never comes back.

I'm not a 3D artist and I've never opened Blender. This was built by directing AI (Claude Code) — describing the mood and story I wanted in plain English, and iterating on the result until it felt right. This repo has the real prompts, the real code, and the real mistakes along the way.

## How it was made (short version)

1. **Models** — four free, CC-licensed low-poly models from [poly.pizza](https://poly.pizza): a table, a chair, a lamp, and a coffee mug (credits below).
2. **The direction** — instead of specifying coordinates, I described a feeling to Claude Code: *"a dim room at night, someone just left, the lamp is still on, there's still coffee in the cup."*
3. **The iteration** — the first version was almost pure black, the lamp looked switched off, and the steam looked like broken pixels. Getting from that to the final version was a back-and-forth: "make the lamp glow," "the steam should only rise from the cup," "the morning light needs to actually light the room."
4. **One continuous shot** — the final structure is a single camera path (a Catmull-Rom curve through 6 keyframes) with lighting that interpolates smoothly alongside it, so the whole thing plays as one unbroken take rather than 6 cut scenes.

The full narration of this process is in the YouTube video linked above.

## Why 3D instead of an AI-generated image or video?

Image generation gives you separate, disconnected pictures. What I wanted was one real, continuous space where time visibly passes — the same camera, the same lamp, the coffee going cold, night turning to dawn. That continuity is something only an actual 3D world can do.

## Running it locally

No build step — it's a static page.

```bash
git clone https://github.com/hytechnology26-prog/threejs.git
cd <your-repo>
python3 -m http.server 8000
```

Then open `http://localhost:8000/empty-room.html`.

**Controls:**
- `Space` — pause / play the timeline
- `R` — restart
- Click and drag — manually orbit the camera (pauses the auto sequence)

## Project structure

```
.
├── index.html        # entry point / landing page
├── empty-room.html   # the main scene (Three.js)
└── models/           # GLB models (table, chair, lamp, cup)
```

## Built with

- [Three.js](https://threejs.org) — 3D rendering in the browser
- [Claude Code](https://claude.com/claude-code) — directed the scene, lighting, camera path, and debugging
- [poly.pizza](https://poly.pizza) — free 3D models
- Deployed on [Vercel](https://vercel.com)

## 3D model credits

Free models via poly.pizza, used under their respective licenses:

- Table — CreativeTrio
- Chair — Quaternius
- Table Lamp — Quaternius
- Coffee Cup — Aaron Clifford

*(Please double-check each model's page on poly.pizza for the exact license/attribution terms and update this list if any names or license types are incorrect.)*

## License

Code in this repo is free to use, adapt, and learn from. The 3D models are third-party assets — see their individual licenses on poly.pizza before reuse.

---

If you'd rather build with AI than fight it, I make videos about exactly this on [ThinkSimpleAI](https://www.youtube.com/@ThinkSimpleAIs).
