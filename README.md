# f0-VM
Running f0 on top of Linux KVM with libvirt

Needed changes:
- different subnet (192.168.124.0/24) for default network because libvirt inside f0 will use the same default subnet (192.168.122.0/24) and cause connectivity issues
- additional hostonly network without DHCP
- f0-GLS.xml defines a VM with:
  - f0-GLS.qcow2 virtio disk (qemu-img create -o size=250G /var/lib/libvirt/images/f0-GLS.qcow2 20G)
  - uses /dev/sdb (USB device on the host) as virtio-scsi disk
  - boot menu enabled for virtio disk, scsi disk and dvd drive
  - memory can be enlarged from 8GiB to 32GiB
  - 4 cores can be expanded to 8 cores
  - BIOS boot (works with all RHEL versions)
  
Install as if installing a physical f0 machine from USB disk.
