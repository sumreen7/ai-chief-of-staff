# 🤖 Personal AI Chief of Staff
An always-on, multi-agent AI productivity assistant built with **n8n**, **Claude AI**, **Gmail**, **Google Calendar**, **Slack**, and **Notion**.

> Automates email triage, calendar management, task extraction, and daily briefings — so you can focus on what matters.

---

## 🧠 Agents Overview

| Agent | What It Does |
|---|---|
| 📧 Email Triage Agent | Reads Gmail, flags priorities, drafts replies |
| 📅 Calendar Agent | Protects focus time, surfaces daily schedule |
| ✅ Task Extraction Agent | Pulls action items from emails & Slack into Notion |
| ☀️ Daily Briefing Agent | Sends a morning summary to Slack every weekday |

---

## 🏗️ Tech Stack

- **Automation:** [n8n](https://n8n.io) (self-hosted on Railway free Cloud)
- **AI Model:** [Claude API](https://console.anthropic.com) (Anthropic)
- **Email:** Gmail API
- **Calendar:** Google Calendar API
- **Messaging:** Slack API
- **Tasks/DB:** Notion API

---

## 📁 Repo Structure

```
ai-chief-of-staff/
├── workflows/
│   ├── email-triage-agent.json
│   ├── calendar-agent.json
│   ├── task-extraction-agent.json
│   ├── daily-briefing-agent.json
│   └── orchestrator.json
├── docs/
│   ├── phase-1-setup.md
│   ├── phase-2-connect-tools.md
│   ├── phase-3-email-triage.md
│   ├── phase-4-calendar-agent.md
│   ├── phase-5-task-extraction.md
│   ├── phase-6-daily-briefing.md
│   └── phase-7-orchestrator.md
├── .env.example
├── .gitignore
└── README.md
```

---

## 🚀 Setup Guide

### Prerequisites
- Railway Cloud free account (or any Ubuntu server)
- Google Cloud account (for Gmail + Calendar APIs)
- Slack workspace
- Notion account
- Anthropic API key

### Phase 1 — Install n8n on Oracle Cloud
See [docs/phase-1-setup.md](docs/phase-1-setup.md)

### Phase 2 — Connect Your Tools
See [docs/phase-2-connect-tools.md](docs/phase-2-connect-tools.md)

### Phase 3–7 — Build Each Agent
Follow the numbered docs in the `/docs` folder in order.

---

## 🔐 Environment Variables

Copy `.env.example` to `.env` and fill in your keys:

```env
ANTHROPIC_API_KEY=your_key_here
NOTION_API_KEY=your_key_here
SLACK_BOT_TOKEN=your_key_here
```

> ⚠️ Never commit your `.env` file. It is listed in `.gitignore`.

---

## 📸 Screenshots
_Coming soon as each agent is built._

---

## 🛣️ Roadmap

- [x] Project setup & documentation
- [ ] Phase 1 — n8n on Oracle Cloud
- [ ] Phase 2 — Connect Gmail, Calendar, Slack, Notion
- [ ] Phase 3 — Email Triage Agent
- [ ] Phase 4 — Calendar Agent
- [ ] Phase 5 — Task Extraction Agent
- [ ] Phase 6 — Daily Briefing Agent
- [ ] Phase 7 — Orchestrator

---

## 🤝 Contributing
This is a personal project, but feel free to fork it and adapt it for your own use!

---

## 📄 License
MIT
