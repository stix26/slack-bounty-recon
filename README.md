# Slack Bug Bounty Reconnaissance

Security research repository targeting the [Slack HackerOne program](https://hackerone.com/slack).  
Slack has awarded over $12M in bounties since 2015.

## Repository Structure
```
├── {YYYY-MM-DD}/
│   ├── session-log.md
│   ├── targets.txt
│   ├── scan-results.txt
├── README.md
```

## Sessions
| Date | Focus | Outcome | Notes |
|------|-------|---------|-------|
| 2026-06-30 | Slack.com infrastructure + services | slackb.com wildcard CORS closed as **Informative** by H1 triage | 11 live targets; open redirects all false positives; 0 secrets discovered |

## Scope
slack.com, api.slack.com, app.slack.com, edgeapi.slack.com, slackb.com, slackatwork.com, slack-redir.net, slack-imgs.com, slack-status.com, quip.com and *.quip.com, GitHub org slackhq, mobile apps, desktop app.
