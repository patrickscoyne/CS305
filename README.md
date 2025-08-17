# Southern New Hampshire University: CS305 Software Security

For this repository, I chose to submit **Project One: Vulnerability Assessment Report**. The project involved examining the web application for a fictional company, Artemis Financial. Specifically, the project requirements were:

- Interpret client needs.

- Identify which areas of security apply to the application using a vulnerability assessment process flow diagram.

- Conduct a manual code review.

- Integrate the Maven Dependency-Check Plug-in and conduct a static test.

- Interpret the results from the manual review and static tests, and create a mitigation plan.
---
## **Reflection:**

***Briefly summarize your client, Artemis Financial, and its software requirements. Who was the client? What issue did the company want you to address?***

Artemis Financial is a consulting firm dedicated to creating personalized financial plans for clients, covering areas like savings, retirement, investments, and insurance. Artemis Financial's software is a RESTful web API designed to handle financial services securely over the internet. The main issue they wanted me to address was safeguarding the organization from external threats. I needed to thoroughly examine the web-based application to uncover security vulnerabilities, document them in detail, and recommend effective mitigation strategies.

***What did you do well when you found your client's software security vulnerabilities? Why is it important to code securely? What value does software security add to a company's overall well-being?***

After identifying the software security vulnerabilities in Artemis Financial's application, I effectively documented each vulnerability in detail within the assessment report while developing a tailored mitigation plan for each one. For example, I recommended updates to vulnerable libraries and implemented input validation techniques to avoid SQL injection and Denial-of-Service attacks. Coding securely is crucial because it protects sensitive data from unauthorized access, manipulation, or interception, which is especially vital in financial applications like Artemis Financial's RESTful web API. For instance, without secure coding practices, customer data such as personal financial details could be exposed, leading to severe consequences, including identity theft, monetary losses for clients, and regulatory penalties. The Gramm-Leach-Bliley Act (GLBA) specifically mandates compliance with security standards to safeguard non-public personal information, underscoring the legal imperative to code securely to avoid non-compliance issues. Overall, software security adds significant value to a company's well-being by creating customer trust, as clients are more likely to engage with a firm that has a history of protecting customer data. Secure software also helps mitigate financial risks by preventing costly data breaches, which could result in substantial fines, legal fees, lawsuits, and operational downtime.

***Which part of the vulnerability assessment was challenging or helpful to you?***

The most challenging aspect of the vulnerability assessment was ensuring thoroughness during the manual code review, particularly when identifying areas in the codebase that required input validation to prevent risks like SQL injection or cross-site scripting. The process demanded that I think like an attacker, simulating potential exploit scenarios to uncover weaknesses, which was time-intensive. Ultimately, I developed practical input validation methods, such as using @Pattern to allow only alphanumeric characters at the endpoints. Despite the challenges, conducting the vulnerability assessment was a learning experience that sharpened my analytical skills.

***How did you increase layers of security? In the future, what would you use to assess vulnerabilities and decide which mitigation techniques to use?***

To increase layers of security in the application, specifically during Project Two, where I refactored the code and implemented enhancements, I utilized the vulnerability assessment process flow diagram to identify and address security areas within the codebase systematically. Through manual code review, I pinpointed weaknesses and applied targeted mitigations. For instance, in the cryptography domain, I deployed SHA-256 hashing to generate a checksum verification for file transfers to ensure their integrity. In the client/server communication layer, I enabled HTTPS to provide encrypted and authenticated exchanges between client browsers and the server, preventing man-in-the-middle attacks. Additionally, for code error handling and quality, I integrated SLF4J logging to provide robust error management while avoiding the exposure of sensitive stack trace details that could aid attackers. In the future, to assess vulnerabilities and decide on mitigation techniques, I would begin with static testing using tools like the Maven Dependency-Check Plug-in to scan for vulnerable dependencies, suppress any false positives via a suppression.xml file, and resolve issues by updating libraries or following recommendations from associated CVEs in the dependency-check report. Following that, I would conduct a comprehensive manual code review guided by the vulnerability assessment process flow diagram to uncover deeper, context-specific risks. Finally, I would address each vulnerability sequentially, selecting mitigations based on factors like severity, potential impact, and feasibility.

***How did you make certain the code and software application were functional and secure? After refactoring the code, how did you check to see whether you introduced new vulnerabilities?***

To ensure the code and software application were functional and secure, I conducted a multifaceted verification process that included both automated scans and manual testing. After refactoring the code in Project Two, I reran the Maven Dependency-Check Plug-in to perform a fresh static analysis, comparing the results against the initial baseline scan to confirm that no new vulnerabilities had been introduced through the refactoring. Additionally, to test functionality and security in a runtime environment, I started the application server and accessed the endpoints via a web browser, simulating typical user interactions to ensure the RESTful API processed requests correctly and returned expected responses without errors. For security validation, I deliberately injected unexpected parameters, such as malformed inputs, to probe for weaknesses like improper error handling. Overall, the combination of static scanning, functional testing, and dynamic probing assured that the application was both operational and resilient against threats.

***What resources, tools, or coding practices did you use that might be helpful in future assignments or tasks?***

I leveraged several resources, tools, and coding practices that proved invaluable for enhancing software security and could be beneficial in future assignments or tasks. The Maven Dependency-Check Plug-in, integrated within the Eclipse IDE, was essential for automated static analysis of third-party libraries, allowing me to identify and mitigate vulnerabilities in dependencies quickly. Additionally, I used Keytool through Eclipse's integrated terminal window to generate and manage keystores and certificates for enabling HTTPS. The integrated terminal was beneficial as it automatically positioned me in the project's root directory, enabling real-time visibility of file changes in the project explorer pane, which streamlined the process compared to using an external terminal. For coding practices, I referred to the *OWASP Secure Coding Practices Quick Reference Guide* (OWASP Foundation, n.d.), which offers concise, actionable checklists for implementing defenses against common threats like injection attacks and improper error handling, serving as a handy reference to embed security into the development lifecycle. Complementing this, the *OWASP Top 10* (OWASP Foundation, 2021) provided a prioritized list of the most critical web application security risks, such as cryptographic failures and vulnerable components, guiding my manual reviews and mitigation strategies to focus on high-impact areas.

***Employers sometimes ask for examples of work that you have successfully completed to show your skills, knowledge, and experience. What might you show future employers from this assignment?***

From this assignment, I could present several examples to future employers to demonstrate my skills in software security assessment and mitigation. For instance, both Project One and Project Two showcase my proficiency in integrating, running, and interpreting the Maven Dependency-Check Plug-in for static vulnerability scanning, including comparing baseline and post-refactoring reports to ensure no new issues were introduced. The Vulnerability Assessment Report from Project One highlights my ability to analyze dependency-check outputs and navigate corresponding CVEs to recommend resolutions like library updates or code fixes. Additionally, the manual code review sections of the reports illustrate my critical thinking in spotting vulnerabilities such as inadequate input validation or cryptographic weaknesses, and proposing targeted mitigations, like implementing SHA-256 hashing for data integrity or enabling HTTPS for secure communications. I could also share code snippets from Project Two's refactoring, demonstrating practical implementations of security layers, including SLF4J logging for error handling without exposing sensitive information.

---
**References**

OWASP Foundation. (n.d.). *OWASP secure coding practices: Quick reference guide* (Version 2.1). https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/assets/docs/OWASP_SCP_Quick_Reference_Guide_v21.pdf

OWASP Foundation. (2021). *OWASP Top 10*. https://owasp.org/
