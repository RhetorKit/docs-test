# Contributing to docs-test

Thank you for contributing to docs-test. Please read this guide before opening a pull request.

## Prerequisites

- Git version 2.30+
- Access to docs-test on GitHub (request via #rhetorkit)

## Five-Minute Quick Start: Edit a File via GitHub Web

1. Navigate to the file you want to edit on GitHub.com
2. Click the pencil icon (Edit this file)
3. Make your change in the inline text editor
4. Scroll down and click **Commit changes**
5. Select **Create a new branch** and name it `docs/typo-fix-[brief-description]`
6. Click **Propose changes** — GitHub will open a PR automatically
7. Fill out the PR template and click **Create pull request**

That's it! A reviewer will provide initial feedback within **24 business hours**.

## Branching Conventions

```text
docs/<ticket-id>-<short-slug>
```

Examples:
- `docs/SEC-123-oauth-flow-clarification`
- `docs/PLAT-456-api-endpoint-typo-fix`
- `docs/sme-rate-limit-explanation` (no ticket ID)

## Commit Message Format

Clear and descriptive. Conventional commits (`docs:`, `fix:`) are encouraged but not enforced:

```text
docs: update OAuth 2.0 flow diagram for clarity

- Replace legacy sequence diagram with mermaid rendering
- Add step-by-step explanation
- Link to related RFC #456
```

## Local Development & Preview

```bash
# Replace with your actual preview command
make preview-docs
# or: docker run --rm -p 8000:8000 -v $(pwd):/docs your-docs-image
# or: npm run dev
```

Rendered docs are available at `http://localhost:8000`. Fix any rendering issues before opening your PR.

## How to Submit a Pull Request

1. Create a branch following the naming convention above
2. Make your changes (verify with local preview if applicable)
3. Commit with a clear message
4. Push: `git push origin docs/[your-branch]`
5. Open a pull request on GitHub
6. **Fill out the PR template completely** — this is how reviewers understand your change and how the automated SLA clock knows who to contact
7. Tag your proposed reviewer per the PR template's "Proposed Reviewers" field

Your PR is automatically labeled and routed by our triage workflow. You will see a welcome comment with your SLA window within minutes.

## Review Process

Your PR is automatically classified on open:

- **Standard content** (how-tos, concepts, guides): **24-hour** initial review window
- **High-risk content** (security, compliance, public APIs): **4-hour** initial review window

After your initial review, keep an eye for "Request Changes" feedback. The reviewer SLA clock restarts once you re-request review (see next section).

## Responding to Change Requests

When a reviewer posts "Request Changes":

1. Push new commits to the same branch addressing each point of feedback
2. Click **Re-request review** on the reviewer's card in the PR sidebar — this is the official signal that restarts the reviewer's SLA clock
3. Do not post a comment saying "done" as a substitute for re-requesting review; the button is the correct action

**If you need more time or are waiting on external input**, post a pause comment:

```text
[PAUSE: waiting on product team sign-off - ETA 2026-07-01]
```

This communicates the delay to reviewers and our automation. When the condition resolves:

```text
[UNPAUSE: product team approved, continuing]
```

### If a PR Gets Stale

If your PR has no activity for **5 business days** after a "Request Changes" review, it will be tagged `stale` and you will receive an automated reminder. After **14 business days** total, standard-content PRs may be auto-closed to keep the review queue clean. **Your branch is always preserved and the PR can be reopened at any time.**

High-risk PRs are never auto-closed — they are escalated to @ghoulmann instead.

## Merge Strategy

All PRs are merged using **squash merge**. Your branch commits are squashed into a single commit on `main`. The merge committer will write (or edit) the final commit message for semantic clarity.

## Code of Conduct

Please see .

## Questions & Escalation

| Problem | Contact |
| --- | --- |
| Git workflow or branch conflicts | Post a comment in the PR or message #rhetorkit |
| Style, tone, or content questions | Post a comment in the PR or ping @ghoulmann |
| Permissions or account issues | Email test@example.com |
| High-risk content urgency | Tag @ghoulmann directly in the PR |
