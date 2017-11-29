# NETCONF on SLX:

## Introduction to NETCONF/YANG
- 
- 

## NETCONF capabilities exposed by the SLX (Example on SLX 9240):

### ssh the device with "-s" option:
```
mab@mab-infra:~$ ssh admin@192.168.254.115 -s netconf
admin@192.168.254.115's password: 
<?xml version="1.0" encoding="UTF-8"?>
<hello xmlns="urn:ietf:params:xml:ns:netconf:base:1.0">
<capabilities>
<capability>urn:ietf:params:netconf:base:1.0</capability>
<capability>urn:ietf:params:netconf:base:1.1</capability>
<capability>urn:ietf:params:netconf:capability:writable-running:1.0</capability>
<capability>urn:ietf:params:netconf:capability:startup:1.0</capability>
<capability>urn:ietf:params:netconf:capability:xpath:1.0</capability>
<capability>urn:ietf:params:netconf:capability:validate:1.0</capability>
<capability>urn:ietf:params:netconf:capability:validate:1.1</capability>
<capability>http://tail-f.com/ns/netconf/actions/1.0</capability>
<capability>urn:ietf:params:netconf:capability:with-defaults:1.0?basic-mode=explicit&amp;also-supported=report-all-tagged</capability>
<capability>urn:ietf:params:xml:ns:yang:ietf-netconf-with-defaults?revision=2011-06-01&amp;module=ietf-netconf-with-defaults</capability>
<capability>http://brocade.com/ns/brocade-auto-shut-edge-port?module=brocade-auto-shut-edge-port&amp;revision=2012-01-20</capability>
<capability>http://brocade.com/ns/brocade-default-config?module=brocade-default-config&amp;revision=2014-11-01</capability>
<capability>http://brocade.com/ns/brocade-logical-chassis?module=brocade-logical-chassis&amp;revision=2012-04-12</capability>
<capability>http://tail-f.com/ns/aaa/1.1?module=tailf-aaa&amp;revision=2011-09-22</capability>
<capability>http://tail-f.com/ns/webui?module=tailf-webui&amp;revision=2013-03-07</capability>
<capability>http://tail-f.com/yang/common-monitoring?module=tailf-common-monitoring&amp;revision=2013-06-14</capability>
<capability>http://tail-f.com/yang/confd-monitoring?module=tailf-confd-monitoring&amp;revision=2013-06-14</capability>
<capability>http://tail-f.com/yang/netconf-monitoring?module=tailf-netconf-monitoring&amp;revision=2012-06-14</capability>
<capability>urn:brocade.com:mgmt:brocade-Enclosure-show?module=brocade-Enclosure-show&amp;revision=2014-06-09</capability>
<capability>urn:brocade.com:mgmt:brocade-aaa?module=brocade-aaa&amp;revision=2010-10-21</capability>
<capability>urn:brocade.com:mgmt:brocade-aaa-ext?module=brocade-aaa-ext&amp;revision=2010-09-21</capability>
<capability>urn:brocade.com:mgmt:brocade-acl-policy?module=brocade-acl-policy&amp;revision=2015-08-25</capability>
<capability>urn:brocade.com:mgmt:brocade-anycast-gateway?module=brocade-anycast-gateway&amp;revision=2014-03-27</capability>
<capability>urn:brocade.com:mgmt:brocade-apply-qos-mpls?module=brocade-apply-qos-mpls&amp;revision=2015-05-11</capability>
<capability>urn:brocade.com:mgmt:brocade-arp?module=brocade-arp&amp;revision=2011-10-31</capability>
<capability>urn:brocade.com:mgmt:brocade-beacon?module=brocade-beacon&amp;revision=2011-10-31</capability>
<capability>urn:brocade.com:mgmt:brocade-bfd?module=brocade-bfd&amp;revision=2014-09-24</capability>
<capability>urn:brocade.com:mgmt:brocade-bgp?module=brocade-bgp&amp;revision=2010-11-29</capability>
<capability>urn:brocade.com:mgmt:brocade-bprate-limit?module=brocade-bprate-limit&amp;revision=2014-10-09</capability>
<capability>urn:brocade.com:mgmt:brocade-bridge-domain?module=brocade-bridge-domain&amp;revision=2011-06-21</capability>
<capability>urn:brocade.com:mgmt:brocade-cdp?module=brocade-cdp&amp;revision=2010-08-17</capability>
<capability>urn:brocade.com:mgmt:brocade-chassis?module=brocade-chassis&amp;revision=2011-04-11</capability>
<capability>urn:brocade.com:mgmt:brocade-clock?module=brocade-clock&amp;revision=2009-05-01</capability>
<capability>urn:brocade.com:mgmt:brocade-common-def?module=brocade-common-def&amp;revision=2010-02-22</capability>
<capability>urn:brocade.com:mgmt:brocade-crypto?module=brocade-crypto&amp;revision=2014-07-01</capability>
<capability>urn:brocade.com:mgmt:brocade-crypto-ext?module=brocade-crypto-ext&amp;revision=2014-07-01</capability>
<capability>urn:brocade.com:mgmt:brocade-dai?module=brocade-dai&amp;revision=2012-07-01</capability>
<capability>urn:brocade.com:mgmt:brocade-dhcp?module=brocade-dhcp&amp;revision=2013-05-20</capability>
<capability>urn:brocade.com:mgmt:brocade-dhcpv6?module=brocade-dhcpv6&amp;revision=2014-06-11</capability>
<capability>urn:brocade.com:mgmt:brocade-distributedlog?module=brocade-distributedlog&amp;revision=2010-12-02</capability>
<capability>urn:brocade.com:mgmt:brocade-dle?module=brocade-dle&amp;revision=2010-04-28</capability>
<capability>urn:brocade.com:mgmt:brocade-dot1ag?module=brocade-dot1ag&amp;revision=2014-01-03</capability>
<capability>urn:brocade.com:mgmt:brocade-dot1x?module=brocade-dot1x&amp;revision=2011-07-13</capability>
<capability>urn:brocade.com:mgmt:brocade-eld?module=brocade-eld&amp;revision=2011-08-08</capability>
<capability>urn:brocade.com:mgmt:brocade-entity?module=brocade-entity&amp;revision=2014-05-09</capability>
<capability>urn:brocade.com:mgmt:brocade-event-handler?module=brocade-event-handler&amp;revision=2010-12-02</capability>
<capability>urn:brocade.com:mgmt:brocade-firmware?module=brocade-firmware&amp;revision=2011-04-11</capability>
<capability>urn:brocade.com:mgmt:brocade-firmware-ext?module=brocade-firmware-ext&amp;revision=2011-02-25</capability>
<capability>urn:brocade.com:mgmt:brocade-gre-vxlan?module=brocade-gre-vxlan&amp;revision=2015-07-14</capability>
<capability>urn:brocade.com:mgmt:brocade-ha?module=brocade-ha&amp;revision=2011-10-31</capability>
<capability>urn:brocade.com:mgmt:brocade-hardware?module=brocade-hardware&amp;revision=2016-02-01</capability>
<capability>urn:brocade.com:mgmt:brocade-http?module=brocade-http-config&amp;revision=2013-11-28</capability>
<capability>urn:brocade.com:mgmt:brocade-http-redirect?module=brocade-http-redirect&amp;revision=2013-01-14</capability>
<capability>urn:brocade.com:mgmt:brocade-icmp?module=brocade-icmp&amp;revision=2013-09-15</capability>
<capability>urn:brocade.com:mgmt:brocade-igmp?module=brocade-igmp&amp;revision=2014-06-12</capability>
<capability>urn:brocade.com:mgmt:brocade-igmp-snooping?module=brocade-igmp-snooping&amp;revision=2010-06-02</capability>
<capability>urn:brocade.com:mgmt:brocade-interface?module=brocade-interface&amp;revision=2012-04-24</capability>
<capability>urn:brocade.com:mgmt:brocade-interface-ext?module=brocade-interface-ext&amp;revision=2014-04-01</capability>
<capability>urn:brocade.com:mgmt:brocade-intf-loopback?module=brocade-intf-loopback&amp;revision=2011-09-28</capability>
<capability>urn:brocade.com:mgmt:brocade-ip-access-list?module=brocade-ip-access-list&amp;revision=2011-03-01</capability>
<capability>urn:brocade.com:mgmt:brocade-ip-administration?module=brocade-ip-administration&amp;revision=2011-04-11</capability>
<capability>urn:brocade.com:mgmt:brocade-ip-config?module=brocade-ip-config&amp;revision=2011-10-31</capability>
<capability>urn:brocade.com:mgmt:brocade-ip-forward?module=brocade-ip-forward&amp;revision=2011-07-18</capability>
<capability>urn:brocade.com:mgmt:brocade-ip-policy?module=brocade-ip-policy&amp;revision=2011-03-19</capability>
<capability>urn:brocade.com:mgmt:brocade-ipv6-access-list?module=brocade-ipv6-access-list&amp;revision=2012-07-01</capability>
<capability>urn:brocade.com:mgmt:brocade-ipv6-config?module=brocade-ipv6-config&amp;revision=2013-07-26</capability>
<capability>urn:brocade.com:mgmt:brocade-ipv6-nd-ra?module=brocade-ipv6-nd-ra&amp;revision=2013-07-26</capability>
<capability>urn:brocade.com:mgmt:brocade-ipv6-rtm?module=brocade-ipv6-rtm&amp;revision=2013-10-22</capability>
<capability>urn:brocade.com:mgmt:brocade-lacp?module=brocade-lacp&amp;revision=2010-01-25</capability>
<capability>urn:brocade.com:mgmt:brocade-lag?module=brocade-lag&amp;revision=2015-05-07</capability>
<capability>urn:brocade.com:mgmt:brocade-lfs?module=brocade-lfs&amp;revision=2010-04-28</capability>
<capability>urn:brocade.com:mgmt:brocade-license?module=brocade-license&amp;revision=2011-08-22</capability>
<capability>urn:brocade.com:mgmt:brocade-lif?module=brocade-lif&amp;revision=2014-06-04</capability>
<capability>urn:brocade.com:mgmt:brocade-linecard-management?module=brocade-linecard-management&amp;revision=2011-09-06</capability>
<capability>urn:brocade.com:mgmt:brocade-lldp?module=brocade-lldp&amp;revision=2010-04-28</capability>
<capability>urn:brocade.com:mgmt:brocade-lldp-ext?module=brocade-lldp-ext&amp;revision=2014-06-01</capability>
<capability>urn:brocade.com:mgmt:brocade-mac-access-list?module=brocade-mac-access-list&amp;revision=2011-02-28</capability>
<capability>urn:brocade.com:mgmt:brocade-mac-address-table?module=brocade-mac-address-table&amp;revision=2011-02-15</capability>
<capability>urn:brocade.com:mgmt:brocade-mc-hms-operational?module=brocade-mc-hms-operational&amp;revision=2017-04-01</capability>
<capability>urn:brocade.com:mgmt:brocade-mct?module=brocade-mct&amp;revision=2011-06-21</capability>
<capability>urn:brocade.com:mgmt:brocade-mld-snooping?module=brocade-mld-snooping&amp;revision=2013-07-29</capability>
<capability>urn:brocade.com:mgmt:brocade-nameserver?module=brocade-nameserver&amp;revision=2012-03-07</capability>
<capability>urn:brocade.com:mgmt:brocade-netconf-ext?module=brocade-netconf-ext&amp;revision=2012-02-03</capability>
<capability>urn:brocade.com:mgmt:brocade-nsm-operational?module=brocade-nsm-operational&amp;revision=2017-04-01</capability>
<capability>urn:brocade.com:mgmt:brocade-ntp?module=brocade-ntp&amp;revision=2009-05-01</capability>
<capability>urn:brocade.com:mgmt:brocade-openflow?module=brocade-openflow&amp;revision=2014-08-12</capability>
<capability>urn:brocade.com:mgmt:brocade-openflow-operational?module=brocade-openflow-operational&amp;revision=2017-04-01</capability>
<capability>urn:brocade.com:mgmt:brocade-ospf?module=brocade-ospf&amp;revision=2010-11-29</capability>
<capability>urn:brocade.com:mgmt:brocade-ospfv3?module=brocade-ospfv3&amp;revision=2013-08-25</capability>
<capability>urn:brocade.com:mgmt:brocade-overlay-policy?module=brocade-overlay-policy&amp;revision=2016-05-15</capability>
<capability>urn:brocade.com:mgmt:brocade-packet-timestamp?module=brocade-packet-timestamp&amp;revision=2016-07-20</capability>
<capability>urn:brocade.com:mgmt:brocade-pld?module=brocade-pld&amp;revision=2010-04-28</capability>
<capability>urn:brocade.com:mgmt:brocade-ptp?module=brocade-ptp&amp;revision=2015-06-24</capability>
<capability>urn:brocade.com:mgmt:brocade-ptp-operational?module=brocade-ptp-operational&amp;revision=2017-04-01</capability>
<capability>urn:brocade.com:mgmt:brocade-pw-profile?module=brocade-pw-profile&amp;revision=2014-04-14</capability>
<capability>urn:brocade.com:mgmt:brocade-pwm-operational?module=brocade-pwm-operational&amp;revision=2017-04-01</capability>
<capability>urn:brocade.com:mgmt:brocade-qos-cee?module=brocade-qos-cee&amp;revision=2011-04-18</capability>
<capability>urn:brocade.com:mgmt:brocade-qos-cpu?module=brocade-qos-cpu&amp;revision=2016-01-28</capability>
<capability>urn:brocade.com:mgmt:brocade-qos-mls?module=brocade-qos-mls&amp;revision=2010-04-28</capability>
<capability>urn:brocade.com:mgmt:brocade-qos-mpls?module=brocade-qos-mpls&amp;revision=2015-04-07</capability>
<capability>urn:brocade.com:mgmt:brocade-qos-mqc?module=brocade-qos-mqc&amp;revision=2011-03-04</capability>
<capability>urn:brocade.com:mgmt:brocade-ras?module=brocade-ras&amp;revision=2011-04-11</capability>
<capability>urn:brocade.com:mgmt:brocade-ras-ext?module=brocade-ras-ext&amp;revision=2011-01-20</capability>
<capability>urn:brocade.com:mgmt:brocade-rbridge?module=brocade-rbridge&amp;revision=2011-06-21</capability>
<capability>urn:brocade.com:mgmt:brocade-rbridge-lag?module=brocade-rbridge-lag&amp;revision=2015-03-16</capability>
<capability>urn:brocade.com:mgmt:brocade-resource-monitor?module=brocade-resource-monitor&amp;revision=2016-02-08</capability>
<capability>urn:brocade.com:mgmt:brocade-rmon?module=brocade-rmon&amp;revision=2011-02-28</capability>
<capability>urn:brocade.com:mgmt:brocade-rtm?module=brocade-rtm&amp;revision=2011-09-28</capability>
<capability>urn:brocade.com:mgmt:brocade-sec-services?module=brocade-sec-services&amp;revision=2012-07-28</capability>
<capability>urn:brocade.com:mgmt:brocade-sflow?module=brocade-sflow&amp;revision=2009-12-10</capability>
<capability>urn:brocade.com:mgmt:brocade-snmp?module=brocade-snmp&amp;revision=2011-03-18</capability>
<capability>urn:brocade.com:mgmt:brocade-span?module=brocade-span&amp;revision=2010-04-28</capability>
<capability>urn:brocade.com:mgmt:brocade-sysdiag-operational?module=brocade-sysdiag-operational&amp;revision=2017-04-01</capability>
<capability>urn:brocade.com:mgmt:brocade-sysmgr?module=brocade-sysmgr&amp;revision=2015-07-22</capability>
<capability>urn:brocade.com:mgmt:brocade-system?module=brocade-system&amp;revision=2011-08-09</capability>
<capability>urn:brocade.com:mgmt:brocade-system-capabilities?module=brocade-system-capabilities&amp;revision=2016-05-20</capability>
<capability>urn:brocade.com:mgmt:brocade-system-monitor?module=brocade-system-monitor&amp;revision=2011-11-16</capability>
<capability>urn:brocade.com:mgmt:brocade-system-monitor-ext?module=brocade-system-monitor-ext&amp;revision=2011-05-05</capability>
<capability>urn:brocade.com:mgmt:brocade-telemetry?module=brocade-telemetry&amp;revision=2016-06-29</capability>
<capability>urn:brocade.com:mgmt:brocade-terminal?module=brocade-terminal&amp;revision=2011-04-18</capability>
<capability>urn:brocade.com:mgmt:brocade-threshold-monitor?module=brocade-threshold-monitor&amp;revision=2011-11-24</capability>
<capability>urn:brocade.com:mgmt:brocade-threshold-monitor-ext?module=brocade-threshold-monitor-ext&amp;revision=2011-05-05</capability>
<capability>urn:brocade.com:mgmt:brocade-tm-stats?module=brocade-tm-stats&amp;revision=2016-04-13</capability>
<capability>urn:brocade.com:mgmt:brocade-trilloam?module=brocade-trilloam</capability>
<capability>urn:brocade.com:mgmt:brocade-tunnels?module=brocade-tunnels&amp;revision=2015-06-01</capability>
<capability>urn:brocade.com:mgmt:brocade-vcs?module=brocade-vcs&amp;revision=2011-05-26</capability>
<capability>urn:brocade.com:mgmt:brocade-vlan?module=brocade-vlan&amp;revision=2016-02-23</capability>
<capability>urn:brocade.com:mgmt:brocade-vrf?module=brocade-vrf&amp;revision=2012-04-28</capability>
<capability>urn:brocade.com:mgmt:brocade-vrrp?module=brocade-vrrp&amp;revision=2011-10-31</capability>
<capability>urn:brocade.com:mgmt:brocade-vrrpv3?module=brocade-vrrpv3&amp;revision=2013-10-21</capability>
<capability>urn:brocade.com:mgmt:brocade-vxlan-visibility?module=brocade-vxlan-visibility&amp;revision=2015-06-15</capability>
<capability>urn:brocade.com:mgmt:brocade-xstp?module=brocade-xstp&amp;revision=2011-07-05</capability>
<capability>urn:brocade.com:mgmt:brocade-xstp-ext?module=brocade-xstp-ext&amp;revision=2011-02-22</capability>
<capability>urn:brocade.com:mgmt:brocade-zone?module=brocade-zone&amp;revision=2010-12-01</capability>
<capability>urn:brocade.com:mgmt:certutil?module=brocade-certutil&amp;revision=2011-06-13</capability>
<capability>urn:ietf:params:xml:ns:yang:ietf-inet-types?module=ietf-inet-types&amp;revision=2010-09-24</capability>
<capability>urn:ietf:params:xml:ns:yang:ietf-netconf-monitoring?module=ietf-netconf-monitoring&amp;revision=2010-10-04</capability>
<capability>urn:ietf:params:xml:ns:yang:ietf-netconf-notifications?module=ietf-netconf-notifications&amp;revision=2012-02-06</capability>
<capability>urn:ietf:params:xml:ns:yang:ietf-yang-types?module=ietf-yang-types&amp;revision=2010-09-24</capability>
</capabilities>
<session-id>16</session-id></hello>]]>]]>
```

