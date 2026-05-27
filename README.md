# Cyber Armory Portfolio

> Private Flask-based security operations platform prototype  
> 공개용 포트폴리오 저장소입니다. 실제 구현 소스코드는 비공개 저장소에 보관합니다.

## Overview

Cyber Armory is a private security operations platform prototype built around:

- authentication and administrator management
- execution dashboard
- file management
- security hardening
- release safety gate
- dependency vulnerability remediation
- Docker/Kubernetes deployment readiness
- operational runbooks and validation workflows

This repository intentionally contains **documentation only**.  
The full source code is not published because the project may be commercialized later.

## Validation Summary

| Item | Result |
|---|---|
| Final version | `v0.33.0` |
| Final commit | `ca4ee2a` |
| Final Release Gate | PASS |
| Test result | 189 passed / 14 skipped / 1 warning |
| Dependabot alerts | 0 Open |
| Default branch | main |
| Runtime artifacts | Excluded |
| Secrets scan review | Completed manually |

## Security Work Completed

- Removed runtime artifacts from release tree
- Excluded local data, logs, uploads, database files, and backup files
- Patched vulnerable dependencies reported by Dependabot
- Added top-level dependency security floors for Dependabot visibility
- Patched Gunicorn request smuggling advisories
- Validated release using automated release gate
- Verified test suite after dependency upgrades

## Disclosure Boundary

The public version only describes the project at a high level.  
It does not include:

- source code
- real deployment configuration
- credentials or secrets
- internal execution logic
- production infrastructure details
- exploit implementation details

## Intended Use

This project is intended for authorized security testing, training, and defensive security operations only.

Do not use security tools or related techniques against systems you do not own or do not have explicit permission to test.

## Repository Structure

```text
Cyber-Armory-Portfolio/
├─ README.md
├─ architecture.md
├─ security-validation-summary.md
├─ release-summary.md
├─ public-disclosure-policy.md
├─ screenshots/
└─ .gitignore
```

## Suggested Screenshots

Add sanitized screenshots only:

- dashboard overview
- user/admin management page
- release gate PASS terminal output
- Dependabot 0 Open screen
- test result screen

Do not include screenshots showing credentials, internal IPs, private domains, real users, or operational secrets.
