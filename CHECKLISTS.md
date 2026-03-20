\# Checklists



\## On-call / Incident Triage Checklist

\- \[ ] Confirm severity and scope

\- \[ ] Confirm start time and current impact

\- \[ ] Identify impacted service(s) and dependency (DB/partner/queue)

\- \[ ] Check recent deployments/config changes

\- \[ ] Gather identifiers (reference/correlation id)

\- \[ ] Apply safe mitigation (rollback/disable feature/scale)

\- \[ ] Communicate status updates (clear and timed)

\- \[ ] Verify recovery (metrics + real test transaction)

\- \[ ] Start RCA notes while memory is fresh



\## Post-Incident Checklist

\- \[ ] Complete RCA (root cause + contributing factors)

\- \[ ] Create action items with owners and deadlines

\- \[ ] Add/adjust alerts and dashboards

\- \[ ] Add tests for the failure mode

\- \[ ] Improve logs for faster diagnosis next time

\- \[ ] Update runbook with lessons learned

