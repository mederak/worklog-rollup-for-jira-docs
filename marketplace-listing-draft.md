# Marketplace Listing Draft

## App Name

Worklog Rollup for Jira

## Tagline

Roll up logged time across Jira issue hierarchies.

## Short Description

See total logged time for a Jira issue and all of its descendant issues directly in the issue view.

## Full Description

`Worklog Rollup for Jira` adds a simple issue panel to Jira Cloud. The panel shows total logged time for the current issue and its descendant issues using Jira's standard parent-child hierarchy.

The app is designed for project managers, delivery leads, and Jira teams who need a quick way to understand logged effort across an issue scope without opening each child issue manually.

The app uses Jira's standard aggregated time tracking fields. It does not edit worklogs, does not require custom fields, and does not use Tempo API.

## Highlights / Key Benefits

- View total logged time directly in the Jira issue view.
- Include the current issue and all descendant issues.
- See time in MH and MD, where 1 MD = 8 MH.
- Review which issues were included in the calculation.
- Open included issues from the details table.
- Use standard Jira issue hierarchy through the `parent` relationship.
- No custom field setup required for the MVP.

## Use Cases

- Check total effort for an epic and its child work.
- Review logged time for a task and its subtasks.
- Understand effort across a custom hierarchy level above epics.
- Validate whether child issues contribute to the total time shown for a parent issue.
- Give project managers a lightweight operational view without a separate reporting tool.

## What Data Does The App Access?

The app reads Jira issue data needed to calculate and display total logged time:

- issue key,
- issue summary,
- issue type,
- parent-child relationship,
- `timespent`,
- `timetracking`.

The app may also use technical user identifiers provided by Atlassian Forge context to keep short-lived cache scoped to the current user.

The app does not modify Jira data, create issues, edit worklogs, or send Jira data to an external backend.

## Why Each Scope Is Needed

### `read:jira-work`

Required to read the current issue, descendant issues, issue metadata, hierarchy relationship, and Jira time tracking fields.

### `storage:app`

Required to store short-lived calculation cache in Forge Storage. This improves performance when the same user refreshes the same issue view.

## Support Information

Support contact:

```text
piotr@mederak.pl
```

Typical response time: 2-5 business days, best effort.

Please include a clear problem description, app version, Jira issue type, whether the problem affects one issue or multiple issues, and a redacted screenshot if useful.

## Privacy & Security Answers Draft

### Does the app send data outside Atlassian Forge?

No. The current version has no external backend and no external egress.

### Does the app write to Jira?

No. The app is read-only and does not request Jira write scopes.

### Does the app use Forge Storage?

Yes. Forge Storage is used only for short-lived calculation cache.

### Does the app sell customer data?

No.

### Does the app require admin scopes?

No.

### Does the app use Tempo data?

No. The app uses standard Jira aggregated time tracking fields.

## Pricing Positioning

Lightweight paid app for project managers and Jira teams who need a fast issue-level rollup of logged time across Jira hierarchies.

TODO: Define final pricing, trial period, and Marketplace billing model.

