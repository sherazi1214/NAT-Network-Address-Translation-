# NAT-Network-Address-Translation

NAT (Network Address Translation) is a method used in computer networking to modify network address information in the IP header of packets while they are in transit. Its main purpose is to remap one IP address space into another, commonly used to enable multiple devices on a private network to access the internet using a single public IP address.


![NAT](https://whatismyipaddress.com/wp-content/uploads/nat.png)

## Why NAT is Used
IP Address Conservation

The IPv4 address space is limited. NAT allows many devices to share a single public IP address.

#### Security and Privacy

Devices behind a NAT are not directly reachable from the internet, offering a layer of protection.

#### Network Flexibility

NAT allows private IP addressing internally, simplifying internal network management.

## Types of NAT
Type of NAT	Description
Static NAT	One-to-one mapping between a private IP and a public IP. Used when a device needs to be accessible from the internet.
Dynamic NAT	Maps private IPs to public IPs from a pool. The mapping changes each time.
PAT (Port Address Translation) / NAT Overload	Most common. Maps multiple private IPs to a single public IP by using different port numbers.

### How NAT Works (Simplified)
A device inside a private network sends a packet to the internet.

The NAT router replaces the source private IP and port with its public IP and a unique port.

The NAT router keeps a table of mappings (private ↔ public).

When a reply comes back, the router uses the table to forward the packet to the correct internal device.

### Example of PAT (Most Common NAT)
Private IP ------------------- Port	Public IP + Port
192.168.0.2:1234-------------	203.0.113.5:4000
192.168.0.3:1234-------------	203.0.113.5:4001

Both private users use the same public IP but different ports.

## Benefits of NAT
Reduces the need for public IP addresses.

Enhances security by hiding internal network structure.

Allows easier network redesign without IP conflicts.

## Limitations of NAT
Some applications (like VoIP, P2P, and gaming) may not work well without additional configuration.

Adds processing overhead.

Breaks end-to-end connectivity, which can be problematic for some protocols.

## NAT vs Firewall
NAT hides IP addresses; a firewall filters traffic.

NAT can provide basic security, but it's not a substitute for a firewall.
