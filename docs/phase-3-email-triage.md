# Phase 3 — Email Triage Agent

## Overview
An AI-powered agent that reads Gmail every 30 minutes, analyzes emails using Groq AI, and saves prioritized tasks to Notion.

## Workflow
Schedule Trigger (every 30 mins) → Get Many Messages (Gmail) → HTTP Request (Groq AI) → Create Database Page (Notion)

## Nodes

### 1. Schedule Trigger
- Runs every 30 minutes

### 2. Get Many Messages (Gmail)
- Fetches up to 10 unread emails
- Filter: Unread only

### 3. HTTP Request (Groq AI)
- URL: https://api.groq.com/openai/v1/chat/completions
- Model: llama-3.3-70b-versatile
- Returns: High, Medium, or Low priority

### 4. Create Database Page (Notion)
- Database: AI Tasks
- Fields: Task (email subject), Priority (AI result), Source (Email), Status (To Do)

## Credentials Needed
- Gmail OAuth
- Groq API Key
- Notion API Key

## Status
✅ Complete and working
