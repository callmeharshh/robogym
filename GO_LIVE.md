# 🚀 RoboGym — Go Live (global data pool + leaderboard)

The game runs single-player out of the box (data saved in your browser). To turn it
into a **real product** — one shared global "demos contributed" counter, a global
leaderboard, and a pooled training dataset every player contributes to — do these
two free steps. Total time: ~15 min. Cost: $0.

> ⚠️ The claude.ai artifact link blocks network calls, so the global features only
> switch on once the game is deployed to a normal host (Step 2). That's expected.

---

## Step 1 — Create the backend (Supabase, free)

1. Go to **https://supabase.com** → sign up → **New project**. Pick any name +
   a database password (save it). Wait ~2 min for it to provision.
2. In the left sidebar open **SQL Editor** → **New query**, paste the block below,
   hit **Run**. This creates the tables, opens them for the game to read/write, and
   adds the global-total function.

```sql
create table if not exists scores (
  id bigint generated always as identity primary key,
  created_at timestamptz default now(),
  handle text not null,
  score int not null,
  demos int default 0,
  combo int default 0,
  mode text
);

create table if not exists contributions (
  id bigint generated always as identity primary key,
  created_at timestamptz default now(),
  handle text,
  demos int,
  frames int,
  data jsonb
);

alter table scores enable row level security;
alter table contributions enable row level security;

create policy "anon insert scores"  on scores        for insert to anon with check (true);
create policy "anon read scores"    on scores        for select to anon using (true);
create policy "anon insert contrib" on contributions for insert to anon with check (true);

create or replace function global_totals()
returns json language sql security definer as $$
  select json_build_object(
    'demos', coalesce((select sum(demos) from scores), 0),
    'runs',  (select count(*) from scores)
  );
$$;
grant execute on function global_totals() to anon;
```

3. In the sidebar go to **Project Settings → API**. Copy two values:
   - **Project URL** (e.g. `https://abcd1234.supabase.co`)
   - **anon public** key (the long one labeled `anon` / `public` — safe to ship in frontend)

4. Open `robogym.html`, find this line near the top of the `<script>`:

   ```js
   const CLOUD = { url:"", key:"" };
   ```

   Paste your values in:

   ```js
   const CLOUD = { url:"https://abcd1234.supabase.co", key:"eyJhbGci...your-anon-key..." };
   ```

That's it — the game now reads/writes the global pool.

---

## Step 2 — Deploy it (Netlify Drop, free, no CLI)

The fastest path to a public URL:

1. Rename `robogym.html` → `index.html`.
2. Go to **https://app.netlify.com/drop** and **drag the file** onto the page.
3. You get a live URL instantly (e.g. `robogym.netlify.app`). Sign up (free) to keep it.

Want a custom domain later? Netlify gives you one free `.netlify.app` subdomain, or
point your own domain in settings. **Vercel** (https://vercel.com) works the same way
if you prefer it.

---

## Verify it's live
- Open your deployed URL. The header counter should say **"demos contributed (global)"**.
- Play a run → on the results screen your score should appear on the **Global leaderboard**
  (open the game in a second browser/incognito to confirm it's shared).
- Check Supabase → **Table Editor → scores / contributions** — you should see rows.

## Notes / next hardening (later, not now)
- The `anon` key is meant to be public; Row Level Security policies above only allow
  insert + read of scores, never deletes. Fine for launch.
- Add basic rate-limiting / a profanity filter on `handle` before you go big.
- The `contributions.data` column stores the full LeRobot-like episode JSON — that's
  your actual training-data asset accumulating in one place. Back it up / export from
  Supabase as it grows.
