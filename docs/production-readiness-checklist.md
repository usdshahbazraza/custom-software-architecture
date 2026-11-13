# Production Readiness Checklist

Use this as a conversation starter, not a certification or proof of security. Adapt requirements to your domain, applicable law, and organizational risk.

## Product and architecture
- [ ] Critical workflows, expected usage, and failure scenarios are documented.
- [ ] Service levels, latency objectives, and recovery objectives are agreed.
- [ ] Module responsibilities, data ownership, and integration contracts are clear.
- [ ] High-risk architectural assumptions have been tested.

## Identity and data protection
- [ ] Authentication and authorization are tested across roles and tenant boundaries.
- [ ] Secrets are centrally managed, rotated where appropriate, and excluded from code/logs.
- [ ] Sensitive data collection, retention, and deletion are justified and documented.
- [ ] Transport security and appropriate data-at-rest protection are configured.
- [ ] Dependency and application security checks run in the delivery pipeline.

## Reliability and operations
- [ ] Timeouts, retries, idempotency, and duplicate-event handling are specified.
- [ ] Business-critical background jobs have alerting and failure recovery.
- [ ] Logs/metrics provide enough context to diagnose important failures without leaking sensitive data.
- [ ] Backups are automated and restoration has been tested.
- [ ] Monitoring alerts have named responders and an escalation route.

## Deployment and change management
- [ ] Reproducible builds and automated tests exist for key flows.
- [ ] Schema migration and rollback/forward-fix procedures are rehearsed.
- [ ] Deployment approvals and access are limited to authorized personnel.
- [ ] A production incident response and communication plan is available.
- [ ] Post-release verification covers important customer journeys.
