# Phase 8 — User Registration System

## Overview
Users can register to receive automated briefings by typing /register in Slack. The system saves their Slack ID and details to a Notion database for use in per-user automations.

## Workflow
Webhook (/register) → Create Notion User → Slack Welcome Message

## Slash Command
- Command: `/register`
- Webhook URL: `https://n8n-production-624fe.up.railway.app/webhook/register`

## Nodes

### 1. Webhook
- Path: `register`
- Method: POST
- Responds immediately with: "Registering you now..."

### 2. Create a Database Page (Notion)
- Database: AI CoS Users
- Fields: Name, Slack ID, Registered On, Active

### 3. Slack Welcome Message
- Sends private DM to the user who registered
- Confirms registration and lists available commands

## Notion Database — AI CoS Users
- **Name:** User's Slack display name
- **Slack ID:** User's Slack member ID
- **Registered On:** Date of registration
- **Active:** Checkbox (true on registration)

## Known Issues
- Notion database ID needs to be verified ⚠️
- Duplicate check not yet implemented (Phase 9)

## Status
🔄 In Progress — Slack registration working, Notion save needs fixing
