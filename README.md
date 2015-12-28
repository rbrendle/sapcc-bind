# sapcc-bind

The bind configuration for a simple DNS server in the cluster. 

It basically contains two files, which serve as the "zone" configuration. One (db.sapcc.local) describes the servers in the domain and their IP addresses. There is a reverse mapping in the corresponding db.124.159.10-file (the IP adddresses in the file name here are usually written from the right to the left to fit with the normal DNS naming direction). This second file contains the reverse mapping from IP addresses to hostnames. 

You need to include these files into the domain directory file "named.conf.local". 

This is only the DNS server configuration. It is activated by using resolvconf. Do not overwrite just the /etc/resolv.conf file. This file is generated and will change over time. Its content is (without a DHCP configuration) generated out of the resolvconf configuration (in /etc/resolvconf) and the basic network configuration (/etc/network).

Still without an DHCP-configuratio the local hostname and the search domain have to be maintained in /etc/hosts.
