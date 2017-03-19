
Objective vendor assessment is always complicated. Internal politics are not often aligned with technical recommendation.
Whatever final choice, initial work should allow appropriate security level.

## General

* Identify security, legal and communication contacts with path for escalation. (business hours or not)
* Review interactions with other customers, partners and security community.
* Review external assessments, be it private or public (pentest, certification, whitepaper...).
* Exchange security policy and incident response process.
* Which data and access are shared, how, where and how long? any sub-contractors? regulated data?

## For any hardware or software vendor

* Can we change all passwords? can access be managed from a directory?
* What is the patching process? How regularly do you issue patch?
* Will you do remote support? what are the rules of engagement and how do you authenticate and audit access? How to revoke access?
    * an inventory of persons and systems communicating between each other is recommended even if often hard
* Can it be managed in a continuous integration manner? (orchestration tool support, automated testing, API...)
* Does it support up-to-date administration channels? (SSHv2, TLSv1.2-1.3, NTP, Syslog+TLS...)
* Do you have a Secure Development Life Cycle or SDLC? which methodologies? what kind of testing? Do your developpers are trained or certified on security?

## References

* [Information Security Assessment RFP Cheat Sheet](https://zeltser.com/security-assessment-rfp-cheat-sheet/)
* [Questions to Ask Your Security Vendor, Sep 2009](http://bhconsulting.ie/securitywatch/?p=768)
* [SECURITY QUESTIONS TO ASK YOUR VENDOR, May 2010](http://webcache.googleusercontent.com/search?q=cache%3Ahttp%3A%2F%2Fwww.cpni.gov.uk%2FDocuments%2FPublications%2F2010%2F2010022-Vendor_security_questions.pdf&oq=cache%3Ahttp%3A%2F%2Fwww.cpni.gov.uk%2FDocuments%2FPublications%2F2010%2F2010022-Vendor_security_questions.pdf)
* [Top Data Protection Questions I Would Ask Your Vendors in 2014, Jan 2014](http://www.goironbox.com/data-protection-questions-ask-vendors-2014/)
* [Are your third-party vendors leaving the door open to hackers? Jun 2014](http://www.net-security.org/article.php?id=2055)
* [Increasing Security Throughout the Network: Five Questions to Ask Your MSSP](https://www.arbornetworks.com/images/documents/Arbor%20Insights/AI_5Questions_EN2013.pdf)