### CLI command: show netconf capabilities
```
spine1# show netconf capabilities
netconf-state capabilities capability urn:ietf:params:netconf:base:1.0
netconf-state capabilities capability urn:ietf:params:netconf:base:1.1
netconf-state capabilities capability urn:ietf:params:netconf:capability:writable-running:1.0
netconf-state capabilities capability urn:ietf:params:netconf:capability:startup:1.0
netconf-state capabilities capability urn:ietf:params:netconf:capability:xpath:1.0
netconf-state capabilities capability urn:ietf:params:netconf:capability:validate:1.0
netconf-state capabilities capability urn:ietf:params:netconf:capability:validate:1.1
netconf-state capabilities capability http://tail-f.com/ns/netconf/actions/1.0
netconf-state capabilities capability urn:ietf:params:netconf:capability:with-defaults:1.0?basic-mode=explicit&also-supported=report-all-tagged
netconf-state capabilities capability urn:ietf:params:xml:ns:yang:ietf-netconf-with-defaults?revision=2011-06-01&module=ietf-netconf-with-defaults
netconf-state capabilities capability http://brocade.com/ns/brocade-auto-shut-edge-port?module=brocade-auto-shut-edge-port&revision=2012-01-20
netconf-state capabilities capability http://brocade.com/ns/brocade-default-config?module=brocade-default-config&revision=2014-11-01
netconf-state capabilities capability http://brocade.com/ns/brocade-logical-chassis?module=brocade-logical-chassis&revision=2012-04-12
netconf-state capabilities capability http://tail-f.com/ns/aaa/1.1?module=tailf-aaa&revision=2011-09-22
netconf-state capabilities capability http://tail-f.com/ns/webui?module=tailf-webui&revision=2013-03-07
netconf-state capabilities capability http://tail-f.com/yang/common-monitoring?module=tailf-common-monitoring&revision=2013-06-14
netconf-state capabilities capability http://tail-f.com/yang/confd-monitoring?module=tailf-confd-monitoring&revision=2013-06-14
netconf-state capabilities capability http://tail-f.com/yang/netconf-monitoring?module=tailf-netconf-monitoring&revision=2012-06-14
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-Enclosure-show?module=brocade-Enclosure-show&revision=2014-06-09
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-aaa?module=brocade-aaa&revision=2010-10-21
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-aaa-ext?module=brocade-aaa-ext&revision=2010-09-21
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-acl-policy?module=brocade-acl-policy&revision=2015-08-25
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-anycast-gateway?module=brocade-anycast-gateway&revision=2014-03-27
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-apply-qos-mpls?module=brocade-apply-qos-mpls&revision=2015-05-11
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-arp?module=brocade-arp&revision=2011-10-31
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-beacon?module=brocade-beacon&revision=2011-10-31
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-bfd?module=brocade-bfd&revision=2014-09-24
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-bgp?module=brocade-bgp&revision=2010-11-29
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-bprate-limit?module=brocade-bprate-limit&revision=2014-10-09
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-bridge-domain?module=brocade-bridge-domain&revision=2011-06-21
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-cdp?module=brocade-cdp&revision=2010-08-17
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-chassis?module=brocade-chassis&revision=2011-04-11
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-clock?module=brocade-clock&revision=2009-05-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-common-def?module=brocade-common-def&revision=2010-02-22
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-crypto?module=brocade-crypto&revision=2014-07-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-crypto-ext?module=brocade-crypto-ext&revision=2014-07-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-dai?module=brocade-dai&revision=2012-07-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-dhcp?module=brocade-dhcp&revision=2013-05-20
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-dhcpv6?module=brocade-dhcpv6&revision=2014-06-11
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-distributedlog?module=brocade-distributedlog&revision=2010-12-02
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-dle?module=brocade-dle&revision=2010-04-28
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-dot1ag?module=brocade-dot1ag&revision=2014-01-03
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-dot1x?module=brocade-dot1x&revision=2011-07-13
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-eld?module=brocade-eld&revision=2011-08-08
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-entity?module=brocade-entity&revision=2014-05-09
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-event-handler?module=brocade-event-handler&revision=2010-12-02
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-firmware?module=brocade-firmware&revision=2011-04-11
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-firmware-ext?module=brocade-firmware-ext&revision=2011-02-25
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-gre-vxlan?module=brocade-gre-vxlan&revision=2015-07-14
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ha?module=brocade-ha&revision=2011-10-31
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-hardware?module=brocade-hardware&revision=2016-02-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-http?module=brocade-http-config&revision=2013-11-28
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-http-redirect?module=brocade-http-redirect&revision=2013-01-14
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-icmp?module=brocade-icmp&revision=2013-09-15
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-igmp?module=brocade-igmp&revision=2014-06-12
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-igmp-snooping?module=brocade-igmp-snooping&revision=2010-06-02
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-interface?module=brocade-interface&revision=2012-04-24
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-interface-ext?module=brocade-interface-ext&revision=2014-04-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-intf-loopback?module=brocade-intf-loopback&revision=2011-09-28
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ip-access-list?module=brocade-ip-access-list&revision=2011-03-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ip-administration?module=brocade-ip-administration&revision=2011-04-11
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ip-config?module=brocade-ip-config&revision=2011-10-31
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ip-forward?module=brocade-ip-forward&revision=2011-07-18
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ip-policy?module=brocade-ip-policy&revision=2011-03-19
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ipv6-access-list?module=brocade-ipv6-access-list&revision=2012-07-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ipv6-config?module=brocade-ipv6-config&revision=2013-07-26
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ipv6-nd-ra?module=brocade-ipv6-nd-ra&revision=2013-07-26
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ipv6-rtm?module=brocade-ipv6-rtm&revision=2013-10-22
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-lacp?module=brocade-lacp&revision=2010-01-25
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-lag?module=brocade-lag&revision=2015-05-07
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-lfs?module=brocade-lfs&revision=2010-04-28
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-license?module=brocade-license&revision=2011-08-22
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-lif?module=brocade-lif&revision=2014-06-04
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-linecard-management?module=brocade-linecard-management&revision=2011-09-06
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-lldp?module=brocade-lldp&revision=2010-04-28
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-lldp-ext?module=brocade-lldp-ext&revision=2014-06-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-mac-access-list?module=brocade-mac-access-list&revision=2011-02-28
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-mac-address-table?module=brocade-mac-address-table&revision=2011-02-15
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-mc-hms-operational?module=brocade-mc-hms-operational&revision=2017-04-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-mct?module=brocade-mct&revision=2011-06-21
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-mld-snooping?module=brocade-mld-snooping&revision=2013-07-29
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-nameserver?module=brocade-nameserver&revision=2012-03-07
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-netconf-ext?module=brocade-netconf-ext&revision=2012-02-03
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-nsm-operational?module=brocade-nsm-operational&revision=2017-04-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ntp?module=brocade-ntp&revision=2009-05-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-openflow?module=brocade-openflow&revision=2014-08-12
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-openflow-operational?module=brocade-openflow-operational&revision=2017-04-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ospf?module=brocade-ospf&revision=2010-11-29
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ospfv3?module=brocade-ospfv3&revision=2013-08-25
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-overlay-policy?module=brocade-overlay-policy&revision=2016-05-15
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-packet-timestamp?module=brocade-packet-timestamp&revision=2016-07-20
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-pld?module=brocade-pld&revision=2010-04-28
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ptp?module=brocade-ptp&revision=2015-06-24
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ptp-operational?module=brocade-ptp-operational&revision=2017-04-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-pw-profile?module=brocade-pw-profile&revision=2014-04-14
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-pwm-operational?module=brocade-pwm-operational&revision=2017-04-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-qos-cee?module=brocade-qos-cee&revision=2011-04-18
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-qos-cpu?module=brocade-qos-cpu&revision=2016-01-28
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-qos-mls?module=brocade-qos-mls&revision=2010-04-28
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-qos-mpls?module=brocade-qos-mpls&revision=2015-04-07
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-qos-mqc?module=brocade-qos-mqc&revision=2011-03-04
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ras?module=brocade-ras&revision=2011-04-11
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-ras-ext?module=brocade-ras-ext&revision=2011-01-20
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-rbridge?module=brocade-rbridge&revision=2011-06-21
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-rbridge-lag?module=brocade-rbridge-lag&revision=2015-03-16
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-resource-monitor?module=brocade-resource-monitor&revision=2016-02-08
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-rmon?module=brocade-rmon&revision=2011-02-28
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-rtm?module=brocade-rtm&revision=2011-09-28
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-sec-services?module=brocade-sec-services&revision=2012-07-28
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-sflow?module=brocade-sflow&revision=2009-12-10
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-snmp?module=brocade-snmp&revision=2011-03-18
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-span?module=brocade-span&revision=2010-04-28
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-sysdiag-operational?module=brocade-sysdiag-operational&revision=2017-04-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-sysmgr?module=brocade-sysmgr&revision=2015-07-22
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-system?module=brocade-system&revision=2011-08-09
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-system-capabilities?module=brocade-system-capabilities&revision=2016-05-20
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-system-monitor?module=brocade-system-monitor&revision=2011-11-16
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-system-monitor-ext?module=brocade-system-monitor-ext&revision=2011-05-05
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-telemetry?module=brocade-telemetry&revision=2016-06-29
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-terminal?module=brocade-terminal&revision=2011-04-18
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-threshold-monitor?module=brocade-threshold-monitor&revision=2011-11-24
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-threshold-monitor-ext?module=brocade-threshold-monitor-ext&revision=2011-05-05
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-tm-stats?module=brocade-tm-stats&revision=2016-04-13
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-trilloam?module=brocade-trilloam
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-tunnels?module=brocade-tunnels&revision=2015-06-01
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-vcs?module=brocade-vcs&revision=2011-05-26
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-vlan?module=brocade-vlan&revision=2016-02-23
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-vrf?module=brocade-vrf&revision=2012-04-28
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-vrrp?module=brocade-vrrp&revision=2011-10-31
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-vrrpv3?module=brocade-vrrpv3&revision=2013-10-21
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-vxlan-visibility?module=brocade-vxlan-visibility&revision=2015-06-15
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-xstp?module=brocade-xstp&revision=2011-07-05
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-xstp-ext?module=brocade-xstp-ext&revision=2011-02-22
netconf-state capabilities capability urn:brocade.com:mgmt:brocade-zone?module=brocade-zone&revision=2010-12-01
netconf-state capabilities capability urn:brocade.com:mgmt:certutil?module=brocade-certutil&revision=2011-06-13
netconf-state capabilities capability urn:ietf:params:xml:ns:yang:ietf-inet-types?module=ietf-inet-types&revision=2010-09-24
netconf-state capabilities capability urn:ietf:params:xml:ns:yang:ietf-netconf-monitoring?module=ietf-netconf-monitoring&revision=2010-10-04
netconf-state capabilities capability urn:ietf:params:xml:ns:yang:ietf-netconf-notifications?module=ietf-netconf-notifications&revision=2012-02-06
netconf-state capabilities capability urn:ietf:params:xml:ns:yang:ietf-yang-types?module=ietf-yang-types&revision=2010-09-24
spine1#
```

