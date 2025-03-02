
## Questions

* maintained, regularly updated?
* dependencies/libraries updated
    * OWASP Dependency Checker
    * Github dependabot
* maturity of the project e.g.  https://www.openhub.net/
* Check for open issues on Github and activity in the community
* does not need admin rights or excessive privileges
* Compiled 64 bits, security flags
* Allowed Licenses
* Documentation
    * Domain, Firewall rules for end-user, privileged application users and platform administrators
    * Hardening
    * Monitoring recommendations (Operations, Security Operations): logs format, structure, alerts

## Tools

* [Microsoft Application Inspector](https://github.com/microsoft/ApplicationInspector)
* [Microsoft ACT](https://docs.microsoft.com/en-us/windows/deployment/planning/act-technical-reference)
* [Standard User Analyzer (SUA) to test your applications and monitor API calls to detect compatibility issues related to the User Account Control (UAC) feature in Windows](https://docs.microsoft.com/en-us/windows/deployment/planning/sua-users-guide)

* [Crxcavator for Chrome Extension](https://crxcavator.io/)

* Security Sandbox
  * Chrome, https://blog.chromium.org/2008/10/new-approach-to-browser-security-google.html, https://chromium.googlesource.com/chromium/src/+/master/docs/design/sandbox.md
  * Mozilla, https://wiki.mozilla.org/Security/Sandbox

* [Robber is open source tool for finding executables prone to DLL hijacking https://mojtabatajik.github.io/Robber/](https://github.com/MojtabaTajik/Robber)

## References

* [advisory-board-open] Reviewing third party Python modules, Jan 2020
* [Security Best Practices for C++, 2018](https://docs.microsoft.com/en-us/cpp/security/security-best-practices-for-cpp?view=vs-2019)
* GCC Compiler security options and flags:
  * Gentoo: https://wiki.gentoo.org/wiki/Hardened_Gentoo#Per_package_hardening_settings
    https://wiki.gentoo.org/wiki/Hardened/FAQ#Do_I_need_to_pass_any_flags_to_LDFLAGS.2FCFLAGS_in_order_to_turn_on_hardened_building.3F
  * [Recommended compiler and linker flags for GCC, RedHat, Mar 2018](https://developers.redhat.com/blog/2018/03/21/compiler-and-linker-flags-gcc/)
  * [Debian Hardening](https://wiki.debian.org/Hardening)
    https://wiki.debian.org/HardeningWalkthrough
  * [Enable Compiler Security hardening flags by default in GCC, Fedora](https://fedoraproject.org/wiki/Changes/HardenedCompiler)
  * [OpenBSD-specific behavior of LLVM/clang](https://man.openbsd.org/clang-local.1)
  * https://gist.github.com/jrelo/f5c976fdc602688a0fd40288fde6d886
  * https://gist.github.com/shekkbuilder/5c776d1f84913cc45c1a
  * Linux: [Signing ELF binaries](https://lwn.net/Articles/532778/)
* [ Memory safetyThe Chromium project finds that around 70% of our serious security bugs are memory safety problems. Our next major project is to prevent such bugs at source. May 2020](https://www.chromium.org/Home/chromium-security/memory-safety)
* [rabin2](https://r2wiki.readthedocs.io/en/latest/tools/rabin2/)
* [Good discussion but hard for twitter :)There is public data on mitigation effectiveness over time. /GS & EH hardening, browser UAF mitigations, and uninit memory mitigations are examples of durable mitigation value IMO.A few of years old, but see this](https://twitter.com/epakskape/status/1462188018752794641)
* [WOOT19 - Trends and challenges in vulnerability mitigation](https://github.com/microsoft/MSRC-Security-Research/blob/master/presentations/2019_08_WOOT/WOOT19%20-%20Trends%20and%20challenges%20in%20vulnerability%20mitigation.pdf)

* https://www.sans.org/security-awareness-training/resources/posters/securing-web-applications-poster
https://software-security.sans.org/resources/swat
https://www.sans.org/security-resources/posters/cloud/cloud-security-devsecops-practices-200
https://www.sans.org/security-resources/posters/cloud-security-devsecops-practices/200/download

* [Rules for secure C language software development, ANSSI - English](https://www.ssi.gouv.fr/en/guide/rules-for-secure-c-language-software-development/), [Règles de programmation pour le développement sécurisé de logiciels en langage C, ANSSI - FRENCH](https://www.ssi.gouv.fr/guide/regles-de-programmation-pour-le-developpement-securise-de-logiciels-en-langage-c/)

* [NISTIR 8276 - Key Practices in Cyber Supply Chain Risk Management: Observations from Industry, Feb 2021](https://csrc.nist.gov/publications/detail/nistir/8276/final)

* SBOM
  * [Preventing Supply Chain Attacks like SolarWinds, Jan 2021](https://www.linuxfoundation.org/blog/blog/preventing-supply-chain-attacks-like-solarwinds)
  * [Microsoft open sources its software bill of materials (SBOM) generation tool, Jun 2022](https://devblogs.microsoft.com/engineering-at-microsoft/microsoft-open-sources-software-bill-of-materials-sbom-generation-tool/)

* [Let's talk about a pet peeve of mine: companies hiding their technical documentation behind login walls. 📚, Dec 2024](https://www.linkedin.com/posts/mayakaczorowski_91-docs-conversion-trick-team-level-activity-7270136707197353984-61RZ)
