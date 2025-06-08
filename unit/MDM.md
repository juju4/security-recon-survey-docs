
Recommended settings for Mobile Device Management (MDM) tool

# Features

* Device Enrollment Program (DEP)

* hostname consistent pattern (ex: location-type-identifier)
* Disk encryption+key escrow
* Screen Locking
* Enforce security update (system, apps) + report deviation
* Control major update compatibility
* Enforce security software presence (Google Santa, osquery, EDR...)
* Remote wipe
* BIOS/UEFI password
* Browser policies (Chrome, Firefox)
* Office, auto-signin (mail+delegated mailbox, online disk, chat...)
* Software distribution (self-service) ~ 80% common software
* Driver distribution including printers

* Dev/Tech profile and Non-Tech (with or without admin rights, allow non-appstore apps...)

# Benefits

* fast imaging and rebuild
* standardization, uniformity
* self-service
* security

# References

* [MacAdmins Documentation](https://macadminsdoc.readthedocs.io/en/master/)
* [Jamf Pro Administrator's Guide > Managing Computers Settings and Security Management for Computers](https://docs.jamf.com/10.25.0/jamf-pro/administrator-guide/Settings_and_Security_Management_for_Computers.html)
* [collection of extension attributes and scripts intended for managing Mac workstations via Jamf Pro](https://github.com/palantir/jamf-pro-scripts/tree/master/scripts)
* [macOS settings to mark devices as compliant or not compliant using Intune](https://docs.microsoft.com/en-us/mem/intune/protect/compliance-policy-create-mac-os)
* [Windows 10 and later settings to mark devices as compliant or not compliant using Intune](https://docs.microsoft.com/en-us/mem/intune/protect/compliance-policy-create-windows)
* [Windows MDM security baseline settings for Intune](https://docs.microsoft.com/en-us/mem/intune/protect/security-baseline-settings-mdm-all)

* [Choosing a Name for Your Computer, IETF RFC1178](https://tools.ietf.org/html/rfc1178)
* [What are the issues you have seen with an on-prem Active Directory forest that uses .local as the TLD?Extra points for corner cases and crazy integration issues.tagging in @NerdPyle, @markmorow, @JosephRyanRies, Dec 2020](https://twitter.com/PyroTek3/status/1334932694136987657)

Alternate remote wipe tools
* MDM: Microsoft intune, MaaS360, Hexnode, SimpleMDM
* [Absolute](https://www.absolute.com/)

Linux
  * https://blog.1password.com/no-mdm-for-linux/  = eam/osquery-based solution, no public pricing
  * https://www.pomerium.com/blog/best-open-source-mobile-device-management-mdm-solutions
  * https://www.reddit.com/r/sysadmin/comments/d6g488/mdm_for_linux_devices/
  * https://scalefusion.com/pricing#uem 2-6$/device/month
  * https://fleetdm.com/pricing 0-7$-custom/device/month
  * https://jumpcloud.com/pricing 9-24$/user/month
  * https://www.42gears.com/pricing/mobile-device-management/ 4-8$/device/month
  * https://www.miradore.com/plans-pricing/ 0-4$/device/month
