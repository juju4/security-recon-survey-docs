
## General

* project goal
* project owner
* resources
* importance
* confidentiality

Ideally, security can establish a threat model on project based on informations provided.

## Technology

* dependence check. any End-Of-Life(EOL) or near-EOL dependency.
    * be especially careful on crypto choice
    * review libraries usage, most notably authentication, cryptography, logging
* any continuous integration support? (automation, API...)
* security review
    * security awareness of developers (OWASP, crypto...)
    * plan for code review and pentest

## References

On Application security program

* [OWASP Application Security Verification Standard Project](https://www.owasp.org/index.php/Category:OWASP_Application_Security_Verification_Standard_Project)
* [Building Security In Maturity Model](https://www.bsimm.com/)
* [Application Security and Development Checklist, STIG Viewer](https://www.stigviewer.com/stig/application_security_and_development_checklist/)

On Threat modeling

* [Docker Security at PyCon: Threat Modeling & State Machines, May 2017](https://blog.docker.com/2017/05/docker-security-pycon-threat-modeling-state-machines/)
* [Threat Modeling Toolkit, May 2017](https://speakerdeck.com/owaspmontreal/threat-modeling-toolkit)
* [If Attackers Can Use Graphs, Then Why Can’t We? Apr 2017](https://t2.fi/2017/04/11/if-attackers-can-use-graphs/)
* [Adversarial Tactics, Techniques & Common Knowledge, US Mitre](https://attack.mitre.org/wiki/Main_Page)

On API

* [API-Security-Checklist, GitHub](https://github.com/shieldfy/API-Security-Checklist)
