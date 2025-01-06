# CODTECH-Advanced-task-2

**Name :** Sangani Dhruvin

**college :** Silver oak university

**Task :** Web Application Vulnerability Scanner

**Intern ID :** CT08DAV

**Key Steps in Building the Vulnerability Scanner:**
Scanning for SQL Injection: Detect if user inputs in URLs or forms are vulnerable to SQL Injection attacks.
Scanning for XSS (Cross-Site Scripting): Check if user inputs in URLs or forms are vulnerable to XSS attacks.
Identifying open ports: Check for common ports that may have vulnerabilities (e.g., HTTP, HTTPS, FTP).
CSRF Detection: Look for missing or improper CSRF tokens.

**Prerequisites:
Libraries:**
requests: For sending HTTP requests.
BeautifulSoup: For parsing HTML content (if needed for form parsing).
re: For regular expression matching (for detecting input patterns).

**Explanation of the Vulnerability Scanner:**
**SQL Injection:**

This part tests for potential SQL injection by sending typical SQL injection payloads in the URL query string. If the response contains error messages related to database queries (mysql, syntax, error), it suggests a potential vulnerability.
**XSS (Cross-Site Scripting):**

The script tests for XSS by injecting common payloads such as <script>alert('XSS')</script> or <img src='x' onerror='alert(1)' />. If the payload is reflected back in the response, it indicates a possible XSS vulnerability.
**CSRF (Cross-Site Request Forgery):**

This part checks if forms in the webpage contain CSRF tokens. If no CSRF token (<input name="csrf_token" />) is present in a form, it is flagged as a potential CSRF vulnerability.

**Limitations & Further Improvements:**

Complex Vulnerabilities: This script only checks for a few common vulnerabilities (SQLi, XSS, CSRF). It could be expanded to include checks for more advanced vulnerabilities such as:
Open redirects
Directory traversal
Insecure HTTP methods (like PUT, DELETE)
Server misconfigurations
Broken authentication/authorization
Error Handling: The script could benefit from better error handling for HTTP requests (timeouts, invalid responses).
Rate Limiting: To avoid being flagged as a potential attacker, consider adding rate-limiting between requests.
Integration with other scanners: The tool can be integrated with more sophisticated scanning frameworks like OWASP ZAP or Burp Suite.
