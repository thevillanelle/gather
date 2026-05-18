# Gather 🌐
### Team Event Intelligence Platform

A self-contained, single-file web app for planning team events smarter — built with zero dependencies (vanilla HTML, CSS, and JavaScript).

## What it does

**🎯 Event Portal** — A 10-question branching questionnaire that returns fully custom event plans ranked for your specific situation. Budget is shown per-person based on your headcount.

**🤖 Build Your Agent** — A step-by-step guide to setting up a Claude AI agent that plans events for you in 60 seconds. Includes a jump nav, a copy-ready system prompt, and FAQ.

**✨ Join the Team** — A fun, quiz-style onboarding intake form that captures event preferences, dietary needs, birthday/work anniversary, and more. Collapsible team directory included.

**💡 What We Love** — A force-directed interest map that visualizes team preferences as interactive clusters. Shows who loves what — and makes it immediately obvious what kind of events to plan.

## Features

- 🌙 **Dark / light mode** — toggle in the header, preference persists
- 🗺 **Interactive force graph** — scroll to zoom, drag to pan, drag individual nodes
- 💰 **Per-person budget estimates** — dynamically calculated from headcount
- 💾 **Local persistence** — intake submissions save to localStorage and appear in the map
- 🎯 **Smart event matching** — multi-dimension scoring across all 10 portal questions
- 🔌 **Plug-in ready** — all API calls are in a single `api{}` object; swap bodies for your backend

## How to use

```bash
# Just open it — no server, no install, no build step
open gather.html
```

Or drop it anywhere and double-click. It runs entirely in the browser.

## Connecting a real backend

All data calls live in one place at the top of the script:

```js
const api = {
  getEvents(filters) { /* → GET /api/events?... */ },
  getMembers()       { /* → GET /api/members     */ },
  submitMember(data) { /* → POST /api/members    */ }
}
```

Replace each function body with a `fetch()` call pointing to your Express/Node backend. The UI never changes.

## Stack

| Layer | Tech |
|---|---|
| Everything | Vanilla HTML + CSS + JavaScript |
| Data viz | Canvas 2D API (custom force simulation) |
| Persistence | `localStorage` |
| Dependencies | None |

## License

MIT — use it, fork it, build on it.
