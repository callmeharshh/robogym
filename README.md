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

**▶ Live: https://robogym.netlify.app** — no signup, play in one click.

Play a few rounds to teach the arm, then hit **"🤖 Watch the AI play what you just taught it"** —
it solves tasks on its own using an in-browser imitation-learning policy trained on *your*
demonstrations. The loop closes: you demonstrate → it learns → the robot acts autonomously.

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
- [x] **Autopilot** — in-browser nearest-neighbour imitation learning (the arm plays autonomously from your demos)
- [x] Deployed live to Netlify + GitHub
- [ ] **Phase 1 (in progress)** — Supabase backend: global pool, global leaderboard, live counter
- [ ] 3D simulation + more tasks + publish open datasets to Hugging Face
- [ ] Prove downstream policy lift (beat RoboCade's 16–56%)

See [`PRD.md`](./PRD.md) for the full plan.

---

Built in the open. 2026.
