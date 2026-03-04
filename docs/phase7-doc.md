# Phase 7 — Orchestrator

## Overview
A Slack slash command system that lets users trigger any agent on demand. Also includes background automations that run without user interaction.

## Slash Commands

| Command | Action |
|---|---|
| `/schedule` | Triggers Calendar Agent → sends schedule to Slack DM |
| `/emails` | Triggers Email Triage Agent → updates Notion |
| `/tasks` | Triggers Task Extraction Agent → updates Notion |
| `/briefing` | Triggers Daily Briefing Agent → sends briefing to Slack DM |
| `/register` | Registers user to receive automatic daily briefings |

## Workflow Architecture

### Orchestrator
```
Webhook (per slash command) → Set (capture slack_user_id) → Execute Sub-workflow
```

### Sub-workflows Called
- Calendar Agent (ID: Hmd46piN7DLEcC0G)
- Email Triage Agent (ID: F9Z3l7OTfADkDeVo)
- Task Extraction Agent (ID: ncokh8lISxuLV9ZX)
- Daily Briefing Agent (ID: BeHuPBLwljRqLTFj)

## Background Automations

| Automation | Trigger | Action |
|---|---|---|
| 📧 Email Triage | Every 30 mins | Adds tasks to Notion silently |
| ✅ Task Extraction | Every hour | Adds tasks to Notion silently |
| ☀️ Daily Briefing | Every day 8 AM | Sends briefing to all registered users |
| 🔔 Meeting Reminders | Every 15 mins | DMs user 30 mins before meetings |
| 📋 Task Summary | Every day 6 PM | Sends open tasks summary to Slack DM |
| 📅 Weekly Digest | Every Monday 8 AM | Sends week ahead summary to Slack DM |

## User Registration
- Users type `/register` in Slack
- Their Slack ID is saved to Notion AI Users database
- Daily briefings and automations are sent to all registered users

## Credentials Needed
- Slack Bot Token
- Notion API Key
- Groq API Key
- Gmail OAuth
- Google Calendar OAuth

## Status
✅ Slash commands working
🔨 Background automations in progress
