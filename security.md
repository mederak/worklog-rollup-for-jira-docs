# Security And Data Processing

`Worklog Rollup for Jira` is built as an Atlassian Forge app for Jira Cloud.

## Hosting

The app runs on Atlassian Forge infrastructure.

There is no external backend operated by the app vendor in the current version.

## External Egress

The app does not declare external egress permissions.

Jira data is not sent to external domains by the app.

## Permissions

The app uses minimal Forge scopes for the MVP.

### `read:jira-work`

Needed to read Jira issue data required for the calculation:

- current issue,
- child issues,
- issue summary,
- issue type,
- parent-child relationship,
- aggregated time tracking fields.

### `storage:app`

Needed to store short-lived calculation cache in Forge Storage.

The cache helps avoid recalculating the same issue hierarchy on normal page refreshes.

## Scopes Not Used

The app does not request:

- Jira write scopes,
- administrative scopes,
- Tempo scopes,
- user profile read scopes beyond technical context provided by Forge.

## Cache

The app uses Forge Storage as a short-lived cache.

The cache may include:

- calculated totals,
- issue metadata needed to render the table,
- calculation timestamp,
- technical cache metadata.

The cache is not used for user profiling.

## Logging

Logs are used for troubleshooting.

Implementation guidelines:

- do not log raw account IDs,
- do not log full cache keys,
- do not log issue summaries,
- do not log full Jira API response bodies,
- mask technical identifiers when they are needed for diagnostics.

## Support Data

When contacting support, screenshots and examples should not contain sensitive data.

Blur or remove:

- customer names,
- personal data,
- confidential issue summaries,
- secrets,
- tokens,
- internal business details.

