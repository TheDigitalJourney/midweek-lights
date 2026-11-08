# Midweek Lights

An unofficial fan app for the 2026/27 UEFA Champions League league phase:

- **League table** with qualification zones, form and full fixtures
- **Match centre** for every played match: timeline, team stats, line-ups, minutes played and position maps
- **Players**: season stats, match-by-match minutes and fantasy points
- **Matchday previews** with a simple goals-based model estimate
- **News** round-up with links to the original reports
- **Fantasy**: pick an XI, create a league, invite friends with a code, and predict scores — sign in with an email link

Live site: https://thedigitaljourney.github.io/midweek-lights/

## How it works

A static site (no build step) served by GitHub Pages. Fantasy accounts, teams and leagues are stored in Supabase, protected by row-level security so each player can only change their own team. `config.js` holds the Supabase project URL and its **publishable** key, which is designed to be public.

## Data

Match data comes from public match reports (ESPN, UEFA.com and others; see the sources listed in the app). Position maps are built from official starting line-ups weighted by minutes played; they are not ball-tracking heat maps. `data.js` is updated after each matchday.

*Unofficial fan project. Not affiliated with UEFA or any club.*
