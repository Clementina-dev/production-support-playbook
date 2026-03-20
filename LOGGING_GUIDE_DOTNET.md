\# Logging Guide (.NET APIs) — Serilog + Correlation IDs



Good logs reduce incident time-to-resolution.



\## Principles

\- Prefer \*\*structured logs\*\* over plain text

\- Include a \*\*correlation ID\*\* on every request

\- Log failures with enough context to reproduce (without leaking secrets)

\- Avoid logging sensitive data (PAN, full tokens, passwords, OTPs)



\## Recommended fields to include

\- `CorrelationId` (from header or generated)

\- `RequestPath`, `Method`, `StatusCode`, `ElapsedMs`

\- `Reference` / `TransactionReference` (where applicable)

\- `Partner` (integration name)

\- `ErrorCode` (internal normalized codes)



\## Correlation ID approach

\- Accept `X-Correlation-Id` (if present)

\- Otherwise generate one per request

\- Return it in response headers for support teams



\## What to avoid

\- Full request/response bodies for payment endpoints (may leak PII)

\- Tokens/keys/secrets

\- Logging stack traces for expected validation errors



\## Suggested Serilog usage

\- Use `Serilog.AspNetCore` request logging

\- Enrich logs with context from middleware

\- Use log levels consistently:

&nbsp; - `Information` for normal flow

&nbsp; - `Warning` for recoverable issues/partner failures

&nbsp; - `Error` for failures that require attention

