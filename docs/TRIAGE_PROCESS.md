# Triage Process

This repository is public so that customers can raise issues, while code changes remain in the private `MobilePos` repository. Use the following workflow when managing submissions.

## Daily triage
1. Review issues labeled `needs-triage`.
2. Request missing information in a comment and add the `status:waiting-for-customer` label.
3. Once verified, add the appropriate severity and platform labels, then remove `needs-triage`.
4. Create or update the corresponding internal ticket in the private repository or your project tracker.

## Sync with private repository
- Reference the public issue number in the private issue or pull request (e.g., `Feedback GH-12`).
- When work begins internally, add the `status:in-progress` label here.
- When the fix ships, leave a closing comment and switch the label to `status:released` before closing the issue.

## Notifications
- GitHub will auto-assign new issues to `@caterlord`. Add additional maintainers in the issue templates if more people should be notified.
- Create a saved search such as `is:issue is:open label:needs-triage repo:caterlord/MobilePos-feedback` and pin it to your Issues list.
- Optional: configure a webhook or Slack/Teams integration that posts new issues to your support channel.

## Discussions
Use Discussions for general Q&A. Promote actionable bugs or feature ideas into Issues to maintain a single intake queue.

## Moderation
Follow the Code of Conduct. Remove sensitive data immediately and email the submitter to continue via a secure channel if needed.
