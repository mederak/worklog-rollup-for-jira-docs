# Worklog Rollup for Jira Documentation

`Worklog Rollup for Jira` is a Jira Cloud app that shows total logged time for the current Jira issue and its descendant issues.

## Where The Panel Appears

The app appears as a Jira issue panel named `Worklog Rollup` in the main issue view, below the issue description.

## Total Logged Time

`Total logged time` includes work logged directly on the current issue and work logged on all descendant issues found through Jira's standard parent-child hierarchy.

The calculation includes:

- the current issue,
- direct child issues,
- child issues of those child issues,
- deeper descendant issues when they exist.

## Time Units

The app displays time in:

- `MH`: man-hour, where 1 MH = 1 hour,
- `MD`: man-day, where 1 MD = 8 MH.

The conversion is:

```text
1 MD = 8 MH
```

## Details Table

The details table shows the issues included in the calculation.

The current issue is shown as the first row. Descendant issues are shown when they have logged time.

Issue keys in the table link to the corresponding Jira issue.

## Data Source

The app uses standard Jira time tracking fields:

- `timespent`,
- `timetracking`.

The app does not require custom fields.

The app does not use Tempo API and does not fetch individual worklog entries.

## Refresh And Cache

Normal page refreshes may use a short-lived cache to avoid recalculating the full hierarchy.

Use the `Refresh` button to force a new calculation.

## MVP Limitations

The current version:

- does not edit worklogs,
- does not create worklogs,
- does not show costs,
- does not support rates,
- does not create portfolio reports,
- does not replace Tempo, eazyBI, accounting systems, billing systems, or official timekeeping systems.

## FAQ

### Does the app change Jira data?

No. The app only reads Jira data and displays calculated totals.

### Does the app require custom fields?

No. It uses Jira's standard `parent`, `timespent`, and `timetracking` fields.

### Does the app use Tempo?

No. It does not use Tempo API.

### Why can two users see different results?

The app reads Jira data as the current user. If users have different Jira permissions, they may see different issue hierarchies and totals.

### What does "No child issues" mean?

It means the current issue has no child issues visible to the current user through the standard Jira parent-child relationship.

### Can I use the result for billing?

The app is intended as a lightweight operational view. Billing, payroll, and financial reporting should rely on systems and processes approved by your organization.

