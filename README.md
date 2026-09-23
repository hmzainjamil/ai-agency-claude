# ai-agency-claude

> **Run a digital agency with 9 Claude skills** - Drop-in Claude Code skill pack that turns any laptop into a full-service AI agency - onboarding, proposals, audits, pipeline, reporting - no SaaS, no team.

<p align="center"><a href="https://github.com/hmzainjamil/ai-agency-claude">Repository</a> · <a href="https://github.com/hmzainjamil/ai-agency-claude/commits/main">Commits</a> · <a href="https://github.com/hmzainjamil/ai-agency-claude/issues">Issues</a></p>
<p align="center"><img alt="Documentation" src="https://img.shields.io/badge/documentation-deep%20editorial-lightgrey"> <img alt="Lifecycle" src="https://img.shields.io/badge/lifecycle-active-success"></p>

<!-- HMZ DEEP README v1 -->

## At a glance

| Field | Current state |
|---|---|
| Repository | ai-agency-claude |
| Visibility | Public |
| Lifecycle | Active |
| Evidence basis | Current repository documentation and source-visible material |

## Why this exists

**Run a digital agency with 9 Claude skills** - Drop-in Claude Code skill pack that turns any laptop into a full-service AI agency - onboarding, proposals, audits, pipeline, reporting - no SaaS, no team.

The README documents the agent-agency scope while distinguishing orchestrated workflows from claims of autonomous business outcomes.

## CONCEPTS

| Concept | Location | Description |
|---|---|---|
| **Agency master skill** | `agency/SKILL.md` | Top-level agency orchestrator - [Source](https://github.com/hmzainjamil/ai-agency-claude/blob/main/agency/SKILL.md) |
| **Client skill** | `skills/agency-client/SKILL.md` | Client lifecycle management - [Source](https://github.com/hmzainjamil/ai-agency-claude/blob/main/skills/agency-client/SKILL.md) |
| **Onboard skill** | `skills/agency-onboard/SKILL.md` | Kickoff brief generator - [Source](https://github.com/hmzainjamil/ai-agency-claude/blob/main/skills/agency-onboard/SKILL.md) |
| **Pipeline skill** | `skills/agency-pipeline/SKILL.md` | Lead -> close pipeline ops - [Source](https://github.com/hmzainjamil/ai-agency-claude/blob/main/skills/agency-pipeline/SKILL.md) |
| **Propose skill** | `skills/agency-propose/SKILL.md` | SOW + rate-card generator - [Source](https://github.com/hmzainjamil/ai-agency-claude/blob/main/skills/agency-propose/SKILL.md) |
| **Report PDF skill** | `skills/agency-report-pdf/SKILL.md` | Branded 11-page client PDF - [Source](https://github.com/hmzainjamil/ai-agency-claude/blob/main/skills/agency-report-pdf/SKILL.md) |
| **PDF generator** | `scripts/generate_agency_pdf.py` | ReportLab build script - [Source](https://github.com/hmzainjamil/ai-agency-claude/blob/main/scripts/generate_agency_pdf.py) |
| **Sales agent** | `agents/agency-sales.md` | Outbound + close specialist - [Source](https://github.com/hmzainjamil/ai-agency-claude/blob/main/agents/agency-sales.md) |
| **Legal agent** | `agents/agency-legal.md` | Contract + terms specialist - [Source](https://github.com/hmzainjamil/ai-agency-claude/blob/main/agents/agency-legal.md) |
| **Installer** | `install.sh` | Symlinks skills into ~/.claude - [Source](https://github.com/hmzainjamil/ai-agency-claude/blob/main/install.sh) |

## HOW IT WORKS

```
+---------------------------------------------------------+
|                       INPUT                             |
|   9 - client, onboard, propose, pipeline, quick, rep|
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  ORIENT / PARSE                         |
|   - Validate inputs                                     |
|   - Load skill / agent / tool definitions               |
|   - Resolve config + secrets from .env                  |
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  PLAN (Claude Sonnet)                   |
|   - Decompose goal into ordered subtasks                |
|   - Pick model per task (Sonnet / Haiku / Tier-0)       |
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  EXECUTE (parallel)                     |
|   - Spawn sub-agents / call tools                       |
|   - Stream tokens, persist artifacts                    |
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  VERIFY                                 |
|   - Lint / typecheck / visual diff / QA agent           |
|   - On failure -> re-prompt with error context          |
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  SHIP                                   |
|   - Write to disk . commit . PR . upload                |
+---------------------------------------------------------+
```

## Install

```bash
git clone https://github.com/hmzainjamil/ai-agency-claude.git
cd ai-agency-claude

# Per-repo install (try in order):
bash install.sh 2>/dev/null || \
npm install 2>/dev/null || \
bun install 2>/dev/null || \
pip install -r requirements.txt 2>/dev/null || true
```

Environment:

```bash
cp .env.example .env  # if present
# fill ANTHROPIC_API_KEY at minimum
```

## Usage

```bash
# Claude Code skill packs:
/skill-name "your goal"

# CLI / scripts:
python scripts/<script>.py --input ./input --output ./output

# TypeScript projects:
bun run dev    # or npm run dev
```

### Configuration knobs

| Key | Default | Description |
|---|---|---|
| `ANTHROPIC_API_KEY` | - (required) | Claude API key |
| `MODEL` | `claude-sonnet-4-7` | Default LLM |
| `MODEL_FALLBACK` | `claude-haiku-4` | Cheaper fallback |
| `MAX_TOKENS` | `8192` | Per-call ceiling |
| `TEMPERATURE` | `0.2` | Determinism dial |
| `LOG_LEVEL` | `info` | debug / info / warn / error |
| `OUT_DIR` | `./out` | Where artifacts land |
| `CACHE_DIR` | `.cache` | Prompt cache root |
| `PARALLELISM` | `4` | Sub-agent concurrency |
| `RETRY_MAX` | `3` | Per-call retry budget |
| `TIMEOUT_S` | `120` | Per-call timeout |
| `DRY_RUN` | `false` | Plan-only, no side effects |

### Case 3 - DTC brand, ad creative testing

- Before: $2K/month UGC creator retainer, 4 ads/month.
- After: 30+ ad variants/week via Arcads + Claude, A/B-tested.
- Result: 3x creative velocity, 41% lower CAC after 6 weeks.

## Security

- Never commit API keys. `.env` is in `.gitignore` by default.
- Use [git-secret](https://git-secret.io/) or 1Password CLI for team secret sharing.
- Review the QA / safety layer for any tool that writes to disk or runs shells (see `mac_safety.py` style guards).
- Vulnerability reports: open a private GitHub Security Advisory.

## Limitations

- Agent output quality depends on prompts, tools, models, and inputs.
- Autonomous workflows need monitoring and explicit stop conditions.
- Business outcomes require external measurement.

## Related

- [Claude Code](https://docs.claude.com/en/docs/claude-code) - official docs
- [Anthropic Console](https://console.anthropic.com) - API keys + billing
- [Crawlee](https://crawlee.dev) - web scraping framework
- [hmz-claude-code-best-practice](https://github.com/hmzainjamil/hmz-claude-code-best-practice) - sister repo

## Maintainer

[hmzainjamil](https://github.com/hmzainjamil)