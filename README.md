# ClipDash AI - Smart Clipboard Manager

**Day 12 of 100 Days, 100 AI Agents**

ClipDash AI catches everything you copy, auto-categorizes it, strips URL trackers, formats JSON, detects sensitive data, deduplicates entries, and makes your entire clipboard history searchable — all in a single-page app with zero backend and zero API keys.

## How It Works

A single agentic engine (`ClipDashAgent`) runs entirely in-browser:

1. **Capture** — Listens for paste events and reads clipboard on tab focus
2. **Detect** — 10 category detectors identify content type (link, email, phone, code, color, address, number, JSON, sensitive, text)
3. **Enhance** — Strips 20+ URL tracker params, formats JSON, detects code language (JS, Python, HTML, CSS, SQL, Go, Rust, Java, YAML), flags sensitive data (SSN, credit card, API key patterns)
4. **Organize** — Deduplicates, timestamps, persists to localStorage, makes everything filterable and searchable

## Features

- 10 auto-detected categories with instant filtering
- URL tracker removal (utm_*, fbclid, gclid, etc.)
- Code language detection across 9 languages
- Sensitive data flagging (SSN, credit cards, API keys, passwords)
- JSON auto-formatting and validation
- Color preview for hex/rgb/hsl values
- Pin/favorite important clips
- Full-text search across all clips
- Export clipboard history as JSON
- Zero backend, zero API keys, zero setup

## Quick Start

1. Open `public/index.html` in any browser
2. Start copying things — ClipDash captures automatically
3. Use Ctrl+V / Cmd+V anywhere on the page to manually add clips
4. Filter by category, search, pin favorites, export

No server, no API key, no install. Just open and use.

## Tech Stack

- Vanilla HTML/CSS/JS (single file)
- Clipboard API + paste events
- localStorage for persistence
- Zero dependencies

## Architecture

Unlike the usual 4-agent swarm, ClipDash uses a single agentic architecture — one intelligent agent class that handles detection, categorization, enhancement, and organization in a single pass. This design choice reflects the nature of the problem: clipboard management needs instant (<5ms) processing with zero external calls.

```
Paste Event / Tab Focus
        ↓
   ClipDashAgent
   ├── categorize() — 10 detector pipeline
   ├── process() — enhance based on category
   ├── deduplicate() — content hash check
   └── persist() — localStorage + UI update
```

## Project Structure

```
Day-12-ClipDash/
├── public/
│   └── index.html      # Complete single-file app
├── README.md
├── startup-one-pager.md
└── LINKEDIN-POST.md
```
