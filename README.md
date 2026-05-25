# ai-agency-claude

> **AI agency with Claude — full digital agency OS built on Claude Code automation**

![Status](https://img.shields.io/badge/status-active-brightgreen?style=flat)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat)
![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-FF6B35?style=flat)
![Stars](https://img.shields.io/github/stars/hmzainjamil/ai-agency-claude?style=flat)
![Last Commit](https://img.shields.io/github/last-commit/hmzainjamil/ai-agency-claude?style=flat)

---

## CONCEPTS

| Concept | Description |
|---|---|
| **Dream 100** | 13-touch outreach across 4 channels |
| **CRM** | Airtable-based prospect tracking |
| **Onboarding** | Automated client intake to delivery |
| **Content** | AI-generated deliverables at scale |
| **Reporting** | Automated client performance reports |
| **Billing** | Invoice and payment automation |
| **Hiring** | AI-assisted contractor sourcing |
| **Operations** | Daily standups, task routing, QA |

---

## 🔥 Hot Commands

```bash
# Activate skill
claude --skill ai-agency-claude 'your task'

# Quick workflow
claude 'agency automation task'

# Get capabilities
claude 'what can ai-agency-claude do?'
```

## ■ tip
> Mention **agency** or **claude** in your prompt to auto-activate this skill.

---

## ☠️ STARTUPS / BUSINESSES

- **Agencies**: automate agency workflows for clients at scale
- **Founders**: ship claude features 10x faster
- **Freelancers**: deliver automation work with AI precision

---

## Features

- Agency automation
- Claude automation
- Automation automation
- Digital automation
- Marketing automation
- Outreach automation

---

## Installation

```bash
git clone https://github.com/hmzainjamil/ai-agency-claude.git
cd ai-agency-claude
```

---

## Usage

```bash
# Activate skill in Claude Code
claude --skill ai-agency-claude "your task here"

# Quick workflow
claude "agency automation task"

# Get help
claude "what can ai-agency-claude do?"
```

---

## Configuration

| Variable | Description | Default |
|---|---|---|
| `API_KEY` | Primary API key | Required |
| `MODEL` | AI model to use | claude-3-5-sonnet |
| `DEBUG` | Enable verbose debug | false |
| `MAX_TOKENS` | Max token budget | 8192 |
| `TIMEOUT` | Request timeout (sec) | 30 |
| `LOG_LEVEL` | Logging verbosity | info |

---

## Architecture

```
ai-agency-claude/
├── README.md           # Documentation
├── SKILL.md            # Claude Code skill definition
├── scripts/            # Automation scripts
├── templates/          # Output templates
├── examples/           # Usage examples
└── docs/               # Extended documentation
```

---

## Examples

### Basic

```bash
# Simple task
claude --skill ai-agency-claude "agency task"

# Verbose
claude --skill ai-agency-claude --verbose "detailed claude task"
```

### Advanced Pipeline

```bash
# Chain skills
claude --skill ai-agency-claude "step 1" | claude --skill summarize

# Batch run
for item in $(cat list.txt); do
  claude --skill ai-agency-claude "process $item"
done
```

---

## Troubleshooting

| Issue | Cause | Fix |
|---|---|---|
| Auth fails | Invalid API key | Re-export key in shell profile |
| Timeout | Network or large payload | Increase TIMEOUT value |
| Empty output | Prompt too vague | Add more context |
| Rate limit | Too many requests | Add delay between calls |
| Model error | Unsupported version | Update MODEL variable |
| Import error | Missing dependency | Run pip install -r requirements.txt |

---

## Comparison

| Feature | This Skill | Alt A | Alt B |
|---|---|---|---|
| Claude Code native | ✅ | ❌ | ✅ |
| Auto-activation | ✅ | ✅ | ❌ |
| Free to use | ✅ | ❌ | ✅ |
| Production ready | ✅ | ✅ | ❌ |
| Active maintenance | ✅ | ❌ | ❌ |

---

## Changelog

| Version | Changes |
|---|---|
| v2.0 | Claude 4 support, auto-activation |
| v1.5 | Added keyword triggers |
| v1.0 | Initial release |

---

## Contributing

1. Fork → feature branch → commit → PR
2. Follow conventional commits: `feat:`, `fix:`, `docs:`
3. Add tests for new features

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=hmzainjamil/ai-agency-claude&type=Date)](https://star-history.com/#hmzainjamil/ai-agency-claude&Date)

---

## 📜 License

MIT — free to use, modify, distribute.

---

Made with ❤️ by [@hmzainjamil](https://github.com/hmzainjamil)
