# Security Policy

Only the latest published Cathy alpha receives security fixes.

Do not disclose access tokens, API keys, private source, exploit details, or
other sensitive information in a public issue. Use this repository's
**Security → Report a vulnerability** form to submit a private report to the
maintainer.

Include the affected Cathy version and operating system, impact, reproduction
steps, and any suggested mitigation. Do not test against systems or data you do
not own or have permission to use. No response or remediation SLA is promised
for this alpha.

Cathy runs locally with the permissions of the invoking user. Native file tools
enforce workspace paths, but an approved Bash command is not isolated from the
rest of the filesystem, credentials, or network. Authentication material is
stored locally in `~/.cathy/auth.json` with mode `0600`.
