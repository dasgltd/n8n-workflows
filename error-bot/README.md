# Global Error Handling (Error Bot)

A workflow designed to act as the master "Error Workflow" for your n8n instance. Whenever any other workflow in your account fails, it invokes this invisible bot, passing the error details (Execution ID, broken workflow name, error message), and this bot notifies you immediately.

> **Notification Note:** This `ErrorBot.json` file uses a **Telegram** node as the default template for sending messages. However, feel entirely free to delete the Telegram node and replace it with the channel that works best for you (Slack, Microsoft Teams, Discord, Email, etc.). The core error formatting logic will continue to work perfectly!

## How to Install:
1. Create a new empty workflow in n8n.
2. Import the contents of the `ErrorBot.json` file.
3. Configure your credentials in the notification node (Telegram, Slack, Discord, Email, etc.).
4. Save and **Activate** the workflow.
5. Grab the text ID of this workflow from your address bar (e.g., `v08hZdac5oFON8nz`) and replace the `errorWorkflow` variable in your `SKILL.md` file (if you are using the n8n LLM Skill) so the AI can link errors automatically.

## Keywords
*Error Handling, Global Error Bot, Notifications, Automation, Telegram, Slack, n8n, Monitoring.*
