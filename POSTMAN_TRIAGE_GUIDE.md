\# Postman Triage Guide (APIs)



Postman is useful during incidents to reproduce and isolate failures.



\## Quick workflow

1\. Use an environment (dev/UAT/prod) so base URLs are consistent

2\. Add headers:

&nbsp;  - `X-Correlation-Id`: generate and reuse while testing

&nbsp;  - Any auth headers required (never share secrets)

3\. Start with a simple health check endpoint (if available)

4\. Reproduce the issue with the same payload that fails in production (remove PII)

5\. Compare:

&nbsp;  - status codes

&nbsp;  - response bodies / error codes

&nbsp;  - latency

6\. Save the request as a collection item for future regression testing



\## Tips

\- Use Postman Console to inspect headers and timing

\- Add tests for status codes and schema when building regression checks

\- Keep a “known good” request saved for quick verification after hotfixes

