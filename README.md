# 🤖 RoboGym

**The open data layer for Physical AI.** *Play a game. Train a robot.*

RoboGym is a browser game where steering a simulated robot arm through manipulation
tasks (reach, sort, stack) silently generates real, exportable robot-training data in a
[LeRobot](https://github.com/huggingface/lerobot)-compatible format. The game is the
viral front door; the pooled, high-diversity demonstration dataset is the moat.

> *Foldit for robot manipulation* — robots can't learn to act in the real world without
> human demonstrations, and the world is critically short on them. So we made collecting
> them a game.

## 🎮 Play

Just open the site — no signup, play in one click. *(Live URL coming once deployed.)*

## 🗂 Project structure

| File | What it is |
|------|-----------|
| `index.html` | Marketing landing page (Bold Editorial design) |
| `robogym.html` | The game — engine, UI, and data-logging pipeline |
| `PRD.md` | Full product requirements doc — vision, architecture, roadmap |
| `GO_LIVE.md` | Backend + deploy guide (Supabase + Netlify, with SQL) |
| `LAUNCH_KIT.md` | Demo-video script, launch thread, investor blurb |

## 🛠 Tech stack

Vanilla HTML + CSS + JavaScript · HTML5 Canvas 2D · Web Audio API · Google Fonts
(Bricolage Grotesque / Hanken Grotesk / JetBrains Mono). **No build step, no dependencies.**
Planned backend: [Supabase](https://supabase.com) (Postgres + REST). Hosting: Netlify.

## 🏃 Run locally

It's a static site — no install needed. Either open `index.html` directly, or serve it:

```bash
python3 -m http.server 8123
# then visit http://localhost:8123
```

## 🚀 Going live

See [`GO_LIVE.md`](./GO_LIVE.md) to switch on the global leaderboard + pooled dataset
via a free Supabase project, and deploy to Netlify.

## 🗺 Roadmap

- [x] Playable game + landing page + data export
- [ ] **Phase 1** — Supabase backend (global pool/leaderboard) + Netlify deploy
- [ ] 3D simulation + more tasks + publish open datasets to Hugging Face
- [ ] Prove downstream policy lift (beat RoboCade's 16–56%)

See [`PRD.md`](./PRD.md) for the full plan.

---

Built in the open. 2026.
