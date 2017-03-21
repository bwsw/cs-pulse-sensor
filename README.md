# cs-pulse-sensor
The purpose of the container is to monitor remote libvirt KVM hypervisor host and gather the information about VM resource usage. It is implemented in python2.7 with libvirt. It stores gathered statistics to the remote influxdb storage.

Currently it gathers next metrics: 
 - Host: CPU statistics, RAM statistics
 - Virtual machines: cpuTime, RAM usage, disk IO, network IO

Features:
 - purposed for KVM hypervisor
 - tested with block devices located in files (native for Apache Cloudstack and NFS storage)
 - bundled as easy to use Docker container (one container per one virtualization host)
