# AcademyScore

AcademyScore is a frontend-only football academy and live competition platform with public scores, role-based workspaces, and a mobile referee control desk.

## Run & Operate

- `pnpm --filter @workspace/academyscore run dev` — run the AcademyScore web app through its managed workflow
- `pnpm run typecheck` — full typecheck across all packages
- `PORT=21166 BASE_PATH=/ pnpm --filter @workspace/academyscore run build` — production build check outside the managed workflow

## Stack

- pnpm workspaces, Node.js 24, TypeScript 5.9
- Frontend: React, TypeScript, Vite, React Router
- UI: Tailwind CSS, Lucide React, Recharts
- State: React state and localStorage-backed mock data/session

## Where things live

- `artifacts/academyscore/src/App.tsx` — routes, centralized mock data, role sessions, and referee match state
- `artifacts/academyscore/src/index.css` — AcademyScore theme and responsive match-control styles
- `artifacts/academyscore/package.json` — web app scripts and frontend dependencies

## Architecture decisions

- The first build is intentionally frontend-only; no API, database, or real authentication is required.
- Demo sessions and referee match mutations persist in localStorage so public and role views remain usable after refresh.
- The referee live-control route is optimized for one-handed mobile use and is the source of truth for match-day updates.

## Product

Public visitors can browse live scores, fixtures, competitions, teams, players, and rankings. Coaches, players, and referees can sign in with the demo accounts and use separate workspaces; referees can start matches, record goals/cards/fouls/substitutions, pause for half time, and submit reports.

## User preferences

_Populate as you build — explicit user instructions worth remembering across sessions._

## Gotchas

_Populate as you build — sharp edges, "always run X before Y" rules._

## Pointers

- See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details
