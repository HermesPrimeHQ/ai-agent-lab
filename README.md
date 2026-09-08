# AI Agent Lab

Experiments in agent design and Python automation for day-to-day operations.

The first prototype is a morning email triage demo. It classifies three built-in sample messages as **Urgent**, **Important**, or **Routine** and prints the keywords behind each decision.

## Current status

This is an early experiment. The demo uses keyword rules and local sample data; it does not connect to an inbox, call an AI model, send messages, or run on a schedule. The [Morning Email Triage Agent design](agents/morning-email-agent.md) describes the broader workflow and future integrations.

## Run the demo

From the repository root, run:

```bash
python scripts/email_triage_v1.py
```

Use a Python 3 installation with `dataclasses` support (Python 3.7 or later). The demo uses only the standard library and requires no API keys or additional packages.

The sample messages produce:

| Sample message | Priority |
| --- | --- |
| Legal demand regarding resident dispute | Urgent |
| Updated maintenance proposal | Important |
| Clubhouse hours question | Routine |

## How triage works

The script checks the sender, subject, and body for matching keywords. Urgent matches take precedence over important matches. Messages with no matching keywords are marked routine.

Keyword matching is a starting point for experimentation. It does not interpret context or reliably determine the urgency of real messages.

## Repository contents

- [Agent design](agents/morning-email-agent.md): intended workflow, priority categories, and output format.
- [Email triage prototype](scripts/email_triage_v1.py): sample data, classification rules, and console summary.
- [Setup notes](notes/setup-notes.md): initial repository purpose and setup record.

## License

[MIT](LICENSE) — Copyright (c) 2026 HermesPrimeHQ.

