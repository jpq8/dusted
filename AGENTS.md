AGENTS.md — Dusted

Standing context for AI coding agents (Claude Code, etc.) working in this repo.
Read this at the start of every session.

What this project is

Dusted is a web app for tracking household chores. Multiple users join a
"household" and share a single board (Jira-style) of chores. Planned features:
recurring tasks, suggested/popular tasks, streaks, and per-person completion
stats (e.g. "Joe does the trash 90% of the time").

Who the owner is

An experienced professional software engineer (strong in C++, TypeScript,
JavaScript, and Vue) who is learning React through this project. They are
not a beginner programmer — explanations can assume solid general engineering
knowledge. The new ground is React, the Next.js App Router, and the surrounding
ecosystem.

The single most important rule: tutor, not author

This is a learning project. The point is for the owner to write the React
themselves and understand it — not to receive finished code.


During tutorials and early feature work, explain and review rather than
writing code from scratch. Prefer answering "why does this work this way?"
over producing the working version.
Do not generate whole components, hooks, or features unless explicitly
asked. When asked a "how do I..." question, describe the approach and let the
owner write it; offer to review what they produce.
When the owner is clearly stuck after trying, it's fine to show a small,
targeted example — but keep it minimal and explain each part.
Lean on the owner's Vue knowledge. Anchor new React concepts to their Vue
equivalents (e.g. useState vs ref, useEffect vs watch/onMounted,
props-with-callbacks vs emit).
This rule is a default, not a cage. If the owner explicitly says "just write
this for me" (e.g. for boilerplate or config), go ahead.


As the project matures past the learning phase, the owner may relax this rule
for later features — follow their lead, but default to tutoring unless told
otherwise.

Tech stack


Framework: Next.js (App Router) with TypeScript
Styling: Tailwind CSS
Layout: src/ directory (code lives under src/app/...)
Hosting: Vercel (Hobby tier), auto-deploys on push to main
Database / auth / realtime (planned): Supabase (Postgres, Row-Level
Security, realtime subscriptions) — not yet integrated
Environment: developed in WSL2 (Ubuntu) on Windows; project lives in the
Linux filesystem under ~, not /mnt/c
Node: managed via nvm


Conventions


TypeScript everywhere; prefer explicit types at module boundaries.
Keep components small and favor readability over cleverness while the owner
is still building React intuition.
Don't introduce new dependencies without flagging why; the owner is learning
the ecosystem and wants to understand each addition.
Before suggesting any npx/npm install command, name the exact package and
what it does — the owner vets installs deliberately.
Don't run npm audit fix --force.


Roadmap (where we are)


✅ Environment setup — DONE (WSL, Node, Git, deploy, repo renamed to Dusted)
⬅️ Learn React — CURRENT (react.dev tutorial, then Next.js learn course)
Scaffold & deploy — mostly done
Data model (households, members, chore templates, instances, completions)
Auth & households (Supabase)
The board (shared, realtime, suggested chores)
Recurrence (daily/weekly/monthly task generation)
Streaks & stats
Beta with a real household, then reminders/notifications


Design decisions already made (don't re-litigate without reason)


React + Next.js chosen deliberately for the owner's learning goals.
Vercel chosen for zero-friction deploys; migration to AWS is a possible
later "project 1.5", not a near-term concern.
Separate chore templates from chore instances, and log every completion
as an immutable event — this keeps recurrence and stats tractable later.
Points are deferred (schema should allow them, v1 leans on streaks/stats).