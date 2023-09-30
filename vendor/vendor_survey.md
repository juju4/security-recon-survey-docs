
Objective vendor assessment is always complicated. Internal politics are not often aligned with technical recommendation.
Whatever final choice, initial work should allow appropriate security level.

## General

* Identify security, legal and communication contacts with path for escalation. (business hours or not)
* Mutual Information Sharing conditions for major incident or threat which can impact both
* Review interactions with other customers, partners and security community.
* Review external assessments, be it private or public (pentest, certification, whitepaper...).
* Exchange security policy and incident response process.
* Which data and access are shared, how, where and how long? any sub-contractors? regulated data?
* Recent exec summary of pentest, audit, certifications, cyberinsurance coverage

## For any hardware or software vendor

* Can we change all passwords? can access be managed from a directory?
* What is the patching process? How regularly do you issue patch? SLA?
* Will you do remote support? what are the rules of engagement and how do you authenticate and audit access? How to revoke access?
    * an inventory of persons and systems communicating between each other is recommended even if often hard
* Can it be managed in a continuous integration manner? (orchestration tool support, automated testing, API...)
* Does it support up-to-date administration channels? (SSHv2, TLSv1.2-1.3, NTP, Syslog+TLS...)
* Do you have a Secure Development Life Cycle or SDLC? which methodologies? what kind of testing? Do your developpers are trained or certified on security?

## References

* [My questions as a customer are things like:- How did it happen?- When did it happen?- What steps are being put in place to stop the issue happening again? - Fortinet SSL VPN, Aug 2019](https://twitter.com/GossiTheDog/status/1166763800609153025)
* [Towards better vendor security assessments, Mar 2019](https://blogs.dropbox.com/tech/2019/03/towards-better-vendor-security-assessments/), [Vendor Security Model Contract](https://github.com/dropbox/vsmc)
* [Google VSAQ, Vendor Security Assessment Questionnaire](https://security.googleblog.com/2016/03/scalable-vendor-security-reviews.html)
* [Information Security Assessment RFP Cheat Sheet](https://zeltser.com/security-assessment-rfp-cheat-sheet/)
* [Questions to Ask Your Security Vendor, Sep 2009](http://bhconsulting.ie/securitywatch/?p=768)
* [SECURITY QUESTIONS TO ASK YOUR VENDOR, May 2010](http://webcache.googleusercontent.com/search?q=cache%3Ahttp%3A%2F%2Fwww.cpni.gov.uk%2FDocuments%2FPublications%2F2010%2F2010022-Vendor_security_questions.pdf&oq=cache%3Ahttp%3A%2F%2Fwww.cpni.gov.uk%2FDocuments%2FPublications%2F2010%2F2010022-Vendor_security_questions.pdf)
* [Top Data Protection Questions I Would Ask Your Vendors in 2014, Jan 2014](http://www.goironbox.com/data-protection-questions-ask-vendors-2014/)
* [Are your third-party vendors leaving the door open to hackers? Jun 2014](http://www.net-security.org/article.php?id=2055)
* [Virginia Tech Security Questions for Technology - Based Procurements](https://itpals.vt.edu/content/dam/itpals_vt_edu/newitasitedocs/it-procurement/it_security_questionnaire2.pdf)
* [Securing the supply chain with risk-based assessments, Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=56359)
* [Standardized Information Gathering (SIG) questionnaire](https://sharedassessments.org/sig/)
* BGP Security: [MANRS: Mutually Agreed Norms for Routing Security](https://www.internetsociety.org/issues/manrs/), [Expanding our commitment to secure Internet routing, Google, Dec 2020](https://cloud.google.com/blog/products/networking/how-google-is-working-to-improve-internet-routing-security), [Unwanted Traffic RemovalService (UTRS)](https://team-cymru.com/community-services/utrs/)
* [Consensus Assessment Initiative Questionnaire (CAIQ) v3.1 - CSA](https://cloudsecurityalliance.org/artifacts/consensus-assessments-initiative-questionnaire-v3-1/)
* [Minimum Viable Secure Product](https://mvsp.dev) - based on Dropbox VSMC and Google VSAQ
