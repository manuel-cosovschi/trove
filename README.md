# Trove

A personal life-management Progressive Web App. Track ventures, goals, fitness,
habits, sleep, routine and a journal — all in one place. **100% offline**, no
backend, no accounts. Everything is stored locally on your device via
`localStorage`.

## Modules

- **Today** — greeting, day-streak, today's focus tasks, habit rings, last
  night's sleep, mood & energy check-in, and a water tracker.
- **Ventures** — track businesses/side-projects with revenue goals, objectives,
  daily tasks (auto-reset each day), and notes.
- **Goals** — personal goals with milestones and progress bars, grouped by
  category or viewed on a timeline.
- **Fitness** — workout logging + weekly volume chart, body metrics + weight
  chart, PR tracker, and fitness goals.
- **Habits** — daily check-ins, current/longest streaks, a 3-month heatmap, and
  weekly completion rate.
- **Me** — time-blocked daily routine, sleep log with debt tracker, a searchable
  journal, and settings (units, goals, export/import/clear data).

## Install on iPhone

1. Open the app's URL in **Safari** (it must be served over `https://` or
   `localhost` for the service worker to register).
2. Tap the **Share** button (the square with the up-arrow).
3. Scroll down and tap **Add to Home Screen**.
4. Tap **Add**. Trove now launches full-screen from your home screen and works
   offline.

> On Android/desktop Chrome you'll get an install prompt, or use the browser
> menu → *Install app*.

## Run locally

A service worker requires an HTTP origin (opening `index.html` via `file://`
won't register it). Serve the folder with any static server:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Backup & restore

Go to **Me → Settings**:

- **Export all data (JSON)** downloads a full backup file.
- **Import from backup** restores from a previously exported file.
- **Clear all data** wipes everything (with confirmation).

## Files

| File            | Purpose                                  |
|-----------------|------------------------------------------|
| `index.html`    | The entire app (HTML + CSS + JS)         |
| `sw.js`         | Service worker (cache-first, offline)    |
| `manifest.json` | PWA manifest (installability)            |
| `icon-192.png` / `icon-512.png` | App icons                |

## Tech

Vanilla HTML/CSS/JavaScript. No frameworks, no build step, no external runtime
dependencies. Dark mode follows your system setting via
`prefers-color-scheme`.
