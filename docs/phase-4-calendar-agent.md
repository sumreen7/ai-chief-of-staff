# Phase 4 — Calendar Agent

## Overview
Fetches today's Google Calendar events every morning at 8 AM,
analyzes them with Groq AI, and sends a formatted daily briefing to Slack.

## Workflow
Schedule Trigger (8 AM) → Get Many Events (Google Calendar) → 
Aggregate → HTTP Request (Groq AI) → Send Message (Slack)

## Status
✅ Complete and working