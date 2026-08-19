# CS-305-Software-Security

Portfolio work from CS 305 Software Security

## Artemis Financial – Practices for Secure Software

### Client and Software Requirements

Artemis Financial is a financial consulting company that develops individualized financial plans for its clients, including savings, retirement, investments, and insurance. The company wanted to modernize its software while improving the protection of sensitive client and financial information. My task was to examine the existing application for security concerns and implement secure communication mechanisms, including checksum verification and HTTPS.

### Software Security and Vulnerability Assessment

One area I did well was identifying how different security controls could be used together rather than relying on a single security solution. I implemented SHA-256 checksum verification for data integrity and configured SSL/TLS so the application communicates through HTTPS. I also used OWASP Dependency-Check to identify known vulnerabilities associated with third-party dependencies.

Secure coding is important because vulnerabilities can expose confidential information, allow unauthorized access, damage data integrity, and create financial and reputational consequences for an organization. For a company such as Artemis Financial, protecting client information is especially important because customers must be able to trust the company with sensitive financial data.

### Challenges and Helpful Parts of the Assessment

One of the more challenging parts of the project was interpreting the results from OWASP Dependency-Check. The scan identified a large number of vulnerabilities in dependencies that were already included in the supplied project. I had to distinguish those existing dependency vulnerabilities from vulnerabilities that might have been introduced by my own refactoring. This was also helpful because it showed me that secure development involves more than reviewing the code that I personally write. Developers must also consider the security of frameworks, libraries, and dependencies used by an application.

### Increasing Layers of Security

I increased the application's security by using a defense-in-depth approach. SHA-256 checksum verification provided a way to verify data integrity, while a self-signed certificate, RSA key pair, PKCS12 keystore, and SSL/TLS configuration allowed the application to communicate through HTTPS. These controls address different security concerns and provide stronger protection when used together.

In future projects, I would continue using automated tools such as OWASP Dependency-Check along with manual code review and functional testing. I would evaluate vulnerabilities based on their severity, exploitability, the affected component, and how that component is used by the application before selecting an appropriate mitigation.

### Functional and Security Testing

I manually reviewed the refactored code and configuration for syntactical, logical, and security problems. After correcting issues encountered during development, I ran the Spring Boot application and verified that the embedded Tomcat server successfully started using HTTPS on port 8443. I also tested the `/hash` endpoint and confirmed that it returned the expected SHA-256 checksum.

After refactoring, I ran OWASP Dependency-Check again as a secondary static test. This allowed me to review whether my changes introduced additional dependency vulnerabilities. My implementation relied primarily on Java's existing security APIs and Spring Boot's SSL/TLS capabilities rather than adding new third-party libraries.

### Resources, Tools, and Coding Practices

Several tools and practices from this course will be useful in future assignments and professional development. I used Java's `MessageDigest` API for SHA-256 hashing, Java Keytool to create and export a certificate, Spring Boot SSL/TLS configuration for HTTPS, Maven for project management, and OWASP Dependency-Check for vulnerability scanning. I also practiced defense in depth, manual code review, dependency analysis, functional testing, and using established cryptographic APIs instead of attempting to create custom cryptographic implementations.

### What I Would Show Future Employers

I would show future employers the completed Artemis Financial secure software project because it demonstrates several practical software security skills. The project shows that I can implement SHA-256 hashing, configure certificate-based HTTPS communication, work with Java Keytool and keystores, perform dependency vulnerability analysis, and test a refactored application for functionality and security. More importantly, it demonstrates my ability to consider security throughout the development process instead of treating security as something that is added only after an application has been completed.
