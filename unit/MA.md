
Merge&Acquisition process is an important step in a life of a company, being acquired or acquiring another.
IT and Security must be reviewed before and after to ensure that assets are protected and that integration can be done smoothly.

Special related case if you spin-off or sell a unit. In this case, ideally, you want attached systems to be already segmented in your network so connection with new environment is limited to targeted unit and possibly allowing third-party access those internal systems until they are fully separated. Plan also transition of identity, storage and system image to reflect new licensing and environment, how you transfer security, monitoring and compliance to new team.

## Course of Action

* Identify deal driver
* Build relationship with the other team
    * Staff interviews: current state, technical debt, how it was x years ago, what should be addressed...
* Data collection and planning
    * Inventory of assets (hardware, software, process)
    * Policies, Main process like Business Continuity or Incident Response
    * Standard systems image, os, version. non-standard & legacy.
    * Commonalities and differences
* Identify existing problems, how affected by M&A and if a fix is mandatory before or after.
* Management Requirements for day one and first 6 months
* Possible liabilities (past incidents, non-compliance...)
    * processes and procedures regarding information security like acceptable use of data, data classification, and data handling
    * evaluate compliance with cyber security frameworks from NIST, CIS, ISO...
* Legal aspects: contracts, NDA, privacy statement...
    * identify non-transferable agreements and contracts after acquisition
    * recognize them as is
    * review, renegotiate...
* Integration path: from beginning to end
    * HR
    * Finance
    * Sales
    * Email (migrate, forward), calendar, File Sharing (internal/external/support...)
    * Domains (update whois, web/brand tag-redirection)
    * Network, VPN/Remote access
* incident-response strategy in case of issue during deal period
    * Contacts, Communication channels
    * Tabletop
* misc: insurance, VIP management, building facilities management...

## Technicalities

* Ask results of their latest audit, VAscan, compromise assessment... Or do one. Decide if this should be done internally or externally.
* Use a security sensor or agents in their network to map it and check their documentation.
* Get and compare some process like patch management, change management, administrator rights approval.
* For privileged accounts, probably better to restart everyone as standard user and revalidate current requirements
* For generic and service accounts, ensure they are required or disable them and rotate all secrets associated.
* Identify what will be integrated into final network, what need to be rebuild, what use your architecture or what will be left out or kept in a segmented network zone.
* Pay attention to Identity and Access Management to keep best of both worlds, especially on Multi-Factor-Authentication tools.
* Have troubleshooting tool in place when migrating services
* Transition public contacts: sales, HR and other might be changed or not but from an IT and security side, you should quickly reclaim domain whois, network whois and any public security contacts (security web page, security.txt...). That should also include private groups (mailing-list, ISACs...).
* Domains and Certificates
    * Identify scope early
    * Update ownership ASAP (whois+contact, brand name+contact in certificates)
* To join/remove computer to/from domain, use least privilege and avoid Domain administrator use
    * either dedicated account with delegation to Create or Delete Computer objects
    * either local admin rights on corresponding systems
* BCP

## Split case

* Identify common infrastructure
    * Clients
    * Servers
    * Security systems: tools consoles, logging, vulnerability scans...
    * any system in expected network zone
* Can link be sever remotely in advance of a local uninstall?
* Double-check that nothing reports anymore in other party tools before due date

## References

* [PinnacleOne ExecBrief | The Hidden Cyber Risks of Mergers & Acquisitions, Mar 2025](https://www.sentinelone.com/blog/pinnacleone-execbrief-the-hidden-cyber-risks-of-mergers-acquisitions/)
* [Threat Hunting For Cybersecurity M&A Due Diligence, Mar 2020](https://blog.renditioninfosec.com/downloads/20200306_BSidesNOVA_MA_Due_Diligence.pdf)
* [Bring identities from disconnected ADs into Azure AD with just a few clicks! Dec 2019](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/bring-identities-from-disconnected-ads-into-azure-ad-with-just-a/ba-p/827835)
* [Don’t Acquire a Company Until You Evaluate Its Data Security, Apr 2019](https://hbr.org/2019/04/dont-acquire-a-company-until-you-evaluate-its-data-security)
* [Merging Companies, Merging Clouds, Apr 2019](https://www.darkreading.com/cloud/merging-companies-merging-clouds/a/d-id/1334314)
* [When cyber threatens M&A, 2018](https://www.pwc.com/us/en/deals/publications/assets/pwc-when-cyber-threatens-m-and-a.pdf)
* [M&A activity can open doors to cyber threats, Aug 2017](http://ameinfo.com/technology/it/alert-ma-activity-can-open-doors-cyber-threats/)
* [Mergers, Acquisitions and Information Security Aspects, Mar 2017](https://www.sans.edu/downloads/Merger-and-Acquisition-Group-Project.pdf)
* [Top Ten Issues with Active Directory Trusts and Corporate Mergers, Feb 2017](https://blogs.technet.microsoft.com/askpfeplat/2017/02/13/top-ten-issues-with-active-directory-trusts-and-corporate-mergers/)
* [Cybersecurity Diligence in M&A Transactions, Oct 2016](https://cooleyma.com/2016/10/26/cybersecurity-diligence-in-ma-transactions-lessons-from-verizonyahoo/)
* [Making cybersecurity a priority in mergers and acquisitions: integration, Aug 2016](http://www.cio.com/article/3105276/mergers-acquisitions/making-cybersecurity-a-priority-in-mergers-and-acquisitions-integration.html)
* [Identifying and Mitigating IT Security Risks in a Merger or Acquisition, Geek Week 2015 Conference](http://www.isaca.org/chapters3/Atlanta/AboutOurChapter/Documents/GW2015/081015-1PM-IdentifyandMitigatingITSecurityRisks-Acquisition.pdf)
* [Top Ten Key Privacy and Security Due Diligence Requests for Mergers and Acquisitions, Sep 2013](https://www.lexisnexis.com/communities/corporatecounselnewsletter/b/newsletter/archive/2013/09/02/top-ten-key-privacy-and-security-due-diligence-requests-for-mergers-and-acquisitions.aspx)
* [Cyber Security M&A Decoding deals in the global Cyber Security industry, Nov 2011](https://www.pwc.com/gx/en/aerospace-defence/pdf/cyber-security-mergers-acquisitions.pdf)
* [Information Security in Mergers & Acquisitions, Blackhat 2004](https://www.blackhat.com/html/bh-media-archives/bh-archives-2004.html), [Youtube](https://www.youtube.com/watch?v=AKrMvsbkEgY)
* [Security Considerations in the Merger/Acquisition Process, SANS Reading Room, Aug 2001](https://www.sans.org/reading-room/whitepapers/casestudies/security-considerations-merger-acquisition-process-)

* [Active Directory administrative tier model](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access-reference-material)
* [Implementing Least-Privilege Administrative Models](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/implementing-least-privilege-administrative-models)
* [How to Grant Rights to be able to Manage Computer Accounts using the Provisioning Services Console](https://support.citrix.com/article/CTX121201)

* [Microsoft-backed AI startup chatbots revealed to be human employees, Jun 2025](https://mashable.com/article/microsoft-backed-ai-startup-chatbot-human-employees)
