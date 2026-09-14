# Active Directory Domain Environment

## Overview

Built a small Windows Server domain environment using two cloud-hosted Windows Server systems.

The original server was promoted to a domain controller and used to create a new Active Directory forest and domain. A second Windows Server was then configured to use the domain controller for DNS and joined to the domain.

## Work Completed

- Deployed a second Windows Server 2019 instance
- Renamed the second server using a consistent naming convention
- Installed Active Directory Domain Services on the primary server
- Promoted the primary server to a domain controller
- Created a new Active Directory forest and domain
- Installed and configured DNS with Active Directory
- Configured the second server to use the domain controller for DNS
- Updated cloud firewall rules to permit secure server-to-server communication
- Joined the second Windows Server to the domain
- Created a standard domain user account
- Created a separate privileged administrative account
- Added the administrative account to the `Domain Admins` group
- Created Organizational Units for standard and administrative users
- Moved user accounts into the appropriate OUs

## Architecture


  
              Active Directory Domain
                    example.internal
                           |
              +------------+------------+
              |                         |
         LAB-DC-01                  LAB-SRV-02
      Domain Controller            Domain Member
      DNS / AD DS                  Windows Server
              |
       Active Directory
              |
       +------+------+
       |             |
    Standard Users  Administrators

##DNS and Domain Communication

Active Directory depends heavily on DNS.
The domain member server was configured to use the domain controller's private address as its preferred DNS server.
Before the DNS configuration was corrected, domain name resolution failed because the server was still using the cloud provider's default DNS resolver.
After updating DNS and allowing traffic between the two server security groups, domain resolution succeeded and the second server was able to join the domain.

## Security Configuration
Server-to-server Active Directory traffic was not exposed publicly.
Instead, the domain controller's cloud firewall was configured to allow traffic originating from the security group assigned to the second Windows Server.
Remote Desktop access remained separately restricted to the authorized administrative source.
Privileged access was also separated by creating:
- a standard user account for normal use
- a separate administrative account
- explicit membership in the Domain Admins group only for the administrative identity

## Organizational Structure
Two Organizational Units were created:
Standard Users
Administrators
Standard accounts were placed in the Standard Users OU, while the privileged administrative account was placed in the Administrators OU.
This provides a cleaner directory structure and creates a foundation for applying different Group Policies later.

## Validation
The environment was considered successfully configured after:
- the domain controller reported membership in the new domain
- Active Directory Users and Computers displayed the domain
- DNS resolution succeeded from the second server
- the second server successfully joined the domain
- the standard user account appeared in Active Directory
- the administrative account appeared in the Domain Admins membership list
- both custom Organizational Units contained the expected accounts
  
## Skills Demonstrated
- Windows Server administration
- Active Directory Domain Services
- Domain controller deployment
- DNS configuration
- Active Directory forests and domains
- Domain joining
- Organizational Units
- Identity and access management
- Privileged account separation
- Security group configuration
- Windows Server networking
- Active Directory troubleshooting
