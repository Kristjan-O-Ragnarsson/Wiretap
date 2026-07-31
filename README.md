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
wiretap remove tap101i0
```
```text
Removed all ingress and egress mirroring from tap101i0
```

### Adding a bridge

```bash
ip link add name vmbrSPAN1 type bridge
ip link set dev vmbrSPAN1 up
```



## Credit

This was built with inspiration from [tylerdotrar/tc-taps](https://github.com/tylerdotrar/tc-taps). However, Wiretap uses `clsact` to do ingress and egress filtering, as it enables ingress and egress filtering on a singualar qdisc and avoids deleting and creating a new root qdisc.