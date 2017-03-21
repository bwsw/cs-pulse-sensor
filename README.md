# cs-pulse-sensor
The purpose of the container is to monitor remote libvirt KVM hypervisor host and gather the information about VM resource usage. It is implemented in python2.7 with libvirt. It stores gathered statistics to the remote influxdb storage.

Currently it gathers next metrics: 
 - Host: CPU statistics, RAM statistics
 - Virtual machines: cpuTime, RAM usage, disk IO, network IO

Features:
 - purposed for KVM hypervisor
 - tested with block devices located in files (native for Apache Cloudstack and NFS storage)
 - bundled as easy to use Docker container (one container per one virtualization host)

Usage:

```
# docker pull bwsw/cs-pulse-sensor
# docker run --restart=always -d --name 10.252.1.$i \
             -e PAUSE=10 \
             -e INFLUX_HOST=influx \
             -e INFLUX_PORT=8086 \
             -e INFLUX_DB=puls \
             -e INFLUX_USER=puls \
             -e INFLUX_PASSWORD=secret \
             -e PAUSE=20
             -e GATHER_HOST_STATS=true
             -e DEBUG=true \
             -e KVM_HOST=qemu+tcp://root@10.252.1.11:16509/system \
             bwsw/cs-pulse-sensor
```
