# cs-pulse-sensor
The purpose of the container is to monitor remote libvirt kvm hypervisor host and gather the information about VM resource usage. It is implemented in python2.7 with libvirt. It stores gathered statistics to the remote influxdb storage.
Currently it gathers next metrics: cpuTime, rss, disk IO, network IO.
