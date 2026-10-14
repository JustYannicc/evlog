---
"evlog": minor
---

Add `issues` to the Sentry drain. With `createSentryDrain({ issues: true })`, `error` and `fatal` wide events are also sent as Sentry error events, so they open issues and trigger issue alerts. Each issue carries the wide event's trace context (`traceId`, `spanId`, `parentSpanId`), the same `trace_id` as its structured log, `service` and the configured `tags` as tags, and `METHOD /path` or `action` as the transaction. Events without a `traceId` get one generated, shared by the log and the issue. The option defaults to `false`, so existing setups keep sending logs only.
