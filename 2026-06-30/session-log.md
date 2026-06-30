# Bug Bounty Session — 2026-06-30 (Slack)

**Target:** Slack (HackerOne program)  
**HackerOne User:** stix26  

---

## Summary

Full recon + aggressive testing against Slack's HackerOne program.  
Slack has awarded over $12M in bounties since 2015 across all their programs.

**No exploitable vulnerabilities found.** One interesting finding documented below.

## Scope Coverage

- slack.com, api.slack.com, app.slack.com → verified accessible
- slackb.com → short link service with interesting CORS config
- slackatwork.com, slack-redir.net, slack-imgs.com → tested
- slack-status.com → accessible
- quip.com, www.quip.com → verified
- edgeapi.slack.com → accessible
- GitHub: slackhq/nebula → checked for secrets

## Pipeline

1. **Subdomain enumeration** — quip.com: 20,097 subdomains, slack.com: timed out
2. **Live host probing** — 11 targets verified
3. **CORS testing** — 3 origins tested per target
4. **Exposed files** — .git/HEAD, .env, configs, debug files, backups
5. **Open redirects** — 10 redirect params tested per target
6. **API probing** — common API paths
7. **Wayback URLs** — gau on 3 domains (tool failure)
8. **GitHub secret scanning** — slackhq org checked

## Notable Finding: slackb.com Wildcard CORS

**Target:** `https://slackb.com`  
**Detail:** Returns `Access-Control-Allow-Origin: *` with custom headers:
- `access-control-allow-headers: Content-Type, X-Slack-Ses-Id, User-Agent, X-Forwarded-For`
- `access-control-allow-methods: POST, GET, OPTIONS, PUT, DELETE`

**Impact:** Potentially allows cross-origin requests from any website.  
**Mitigation:** The endpoint returns "404 page not found" with no sensitive content.  
**Severity:** Low (no exploitable data returned, but misconfiguration noted)

## Files Saved

- `~/Desktop/slack-recon/targets.txt`
- `~/Desktop/slack-recon/scan-results.txt`
- This document
