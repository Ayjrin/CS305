# CS305


## Briefly summarize your client, Artemis Financial, and its software requirements. Who was the client? What issue did the company want you to address?
Artemis Financial is a consulting firm that buidls individualized savings, retirement, investment, and insurance plans. They asked Global Rain to modernize their public web application by adding a cryptographic checksum step and converting all traffic from HTTP to HTTPS to protect customer financial data.

---
## What did you do well when you found your client’s software security vulnerabilities? Why is it important to code securely? What value does software security add to a company’s overall well-being?
Artemis Financial is a consulting firm that builds individualized savings, retirement, investment, and insurance plans. They asked Global Rain to modernize their public web application by adding a cryptographic checksum step and converting all traffic from HTTP to HTTPS to protect customer financial data.

---
## Which part of the vulnerability assessment was challenging or helpful to you?
Generating the self-signed certificate with Java Keytool and wiring it into Spring Boot’s keystore required exact command syntax, which was the most challenging step given the documentation was foor windows; the OWASP style static dependency check was most helpful because it quickly showed whether new code introduced additional risks.

---
## How did you increase layers of security? In the future, what would you use to assess vulnerabilities and decide which mitigation techniques to use?
I enabled SHA 256 checksum generation in the /hash endpoint, forced TLS on port 8443, and added HSTS in application.properties. For future work I would pair the dependency check with manual code review following the OWASP vulnerability assessment diagram.

---
## How did you make certain the code and software application were functional and secure? After refactoring the code, how did you check to see whether you introduced new vulnerabilities?
I compiled and ran the service, then visited https://localhost:8443/hash to verify both the checksum output and the green padlock; afterward I reran the dependency-check scan and confirmed that no new CVEs appeared in the report.

---
## What resources, tools, or coding practices did you use that might be helpful in future assignments or tasks?
Key tools included Java Keytool for certificate generation, Spring Boot’s TLS configuration, the OWASP dependency-check Maven plugin, and the secure-coding sections of the OWASP Cheat Sheet Series; all align with industry best practices and are reusable on later projects.

---
## Employers sometimes ask for examples of work that you have successfully completed to show your skills, knowledge, and experience. What might you show future employers from this assignment?
I would present the HTTPS screenshot displaying the checksum and my name, the before and after code diff showing the TLS and checksum refactor, and the final dependency-check HTML report that lists zero outstanding vulnerabilities.
