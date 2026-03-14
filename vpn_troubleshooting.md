How to Troubleshoot Remote VPN Connectivity Issues

Overview

This guide provides a step-by-step workflow for technical support staff to resolve common VPN connection failures for remote employees.

Prerequisites

Access to the VPN Gateway/Firewall logs (e.g., AWS Client VPN or Cisco AnyConnect).

End-user device (Windows/macOS).

Step-by-Step Instructions

1. Basic Connectivity Check

Ask the user to verify their local internet connection:

Run a ping test: ping google.com

Check speed: Ensure at least 5Mbps for a stable tunnel.

2. DNS Flush

Often, cached DNS records prevent the VPN client from resolving the gateway address.

Windows: Open CMD as Admin and type ipconfig /flushdns.

macOS: Type sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder.

3. Client Software Verification

Ensure the VPN client is updated to the latest version.

Verify if the user is using the correct Profile/Gateway URL.

4. Credential & MFA Reset

Check the Active Directory/Identity Provider for locked accounts.

Sync the MFA token if the user reports "Authentication Failed" despite having the correct password.

5. Advanced: MTU Issues

If the VPN connects but the user cannot access specific internal tools:

Lower the MTU size on the virtual adapter to 1350 to avoid packet fragmentation over home ISP networks.

Created by Christopher Castillo - Senior Infrastructure Specialist
