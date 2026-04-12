## Step 01 — Network Configuration (DC01)

Configured dual network adapters in VirtualBox to simulate an enterprise environment.

- Adapter 1 (NAT): Provides internet access
- Adapter 2 (Host-Only): Internal network for domain communication

Assigned a static IP address to the internal adapter:

- IP: 192.168.56.10
- Subnet: 255.255.255.0
- DNS: 192.168.56.10

Verified connectivity:
- Successfully pinged external IP (8.8.8.8)
- DNS resolution not yet configured (expected at this stage)

This setup prepares the server for Active Directory and DNS installation.

## Key Takeaways

- A dual-NIC setup allows separation between external (internet) and internal (domain) traffic
- Static IP addressing is required for domain controllers to ensure consistent network communication
- DNS must point to the domain controller for Active Directory to function properly
- Initial lack of DNS resolution is expected before AD DS installation

## Real-World Relevance

This configuration mirrors how enterprise environments isolate domain traffic from external networks while maintaining controlled internet access for updates and management.