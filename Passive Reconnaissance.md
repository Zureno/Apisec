# Passive Reconnaissance Matrix

> **Authorized use only.**
> Use these techniques only on assets you own or have explicit written permission to test.
> Store any sensitive reconnaissance queries in a private repository or restricted documentation.

---

## Google Dorking (Matrix)

| Google Dorking Query  | Expected results 
|---|---|
| inurl:"/wp-json/wp/v2/users" | 	Finds all publicly available WordPress API user directories | 

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
