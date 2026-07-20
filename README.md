# Wiretap

A Proxmox wiretapping (SPAN) tool using `tc` to direct duplicate traffic to a separate bride for inspection. 
In Proxmox every VM and LXC have a tap port where you can listen in on traffic.
Building on that this tool allows you to monitor multiple VMs on a singular bridge.

## Usage 

```bash
wiretap add tap101i0 vmbrSPAN1
```
```text
Added tap101i0 ingress and egress mirroring to vmbrSPAN1
```
```bash
wiretap remove tap101i0 vmbrSPAN1
```
```text
Removed tap101i0 ingress and egress mirroring to vmbrSPAN1
```