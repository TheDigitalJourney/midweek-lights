# Midweek Lights

An unofficial fan app for the 2026/27 UEFA Champions League league phase:

- **League table** with qualification zones, form and full fixtures
- **Live scores** with match clock, goal alerts and live match centre
- **Match centre** for every played match: timeline, team stats, line-ups, minutes played and position maps
- **Players**: season stats, match-by-match minutes and fantasy points
- **Matchday previews** with a simple goals-based model estimate
- **News** round-up with links to the original reports
- **Fantasy**: pick an XI, create a league, invite friends with a code, and predict scores — sign in with Google

Live site: https://thedigitaljourney.github.io/midweek-lights/

## How it works

A static site (no build step) served by GitHub Pages. Fantasy accounts, teams and leagues are stored in Supabase, protected by row-level security so each player can only change their own team. `config.js` holds the Supabase project URL and its **publishable** key, which is designed to be public.

## Data

**Live updates:** each visitor's browser reads ESPN's public Champions League feed directly — live scores and match clock (every 30 seconds while a match is on), goals, cards, substitutions, line-ups, team stats, the table and news. Season player stats and fantasy points are updated automatically from finished matches. No server or scheduled job is involved.

**Verified fallback:** `data.js` holds checked data (results, line-ups and stats from ESPN, UEFA.com and others). If the live feed is unavailable or changes format, the app keeps showing this data. `espn-ids` in `data.js` maps ESPN's team and player IDs to the app's.

Position maps are built from official starting line-ups weighted by minutes played; they are not ball-tracking heat maps.

Club crests in `crests/` are trademarks of their respective clubs, used here only to identify the teams. They were taken from each club's Wikipedia page. If you represent a club and want a crest removed, open an issue.

*Unofficial fan project. Not affiliated with UEFA or any club.*
