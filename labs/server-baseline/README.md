# Windows Server Lab Baseline

## Overview

Established a Windows Server lab environment to provide a reusable foundation for administration, automation, networking, and security exercises.

The baseline focused on secure administrative access, initial system configuration, network validation, and documentation of the environment before additional server roles and services were introduced.

## Work Completed

- Provisioned a Windows Server virtual machine
- Established Remote Desktop administrative access
- Restricted Remote Desktop traffic to an authorized source
- Configured the Remote Desktop Protocol service on TCP port `3389`
- Associated a persistent public address with the server using an Elastic IP
- Renamed the server using a standardized lab naming convention
- Created a separate local user account
- Verified basic network connectivity
- Reviewed the initial server configuration
- Established a known baseline for future configuration changes

## Networking and Remote Access

Remote administration was performed using Remote Desktop Protocol (RDP).

The environment was configured to allow:

Protocol: TCP
Port: 3389
Service: Remote Desktop Protocol
Inbound access was restricted to an authorized source rather than allowing unrestricted Internet access.
A cloud Elastic IP was associated with the server to provide a persistent public endpoint for remote administration. This prevented the server's public address from changing between stop/start cycles and allowed the existing RDP configuration to remain consistent.
For public documentation, the actual address is intentionally omitted.
Example:
Public Endpoint: <ELASTIC-IP>
RDP: TCP/3389
Source: Authorized administrative network only
Security Considerations
Remote administrative access was restricted rather than exposed broadly.
The RDP security rule was limited to an authorized source instead of:
0.0.0.0/0
This reduced unnecessary exposure of the Remote Desktop service.
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
Validation
The baseline was considered complete after:
- the server successfully booted
- administrative access was confirmed
- RDP connectivity over TCP 3389 was verified
- the Elastic IP remained associated with the server
- remote access restrictions were validated
- network connectivity was verified
- initial system configuration was reviewed
Skills Demonstrated
- Windows Server administration
- Cloud-hosted virtual machine deployment
- Remote Desktop administration
- Elastic IP configuration
- TCP port and protocol configuration
- Network access control
- Basic network validation
- Secure infrastructure documentation
