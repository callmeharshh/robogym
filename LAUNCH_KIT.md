# 🎬 RoboGym — Launch Kit

Everything you need to make RoboGym spread the day it goes live. Copy, tweak, post.

---

## ⚡ The one-liners (memorize these)

- **The hook:** "Foldit for robot manipulation — a browser game where playing trains real robots."
- **The thesis:** "Robots are starved for real-world manipulation data. We turn collecting it into a game."
- **The honest investor version:** "We're building the open *diversity layer* for the LeRobot ecosystem — the breadth of human demonstration data that labs can't buy, crowdsourced through a game and exported in the format Hugging Face already runs on."

---

## 📱 The 20-second demo video (X / TikTok / Reels)

Format: screen recording of the game + your voice or on-screen captions. Vertical 9:16. Fast cuts. No intro — start mid-action.

| Time | On screen | Caption / voiceover |
|------|-----------|---------------------|
| 0:00–0:03 | Arm snaps to a block, grabs it, drops it on target. **+100 ×3** pops. | **"I'm playing a game…"** |
| 0:03–0:07 | Quick combo: sort, then stack. Score climbing, sound effects. | **"…but every move I make"** |
| 0:07–0:11 | Cut to the DATASET panel: live JSON frames scrolling (joint_angles, ee, gripper). | **"is recorded as robot-training data."** |
| 0:11–0:15 | Show the "demos contributed" counter ticking up. Export → file downloads. | **"Real labeled demos. LeRobot format. Free."** |
| 0:15–0:20 | Cut to text card: *"Robots can't learn without human demos. So we made it a game."* + URL. | **"Play it. Train a robot. Link below."** |

**Pinned-comment / caption text:**
> Robots learn to grab, sort & stack from human demonstrations — and there's nowhere near enough. So I built RoboGym: a browser game where playing *is* the data collection. Every session exports as LeRobot-compatible training data. Built solo at 18. Link 👇

**Hashtags:** `#PhysicalAI #robotics #AI #LeRobot #embodiedAI #buildinpublic`

---

## 🐦 Launch thread (X)

**Tweet 1 (the hook):**
> Robots can't learn to use their hands without human demonstrations — and the world is critically short on them.
>
> So I built a game where *playing* generates that data.
>
> Meet RoboGym 🤖 a browser game that trains robots. Solo-built, I'm 18. 🧵

**Tweet 2 (show, don't tell):** [attach the 20s video]
> You steer a robot arm to reach, sort & stack. Combos, leaderboard, the works.
>
> But under the hood, every frame logs joint angles + actions as a LeRobot-compatible training episode. The fun *is* the data pipeline.

**Tweet 3 (the why / credibility):**
> Why this matters: $27B went into Physical AI in 2025, but labs collect data by paying teleoperators one task at a time. Slow, narrow.
>
> The thing they can't buy is *breadth* — thousands of people solving tasks thousands of ways. A game collects that best.

**Tweet 4 (the honest framing — this earns respect):**
> I'm not claiming a 2D game trains a humanoid by itself. This is high-diversity data for *co-training & demo-amplification* — the exact axis the research (RoboCade, Stanford '25) shows boosts policy success 16–56%.

**Tweet 5 (CTA):**
> Play it right now, no signup, train a robot in 60 seconds 👇
> [URL]
>
> Open dataset, built in public. Tell me what to build next.

---

## 💰 Investor blurb (for a cold email / DM / deck slide)

> **RoboGym** is the open data layer for Physical AI. Robot foundation models are bottlenecked on real-world manipulation data; the field's scarcest input is *diversity* of human demonstrations, which the leading labs collect in-house and teleop vendors sell at warehouse cost. We crowdsource it through a browser game — players solve manipulation puzzles, and every session becomes a labeled, LeRobot-compatible training episode pooled into an open dataset. Stanford's RoboCade ('25) proved gamified collection lifts policy success 16–56%; we're the first to do it as a public, internet-scale, browser-native loop exporting the de-facto open format. Game = distribution and a compounding data moat; we monetize via dataset access and pipelines for the labs and the 16,000+ LeRobot projects already on Hugging Face.

**Three numbers to know cold:**
- **$27.6B** into robotics/Physical AI in 2025 (PitchBook).
- **16–56%** policy-success lift from gamified demo data (RoboCade, Stanford, 2025) — our benchmark to beat.
- **~16,000** LeRobot datasets on Hugging Face; median size just **10 episodes** — the ecosystem is starving for volume *and* breadth.

---

## ✅ Pre-launch checklist
- [ ] Deploy the game (see `GO_LIVE.md`) so the URL is public + the global counter is real.
- [ ] Record the 20s demo on the deployed version (so the leaderboard/counter look alive).
- [ ] Set the landing page `GAME_URL` to the deployed game URL.
- [ ] First post target: a builder-friendly audience (X #buildinpublic, r/robotics, Hacker News "Show HN").
- [ ] Have the open dataset ready to share — researchers pulling it is your strongest credibility signal.
