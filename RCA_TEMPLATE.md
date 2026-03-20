\# Root Cause Analysis (RCA) Template



> Use this template after an incident/outage to document what happened, what was done, and how to prevent recurrence.



\## 1) Incident Summary

\- \*\*Incident Title:\*\*  

\- \*\*Date (UTC):\*\*  

\- \*\*Start Time (UTC):\*\*  

\- \*\*End Time (UTC):\*\*  

\- \*\*Duration:\*\*  

\- \*\*Severity:\*\* (SEV-1 / SEV-2 / SEV-3)  

\- \*\*Services Affected:\*\*  

\- \*\*Customer Impact:\*\* (Who/what was impacted? How did it present?)  



\## 2) Detection \& Alerting

\- \*\*How was it detected?\*\* (Monitoring alert, customer report, internal report, etc.)

\- \*\*First signal observed:\*\* (error spikes, latency, queue backlog, partner failures, etc.)

\- \*\*Did alerts fire correctly?\*\* (Yes/No)  

&nbsp; - If no: what was missing or misconfigured?



\## 3) Timeline (UTC)

| Time (UTC) | Event |

|---|---|

| | First signal detected |

| | Triage started |

| | Mitigation applied |

| | Service restored |

| | Root cause confirmed |

| | Follow-up tasks created |



\## 4) Technical Details

\### What happened?

Describe symptoms, errors, and observed behavior.



\### Root cause

Explain the underlying root cause (not just the trigger).



\### Contributing factors

\- Missing validation?

\- Unhandled failure mode?

\- Poor observability?

\- Deployment/process issue?

\- Partner instability?



\## 5) Resolution \& Mitigation

\- \*\*Immediate mitigation:\*\* (rollback, feature flag off, config change, scaling, hotfix, etc.)

\- \*\*Permanent fix:\*\* (code change, architectural change, data fix, process update)

\- \*\*Verification steps:\*\* (how you confirmed normal behavior)



\## 6) Customer Communication

\- What was communicated?

\- When?

\- Through which channel?



\## 7) Preventing Recurrence (Action Items)

| Action Item | Owner | Priority | Due Date | Status |

|---|---|---|---|---|

| Add alert for X | | High | | |

| Add validation for Y | | Medium | | |

| Improve logging around Z | | Medium | | |



\## 8) Lessons Learned

\- What went well?

\- What was painful/slow?

\- What should we improve next time?

