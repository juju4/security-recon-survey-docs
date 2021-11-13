
Application

## General

* project goal
* project owner
* resources
* importance
* confidentiality

Ideally, security can establish a threat model on project based on informations provided.

## Workflows

Be it for programming, for security, for design or whatever group, application documentation should include core business workflows and data flows.
This will likely help identifying critical parts and define functions or groups of functions.

* Identification should be adapted to the type of services. Gov ID should be needed only when required, typically financial and health services.
* Authentification should allow modern options
  * Federation like SAML or OpenID if fit context
  * Good settings for password rules based on NIST guidance and check against trivial+compromised password
  * Passwordless options with choice for users (mobile phone or app, hardware token, biometrics...)
  * MFA enforced for critical actions based on risk
  * Password reset with best practices be it online, phone or else
* Data takeout mechanisms
* Support with good authentications
* Abuse or security issues report options
* Warning message at home/welcome/login or conflicting/under evaluation user content

## Technology

* dependency check. any End-Of-Life(EOL) or near-EOL dependency.
    * be especially careful on crypto choice
    * review libraries usage, most notably authentication, cryptography, logging
* any continuous integration support? (automation, API...)
* keep presentation code, functional code and backend code well separated depending on context
* security review
    * security awareness of developers (OWASP, crypto...)
    * plan for code review and pentest
* design your logs for security and debugging with clear loglevel and tagging and if should alert with ideally follow-up actions/process. make them actionable.

## References

On Application security program

