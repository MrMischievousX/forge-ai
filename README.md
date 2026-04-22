# Forge AI — Your codebase, in your pocket.

> "Coding is becoming optional. Decision-making is not."

Start AI coding tasks from anywhere. Review PRs on the go. Ship faster without being chained to your desk.

---

## The Problem

Lightweight engineering decisions — reviewing PRs, triaging bugs, guiding AI agents — are blocked by heavy tooling. GitHub's mobile experience is too limited for real work, AI tools live in separate IDEs, and developers delay action until they're back at a laptop.

**Result:** Issues sit open, PRs stack up, and context-switching kills flow.

---

## What Forge AI Does

Go from **issue → decision → merged PR** entirely from mobile, with AI doing the heavy lifting and you staying in control.

- **Issue → AI → PR** — tap an issue, dispatch to AI, get notified when the PR is ready, review and merge
- **Live task timeline** — step-by-step progress as the agent works, built from its GitHub issue comments
- **Token budget control** — set a max token budget before each task; cost visible in real time
- **AI transparency** — see which files the agent read, what it changed, and why
- **Mid-task steering** — post a comment from the app at any point; the agent picks it up and adapts
- **Smart PR review** — AI summary, risk level, and highlighted diff instead of raw code overload
- **GitHub native** — Issues, labels, comments, branches, and PRs are the complete state layer; no proprietary data store

---

## Core User Flows

| Flow | What happens |
|---|---|
| Fix it while I'm out | Bug reported → dispatch to AI → push notification → review PR → merge. Never opened a laptop. |
| Clear the PR backlog | Open app → AI-summarized PRs with risk badges → approve or request changes |
| Guide AI mid-task | Agent hits an ambiguous decision → you comment "use the existing utils module" → agent continues |

---

## How It Works

1. **Login** via GitHub OAuth and install the Forge AI GitHub App
2. **Add your Anthropic API key** — stored as a GitHub repo secret; Forge AI never holds it
3. **Tap an issue** → configure task type, constraints, token budget, and model
4. **Dispatch** — adds a `forge:pending` label, triggering the GitHub Actions workflow
5. **Watch the timeline** — the agent posts progress comments as it reads files, plans, and commits
6. **Review the PR** — AI summary, risk label, smart diff, one-tap approve and merge

---

## Key Differentiators

| Product | Focus |
|---|---|
| GitHub mobile | Code hosting, basic PR review |
| GitHub Copilot | In-IDE code completion |
| Cursor / Windsurf | AI-native desktop IDE |
| **Forge AI** | **AI execution + decision layer, mobile-first, async** |

The gap Forge AI fills: none of the above let you dispatch an AI coding task from your phone, walk away, and come back to a ready-to-merge PR.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Mobile | React Native (Expo) |
| Execution | GitHub Actions (ephemeral VMs) |
| Agent runtime | Forge AI reusable action |
| AI | Claude API — Sonnet 4.6 default, Opus 4.7 opt-in |
| State | GitHub (Issues, Comments, Labels, PRs) |
| Notifications | Firebase Cloud Messaging |
| Secrets | GitHub repository secrets (user-owned) |
| Backend | None |

---

## MVP Scope

**Must have**
- GitHub login + App installation
- Issue list → task configuration → dispatch
- GitHub Actions agent runner
- Task timeline from issue comments
- Push notifications (completion, blocked)
- PR summary view
- Approve / request changes

**Should have**
- Token usage display per task
- Risk badge on PRs
- Mid-task instruction via comment
- Smart diff (important changes only toggle)
- Token budget enforcement at planning

---

## Live Demo

[forge-ai landing page](https://mrmischievousx.github.io/forge-ai/)
