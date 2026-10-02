# AI Agency Claude

A Claude Code skill pack for agency workflows: client onboarding, proposals, pipeline tracking, quick assessments, status checks, and PDF report generation. The repository contains Markdown instructions plus a Python PDF generator and shell install scripts. The skills guide Claude Code; they are not a hosted agency service or standalone autonomous runtime.

## What is included

| Area | Contents |
|---|---|
| Orchestration | `agency/SKILL.md` |
| Workflow skills | Client, onboarding, pipeline, proposals, quick assessment, reporting, stack and status under `skills/` |
| Agent instructions | Marketing, reputation, GEO, legal and sales roles under `agents/` |
| PDF output | `scripts/generate_agency_pdf.py` |
| Setup | `install.sh`, `uninstall.sh`, and `requirements.txt` |

Some instructions call for web access, subagents, or other tools. Availability and behavior depend on the Claude Code environment and its configured tools. Review each skill before use. Treat generated scores, findings, legal topics, prices and business projections as drafts requiring evidence and qualified human review.

## Requirements

- Claude Code for the Markdown skills and agent instructions.
- Bash and Git for the installer.
- Python 3 and ReportLab for PDF generation. The declared dependency is in `requirements.txt`.

The repository does not declare an API-key configuration contract. The installer checks Claude Code and Python availability; it does not configure a model API key.

## Install

Review `install.sh` before running. It copies the orchestrator and scripts into `$HOME/.claude/skills/agency`, copies the listed skills into `$HOME/.claude/skills`, and copies agent files into `$HOME/.claude/agents`. Existing files at those paths may be overwritten. It also checks for related tool suites and prints suggested installer commands; it does not install those suites itself.

```bash
git clone https://github.com/hmzainjamil/ai-agency-claude.git
cd ai-agency-claude
bash install.sh
```

The installer currently points its remote-clone path and related suite links at the original `zubair-trabzada` namespace. For a remote install, verify those URLs before running.

## Use

After installation, start a Claude Code session and invoke the installed skills by their names, following the invocation documented in each skill file. Examples defined in the repository include:

```text
/agency onboard <url>
/agency quick <url>
```

These workflows may retrieve and process public business-site information when the configured Claude Code tools support it. Do not submit confidential client data unless your organization has approved the destination and handling. Verify findings against cited evidence before sharing externally.

Generate a demo PDF:

```bash
python3 scripts/generate_agency_pdf.py --demo
```

The script writes `AGENCY-REPORT.pdf` in the current directory. With a JSON input path, it reads that file and writes the report to the optional second path. See the script for the expected data structure.

## Uninstall

Review `uninstall.sh` first. It recursively deletes the named agency skill directories under `$HOME/.claude/skills` and removes five matching agent files under `$HOME/.claude/agents`. Back up local edits and confirm those paths contain only this installation before running:

```bash
bash uninstall.sh
```

## Scope and limitations

- This repository provides prompts and scripts, not an independently running multi-agent service.
- The installer copies files; it does not create a symlink.
- Audit scores, legal observations, recommendations, pricing, and forecast examples are not verified outcomes or professional advice.
- The demo data in the PDF generator is illustrative and should not be presented as a real client assessment.
- Tool names and invocation behavior in skill instructions can vary by host environment.
- No test suite or supported-platform matrix is declared in the repository.

## Repository map

- [Agency orchestrator](agency/SKILL.md)
- [Skills](skills/)
- [Agent instructions](agents/)
- [PDF generator](scripts/generate_agency_pdf.py)
- [Security notes](SECURITY.md)
- [License](LICENSE)

## Contributing

Open an issue to report a defect or propose a change. Include the affected file, expected behavior, and a safe reproduction using synthetic data. Do not include API keys, private client data, or generated reports containing personal information.

## Security and privacy

See [SECURITY.md](SECURITY.md) for installation, data-handling, and reporting guidance.

## License

MIT. See [LICENSE](LICENSE).
