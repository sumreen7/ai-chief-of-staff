# Phase 8 — User Registration System

## Overview
Users can register to receive automated briefings by typing /register in Slack. The system saves their Slack ID and details to a Notion database for use in per-user automations.

## Workflow Architecture
```
Webhook (/register)
    ↓
Notion Get Many (check if Slack ID exists)
    ↓
Code Node (sets isNewUser flag)
    ↓
If Node (isNewUser = true?)
    ├── TRUE → Create Notion Page → Slack Welcome Message
    └── FALSE → Slack Already Registered Message
```

## Slash Command
- **Command:** `/register`
- **Webhook URL:** `https://n8n-production-624fe.up.railway.app/webhook/register`

## Nodes

### 1. Webhook
- Path: `register`
- Method: POST
- Responds immediately with: "Registering you now..."

### 2. Notion Get Many
- Database: AI CoS Users
- Filter: Slack ID equals `{{ $json.body.user_id }}`
- Option: Always Output Data = ON

### 3. Code Node
- Checks if returned Notion item has a real ID
- Sets isNewUser flag
- Passes user_id and user_name forward

### 4. If Node
- Condition: isNewUser equals true (Boolean)
- ⚠️ Important: "Always Output Data" must be OFF

### 5. Create Notion Page (True path)
- Database: AI CoS Users
- Fields: Name, Slack ID, Registered On, Active

### 6. Slack Welcome Message (True path)
- Sends private DM to new user
- Lists all available commands

### 7. Slack Already Registered (False path)
- Sends private DM to existing user
- Lists all available commands

## Notion Database — AI CoS Users
| Column | Type |
|---|---|
| Name | Title |
| Slack ID | Text |
| Registered On | Date |
| Active | Checkbox |

## Key Learnings
- "Always Output Data" on If node causes both paths to execute — keep it OFF
- Slack retries can cause duplicate executions — use x-slack-retry-num header to filter
- Notion returns empty object `{}` instead of `[]` when no results — use Code node to handle

## Status
✅ Complete and working
