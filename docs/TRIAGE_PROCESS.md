# Triage Process

This repository is public so customers and partners can raise X1 feedback, while product code and remediation tracking remain in the matching private X1 repository. Use this workflow for every issue that originates in `caterlord/X1.Feedback`.

`X1.Feedback` covers multiple X1 product lines. Triage must classify the affected product first, mirror accepted work into the correct internal tracker, and keep the public issue labels and customer-facing comments current.

## Daily Triage

1. Review issues labeled `needs-triage`.
2. Check whether the report contains enough information to classify the product, platform, type, and impact.
3. If details are missing, leave a public comment asking for the specific information needed, add `status:waiting-for-customer`, and keep `needs-triage` until the issue can be verified.
4. If sensitive data is present, remove or hide it immediately and move follow-up to a secure support channel.
5. Once verified, apply the public label rules below and mirror accepted work into the matching private tracker.

## Mirror The Report

- Identify the affected X1 product line before creating the private tracker issue.
- Create a matching GitHub issue in the correct private repository or private project tracker. Do not create ad-hoc Markdown tracking files.
- Use `gh issue create` or the GitHub UI so assignees, labels, and cross-links stay in the canonical tracker.
- Include the public issue number in the private issue title, for example `[#109] Payment methods need reorder support`.
- Copy the original description, reproduction details, screenshots, attachments, product metadata, and business impact into the private issue body.
- Add a source link at the top of the private issue, for example `Source: caterlord/X1.Feedback#109`.
- Reference the private issue or PR from implementation work so release notes and customer follow-up stay traceable.

## Product Routing

Use exactly one `product:*` label after the issue is accepted:

- `product:hq` for X1 HQ merchant back-office workflows, including browser-based admin pages.
- `product:online-ordering` for customer storefront and online ordering flows.
- `product:pos` for POS runtime and in-store operational workflows.
- `product:docs` for documentation feedback.
- `product:integrations` for third-party integration and partner connectivity work.

Mirror the private issue into the repository or tracker owned by that product line. Do not force non-POS work into a POS tracker just because the public report arrived here.

## Public Label Rules

Apply labels as soon as an issue is accepted for internal tracking:

- Remove `needs-triage`.
- Add exactly one `product:*` label.
- Add the most specific `platform:*` label when a client, runtime, or browser surface is involved.
- Keep exactly one type label: `type:bug`, `type:feature`, or `type:documentation`.
- Keep exactly one `status:*` label at any time.
- Add a severity label when impact is clear.

Current platform labels:

- `platform:web` for browser-only workflows such as HQ and online ordering admin/storefront pages.
- `platform:desktop` for desktop client issues.
- `platform:android` for Android client issues.
- `platform:ios` for iOS client issues.
- `platform:multiple` only when the issue genuinely affects more than one platform.

Status label progression:

- `status:waiting-for-customer` when reporter input is required before work can continue.
- `status:in-progress` while investigation, coding, review, or testing is actively ongoing.
- `status:blocked` only when work cannot proceed because of an external blocker.
- `status:pending-release` after the fix is merged or validated but not yet shipped to users.
- `status:released` only after the fix is confirmed live in a released build or deployed environment.

## Track Remediation Privately

- Add a private status comment describing investigation findings, planned fixes, and ownership.
- Keep the private issue updated with branch names, commits, PR links, test evidence, release targeting, and customer communication needs.
- Develop fixes on a dedicated branch named after the issue or problem.
- Open a PR against the appropriate base branch once validation is complete.
- Include links to both the public issue and private tracker issue in the PR.
- After approval, merge through the normal repository workflow and tag release branches if needed.

## Update The Public Report

- Post a public progress reply when work begins or when the status changes materially.
- Keep public comments customer-friendly and non-technical; avoid framework, engine, private infrastructure, or implementation-only details.
- Mention whether the fix is being investigated, in progress, pending release, or already live.
- Include expected timelines when they are known.
- Acknowledge blockers publicly when they affect customer expectations.
- If a private issue or PR can be referenced safely, link it; otherwise describe the public status without exposing private details.
- When posting via CLI, always use real Markdown paragraph breaks with blank lines. Use a heredoc or `--body-file`; do not embed literal `\n` sequences in the comment body.

## Close Out

- Close the private issue with a short summary of the resolution, verification steps, and release vehicle.
- When the fix is staged but not live, leave the public issue open with `status:pending-release`.
- After the fix is live, leave a public closing comment with a customer-friendly summary and availability details such as version, build number, release channel, or deployed environment.
- Switch the public issue to `status:released` and close it only after the release is confirmed.

## Notifications

- GitHub will auto-assign new issues to `@caterlord`. Add additional maintainers in the issue templates if more people should be notified.
- Create a saved search such as `is:issue is:open label:needs-triage repo:caterlord/X1.Feedback` and pin it to your Issues list.
- Optional: configure a webhook or Slack/Teams integration that posts new issues to your support channel.

## Discussions

Use Discussions for general Q&A. Promote actionable bugs or feature ideas into Issues to maintain a single intake queue.

## Moderation

Follow the Code of Conduct. Remove sensitive data immediately and email the submitter to continue via a secure channel if needed.

## Process Updates

- Capture lessons learned or process improvements in this file so all product repositories can reference the same public issue workflow.
- If repository-specific `AGENTS.md` files mention public feedback handling, update them to point here rather than duplicating divergent rules.
