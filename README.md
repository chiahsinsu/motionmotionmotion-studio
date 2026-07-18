# Motion Studio

> Pick a template, adjust a few sliders, drop in your own content — get an embeddable animated showcase in minutes.

<!-- ⬇︎ DEMO VIDEO GOES HERE (hero — show the motion before the words).
     GitHub does NOT embed a video from a committed file (`![](x.mp4)` renders as a broken
     image, and <video> tags are stripped). A real player only appears when the file is
     dragged into the GitHub web editor. To add it:
       1. Open this README on github.com and click the pencil (Edit).
       2. Drag the file  motion-studio-demo-1080p.mp4  onto the line below this comment —
          GitHub uploads it and inserts a  https://github.com/user-attachments/assets/…  URL
          that renders as an inline player.
       3. Commit.
     Until then this hero is intentionally empty. -->

https://github.com/user-attachments/assets/ca3a41d2-b0ac-4eda-8162-86efe806e1ef


---

## What it is

Motion Studio is a web-based animation tool for designers. No code required — pick a template, pull a few sliders, drop in your own images, and you get a polished animated showcase you can embed straight into your portfolio or website.

It was built for a very specific frustration: freelance designers periodically refresh their portfolios, want to add some motion, and end up relearning tools, digging for old files, and trying to remember how they set things up months ago. Motion Studio aims to turn that into "open it, tweak it, export it."

## Why I built it

Most animation tools lock in the result the moment you're done. Video-based tools export a file — want to change it, and you start over. Effect libraries hand you a pile of ready-made animations, but each one is a dead end: swap the content or the style and you're building from scratch again.

Motion Studio's output isn't a frozen result — it's a **configuration you can reopen**. Every file you export carries its own settings inside it. Open the same file six months later and you don't need to remember anything or hunt for the source — you just keep adjusting from where you left off.

This isn't a technical flex. It's so that work you've already done can be reused and revised, instead of rebuilt every time.

## Core concepts

Three words give you the whole mental model:

- **Template** — the spatial archetype that decides *how things are arranged and how they move*. Cards orbiting a center, or fanned out along an arc, for example.
- **Preset** — a few personalities for one template, deciding *what it feels like*. Usually 5–7 per template.
- **Scene** — your one complete configuration, saved as JSON. Reopenable, embeddable, and (in development) exportable as video.

The template answers "what form is this," the preset answers "what mood is this," and the scene is the finished thing you've dialed in.

## Quick start

1. Open [Motion Studio](https://motion-studio-ecru.vercel.app)
2. Pick a template
3. Switch presets, pull sliders, drop in your own images
4. Export as embeddable HTML, or save a scene file to keep adjusting later

## Templates

Five templates, each with several presets. The clips below show each template's default preset (placeholder cards — drop in your own images to make it yours).

### orbit — cards rotating around a center
<img src="./assets/orbit.gif" alt="orbit template demo" width="360">

### carousel — an infinite marquee where cards flow along a line, with optional depth
<img src="./assets/carousel.gif" alt="carousel template demo" width="360">

### stack — cards stacking, entering and exiting one by one
<img src="./assets/stack.gif" alt="stack template demo" width="360">

### band — a masked marquee with a fisheye-like perspective
<img src="./assets/band.gif" alt="band template demo" width="360">

### coverflow — cards arranged along an arc with a focused center (that Apple Music feel)
<img src="./assets/coverflow.gif" alt="coverflow template demo" width="360">

## Interaction

An exported piece isn't just autoplay — it can respond to the viewer. All optional (off by default), and live in both the editor and exported embeds:

- **Drag / scroll / momentum** — visitors push the timeline themselves, with inertia on release; works with touch on mobile too
- **Cursor response** — cards react to the pointer: drawn toward it, scaled up, or turning to face it like a head

Turn them off and it's pure autoplay.

## Under the hood

For developers, and for future me:

- **`(config, t) → transform` pure-function model** — animation is a pure function of configuration and time, so the same moment in time always draws the same frame. This is what lets output be reconstructed deterministically.
- **App and embed dual renderers, pixel-identical** — what you see in the editor is the same frame you see once embedded on a site. Verified against a dual hash baseline (with a fixed clock) so the two never drift.
- **Self-describing output** — every export carries the engine version, schema version, and the full embedded scene, so it can be rebuilt in reverse. This is the mechanism behind "files you can reopen."
- **Schema-driven parameters** — the control panel is generated entirely from schema, with no template knowledge hardcoded into it.

## Status

A personal project, in active development.

Five templates ship today (orbit / carousel / stack / band / coverflow), each with several presets. The tool and landing page are deployed. Interaction — drag / scroll / momentum and cursor response — is live in both the editor and exported embeds. Export formats: embeddable HTML and scene JSON; video (mp4) export is in development.

Also available:

- A machine-readable scene spec for AI agents — [for agent](https://ms-landing-one.vercel.app/for-agent.html) — so an agent can generate a valid, importable scene from a description.
- A Cover Flow component submitted to the [Framer](https://www.framer.com/) marketplace (in review).

This is a project built by a visual designer (who doesn't code) working with AI — concept, visual direction, and product decisions are human-led; engineering execution is handled by AI.

Try it and send feedback — that's welcome.

## License

<!-- To be decided. Putting this on GitHub doesn't mean the code has to be open source —
     you can publish just the README + demo and keep the code private.
     If you do open source, MIT is the most permissive. Fill this in once decided. -->

_(License to be determined.)_
