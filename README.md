# Zabbix Template: OS Linux diskstats

Monitoring template for Zabbix to get Linux disk statistics.

## About

This is a self-contained monitoring template for Zabbix to get I/O statistics from Linux systems. The information will be taken from /proc/diskstats.

## Examples

### Items

![Items](img/example-items.png)

### Graph

![Graph](img/example-graph.png)

## Links

* [/proc/diskstats](https://www.kernel.org/doc/Documentation/ABI/testing/procfs-diskstats)
* [I/O statistics fields](https://www.kernel.org/doc/Documentation/admin-guide/iostats.rst)

## Known Issues

* If the file /proc/diskstats is larger than 64KB, then this template won't work anymore because of the limit of [vfs.file.contents](https://www.zabbix.com/documentation/current/manual/config/items/itemtypes/zabbix_agent).
* The following items are available on Linux 4.18+. Disable them, if you use an older version.
  * discards completed
  * discards merged
  * sectors discarded
  * time spent discarding
* The following items are available on Linux 5.5+. Disable them, if you use an older version.
  * flush requests completed
  * time spent flushing
