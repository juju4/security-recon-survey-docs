
I'm looking for recommendations or templates to help formalize a policy + standard on domain managementThere are multiple aspects that I want to address
1. Brand/marketing
2. IT operations
3. Security operations

At a high level:

# Brand/marketing

Depending on marketing strategy, I think a limited number of top level domains should be targeted and that the rest should be subdomains or subdirectories of those.Eventually, some extra less important tld with redirection to strategic brands, like for special event.
Critical top level domains should be registered on the main targeted gTLDs and ccTLDs.Without strategy here, risk is to create tons of dns increasing the difficulty of managing and protecting them vs increasing attack surface.
Like in real life, established/aged domain is more trusted than new ones.
Using per customer domain or subdomain means disclosing customer list to public which may be desirable or not.

## M&A
During Day0, Brand/Marketing should identified if want to keep part/all domains or transition them. Transition would be usually 6 to 12 months depending on brand.
Registration information should be updated ASAP.Transitioned/deprecated domains should over time redirected to corresponding new brands subdomain or subdirectory pages. Even after deactivation, ownership should be retain an extra grace time to avoid fraud.

# IT Operations
need a limited number of domain providers carefully managed and centrally (admin with 2FA), well monitored, domain lock transfer and with good whois information (identified contacts brand@/marketing@, noc@, abuse@/security@).IMHO, use of proxy/anonymizer domain service by a public company should be avoided.Outside of individual protection, this is more a bullet-proof hosting usage.Domain provider should provide automation mechanisms (ACME) as much as possible, and ensure service redundancy (both geography and ASN).
Domain inventory should be regularly refreshed and ensure internal contact/owner identifiedLab/Staging environments should be clearly identified as such, usually as a subdomain.Internal systems should also be clearly identified, usually with a subdomain too.Domain delegation should be done only for subdomain with provider of same service level.
It's recommended to avoid differentiate domain for usage (customer, admin, monitoring) and more to differentiate after authentication based on credentials.
Example in Azure context: have a single entry point with App Gateway managing authentication and based on authorization, send to appropriate interface (end-user, admin, monitoring...)
Outside of tier boundaries (prod likely default, staging/qa, lab/dev), you may want to have subdomains identified per functions (static, cdn...)

## Certificates
Contacts should include brand@, noc@, abuse@
Wildcard certificates usage should be avoided for top-level domains.
Internal systems should use internal CA and not a public one.
Duration should be 1y maximum. Recommended to automate renewal every 3 months.

## Email
Email services number should be as limited as possible and ideally use a single platform carefully maintained both from an IT and Security perspective, including industry-standards SPF, DKIM, DMARC

MX to 0 in your DNS if not used. See references.
To be exhaustive add a TXT entry and a DMARC p=reject

## Web server
Ensure security.txt is used and point to appropriate reference ideally on the main corporate public website.

## Azure AD
Should lab/staging environment be in same or different tenant than production? For on-premise AD, I would tend to go to a different one with one-direction trust but not sure for Azure AD.

## Windows Domain

[Active Directory Shadow Group Script  will let you spend less time on updating group memberships, 2010](https://www.sole.dk/active-directory-shadow-group-script-will-let-you-spend-less-time-on-updating-group-memberships/)

# Security operations

Critical list of top domains, regularly refreshed should be monitored for change (whois/website), typosquatting names (like dnstwist) and certificates (with certificate transparency)

Dynamic domains are often associated to malware fast flux.
Newly seen domains: if for production usage should be tested before golive and IT+Security notified early for for validation (3-7d+), eventually temporary manually allowed if emergency.for lab/staging environment with identified subdomain, they can be added to ignore list.


## References

* Newly seen/observed domains
https://support.umbrella.com/hc/en-us/articles/235911828-Newly-Seen-Domains-Security-Category
https://www.farsightsecurity.com/solutions/threat-intelligence-team/newly-observed-domains/
* Browsers restricting certificate to 1 year.
[Maximum HTTPS certificate lifetime to be 1 year soon, Feb 2020](https://www.michalspacek.com/maximum-https-certificate-lifetime-to-be-1-year-soon)
[Chrome joins Apple in limiting public TLS certificates to 398 days starting Sept 1st. Jun 2020](https://twitter.com/chosensecurity/status/1270819404452937729)

* Services with or without customer portal
Without:
O365 Mail, Onedrive
Gmail, Google drive (unless business domain)
Dropbox

With
O365 Sharepoint
File Sharing Sharefile, Box

* [RFC7505 Means Yes, Your Domain Can Refuse to Handle Mail. Please Leave Us a TXT If You Do. Feb 2021](https://bsdly.blogspot.com/2021/02/rfc7505-means-yes-your-domain-can.html)

* What TLD to use for internal? public-facing owned domain, not .local, .home, .lan. .int.example.com
  * [Reserved Top Level DNS Names, RFC2606](https://datatracker.ietf.org/doc/html/rfc2606): .test, .example, .invalid, .localhost, example.com, example.net, example.org; [Private DNS Namespaces, RFC6762](https://www.rfc-editor.org/rfc/rfc6762#appendix-G): .intranet, .internal, .private, .corp, .home, .lan
  * [Approved Resolutions | Special Meeting of the ICANN Board | 29 July 2024: Reserving .INTERNAL for Private-Use Applications](https://www.icann.org/en/board-activities-and-meetings/materials/approved-resolutions-special-meeting-of-the-icann-board-29-07-2024-en#section2.a)
  * [Active Directory: Best Practices for Internal Domain and Network Names](https://learn.microsoft.com/en-us/archive/technet-wiki/34981.active-directory-best-practices-for-internal-domain-and-network-names): "Microsoft strongly suggests to work with subdomains, within a publicly registered TLD domain", [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://learn.microsoft.com/en-us/troubleshoot/windows-server/active-directory/naming-conventions-for-computer-domain-site-ou)
  * [Active Directory Naming FAQ, Samba](https://wiki.samba.org/index.php/Active_Directory_Naming_FAQ)
  * [What domain name do you use for your homelab services ? Jun 2022](https://www.reddit.com/r/homelab/comments/vlmzc0/what_domain_name_do_you_use_for_your_homelab/), [Simplified Home Lab Domain Name Resolution, Aug 2021](https://enterpriseadmins.org/blog/lab-infrastructure/simplified-home-lab-domain-name-resolution/),
