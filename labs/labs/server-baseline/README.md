# Windows Server Lab Baseline

## Overview

Established a Windows Server lab environment to provide a reusable foundation for administration, automation, networking, and security exercises.

The baseline focused on secure administrative access, initial system configuration, network validation, and documentation of the environment before additional server roles and services were introduced.

## Work Completed

- Provisioned a Windows Server virtual machine
- Established Remote Desktop administrative access
- Configured the Remote Desktop Protocol service on TCP port `3389`
- Associated a persistent public address with the server using an Elastic IP
- Renamed the server using a standardized lab naming convention
- Created a separate local user account
- Verified basic network connectivity
- Reviewed the initial server configuration
- Established a known baseline for future configuration changes

## Security Considerations

Remote administrative access was restricted rather than exposed broadly.

Public documentation intentionally omits:

- IP addresses
- cloud instance identifiers
- security group identifiers
- private DNS information
- real hostnames
- usernames
- credentials
- private keys

Generic identifiers are used throughout the repository where infrastructure examples are required.

## Validation

The baseline was considered complete after:

- the server successfully booted
- administrative access was confirmed
- network connectivity was verified
- remote access restrictions were validated
- initial system configuration was reviewed

## Skills Demonstrated

- Windows Server administration
- Cloud-hosted virtual machine deployment
- Remote Desktop administration
- Basic network validation
- Access control
- Secure infrastructure documentation
