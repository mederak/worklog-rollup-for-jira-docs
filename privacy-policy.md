# Privacy Policy

Last updated: TODO: 2026-05-17

This Privacy Policy describes how `Worklog Rollup for Jira` processes data when used as an Atlassian Forge app for Jira Cloud.

TODO/LEGAL REVIEW: This draft should be reviewed by legal counsel before publication.

## What The App Does

`Worklog Rollup for Jira` reads Jira issue data only to calculate and display total logged time for the current issue and its descendant issues.

The app does not modify Jira data, create issues, edit worklogs, or change issue hierarchy.

## Data The App May Read

Depending on the issue hierarchy and the current user's Jira permissions, the app may read:

- issue key,
- issue summary,
- issue type,
- parent-child relationship,
- `timespent`,
- `timetracking`,
- technical user identifiers required by Atlassian Forge context or short-lived cache.

The app reads this data through Jira REST API using Atlassian Forge runtime and the permissions granted to the current Jira user.

## How Data Is Used

The app uses the data only to:

- calculate total logged time for an issue and its descendants,
- show the issues included in the calculation,
- cache the calculated result for a short time to improve performance.

The app does not use the data for advertising, user profiling, analytics resale, or cross-customer aggregation.

## Data Storage

The app uses Forge Storage only for short-lived cache.

The cache is used to avoid recalculating the same issue hierarchy on normal page refreshes. Cache entries are technical and temporary. The cache is not used to profile users.

## Data Sharing And External Transfer

The app does not send Jira data to an external backend.

The app does not sell customer data.

Data is processed within Atlassian Forge infrastructure unless future documentation explicitly states otherwise.

## Logs

Application logs are intended for technical troubleshooting.

Logs should not contain raw Atlassian account IDs, full cache keys, issue summaries, or full Jira response bodies. Technical identifiers should be masked where logging is needed.

## Customer Content

Issue summaries and issue metadata may contain personal data or confidential customer content entered by Jira users. Customers are responsible for the content stored in their Jira site.

## Contact

For privacy questions, contact:

```text
piotr@mederak.pl
```