### CLI command: show netconf-state schemas
```
spine1# show netconf-state schemas
netconf-state schemas schema brocade-aaa 2010-10-21 yang
 namespace urn:brocade.com:mgmt:brocade-aaa
 location [ NETCONF ]
netconf-state schemas schema brocade-aaa-ext 2010-09-21 yang
 namespace urn:brocade.com:mgmt:brocade-aaa-ext
 location [ NETCONF ]
netconf-state schemas schema brocade-apply-qos-mpls 2015-05-11 yang
 namespace urn:brocade.com:mgmt:brocade-apply-qos-mpls
 location [ NETCONF ]
netconf-state schemas schema brocade-arp 2011-10-31 yang
 namespace urn:brocade.com:mgmt:brocade-arp
 location [ NETCONF ]
netconf-state schemas schema brocade-bfd 2014-09-24 yang
 namespace urn:brocade.com:mgmt:brocade-bfd
 location [ NETCONF ]
netconf-state schemas schema brocade-bgp 2010-11-29 yang
 namespace urn:brocade.com:mgmt:brocade-bgp
 location [ NETCONF ]
netconf-state schemas schema brocade-bridge-domain 2011-06-21 yang
 namespace urn:brocade.com:mgmt:brocade-bridge-domain
 location [ NETCONF ]
netconf-state schemas schema brocade-certutil 2011-06-13 yang
 namespace urn:brocade.com:mgmt:certutil
 location [ NETCONF ]
netconf-state schemas schema brocade-chassis 2011-04-11 yang
 namespace urn:brocade.com:mgmt:brocade-chassis
 location [ NETCONF ]
netconf-state schemas schema brocade-clock 2009-05-01 yang
 namespace urn:brocade.com:mgmt:brocade-clock
 location [ NETCONF ]
netconf-state schemas schema brocade-common-def 2010-02-22 yang
 namespace urn:brocade.com:mgmt:brocade-common-def
 location [ NETCONF ]
netconf-state schemas schema brocade-crypto 2014-07-01 yang
 namespace urn:brocade.com:mgmt:brocade-crypto
 location [ NETCONF ]
netconf-state schemas schema brocade-crypto-ext 2014-07-01 yang
 namespace urn:brocade.com:mgmt:brocade-crypto-ext
 location [ NETCONF ]
netconf-state schemas schema brocade-dai 2012-07-01 yang
 namespace urn:brocade.com:mgmt:brocade-dai
 location [ NETCONF ]
netconf-state schemas schema brocade-dhcp 2013-05-20 yang
 namespace urn:brocade.com:mgmt:brocade-dhcp
 location [ NETCONF ]
netconf-state schemas schema brocade-dhcpv6 2014-06-11 yang
 namespace urn:brocade.com:mgmt:brocade-dhcpv6
 location [ NETCONF ]
netconf-state schemas schema brocade-diagnostics 2016-08-20 yang
 namespace urn:brocade.com:mgmt:brocade-diagnostics
 location [ NETCONF ]
netconf-state schemas schema brocade-distributedlog 2010-12-02 yang
 namespace urn:brocade.com:mgmt:brocade-distributedlog
 location [ NETCONF ]
netconf-state schemas schema brocade-dle 2010-04-28 yang
 namespace urn:brocade.com:mgmt:brocade-dle
 location [ NETCONF ]
netconf-state schemas schema brocade-dot1ag 2014-01-03 yang
 namespace urn:brocade.com:mgmt:brocade-dot1ag
 location [ NETCONF ]
netconf-state schemas schema brocade-dot1x 2011-07-13 yang
 namespace urn:brocade.com:mgmt:brocade-dot1x
 location [ NETCONF ]
netconf-state schemas schema brocade-entity 2014-05-09 yang
 namespace urn:brocade.com:mgmt:brocade-entity
 location [ NETCONF ]
netconf-state schemas schema brocade-event-handler 2010-12-02 yang
 namespace urn:brocade.com:mgmt:brocade-event-handler
 location [ NETCONF ]
netconf-state schemas schema brocade-firmware 2011-04-11 yang
 namespace urn:brocade.com:mgmt:brocade-firmware
 location [ NETCONF ]
netconf-state schemas schema brocade-firmware-ext 2011-02-25 yang
 namespace urn:brocade.com:mgmt:brocade-firmware-ext
 location [ NETCONF ]
netconf-state schemas schema brocade-gre-vxlan 2015-07-14 yang
 namespace urn:brocade.com:mgmt:brocade-gre-vxlan
 location [ NETCONF ]
netconf-state schemas schema brocade-ha 2011-10-31 yang
 namespace urn:brocade.com:mgmt:brocade-ha
 location [ NETCONF ]
netconf-state schemas schema brocade-hardware 2016-02-01 yang
 namespace urn:brocade.com:mgmt:brocade-hardware
 location [ NETCONF ]
netconf-state schemas schema brocade-http-config 2013-11-28 yang
 namespace urn:brocade.com:mgmt:brocade-http
 location [ NETCONF ]
netconf-state schemas schema brocade-http-redirect 2013-01-14 yang
 namespace urn:brocade.com:mgmt:brocade-http-redirect
 location [ NETCONF ]
netconf-state schemas schema brocade-icmp 2013-09-15 yang
 namespace urn:brocade.com:mgmt:brocade-icmp
 location [ NETCONF ]
netconf-state schemas schema brocade-igmp 2014-06-12 yang
 namespace urn:brocade.com:mgmt:brocade-igmp
 location [ NETCONF ]
netconf-state schemas schema brocade-igmp-snooping 2010-06-02 yang
 namespace urn:brocade.com:mgmt:brocade-igmp-snooping
 location [ NETCONF ]
netconf-state schemas schema brocade-interface 2012-04-24 yang
 namespace urn:brocade.com:mgmt:brocade-interface
 location [ NETCONF ]
netconf-state schemas schema brocade-interface-ext 2014-04-01 yang
 namespace urn:brocade.com:mgmt:brocade-interface-ext
 location [ NETCONF ]
netconf-state schemas schema brocade-intf-loopback 2011-09-28 yang
 namespace urn:brocade.com:mgmt:brocade-intf-loopback
 location [ NETCONF ]
netconf-state schemas schema brocade-ip-access-list 2011-03-01 yang
 namespace urn:brocade.com:mgmt:brocade-ip-access-list
 location [ NETCONF ]
netconf-state schemas schema brocade-ip-administration 2011-04-11 yang
 namespace urn:brocade.com:mgmt:brocade-ip-administration
 location [ NETCONF ]
netconf-state schemas schema brocade-ip-config 2011-10-31 yang
 namespace urn:brocade.com:mgmt:brocade-ip-config
 location [ NETCONF ]
netconf-state schemas schema brocade-ip-forward 2011-07-18 yang
 namespace urn:brocade.com:mgmt:brocade-ip-forward
 location [ NETCONF ]
netconf-state schemas schema brocade-ip-policy 2011-03-19 yang
 namespace urn:brocade.com:mgmt:brocade-ip-policy
 location [ NETCONF ]
netconf-state schemas schema brocade-ipv6-access-list 2012-07-01 yang
 namespace urn:brocade.com:mgmt:brocade-ipv6-access-list
 location [ NETCONF ]
netconf-state schemas schema brocade-ipv6-config 2013-07-26 yang
 namespace urn:brocade.com:mgmt:brocade-ipv6-config
 location [ NETCONF ]
netconf-state schemas schema brocade-ipv6-nd-ra 2013-07-26 yang
 namespace urn:brocade.com:mgmt:brocade-ipv6-nd-ra
 location [ NETCONF ]
netconf-state schemas schema brocade-ipv6-rtm 2013-10-22 yang
 namespace urn:brocade.com:mgmt:brocade-ipv6-rtm
 location [ NETCONF ]
netconf-state schemas schema brocade-lacp 2010-01-25 yang
 namespace urn:brocade.com:mgmt:brocade-lacp
 location [ NETCONF ]
netconf-state schemas schema brocade-lag 2015-05-07 yang
 namespace urn:brocade.com:mgmt:brocade-lag
 location [ NETCONF ]
netconf-state schemas schema brocade-lfs 2010-04-28 yang
 namespace urn:brocade.com:mgmt:brocade-lfs
 location [ NETCONF ]
netconf-state schemas schema brocade-license 2011-08-22 yang
 namespace urn:brocade.com:mgmt:brocade-license
 location [ NETCONF ]
netconf-state schemas schema brocade-lif 2014-06-04 yang
 namespace urn:brocade.com:mgmt:brocade-lif
 location [ NETCONF ]
netconf-state schemas schema brocade-linecard-management 2011-09-06 yang
 namespace urn:brocade.com:mgmt:brocade-linecard-management
 location [ NETCONF ]
netconf-state schemas schema brocade-lldp 2010-04-28 yang
 namespace urn:brocade.com:mgmt:brocade-lldp
 location [ NETCONF ]
netconf-state schemas schema brocade-lldp-ext 2014-06-01 yang
 namespace urn:brocade.com:mgmt:brocade-lldp-ext
 location [ NETCONF ]
netconf-state schemas schema brocade-mac-access-list 2011-02-28 yang
 namespace urn:brocade.com:mgmt:brocade-mac-access-list
 location [ NETCONF ]
netconf-state schemas schema brocade-mac-address-table 2011-02-15 yang
 namespace urn:brocade.com:mgmt:brocade-mac-address-table
 location [ NETCONF ]
netconf-state schemas schema brocade-mc-hms-operational 2017-04-01 yang
 namespace urn:brocade.com:mgmt:brocade-mc-hms-operational
 location [ NETCONF ]
netconf-state schemas schema brocade-mct 2011-06-21 yang
 namespace urn:brocade.com:mgmt:brocade-mct
 location [ NETCONF ]
netconf-state schemas schema brocade-mld-snooping 2013-07-29 yang
 namespace urn:brocade.com:mgmt:brocade-mld-snooping
 location [ NETCONF ]
netconf-state schemas schema brocade-netconf-ext 2012-02-03 yang
 namespace urn:brocade.com:mgmt:brocade-netconf-ext
 location [ NETCONF ]
netconf-state schemas schema brocade-nsm-operational 2017-04-01 yang
 namespace urn:brocade.com:mgmt:brocade-nsm-operational
 location [ NETCONF ]
netconf-state schemas schema brocade-ntp 2009-05-01 yang
 namespace urn:brocade.com:mgmt:brocade-ntp
 location [ NETCONF ]
netconf-state schemas schema brocade-openflow 2014-08-12 yang
 namespace urn:brocade.com:mgmt:brocade-openflow
 location [ NETCONF ]
netconf-state schemas schema brocade-openflow-operational 2017-04-01 yang
 namespace urn:brocade.com:mgmt:brocade-openflow-operational
 location [ NETCONF ]
netconf-state schemas schema brocade-ospf 2010-11-29 yang
 namespace urn:brocade.com:mgmt:brocade-ospf
 location [ NETCONF ]
netconf-state schemas schema brocade-ospfv3 2013-08-25 yang
 namespace urn:brocade.com:mgmt:brocade-ospfv3
 location [ NETCONF ]
netconf-state schemas schema brocade-packet-timestamp 2016-07-20 yang
 namespace urn:brocade.com:mgmt:brocade-packet-timestamp
 location [ NETCONF ]
netconf-state schemas schema brocade-pld 2010-04-28 yang
 namespace urn:brocade.com:mgmt:brocade-pld
 location [ NETCONF ]
netconf-state schemas schema brocade-ptp 2015-06-24 yang
 namespace urn:brocade.com:mgmt:brocade-ptp
 location [ NETCONF ]
netconf-state schemas schema brocade-ptp-operational 2017-04-01 yang
 namespace urn:brocade.com:mgmt:brocade-ptp-operational
 location [ NETCONF ]
netconf-state schemas schema brocade-pw-profile 2014-04-14 yang
 namespace urn:brocade.com:mgmt:brocade-pw-profile
 location [ NETCONF ]
netconf-state schemas schema brocade-pwm-operational 2017-04-01 yang
 namespace urn:brocade.com:mgmt:brocade-pwm-operational
 location [ NETCONF ]
netconf-state schemas schema brocade-qos-cee 2011-04-18 yang
 namespace urn:brocade.com:mgmt:brocade-qos-cee
 location [ NETCONF ]
netconf-state schemas schema brocade-qos-cpu 2016-01-28 yang
 namespace urn:brocade.com:mgmt:brocade-qos-cpu
 location [ NETCONF ]
netconf-state schemas schema brocade-qos-mls 2010-04-28 yang
 namespace urn:brocade.com:mgmt:brocade-qos-mls
 location [ NETCONF ]
netconf-state schemas schema brocade-qos-mpls 2015-04-07 yang
 namespace urn:brocade.com:mgmt:brocade-qos-mpls
 location [ NETCONF ]
netconf-state schemas schema brocade-qos-mqc 2011-03-04 yang
 namespace urn:brocade.com:mgmt:brocade-qos-mqc
 location [ NETCONF ]
netconf-state schemas schema brocade-ras 2011-04-11 yang
 namespace urn:brocade.com:mgmt:brocade-ras
 location [ NETCONF ]
netconf-state schemas schema brocade-ras-ext 2011-01-20 yang
 namespace urn:brocade.com:mgmt:brocade-ras-ext
 location [ NETCONF ]
netconf-state schemas schema brocade-rbridge-lag 2015-03-16 yang
 namespace urn:brocade.com:mgmt:brocade-rbridge-lag
 location [ NETCONF ]
netconf-state schemas schema brocade-resource-monitor 2016-02-08 yang
 namespace urn:brocade.com:mgmt:brocade-resource-monitor
 location [ NETCONF ]
netconf-state schemas schema brocade-rmon 2011-02-28 yang
 namespace urn:brocade.com:mgmt:brocade-rmon
 location [ NETCONF ]
netconf-state schemas schema brocade-rtm 2011-09-28 yang
 namespace urn:brocade.com:mgmt:brocade-rtm
 location [ NETCONF ]
netconf-state schemas schema brocade-sec-services 2012-07-28 yang
 namespace urn:brocade.com:mgmt:brocade-sec-services
 location [ NETCONF ]
netconf-state schemas schema brocade-sflow 2009-12-10 yang
 namespace urn:brocade.com:mgmt:brocade-sflow
 location [ NETCONF ]
netconf-state schemas schema brocade-snmp 2011-03-18 yang
 namespace urn:brocade.com:mgmt:brocade-snmp
 location [ NETCONF ]
netconf-state schemas schema brocade-span 2010-04-28 yang
 namespace urn:brocade.com:mgmt:brocade-span
 location [ NETCONF ]
netconf-state schemas schema brocade-sysdiag-operational 2017-04-01 yang
 namespace urn:brocade.com:mgmt:brocade-sysdiag-operational
 location [ NETCONF ]
netconf-state schemas schema brocade-sysmgr 2015-07-22 yang
 namespace urn:brocade.com:mgmt:brocade-sysmgr
 location [ NETCONF ]
netconf-state schemas schema brocade-system 2011-08-09 yang
 namespace urn:brocade.com:mgmt:brocade-system
 location [ NETCONF ]
netconf-state schemas schema brocade-system-capabilities 2016-05-20 yang
 namespace urn:brocade.com:mgmt:brocade-system-capabilities
 location [ NETCONF ]
netconf-state schemas schema brocade-system-monitor 2011-11-16 yang
 namespace urn:brocade.com:mgmt:brocade-system-monitor
 location [ NETCONF ]
netconf-state schemas schema brocade-system-monitor-ext 2011-05-05 yang
 namespace urn:brocade.com:mgmt:brocade-system-monitor-ext
 location [ NETCONF ]
netconf-state schemas schema brocade-telemetry 2016-06-29 yang
 namespace urn:brocade.com:mgmt:brocade-telemetry
 location [ NETCONF ]
netconf-state schemas schema brocade-terminal 2011-04-18 yang
 namespace urn:brocade.com:mgmt:brocade-terminal
 location [ NETCONF ]
netconf-state schemas schema brocade-threshold-monitor 2011-11-24 yang
 namespace urn:brocade.com:mgmt:brocade-threshold-monitor
 location [ NETCONF ]
netconf-state schemas schema brocade-threshold-monitor-ext 2011-05-05 yang
 namespace urn:brocade.com:mgmt:brocade-threshold-monitor-ext
 location [ NETCONF ]
netconf-state schemas schema brocade-vcs 2011-05-26 yang
 namespace urn:brocade.com:mgmt:brocade-vcs
 location [ NETCONF ]
netconf-state schemas schema brocade-vlan 2016-02-23 yang
 namespace urn:brocade.com:mgmt:brocade-vlan
 location [ NETCONF ]
netconf-state schemas schema brocade-vrf 2012-04-28 yang
 namespace urn:brocade.com:mgmt:brocade-vrf
 location [ NETCONF ]
netconf-state schemas schema brocade-vrrp 2011-10-31 yang
 namespace urn:brocade.com:mgmt:brocade-vrrp
 location [ NETCONF ]
netconf-state schemas schema brocade-vrrpv3 2013-10-21 yang
 namespace urn:brocade.com:mgmt:brocade-vrrpv3
 location [ NETCONF ]
netconf-state schemas schema brocade-xstp 2011-07-05 yang
 namespace urn:brocade.com:mgmt:brocade-xstp
 location [ NETCONF ]
netconf-state schemas schema brocade-xstp-ext 2011-02-22 yang
 namespace urn:brocade.com:mgmt:brocade-xstp-ext
 location [ NETCONF ]
netconf-state schemas schema brocade-zone 2010-12-01 yang
 namespace urn:brocade.com:mgmt:brocade-zone
 location [ NETCONF ]
netconf-state schemas schema ietf-inet-types 2010-09-24 yang
 namespace urn:ietf:params:xml:ns:yang:ietf-inet-types
 location [ NETCONF ]
netconf-state schemas schema ietf-netconf 2011-06-01 yang
 namespace urn:ietf:params:xml:ns:netconf:base:1.0
 location [ NETCONF ]
netconf-state schemas schema ietf-netconf-acm 2012-02-22 yang
 namespace urn:ietf:params:xml:ns:yang:ietf-netconf-acm
 location [ NETCONF ]
netconf-state schemas schema ietf-netconf-monitoring 2010-10-04 yang
 namespace urn:ietf:params:xml:ns:yang:ietf-netconf-monitoring
 location [ NETCONF ]
netconf-state schemas schema ietf-netconf-notifications 2012-02-06 yang
 namespace urn:ietf:params:xml:ns:yang:ietf-netconf-notifications
 location [ NETCONF ]
netconf-state schemas schema ietf-netconf-notifications-ann "" yang
 namespace urn:dummy
 location [ NETCONF ]
netconf-state schemas schema ietf-netconf-with-defaults 2011-06-01 yang
 namespace urn:ietf:params:xml:ns:yang:ietf-netconf-with-defaults
 location [ NETCONF ]
netconf-state schemas schema ietf-yang-smiv2 2011-11-25 yang
 namespace urn:ietf:params:xml:ns:yang:ietf-yang-smiv2
 location [ NETCONF ]
netconf-state schemas schema ietf-yang-types 2010-09-24 yang
 namespace urn:ietf:params:xml:ns:yang:ietf-yang-types
 location [ NETCONF ]
netconf-state schemas schema tailf-aaa 2011-09-22 yang
 namespace http://tail-f.com/ns/aaa/1.1
 location [ NETCONF ]
netconf-state schemas schema tailf-acm 2013-03-07 yang
 namespace http://tail-f.com/yang/acm
 location [ NETCONF ]
netconf-state schemas schema tailf-cli-extensions 2012-11-08 yang
 namespace http://tail-f.com/yang/common
 location [ NETCONF ]
netconf-state schemas schema tailf-common 2013-11-01 yang
 namespace http://tail-f.com/yang/common
 location [ NETCONF ]
netconf-state schemas schema tailf-common-monitoring 2013-06-14 yang
 namespace http://tail-f.com/yang/common-monitoring
 location [ NETCONF ]
netconf-state schemas schema tailf-confd-monitoring 2013-06-14 yang
 namespace http://tail-f.com/yang/confd-monitoring
 location [ NETCONF ]
netconf-state schemas schema tailf-meta-extensions 2010-08-19 yang
 namespace http://tail-f.com/yang/common
 location [ NETCONF ]
netconf-state schemas schema tailf-netconf-monitoring 2012-06-14 yang
 namespace http://tail-f.com/yang/netconf-monitoring
 location [ NETCONF ]
netconf-state schemas schema tailf-webui 2013-03-07 yang
 namespace http://tail-f.com/ns/webui
 location [ NETCONF ]
netconf-state schemas schema tailf-xsd-types 2009-03-17 yang
 namespace http://www.w3.org/2001/XMLSchema
 location [ NETCONF ]
spine1#
```
