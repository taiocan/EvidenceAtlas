# Naming Conventions

## Events

Format: `<Entity><Action><Outcome>`

Examples:
- `CartItemAdded`
- `PaymentCaptureFailed`
- `UserLoginSucceeded`
- `OrderCreated`

Failure events end with `Failed`, `Rejected`, or `Timeout`:
- `CartItemAddFailed`
- `LoginRejected`
- `PaymentGatewayTimeout`

## Metrics

Format: `<feature>_<measurement>`

Examples:
- `add_item_latency_ms`
- `payment_failure_rate`
- `login_duration_ms`
- `session_creation_success_rate`

## Errors

Format: `snake_case_failure_reason`

Examples:
- `item_not_found`
- `payment_gateway_timeout`
- `session_expired`
- `invalid_input`

## Feature IDs

Format: `EA-NNNN` (stable, sequential, never reused, never renamed) paired with a separate
`lowercase_underscore` slug (readable working name — may be revised if the feature's name
changes during discovery).

Examples:
- `EA-0001` / slug `research_brief`

Why separate: a feature's working name can change during Feature Brief / Discovery
(this project's first feature was called "Topic Registry," then "Topic Brief," before
landing on "Research Brief"). The ID stays stable across renames so file paths, registry
entries, and review logs never need to be retroactively fixed.

Filenames follow `backlog/[feature_id]-[slug].md`, e.g. `backlog/EA-0001-research_brief.md`.

## Correlation IDs

- Format: UUID v4
- Required on ALL events without exception
- Must propagate through the entire feature execution chain
- Every log line during feature execution must include `correlation_id`
