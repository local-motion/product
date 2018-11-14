# Non-functional requirements

All software components in LocalMotion should meet the requirements specified here.

## Information security
- Users must only have access to functions or services to which they possess specific authorisation
- Client-side caching must be disabled when sensitive information is processed
- Forms containing sensitive information (like passwords) must have client caching and autocomplete features disabled
- All input must be validated and all output must be encoded
- Prevent CSRF attacks by providing and validating an authorisation token in the HTTP header
- In case of technical errors show a user friendly error message and an error code for traceability. Additional write the technical details of the error to the application log.
- Set these security headers on the HTTP traffic:
  1. HTTP Strict-Transport-Security (HSTS)
  2. X-Frame-Options set to 'deny' to prevent our pages from being framed in
  3. X-XSS-Protection
- Disable directory browsing on the content server
- Sensitive data must be sent to the server through HTTP message body of a POST or PUT request
- Software must comply with the OWASP top 10 rules: https://www.owasp.org/index.php/OWASP_Top_Ten_Cheat_Sheet

## Scalability
- The system should be capable of handling 20 concurrent user sessions
