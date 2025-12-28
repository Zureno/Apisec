# Passive Reconnaissance Matrix

> **Authorized use only.**
> Use these techniques only on assets you own or have explicit written permission to test.
> Store any sensitive reconnaissance queries in a private repository or restricted documentation.

---

## Google Dorking (Matrix)

| Google Dorking Query  | Expected results 
|---|---|
| inurl:"/wp-json/wp/v2/users" | 	Finds all publicly available WordPress API user directories. | 
| intitle:"index.of" intext:"api.txt" | Finds publicly available API key files. |
| inurl:"/api/v1" intext:"index of /" | Finds potentially interesting API directories. | 
| ext:php inurl:"api.php?action=" | Finds all sites with a XenAPI SQL injection vulnerability. (This query was posted in 2016; four years later, there are currently 141,000 results.) |
| intitle:"index of" api_key OR "api key" OR apiKey -pool | This is one of my favorite queries. It lists potentially exposed API keys. | 

---

## Showdan
 
| Shodan Queries | Purpose
|---|---|
| hostname:"targetname.com" | Using hostname will perform a basic Shodan search for your target’s domain name. This should be combined with the following queries to get results specific to your target. | 
| "content-type: application/json" | APIs should have their content-type set to JSON or XML. This query will filter results that respond with JSON. |
|"content-type: application/xml"  | This query will filter results that respond with XML. | 
| "200 OK" |You can add "200 OK" to your search queries to get results that have had successful requests. However, if an API does not accept the format of Shodan’s request, it will likely issue a 300 or 400 response.|
| "wp-json" | This will search for web applications using the WordPress API. | 


---

## Notes

- **Logging:** Capture findings with URL, timestamp, and evidence screenshot.