* [OWASP Application Security Verification Standard Project](https://www.owasp.org/index.php/Category:OWASP_Application_Security_Verification_Standard_Project)
* [Building Security In Maturity Model](https://www.bsimm.com/)
* [Application Security and Development Checklist, STIG Viewer](https://www.stigviewer.com/stig/application_security_and_development_checklist/)
* [NIST SP 800-53 - Security Controls](https://nvd.nist.gov/800-53)
* [NIST SP 800-123 - Guide to General Server Security](https://csrc.nist.gov/publications/detail/sp/800-123/final) + bastion/jumphost
* [What's inside Microsoft security architecture recommendations?](https://docs.microsoft.com/en-us/security/compass/microsoft-security-compass-introduction)
* [TIC 3.0 Core Guidance Documents, CISA, Jul 2020](https://www.cisa.gov/publication/tic-30-core-guidance-documents)
* [Security Architecture Patterns - OpenSecurityArchitecture](https://www.opensecurityarchitecture.org/cms/library/patternlandscape)
* [Checksec tool in Python, Rich output, based on LIEF](https://github.com/Wenzel/checksec.py)
* [FLOSS Best Practices Criteria (Passing Badge)](https://bestpractices.coreinfrastructure.org/en/criteria/0)
* [Rugged Software Manifesto](https://ruggedsoftware.org)
* [Minimum Viable Secure Product](https://mvsp.dev)

On Threat modeling

* [Threat Modeling, OWASP](https://owasp.org/www-community/Threat_Modeling)
* [Docker Security at PyCon: Threat Modeling & State Machines, May 2017](https://blog.docker.com/2017/05/docker-security-pycon-threat-modeling-state-machines/)
* [Threat Modeling Toolkit, May 2017](https://speakerdeck.com/owaspmontreal/threat-modeling-toolkit)
* [If Attackers Can Use Graphs, Then Why Can’t We? Apr 2017](https://t2.fi/2017/04/11/if-attackers-can-use-graphs/)
* [Adversarial Tactics, Techniques & Common Knowledge, US Mitre](https://attack.mitre.org/wiki/Main_Page)
* [Discovering risks with interviews., Oct 2020](https://github.com/magoo/minimalist-risk-management/blob/master/INTERVIEW.md)
* [Threat Taxonomy, ENISA](https://www.enisa.europa.eu/topics/threat-risk-management/threats-and-trends/enisa-threat-landscape/threat-taxonomy/view)
* [Threat Modeling Manifesto](https://www.threatmodelingmanifesto.org)
https://attack.mitre.org/
* Kubernetes focused
https://adam.shostack.org/blog/2018/05/threat-model-thursday-google-on-kubernetes/
https://research.nccgroup.com/2017/11/23/kubernetes-security-consider-your-threat-model/
https://github.com/trailofbits/audit-kubernetes/blob/master/reports/Kubernetes%20Threat%20Model.pdf
https://www.trendmicro.com/vinfo/us/security/news/virtualization-and-cloud/guidance-on-kubernetes-threat-modeling
https://owasp-kstg.netlify.app/threat-model/introduction.html
* Examples Risks
  * Unauthorized access to data: Impact/Cost? authentication+MFA+authorization logs? sensitive data, takeout function one or multiple user, database encrypted columns...
  * Data tampering: Impact/Cost? authentication+MFA+authorization logs?
  * Service unavailable: Impact/Cost? DDoS? How to confirm/troubleshoot? network/cpu/memory stats, network diagram/each hop...
  * Ransomware on application stack or developers
  * Supply chain attack: one stack component was compromised? how validate if application is? CI/CD, sandbox, privilege separation, network segmentation/flow logs...
  * Define others (see links/taxonomy)


On Logging

* [Logging Cheat Sheet, OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html)
* [Designing systems for investigability is an underrated discipline. Someone should write a book, think of it like thread modeling. Any new application or feature should have a review for how and what it logs for both security and debugging. Aug 2020](https://twitter.com/davehull/status/1294646265016393731)
* [Get your logging act together, loggers! Dec 2018](https://www.hexacorn.com/blog/2018/12/05/get-your-logging-act-together-loggers/)
* [LogLevel Enum, Microsoft .Net](https://docs.microsoft.com/en-us/dotnet/api/microsoft.extensions.logging.loglevel?view=dotnet-plat-ext-3.1)
* [Python Logging](https://docs.python.org/3/library/logging.html)
* [Audit Policy Recommendations, Windows, 2017](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/audit-policy-recommendations)

On API

* [API-Security-Checklist, GitHub](https://github.com/shieldfy/API-Security-Checklist)

On password

* [Digital Identity Guidelines - Authentication and Lifecycle Management, NIST SP800-63B](https://pages.nist.gov/800-63-3/sp800-63b.html)
* [Disabling Google 2FA Doesn't Need 2FA, Jul 2020](https://www.infoq.com/news/2020/07/google-password-2fa-woes/)
* [What I Learned About Security from Calling 35 Contact Centers, Feb 2019](https://www.twilio.com/blog/learned-about-security-from-calling-35-contact-centers)
* [Best practices to secure inbound calls to your contact center, May 2020](https://www.twilio.com/blog/best-practices-security-inbound-contact-center)
* [Phishing Resistant SMS Autofill, Sep 2020](https://github.blog/2020-09-25-phishing-resistant-sms-autofill/), https://wicg.github.io/web-otp/

On naming (API tokens, secret id, pipename...)
* [Behind GitHub’s new authentication token formats, Apr 2021](https://github.blog/2021-04-05-behind-githubs-new-authentication-token-formats/)

On documentation
* network traffic matrix: domain, IP - proxy, firewall settings
* identity matrix: privileges and identities needed - standard or admin or system, domain or not, API users, Service Accounts
  * Examples: (bad) SolarWinds
  [One to keep in mind - if you deploy SolarWinds agent on Domain Controllers as SYSTEM, SYSTEM on a Domain Controller = Domain Admin in effect. Jan 2021](https://twitter.com/GossiTheDog/status/1345625968690536449)
* Business workflows, data workflows, risk level
* Identified risks, threats, how to detect and respond to them
* Privilege Separation, Sandboxing
* Dependencies list (library, softwares) and more detailed used of any cryptographic/authentication libraries and functions
* Which programming languages are used? are components sandboxed?
* automated report of configuration, users/roles, login/privileged activities
* [Security Scorecards, OSSF](https://github.com/ossf/scorecard), [Are Canaries Secure? Mar 2020](https://blog.thinkst.com/2020/03/are-canaries-secure.html), [How we’re helping to reshape the software supply chain ecosystem securely, Jan 2021](https://cloud.google.com/blog/products/identity-security/how-were-helping-reshape-software-supply-chain-ecosystem-securely), [Supply chain attack prevention: 3 things to do now, Jan 2021](https://expel.io/blog/supply-chain-attack-prevention-3-things-to-do-now/), [I'm hoping that SBOM ends up like a binary transparency log of hashes of all inputs to a resulting reproducibly-built binary, but I'm preparing myself for it to be a manifest of package names and versions... May 2021](https://twitter.com/dinodaizovi/status/1392642264535506944), [ sigstoreA non-profit, public good software signing & transparency service](https://sigstore.dev), [Security/Binary Transparency - Mozilla](https://wiki.mozilla.org/Security/Binary_Transparency)
* [SOFTWARE BILL OF MATERIALS](https://www.ntia.gov/SBOM)
* [Our product is a profiling agent, which has to run privileged on the underlying machines in production. This would of course create a potential risk for users. We are hence taking many steps to mitigate the risk: Apr 2021](https://twitter.com/halvarflake/status/1385169740088348673)
* Test/Scan
  * VirusTotal and similar
  * Android: [Scanning APK file for URIs, endpoints & secrets](https://github.com/dwisiswant0/apkleaks), [Pithus - Android security & privacy analysis for the masses, Jan 2021](https://beta.pithus.org)
  * Chrome extension: crxcavator

On CI/CD
* https://github.com/BBVA/proctool

(Heavy) Client

* Sandboxing
  * [A new approach to browser security: the Google Chrome Sandbox, Oct 2008](https://blog.chromium.org/2008/10/new-approach-to-browser-security-google.html), [Chromium Sandbox](ttps://chromium.googlesource.com/chromium/src/+/master/docs/design/sandbox.md), [System Hardening](https://www.chromium.org/chromium-os/chromiumos-design-docs/system-hardening), [OSX Sandboxing Design](https://www.chromium.org/developers/design-documents/sandbox/osx-sandboxing-design)
  * [Mozilla Security/Sandbox](https://wiki.mozilla.org/Security/Sandbox)
  * [Systemd seccomp, apparmor/selinux, cgroups, namespaces - Freedesktop Official documentation](https://www.freedesktop.org/software/systemd/man/systemd.exec.html), [French ANSSI, RMLL 2017](https://tim.siosm.fr/downloads/2017-07-05_rmll2017_linux_system_hardening_with_systemd.pdf), https://www.redhat.com/sysadmin/mastering-systemd, https://www.redhat.com/files/summit/session-assets/2019/T4D2A2.pdf
  * [Linux seccomp made easy, library](https://github.com/cloudflare/sandbox)
  * [Sandboxing and Workload Isolation, Jul 2020](https://fly.io/blog/sandboxing-and-workload-isolation/)
  * [Sandboxing in Linux with zero lines of code, Aug 2020](https://blog.cloudflare.com/sandboxing-in-linux-with-zero-lines-of-code/)
  * Electron: [Security, Native Capabilities, and Your Responsibility - Electron Documentation](https://www.electronjs.org/docs/tutorial/security), [The App Sandbox, Jun 2020](https://slack.engineering/the-app-sandbox/)
  * [Sandboxing and Multimedia/VLC, May 2017](https://news.ycombinator.com/item?id=14409234), [Software sandboxing - Multimedia/VLC, Aug 2021 - FR](https://www.nolimitsecu.fr/software-sandboxing/)
  * [Firefox and Chromium - Exploit mitigation comparison, Jun 2021](https://madaidans-insecurities.github.io/firefox-chromium.html)

* [Security Best Practices for C++](https://docs.microsoft.com/en-us/cpp/security/security-best-practices-for-cpp?view=vs-2019)
* [Developer Guidance for Hardware-enforced Stack Protection, Feb 2021](https://techcommunity.microsoft.com/t5/windows-kernel-internals/developer-guidance-for-hardware-enforced-stack-protection/ba-p/2163340)
* [Règles de programmation pour le développement sécurisé de logiciels en langage C, ANSSI - FRENCH](https://www.ssi.gouv.fr/entreprise/guide/regles-de-programmation-pour-le-developpement-securise-de-logiciels-en-langage-c/)
* [Programming Rules to Develop Secure Applications With Rust, ANSSI](https://www.ssi.gouv.fr/en/guide/programming-rules-to-develop-secure-applications-with-rust/)
* [Python Security Best Practices Cheat Sheet, Feb 2019](https://snyk.io/blog/python-security-best-practices-cheat-sheet/)
* [Worrying about the NPM ecosystem, Jun 2020](https://sambleckley.com/writing/npm.html)

On folder structure

* Please respect operating system file hierarchy (Unix or Windows): global config, user config, data files, logs files, temporary/cache files...
  * This supports File Integrity Monitoring and avoid extra rules per application

Web page

* [GitHub’s CSP journey, Apr 2016](https://github.blog/2016-04-12-githubs-csp-journey/)
* [GitHub’s post-CSP journey, Jan 2017](https://github.blog/2017-01-19-githubs-post-csp-journey/)
* [Security Headers](https://securityheaders.com)
* Certificates
  * [SSL Certificate Validity Will Be Limited to One Year by Apple’s Safari Browser, Feb 2020](https://www.thesslstore.com/blog/ssl-certificate-validity-will-be-limited-to-one-year-by-apples-safari-browser/)
  * [Reducing TLS Certificate Lifespans to 398 Days, Jul 2020](https://blog.mozilla.org/security/2020/07/09/reducing-tls-certificate-lifespans-to-398-days/)
  * [Avoid wildcard certificates, NIST](https://csrc.nist.gov/CSRC/media/Projects/Computer-Security-Objects-Register/documents/ACES-CP-v3-2_signed_05122017.pdf) p27 (SC-12)
* .well-known
  * security.txt
  * change-passwd. https://web.dev/change-password-url/
* Error code and pages
  * provide meaningful errors message, especially to say if issue is user input, client-side, network-related or server
  * provide a troubleshooting id that user can report to support for easy troubleshooting
  * don't display verbose errors to users in production

Cookies

...

SQL/Database

* Ensure SQL backend is only accessible to approved systems, usually frontend and jumphosts. Never Internet facing or customer facing. Network segmentation.
* Enforce Stored Procedures with defined pattern (meaning deny direct sql statements for most users). easier maintain and easier to monitor. CIS SQL 6.1. also help input validation
* Avoid generic user, dbo and sysdba roles for all day2day activities. Identity segmentation by role privileges (if only read-only, if dbo, if backup…)
* Ensure diagnostics settings well configured included audit and errors logs
* Share database schema with security team
* [Top 10 Oracle Steps to a Secure Oracle Database Server, Mar 2012](https://blog.opensecurityresearch.com/2012/03/top-10-oracle-steps-to-secure-oracle.html)

Server

* Isolate with systemd and seccomp, cgroups, namespaces, selinux/apparmor

Documentation

* Have a security section:
  * default security settings, what can create issue, what can be pushed further if high risk
  * firewall/domain rules aka network matrix: all network settings required to pass a firewall or proxy or a browser content-security-policy
  * identity matrix: used account and least required privileges
  * known process, scheduled tasks, if use of external tools, scripting
