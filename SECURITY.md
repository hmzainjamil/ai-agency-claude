# Security and privacy

## Before installation

Review `install.sh` and `uninstall.sh` before running them. The installer copies files into `$HOME/.claude/skills` and `$HOME/.claude/agents`; it can overwrite files with matching names. The uninstaller recursively removes the listed agency skill directories and deletes matching agent files. Back up local changes and inspect the target paths first.

The installer includes remote URLs under the `zubair-trabzada` namespace, including its curl-pipe clone path and related-suite commands. Verify that namespace and every URL before using remote installation commands.

## Client information

The skill instructions can collect website and business details and create reports. Use public or synthetic data while evaluating the workflows. Do not send confidential client, employee, account, or personal information to an AI provider or external tool unless the data owner and your organization have approved that handling.

Review output for accuracy, personal information, unsupported claims, and confidential details before saving or sharing it. Legal workflow output is not legal advice and needs review by qualified counsel.

## Credentials

This repository does not document a required API-key variable. Never add credentials to tracked files, prompts, reports, shell history, or issue comments. Follow the provider's current secret-handling guidance.

## Reporting

Report security concerns through a private GitHub Security Advisory for this repository. Do not publish exploit details or sensitive data in a public issue.
