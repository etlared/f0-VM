# f0-VM
Running f0 on top of Linux KVM with libvirt

Needed changes:
- different subnet (192.168.124.0/24) for default network because libvirt inside f0 will use the same default subnet (192.168.122.0/24) and cause connectivity issues
- additional hostonly network without DHCP
