# Passive Reconnaissance Matrix

> **Authorized use only.**
> Use these techniques only on assets you own or have explicit written permission to test.
> Store any sensitive reconnaissance queries in a private repository or restricted documentation.

---

## Google Dorking (Matrix)

| Category | Query (placeholder) | Expected Results | What to Validate (Defensive) | Recommended Remediation |
|---|---|---|---|---|
| WordPress Enumeration | **[REDACTED_QUERY_1]** | Identifies publicly accessible endpoints that may reveal usernames or metadata. | Confirm endpoint is intended to be public; check for user enumeration; verify rate-limiting. | Disable public user listing; tighten REST permissions; add rate-limiting/WAF rules. |
| Public Directory Listings | **[REDACTED_QUERY_2]** | Finds directory indexes and exposed files that should not be public. | Confirm if directory listing is enabled; review what files are accessible. | Disable directory indexing; restrict access; move sensitive files out of web root. |
| API Directories | **[REDACTED_QUERY_3]** | Locates API directories / routes that may expose documentation or debug paths. | Validate auth requirements; confirm no debug endpoints; check access logs. | Require auth; remove debug routes; restrict by IP/VPN; add WAF policies. |
| Sensitive File Exposure | **[REDACTED_QUERY_4]** | Detects potentially exposed config/key/token files. | Confirm if any secrets are present; rotate if exposed; verify repo history. | Rotate keys; add secret scanning; ensure `.gitignore`; move secrets to vault/KMS. |
| Injection Indicators (Research) | **[REDACTED_QUERY_5]** | Finds pages likely to accept parameters and require security review. | Confirm parameter handling; validate input validation; check for error leakage. | Parameterized queries; input validation; WAF rules; safe error handling. |
| “API Key” Mentions | **[REDACTED_QUERY_6]** | Surfaces pages mentioning keys/tokens that may be accidentally published. | Confirm content is not leaking secrets; validate no hardcoded tokens. | Remove secrets; rotate; enable DLP; add pre-commit secret detection. |

---

## Safe examples (for authorized internal use)

Use these *scope-limited* patterns when validating your own domains:

- `site:yourcompany.com`
- `site:yourcompany.com filetype:pdf`
- `site:yourcompany.com "confidential"`
- `site:yourcompany.com inurl:docs`
- `site:yourcompany.com inurl:api`

> Keep real queries that target sensitive files/keys in an internal-only location.

---

## Notes

- **Logging:** Capture findings with URL, timestamp, and evidence screenshot.
- **Triage:** Confirm exposure, impact, and whether authentication is missing/misconfigured.
- **Follow-up:** Track remediation and re-validate after fixes.
