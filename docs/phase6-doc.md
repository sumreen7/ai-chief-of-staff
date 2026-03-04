# Phase 6 — Daily Briefing Agent

## Overview
Every morning at 8 AM, pulls today's calendar events and open Notion tasks, synthesizes everything with Groq AI, and sends a clean friendly briefing to Slack.

## Workflow
Schedule Trigger (8 AM) → Google Calendar → Aggregate (events) → Notion (Get Tasks) → Aggregate (tasks) → HTTP Request (Groq AI) → Send Message (Slack)

## Nodes

### 1. Schedule Trigger
- Runs every day at 8:00 AM

### 2. Google Calendar
- Fetches all events for today
- After: start of day
- Before: end of day

### 3. Aggregate (events)
- Combines all calendar events into one item

### 4. Notion (Get Tasks)
- Queries AI Tasks database
- Filter: Status = To Do

### 5. Aggregate (tasks)
- Combines all tasks into one item

### 6. HTTP Request (Groq AI)
- Model: llama-3.3-70b-versatile
- Synthesizes calendar + tasks into a morning briefing

### 7. Send Message (Slack)
- Channel: #daily-briefing
- Sends formatted morning briefing

## Output Format
- Good morning greeting
- Today's schedule with times
- Open tasks ranked by priority
- Focus suggestion for the day

## Credentials Needed
- Google Calendar OAuth
- Notion API Key
- Groq API Key
- Slack Bot Token

## Status
✅ Complete and working
