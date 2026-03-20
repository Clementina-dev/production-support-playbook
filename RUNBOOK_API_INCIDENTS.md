\# Runbook: API Incidents (Payments/Integrations)



This runbook helps you troubleshoot common production incidents for backend APIs.



\## 0) First principles (do these first)

1\. \*\*Confirm scope:\*\* one customer, one region, or system-wide?

2\. \*\*Confirm time window:\*\* when did it start?

3\. \*\*Check recent changes:\*\* deployments, config changes, partner changes

4\. \*\*Get a correlation ID / reference:\*\* transaction reference, request id, customer id (if allowed)



\## 1) API is down (5xx for most requests)

Checklist:

\- Check service health endpoint (if available)

\- Check last deployment time and rollback plan

\- Check logs for startup errors, missing config, DB connection failures

\- Check infra (CPU/memory spikes, restarts, app pool crashes)



Common causes:

\- bad config/secret, DB connectivity, breaking change deployed, certificate issues



Mitigation:

\- rollback / redeploy previous version

\- revert config change

\- temporarily disable a failing feature with a flag (if available)



\## 2) High latency / timeouts

Checklist:

\- Is latency external (partner calls) or internal (DB)?

\- Check DB slow queries / blocked sessions

\- Check thread pool starvation / high CPU

\- Check downstream dependencies (partner/slowness)



Mitigation:

\- reduce load (rate limit, disable non-critical endpoints)

\- add timeouts + circuit breaker for partner calls

\- scale out (if applicable)



\## 3) Payment/integration failures increased

Checklist:

\- Identify which partner/system is failing

\- Compare success vs failure codes

\- Validate request payload changes

\- Confirm partner status page/communications (if available)



Mitigation:

\- switch to retry-with-backoff (carefully)

\- circuit breaker to protect your system

\- queue requests for later retry (if supported)

\- fall back to “pending” status and reconcile later



\## 4) Data inconsistency / duplicate transactions

Checklist:

\- Check idempotency enforcement

\- Confirm unique constraints and duplicate keys

\- Review recent code changes around references/keys

\- Compare logs + DB records + partner responses



Mitigation:

\- stop the bleeding (disable endpoint / add temporary guard)

\- dedupe safely and reconcile using audit trails

\- create a script-based fix only with approvals and logging



\## 5) After stabilization

\- Capture timeline

\- Save key logs (with sensitive data removed)

\- Create RCA using `RCA\_TEMPLATE.md`

\- Create follow-up tasks (alerts, tests, docs, fixes)

