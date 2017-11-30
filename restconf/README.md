# RESTCONF on SLX

## Introduction to RESTCONF:
- 
- 
- 

## In the context of SLX-OS:
- The base URI (http://host:port/rest/) is the entry point to access and manage all the resources defined in the system.By default, the HTTP port number is 80.
- The base resource consists of 
	- Configuration resource (**/config**)
	- YANG-RPC Operations resource (**/operations**)
	- Operational-state (**/operational-state**) resources as first-level child resources.
- The URI path conveys a resource model that is similar to the YANG model, with each forward slash-separated path segment corresponding to a unique resource within the model's hierarchy (using the following syntax: <base_URI>/path1/path2/{key1},{key2}/path3/...).
- URI encoding:
	- A key that contains a forward slash (/) must be contained within a pair of double quotes("). The double quotes character is encoded as %22. For example, a value of 1/1 for {interface-name} is represented in a URI as "1/1", which is encoded as %221/1%22.


## Running Configuration API:

### Entire running config:

```
mab@mab-infra:~$ st2 run core.http username=admin password=********** url=http://192.168.254.115:80/rest/config/running/
.
id: 5a20316f7cae220a3a55880c
status: succeeded
parameters: 
  password: **********
  url: http://192.168.254.115:80/rest/config/running/
  username: admin
result: 
  body: "<data xmlns=\"http://brocade.com/ns/rest\" xmlns:y=\"http://brocade.com/ns/rest\" y:self=\"/rest/config/running\">\r\n<root xmlns=\"urn:brocade.com:mgmt:brocade-aaa\" y:self=\"/rest/config/running/root\">\r\n  <enable>false</enable>\r\n</root>\r\n<alias-config xmlns=\"urn:brocade.com:mgmt:brocade-aaa\" y:self=\"/rest/config/running/alias-config\">\r\n</alias-config>\r\n<chassis xmlns=\"urn:brocade.com:mgmt:brocade-chassis\" y:self=\"/rest/config/running/chassis\">\r\n  <virtual-ip y:self=\"/rest/config/running/chassis/virtual-ip\">\r\n  </virtual-ip>\r\n</chassis>\r\n<clock xmlns=\"urn:brocade.com:mgmt:brocade-clock\" y:self=\"/rest/config/running/clock\">\r\n  <timezone>Etc/GMT</timezone>\r\n</clock>\r\n<event-handler xmlns=\"urn:brocade.com:mgmt:brocade-event-handler\" y:self=\"/rest/config/running/event-handler\">\r\n  <activate y:self=\"/rest/config/running/event-handler/activate\">\r\n  </activate>\r\n</event-handler>\r\n<hardware xmlns=\"urn:brocade.com:mgmt:brocade-hardware\" y:self=\"/rest/config/running/hardware\">\r\n  <profile y:self=\"/rest/config/running/hardware/profile\">\r\n    <tcam y:self=\"/rest/config/running/hardware/profile/tcam\">\r\n      <tcam_profiletype>default</tcam_profiletype>\r\n    </tcam>\r\n    <route-table y:self=\"/rest/config/running/hardware/profile/route-table\">\r\n      <routing_profiletype>default</routing_profiletype>\r\n      <maximum_paths>8</maximum_paths>\r\n    </route-table>\r\n  </profile>\r\n  <system-mode>default</system-mode>\r\n</hardware>\r\n<http xmlns=\"urn:brocade.com:mgmt:brocade-http\" y:self=\"/rest/config/running/http\">\r\n  <server y:self=\"/rest/config/running/http/server\">\r\n    <use-vrf y:self=\"/rest/config/running/http/server/use-vrf/default-vrf\">\r\n      <use-vrf-name>default-vrf</use-vrf-name>\r\n    </use-vrf>\r\n    <use-vrf y:self=\"/rest/config/running/http/server/use-vrf/mgmt-vrf\">\r\n      <use-vrf-name>mgmt-vrf</use-vrf-name>\r\n    </use-vrf>\r\n  </server>\r\n</http>\r\n<link-fault-signaling xmlns=\"urn:brocade.com:mgmt:brocade-lfs\" y:self=\"/rest/config/running/link-fault-signaling\">\r\n</link-fault-signaling>\r\n<ntp xmlns=\"urn:brocade.com:mgmt:brocade-ntp\" y:self=\"/rest/config/running/ntp\">\r\n</ntp>\r\n<openflow xmlns=\"urn:brocade.com:mgmt:brocade-openflow\" y:self=\"/rest/config/running/openflow\">\r\n  <enable y:self=\"/rest/config/running/openflow/enable\">\r\n  </enable>\r\n  <default-behavior y:self=\"/rest/config/running/openflow/default-behavior\">\r\n  </default-behavior>\r\n</openflow>\r\n<logging xmlns=\"urn:brocade.com:mgmt:brocade-ras\" y:self=\"/rest/config/running/logging\">\r\n  <raslog y:self=\"/rest/config/running/logging/raslog\">\r\n    <interface y:self=\"/rest/config/running/logging/raslog/interface\">\r\n    </interface>\r\n    <console>INFO</console>\r\n  </raslog>\r\n  <auditlog y:self=\"/rest/config/running/logging/auditlog\">\r\n    <class y:self=\"/rest/config/running/logging/auditlog/class/SECURITY\">\r\n      <class>SECURITY</class>\r\n    </class>\r\n    <class y:self=\"/rest/config/running/logging/auditlog/class/CONFIGURATION\">\r\n      <class>CONFIGURATION</class>\r\n    </class>\r\n    <class y:self=\"/rest/config/running/logging/auditlog/class/FIRMWARE\">\r\n      <class>FIRMWARE</class>\r\n    </class>\r\n  </auditlog>\r\n  <syslog-facility y:self=\"/rest/config/running/logging/syslog-facility\">\r\n    <local>LOG_LOCAL7</local>\r\n  </syslog-facility>\r\n  <syslog-client y:self=\"/rest/config/running/logging/syslog-client\">\r\n    <localip>CHASSIS_IP</localip>\r\n  </syslog-client>\r\n</logging>\r\n<switch-attributes xmlns=\"urn:brocade.com:mgmt:brocade-ras\" y:self=\"/rest/config/running/switch-attributes\">\r\n  <chassis-name>spine1</chassis-name>\r\n  <host-name>spine1</host-name>\r\n</switch-attributes>\r\n<support xmlns=\"urn:brocade.com:mgmt:brocade-ras\" y:self=\"/rest/config/running/support\">\r\n  <autoupload-param y:self=\"/rest/config/running/support/autoupload-param\">\r\n  </autoupload-param>\r\n  <support-param y:self=\"/rest/config/running/support/support-param\">\r\n  </support-param>\r\n  <autoupload y:self=\"/rest/config/running/support/autoupload\">\r\n  </autoupload>\r\n  <ffdc>true</ffdc>\r\n</support>\r\n<load-balance xmlns=\"urn:brocade.com:mgmt:brocade-rbridge-lag\" y:self=\"/rest/config/running/load-balance\">\r\n</load-balance>\r\n<resource-monitor xmlns=\"urn:brocade.com:mgmt:brocade-resource-monitor\" y:self=\"/rest/config/running/resource-monitor\">\r\n  <cpu y:self=\"/rest/config/running/resource-monitor/cpu\">\r\n    <enable>true</enable>\r\n    <threshold>90</threshold>\r\n    <action>raslog</action>\r\n  </cpu>\r\n  <memory y:self=\"/rest/config/running/resource-monitor/memory\">\r\n    <enable>true</enable>\r\n    <threshold>100</threshold>\r\n    <action>raslog</action>\r\n  </memory>\r\n  <process y:self=\"/rest/config/running/resource-monitor/process\">\r\n    <memory y:self=\"/rest/config/running/resource-monitor/process/memory\">\r\n      <enable>true</enable>\r\n      <alarm>1000</alarm>\r\n      <critical>1200</critical>\r\n    </memory>\r\n  </process>\r\n</resource-monitor>\r\n<snmp-server xmlns=\"urn:brocade.com:mgmt:brocade-snmp\" y:self=\"/rest/config/running/snmp-server\">\r\n  <contact>&quot;Field Support.&quot;</contact>\r\n  <location>&quot;End User Premise.&quot;</location>\r\n  <sys-descr>&quot;Brocade BR-SLX9240 Router&quot;</sys-descr>\r\n  <enable y:self=\"/rest/config/running/snmp-server/enable\">\r\n    <trap y:self=\"/rest/config/running/snmp-server/enable/trap\">\r\n      <trap-flag>true</trap-flag>\r\n    </trap>\r\n  </enable>\r\n  <engineID y:self=\"/rest/config/running/snmp-server/engineID\">\r\n  </engineID>\r\n</snmp-server>\r\n<sysmon xmlns=\"urn:brocade.com:mgmt:brocade-sysmon\" y:self=\"/rest/config/running/sysmon\">\r\n  <fe-access-check y:self=\"/rest/config/running/sysmon/fe-access-check\">\r\n  </fe-access-check>\r\n  <link-crc-monitoring y:self=\"/rest/config/running/sysmon/link-crc-monitoring\">\r\n  </link-crc-monitoring>\r\n  <sfm-walk y:self=\"/rest/config/running/sysmon/sfm-walk\">\r\n  </sfm-walk>\r\n</sysmon>\r\n<system-monitor xmlns=\"urn:brocade.com:mgmt:brocade-system-monitor\" y:self=\"/rest/config/running/system-monitor\">\r\n  <fan y:self=\"/rest/config/running/system-monitor/fan\">\r\n    <threshold y:self=\"/rest/config/running/system-monitor/fan/threshold\">\r\n      <marginal-threshold>1</marginal-threshold>\r\n      <down-threshold>2</down-threshold>\r\n    </threshold>\r\n    <alert y:self=\"/rest/config/running/system-monitor/fan/alert\">\r\n      <state>removed</state>\r\n      <action>raslog</action>\r\n    </alert>\r\n  </fan>\r\n  <power y:self=\"/rest/config/running/system-monitor/power\">\r\n    <threshold y:self=\"/rest/config/running/system-monitor/power/threshold\">\r\n      <marginal-threshold>1</marginal-threshold>\r\n      <down-threshold>2</down-threshold>\r\n    </threshold>\r\n    <alert y:self=\"/rest/config/running/system-monitor/power/alert\">\r\n      <state>removed</state>\r\n      <action>raslog</action>\r\n    </alert>\r\n  </power>\r\n  <temp y:self=\"/rest/config/running/system-monitor/temp\">\r\n    <threshold y:self=\"/rest/config/running/system-monitor/temp/threshold\">\r\n      <marginal-threshold>1</marginal-threshold>\r\n      <down-threshold>2</down-threshold>\r\n    </threshold>\r\n  </temp>\r\n  <cid-card y:self=\"/rest/config/running/system-monitor/cid-card\">\r\n    <threshold y:self=\"/rest/config/running/system-monitor/cid-card/threshold\">\r\n      <marginal-threshold>1</marginal-threshold>\r\n      <down-threshold>2</down-threshold>\r\n    </threshold>\r\n    <alert y:self=\"/rest/config/running/system-monitor/cid-card/alert\">\r\n      <state>none</state>\r\n      <action>none</action>\r\n    </alert>\r\n  </cid-card>\r\n  <compact-flash y:self=\"/rest/config/running/system-monitor/compact-flash\">\r\n    <threshold y:self=\"/rest/config/running/system-monitor/compact-flash/threshold\">\r\n      <marginal-threshold>1</marginal-threshold>\r\n      <down-threshold>0</down-threshold>\r\n    </threshold>\r\n  </compact-flash>\r\n  <MM y:self=\"/rest/config/running/system-monitor/MM\">\r\n    <threshold y:self=\"/rest/config/running/system-monitor/MM/threshold\">\r\n      <marginal-threshold>1</marginal-threshold>\r\n      <down-threshold>0</down-threshold>\r\n    </threshold>\r\n  </MM>\r\n  <LineCard y:self=\"/rest/config/running/system-monitor/LineCard\">\r\n    <threshold y:self=\"/rest/config/running/system-monitor/LineCard/threshold\">\r\n      <marginal-threshold>1</marginal-threshold>\r\n      <down-threshold>2</down-threshold>\r\n    </threshold>\r\n    <alert y:self=\"/rest/config/running/system-monitor/LineCard/alert\">\r\n      <state>none</state>\r\n      <action>none</action>\r\n    </alert>\r\n  </LineCard>\r\n  <SFM y:self=\"/rest/config/running/system-monitor/SFM\">\r\n    <threshold y:self=\"/rest/config/running/system-monitor/SFM/threshold\">\r\n      <marginal-threshold>1</marginal-threshold>\r\n      <down-threshold>2</down-threshold>\r\n    </threshold>\r\n  </SFM>\r\n</system-monitor>\r\n<system-monitor-mail xmlns=\"urn:brocade.com:mgmt:brocade-system-monitor\" y:self=\"/rest/config/running/system-monitor-mail\">\r\n  <fru y:self=\"/rest/config/running/system-monitor-mail/fru\">\r\n  </fru>\r\n  <sfp y:self=\"/rest/config/running/system-monitor-mail/sfp\">\r\n  </sfp>\r\n  <security y:self=\"/rest/config/running/system-monitor-mail/security\">\r\n  </security>\r\n  <interface y:self=\"/rest/config/running/system-monitor-mail/interface\">\r\n  </interface>\r\n</system-monitor-mail>\r\n<telemetry xmlns=\"urn:brocade.com:mgmt:brocade-telemetry\" y:self=\"/rest/config/running/telemetry\">\r\n  <profile y:self=\"/rest/config/running/telemetry/profile\">\r\n    <system-utilization y:self=\"/rest/config/running/telemetry/profile/system-utilization/default_system_utilization_statistics\">\r\n      <name>default_system_utilization_statistics</name>\r\n    </system-utilization>\r\n    <interface y:self=\"/rest/config/running/telemetry/profile/interface/default_interface_statistics\">\r\n      <name>default_interface_statistics</name>\r\n    </interface>\r\n  </profile>\r\n</telemetry>\r\n<line xmlns=\"urn:brocade.com:mgmt:brocade-terminal\" y:self=\"/rest/config/running/line/vty\">\r\n  <sessionid>vty</sessionid>\r\n</line>\r\n<threshold-monitor xmlns=\"urn:brocade.com:mgmt:brocade-threshold-monitor\" y:self=\"/rest/config/running/threshold-monitor\">\r\n  <sfp y:self=\"/rest/config/running/threshold-monitor/sfp\">\r\n    <pause>false</pause>\r\n    <policy y:self=\"/rest/config/running/threshold-monitor/sfp/policy/\">\r\n    </policy>\r\n  </sfp>\r\n  <Cpu y:self=\"/rest/config/running/threshold-monitor/Cpu\">\r\n  </Cpu>\r\n  <Memory y:self=\"/rest/config/running/threshold-monitor/Memory\">\r\n  </Memory>\r\n  <Buffer y:self=\"/rest/config/running/threshold-monitor/Buffer\">\r\n    <limit>70</limit>\r\n  </Buffer>\r\n</threshold-monitor>\r\n<vrf xmlns=\"urn:brocade.com:mgmt:brocade-vrf\" y:self=\"/rest/config/running/vrf/mgmt-vrf\">\r\n  <vrf-name>mgmt-vrf</vrf-name>\r\n</vrf>\r\n<ssh xmlns=\"urn:brocade.com:mgmt:brocade-sec-services\" y:self=\"/rest/config/running/ssh\">\r\n  <server y:self=\"/rest/config/running/ssh/server\">\r\n    <standby y:self=\"/rest/config/running/ssh/server/standby\">\r\n      <enable>false</enable>\r\n    </standby>\r\n    <key y:self=\"/rest/config/running/ssh/server/key\">\r\n      <rsa>2048</rsa>\r\n      <ecdsa>256</ecdsa>\r\n      <dsa>true</dsa>\r\n    </key>\r\n    <use-vrf y:self=\"/rest/config/running/ssh/server/use-vrf/default-vrf\">\r\n      <use-vrf-name>default-vrf</use-vrf-name>\r\n    </use-vrf>\r\n    <use-vrf y:self=\"/rest/config/running/ssh/server/use-vrf/mgmt-vrf\">\r\n      <use-vrf-name>mgmt-vrf</use-vrf-name>\r\n    </use-vrf>\r\n  </server>\r\n  <client y:self=\"/rest/config/running/ssh/client\">\r\n    <source-interface y:self=\"/rest/config/running/ssh/client/source-interface\">\r\n    </source-interface>\r\n  </client>\r\n</ssh>\r\n<telnet xmlns=\"urn:brocade.com:mgmt:brocade-sec-services\" y:self=\"/rest/config/running/telnet\">\r\n  <server y:self=\"/rest/config/running/telnet/server\">\r\n    <standby y:self=\"/rest/config/running/telnet/server/standby\">\r\n      <enable>false</enable>\r\n    </standby>\r\n    <use-vrf y:self=\"/rest/config/running/telnet/server/use-vrf/default-vrf\">\r\n      <use-vrf-name>default-vrf</use-vrf-name>\r\n    </use-vrf>\r\n    <use-vrf y:self=\"/rest/config/running/telnet/server/use-vrf/mgmt-vrf\">\r\n      <use-vrf-name>mgmt-vrf</use-vrf-name>\r\n    </use-vrf>\r\n  </server>\r\n  <client y:self=\"/rest/config/running/telnet/client\">\r\n    <source-interface y:self=\"/rest/config/running/telnet/client/source-interface\">\r\n    </source-interface>\r\n  </client>\r\n</telnet>\r\n<banner xmlns=\"urn:brocade.com:mgmt:brocade-aaa\" y:self=\"/rest/config/running/banner\">\r\n</banner>\r\n<password-attributes xmlns=\"urn:brocade.com:mgmt:brocade-aaa\" y:self=\"/rest/config/running/password-attributes\">\r\n  <character-restriction y:self=\"/rest/config/running/password-attributes/character-restriction\">\r\n  </character-restriction>\r\n  <admin-lockout>false</admin-lockout>\r\n</password-attributes>\r\n<role xmlns=\"urn:brocade.com:mgmt:brocade-aaa\" y:self=\"/rest/config/running/role\">\r\n  <name y:self=\"/rest/config/running/role/name/admin\">\r\n    <name>admin</name>\r\n  </name>\r\n  <name y:self=\"/rest/config/running/role/name/user\">\r\n    <name>user</name>\r\n  </name>\r\n</role>\r\n<radius-server xmlns=\"urn:brocade.com:mgmt:brocade-aaa\" y:self=\"/rest/config/running/radius-server\">\r\n</radius-server>\r\n<tacacs-server xmlns=\"urn:brocade.com:mgmt:brocade-aaa\" y:self=\"/rest/config/running/tacacs-server\">\r\n</tacacs-server>\r\n<ldap-server xmlns=\"urn:brocade.com:mgmt:brocade-aaa\" y:self=\"/rest/config/running/ldap-server\">\r\n</ldap-server>\r\n<aaa xmlns=\"urn:brocade.com:mgmt:brocade-aaa\" y:self=\"/rest/config/running/aaa\">\r\n  <authentication y:self=\"/rest/config/running/aaa/authentication\">\r\n    <login y:self=\"/rest/config/running/aaa/authentication/login\">\r\n      <first>local</first>\r\n    </login>\r\n  </authentication>\r\n  <accounting y:self=\"/rest/config/running/aaa/accounting\">\r\n    <exec y:self=\"/rest/config/running/aaa/accounting/exec\">\r\n      <default y:self=\"/rest/config/running/aaa/accounting/exec/default\">\r\n        <start-stop y:self=\"/rest/config/running/aaa/accounting/exec/default/start-stop\">\r\n          <server-type>none</server-type>\r\n        </start-stop>\r\n      </default>\r\n    </exec>\r\n    <commands y:self=\"/rest/config/running/aaa/accounting/commands\">\r\n      <default y:self=\"/rest/config/running/aaa/accounting/commands/default\">\r\n        <start-stop y:self=\"/rest/config/running/aaa/accounting/commands/default/start-stop\">\r\n          <server-type>none</server-type>\r\n        </start-stop>\r\n      </default>\r\n    </commands>\r\n  </accounting>\r\n</aaa>\r\n<service xmlns=\"urn:brocade.com:mgmt:brocade-aaa\" y:self=\"/rest/config/running/service\">\r\n  <password-encryption>true</password-encryption>\r\n</service>\r\n<username xmlns=\"urn:brocade.com:mgmt:brocade-aaa\" y:self=\"/rest/config/running/username/admin\">\r\n  <name>admin</name>\r\n</username>\r\n<username xmlns=\"urn:brocade.com:mgmt:brocade-aaa\" y:self=\"/rest/config/running/username/user\">\r\n  <name>user</name>\r\n</username>\r\n<cee-map xmlns=\"urn:brocade.com:mgmt:brocade-qos-cee\" y:self=\"/rest/config/running/cee-map/default\">\r\n  <name>default</name>\r\n</cee-map>\r\n<ipv6 xmlns=\"urn:brocade.com:mgmt:brocade-common-def\" y:self=\"/rest/config/running/ipv6\">\r\n  <protocol xmlns=\"urn:brocade.com:mgmt:brocade-vrrpv3\" y:self=\"/rest/config/running/ipv6/protocol\">\r\n  </protocol>\r\n  <route xmlns=\"urn:brocade.com:mgmt:brocade-ipv6-rtm\" y:self=\"/rest/config/running/ipv6/route\">\r\n    <static y:self=\"/rest/config/running/ipv6/route/static\">\r\n      <bfd y:self=\"/rest/config/running/ipv6/route/static/bfd\">\r\n      </bfd>\r\n    </static>\r\n  </route>\r\n  <nd xmlns=\"urn:brocade.com:mgmt:brocade-ipv6-nd-ra\" y:self=\"/rest/config/running/ipv6/nd\">\r\n  </nd>\r\n</ipv6>\r\n<ip xmlns=\"urn:brocade.com:mgmt:brocade-ip-access-list\" y:self=\"/rest/config/running/ip\">\r\n  <access-list y:self=\"/rest/config/running/ip/access-list\">\r\n    <extended y:self=\"/rest/config/running/ip/access-list/extended/acl_10\">\r\n      <name>acl_10</name>\r\n    </extended>\r\n  </access-list>\r\n  <igmp xmlns=\"urn:brocade.com:mgmt:brocade-igmp-snooping\" y:self=\"/rest/config/running/ip/igmp\">\r\n    <ssm-map y:self=\"/rest/config/running/ip/igmp/ssm-map\">\r\n    </ssm-map>\r\n  </igmp>\r\n</ip>\r\n<vlan xmlns=\"urn:brocade.com:mgmt:brocade-interface\" y:self=\"/rest/config/running/vlan/1\">\r\n  <name>1</name>\r\n</vlan>\r\n<vlan xmlns=\"urn:brocade.com:mgmt:brocade-interface\" y:self=\"/rest/config/running/vlan/10\">\r\n  <name>10</name>\r\n</vlan>\r\n<vlan xmlns=\"urn:brocade.com:mgmt:brocade-interface\" y:self=\"/rest/config/running/vlan/200\">\r\n  <name>200</name>\r\n</vlan>\r\n<qos xmlns=\"urn:brocade.com:mgmt:brocade-qos-mls\" y:self=\"/rest/config/running/qos\">\r\n  <map y:self=\"/rest/config/running/qos/map\">\r\n    <cos-mutation y:self=\"/rest/config/running/qos/map/cos-mutation/all-zero-map\">\r\n      <name>all-zero-map</name>\r\n    </cos-mutation>\r\n    <cos-mutation y:self=\"/rest/config/running/qos/map/cos-mutation/default\">\r\n      <name>default</name>\r\n    </cos-mutation>\r\n    <cos-traffic-class y:self=\"/rest/config/running/qos/map/cos-traffic-class/all-zero-map\">\r\n      <name>all-zero-map</name>\r\n    </cos-traffic-class>\r\n    <cos-traffic-class y:self=\"/rest/config/running/qos/map/cos-traffic-class/default\">\r\n      <name>default</name>\r\n    </cos-traffic-class>\r\n    <cos-dscp y:self=\"/rest/config/running/qos/map/cos-dscp/all-zero-map\">\r\n      <name>all-zero-map</name>\r\n    </cos-dscp>\r\n    <cos-dscp y:self=\"/rest/config/running/qos/map/cos-dscp/default\">\r\n      <name>default</name>\r\n    </cos-dscp>\r\n    <traffic-class-cos y:self=\"/rest/config/running/qos/map/traffic-class-cos/all-zero-map\">\r\n      <traffic-class-cos-map-name>all-zero-map</traffic-class-cos-map-name>\r\n    </traffic-class-cos>\r\n    <traffic-class-cos y:self=\"/rest/config/running/qos/map/traffic-class-cos/default\">\r\n      <traffic-class-cos-map-name>default</traffic-class-cos-map-name>\r\n    </traffic-class-cos>\r\n    <traffic-class-mutation y:self=\"/rest/config/running/qos/map/traffic-class-mutation/all-zero-map\">\r\n      <name>all-zero-map</name>\r\n    </traffic-class-mutation>\r\n    <traffic-class-mutation y:self=\"/rest/config/running/qos/map/traffic-class-mutation/default\">\r\n      <name>default</name>\r\n    </traffic-class-mutation>\r\n    <traffic-class-dscp y:self=\"/rest/config/running/qos/map/traffic-class-dscp/all-zero-map\">\r\n      <name>all-zero-map</name>\r\n    </traffic-class-dscp>\r\n    <traffic-class-dscp y:self=\"/rest/config/running/qos/map/traffic-class-dscp/default\">\r\n      <name>default</name>\r\n    </traffic-class-dscp>\r\n    <dscp-mutation y:self=\"/rest/config/running/qos/map/dscp-mutation/all-zero-map\">\r\n      <dscp-mutation-map-name>all-zero-map</dscp-mutation-map-name>\r\n    </dscp-mutation>\r\n    <dscp-mutation y:self=\"/rest/config/running/qos/map/dscp-mutation/default\">\r\n      <dscp-mutation-map-name>default</dscp-mutation-map-name>\r\n    </dscp-mutation>\r\n    <dscp-traffic-class y:self=\"/rest/config/running/qos/map/dscp-traffic-class/all-zero-map\">\r\n      <dscp-traffic-class-map-name>all-zero-map</dscp-traffic-class-map-name>\r\n    </dscp-traffic-class>\r\n    <dscp-traffic-class y:self=\"/rest/config/running/qos/map/dscp-traffic-class/default\">\r\n      <dscp-traffic-class-map-name>default</dscp-traffic-class-map-name>\r\n    </dscp-traffic-class>\r\n    <dscp-cos y:self=\"/rest/config/running/qos/map/dscp-cos/all-zero-map\">\r\n      <dscp-cos-map-name>all-zero-map</dscp-cos-map-name>\r\n    </dscp-cos>\r\n    <dscp-cos y:self=\"/rest/config/running/qos/map/dscp-cos/default\">\r\n      <dscp-cos-map-name>default</dscp-cos-map-name>\r\n    </dscp-cos>\r\n  </map>\r\n  <tx-queue y:self=\"/rest/config/running/qos/tx-queue\">\r\n    <scheduler y:self=\"/rest/config/running/qos/tx-queue/scheduler\">\r\n      <strict-priority y:self=\"/rest/config/running/qos/tx-queue/scheduler/strict-priority\">\r\n      </strict-priority>\r\n    </scheduler>\r\n  </tx-queue>\r\n</qos>\r\n<qos-mpls xmlns=\"urn:brocade.com:mgmt:brocade-qos-mpls\" y:self=\"/rest/config/running/qos-mpls\">\r\n  <map-apply xmlns=\"urn:brocade.com:mgmt:brocade-apply-qos-mpls\" y:self=\"/rest/config/running/qos-mpls/map-apply\">\r\n    <exp-traffic-class y:self=\"/rest/config/running/qos-mpls/map-apply/exp-traffic-class\">\r\n    </exp-traffic-class>\r\n    <traffic-class-exp y:self=\"/rest/config/running/qos-mpls/map-apply/traffic-class-exp\">\r\n    </traffic-class-exp>\r\n    <dscp-exp y:self=\"/rest/config/running/qos-mpls/map-apply/dscp-exp\">\r\n    </dscp-exp>\r\n    <exp-dscp y:self=\"/rest/config/running/qos-mpls/map-apply/exp-dscp\">\r\n    </exp-dscp>\r\n  </map-apply>\r\n</qos-mpls>\r\n<protocol xmlns=\"urn:brocade.com:mgmt:brocade-interface\" y:self=\"/rest/config/running/protocol\">\r\n  <lldp xmlns=\"urn:brocade.com:mgmt:brocade-lldp\" y:self=\"/rest/config/running/protocol/lldp\">\r\n    <advertise y:self=\"/rest/config/running/protocol/lldp/advertise\">\r\n      <dcbx-iscsi-app-tlv>false</dcbx-iscsi-app-tlv>\r\n      <dcbx-tlv>true</dcbx-tlv>\r\n      <optional-tlv y:self=\"/rest/config/running/protocol/lldp/advertise/optional-tlv\">\r\n      </optional-tlv>\r\n    </advertise>\r\n    <system-description>Brocade BR-SLX9240 Router</system-description>\r\n    <disable>false</disable>\r\n  </lldp>\r\n</protocol>\r\n<vlan xmlns=\"urn:brocade.com:mgmt:brocade-vlan\" y:self=\"/rest/config/running/vlan\">\r\n  <dot1q y:self=\"/rest/config/running/vlan/dot1q\">\r\n    <tag y:self=\"/rest/config/running/vlan/dot1q/tag\">\r\n      <native>true</native>\r\n    </tag>\r\n  </dot1q>\r\n</vlan>\r\n<lacp xmlns=\"urn:brocade.com:mgmt:brocade-lacp\" y:self=\"/rest/config/running/lacp\">\r\n</lacp>\r\n<dot1x xmlns=\"urn:brocade.com:mgmt:brocade-dot1x\" y:self=\"/rest/config/running/dot1x\">\r\n  <enable>false</enable>\r\n  <test y:self=\"/rest/config/running/dot1x/test\">\r\n  </test>\r\n</dot1x>\r\n<ip xmlns=\"urn:brocade.com:mgmt:brocade-common-def\" y:self=\"/rest/config/running/ip\">\r\n  <route xmlns=\"urn:brocade.com:mgmt:brocade-rtm\" y:self=\"/rest/config/running/ip/route\">\r\n    <static-route-nh y:self=\"/rest/config/running/ip/route/static-route-nh/%220.0.0.0/0%22%2C192.168.254.1\">\r\n      <static-route-dest>0.0.0.0/0</static-route-dest>\r\n      <static-route-next-hop>192.168.254.1</static-route-next-hop>\r\n    </static-route-nh>\r\n    <static y:self=\"/rest/config/running/ip/route/static\">\r\n      <bfd y:self=\"/rest/config/running/ip/route/static/bfd\">\r\n      </bfd>\r\n    </static>\r\n  </route>\r\n  <import y:self=\"/rest/config/running/ip/import\">\r\n  </import>\r\n</ip>\r\n<sflow xmlns=\"urn:brocade.com:mgmt:brocade-sflow\" y:self=\"/rest/config/running/sflow\">\r\n  <enable>false</enable>\r\n  <source-interface y:self=\"/rest/config/running/sflow/source-interface\">\r\n  </source-interface>\r\n</sflow>\r\n<police-remark-profile xmlns=\"urn:brocade.com:mgmt:brocade-qos-mqc\" y:self=\"/rest/config/running/police-remark-profile/default\">\r\n  <profile-name>default</profile-name>\r\n</police-remark-profile>\r\n<class-map xmlns=\"urn:brocade.com:mgmt:brocade-qos-mqc\" y:self=\"/rest/config/running/class-map/cee\">\r\n  <name>cee</name>\r\n</class-map>\r\n<class-map xmlns=\"urn:brocade.com:mgmt:brocade-qos-mqc\" y:self=\"/rest/config/running/class-map/default\">\r\n  <name>default</name>\r\n</class-map>\r\n<mac xmlns=\"urn:brocade.com:mgmt:brocade-common-def\" y:self=\"/rest/config/running/mac\">\r\n  <receive xmlns=\"urn:brocade.com:mgmt:brocade-mac-access-list\" y:self=\"/rest/config/running/mac/receive\">\r\n    <access-group y:self=\"/rest/config/running/mac/receive/access-group\">\r\n    </access-group>\r\n  </receive>\r\n</mac>\r\n<ip xmlns=\"urn:brocade.com:mgmt:brocade-common-def\" y:self=\"/rest/config/running/ip\">\r\n  <receive xmlns=\"urn:brocade.com:mgmt:brocade-ip-access-list\" y:self=\"/rest/config/running/ip/receive\">\r\n    <access-group y:self=\"/rest/config/running/ip/receive/access-group\">\r\n    </access-group>\r\n  </receive>\r\n  <dhcp xmlns=\"urn:brocade.com:mgmt:brocade-dhcp\" y:self=\"/rest/config/running/ip/dhcp\">\r\n    <relay y:self=\"/rest/config/running/ip/dhcp/relay\">\r\n      <information y:self=\"/rest/config/running/ip/dhcp/relay/information\">\r\n      </information>\r\n    </relay>\r\n  </dhcp>\r\n</ip>\r\n<ipv6 xmlns=\"urn:brocade.com:mgmt:brocade-common-def\" y:self=\"/rest/config/running/ipv6\">\r\n  <receive xmlns=\"urn:brocade.com:mgmt:brocade-ipv6-access-list\" y:self=\"/rest/config/running/ipv6/receive\">\r\n    <access-group y:self=\"/rest/config/running/ipv6/receive/access-group\">\r\n    </access-group>\r\n  </receive>\r\n</ipv6>\r\n<interface xmlns=\"urn:brocade.com:mgmt:brocade-interface\" y:self=\"/rest/config/running/interface\">\r\n  <Ve y:self=\"/rest/config/running/interface/Ve/100\">\r\n    <name>100</name>\r\n  </Ve>\r\n  <Ve y:self=\"/rest/config/running/interface/Ve/200\">\r\n    <name>200</name>\r\n  </Ve>\r\n</interface>\r\n<interface xmlns=\"urn:brocade.com:mgmt:brocade-interface\" y:self=\"/rest/config/running/interface\">\r\n  <Management y:self=\"/rest/config/running/interface/Management/0\">\r\n    <name>0</name>\r\n  </Management>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/1%22\">\r\n    <name>0/1</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/2%22\">\r\n    <name>0/2</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/3%22\">\r\n    <name>0/3</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/4%22\">\r\n    <name>0/4</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/5%22\">\r\n    <name>0/5</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/6%22\">\r\n    <name>0/6</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/7%22\">\r\n    <name>0/7</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/8%22\">\r\n    <name>0/8</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/9%22\">\r\n    <name>0/9</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/10%22\">\r\n    <name>0/10</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/11%22\">\r\n    <name>0/11</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/12%22\">\r\n    <name>0/12</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/13%22\">\r\n    <name>0/13</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/14%22\">\r\n    <name>0/14</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/15%22\">\r\n    <name>0/15</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/16%22\">\r\n    <name>0/16</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/17%22\">\r\n    <name>0/17</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/18%22\">\r\n    <name>0/18</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/19%22\">\r\n    <name>0/19</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/20%22\">\r\n    <name>0/20</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/21%22\">\r\n    <name>0/21</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/22%22\">\r\n    <name>0/22</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/23%22\">\r\n    <name>0/23</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/24%22\">\r\n    <name>0/24</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/25%22\">\r\n    <name>0/25</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/26%22\">\r\n    <name>0/26</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/27%22\">\r\n    <name>0/27</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/28%22\">\r\n    <name>0/28</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/29%22\">\r\n    <name>0/29</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/30%22\">\r\n    <name>0/30</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/31%22\">\r\n    <name>0/31</name>\r\n  </Ethernet>\r\n  <Ethernet y:self=\"/rest/config/running/interface/Ethernet/%220/32%22\">\r\n    <name>0/32</name>\r\n  </Ethernet>\r\n  <Port-channel y:self=\"/rest/config/running/interface/Port-channel/30\">\r\n    <name>30</name>\r\n  </Port-channel>\r\n</interface>\r\n<mac-address-table xmlns=\"urn:brocade.com:mgmt:brocade-mac-address-table\" y:self=\"/rest/config/running/mac-address-table\">\r\n  <aging-time y:self=\"/rest/config/running/mac-address-table/aging-time\">\r\n  </aging-time>\r\n  <mac-move y:self=\"/rest/config/running/mac-address-table/mac-move\">\r\n  </mac-move>\r\n</mac-address-table>\r\n<rmon xmlns=\"urn:brocade.com:mgmt:brocade-rmon\" y:self=\"/rest/config/running/rmon\">\r\n</rmon>\r\n<monitor xmlns=\"urn:brocade.com:mgmt:brocade-span\" y:self=\"/rest/config/running/monitor\">\r\n</monitor>\r\n<bridge-domain xmlns=\"urn:brocade.com:mgmt:brocade-bridge-domain\" y:self=\"/rest/config/running/bridge-domain/10%2Cp2mp\">\r\n  <bridge-domain-id>10</bridge-domain-id>\r\n  <bridge-domain-type>p2mp</bridge-domain-type>\r\n</bridge-domain>\r\n</data>\r\n"
  headers:
    Authentication-Token: dG94RDF8QldQNn10UUw3bDBWeFA3azthM25cYlp2QDI=
    Cache-control: private, no-cache, must-revalidate, proxy-revalidate
    Connection: Keep-Alive
    Content-Type: application/vnd.configuration.resource+xml
    Date: '2017-12-01 00:26:37'
    Keep-Alive: timeout=180, max=100
    Server: SLX-OS Wave WWW
    Transfer-Encoding: chunked
  parsed: false
  status_code: 200
mab@mab-infra:~/mab_automate/nw_automation_on_slx$ 
mab@mab-infra:~$
mab@mab-infra:~$
mab@mab-infra:~$
mab@mab-infra:~$ st2 execution get 5a20316f7cae220a3a55880c -k body
<data xmlns="http://brocade.com/ns/rest" xmlns:y="http://brocade.com/ns/rest" y:self="/rest/config/running">
<root xmlns="urn:brocade.com:mgmt:brocade-aaa" y:self="/rest/config/running/root">
  <enable>false</enable>
</root>
<alias-config xmlns="urn:brocade.com:mgmt:brocade-aaa" y:self="/rest/config/running/alias-config">
</alias-config>
<chassis xmlns="urn:brocade.com:mgmt:brocade-chassis" y:self="/rest/config/running/chassis">
  <virtual-ip y:self="/rest/config/running/chassis/virtual-ip">
  </virtual-ip>
</chassis>
<clock xmlns="urn:brocade.com:mgmt:brocade-clock" y:self="/rest/config/running/clock">
  <timezone>Etc/GMT</timezone>
</clock>
<event-handler xmlns="urn:brocade.com:mgmt:brocade-event-handler" y:self="/rest/config/running/event-handler">
  <activate y:self="/rest/config/running/event-handler/activate">
  </activate>
</event-handler>
<hardware xmlns="urn:brocade.com:mgmt:brocade-hardware" y:self="/rest/config/running/hardware">
  <profile y:self="/rest/config/running/hardware/profile">
    <tcam y:self="/rest/config/running/hardware/profile/tcam">
      <tcam_profiletype>default</tcam_profiletype>
    </tcam>
    <route-table y:self="/rest/config/running/hardware/profile/route-table">
      <routing_profiletype>default</routing_profiletype>
      <maximum_paths>8</maximum_paths>
    </route-table>
  </profile>
  <system-mode>default</system-mode>
</hardware>
<http xmlns="urn:brocade.com:mgmt:brocade-http" y:self="/rest/config/running/http">
  <server y:self="/rest/config/running/http/server">
    <use-vrf y:self="/rest/config/running/http/server/use-vrf/default-vrf">
      <use-vrf-name>default-vrf</use-vrf-name>
    </use-vrf>
    <use-vrf y:self="/rest/config/running/http/server/use-vrf/mgmt-vrf">
      <use-vrf-name>mgmt-vrf</use-vrf-name>
    </use-vrf>
  </server>
</http>
<link-fault-signaling xmlns="urn:brocade.com:mgmt:brocade-lfs" y:self="/rest/config/running/link-fault-signaling">
</link-fault-signaling>
<ntp xmlns="urn:brocade.com:mgmt:brocade-ntp" y:self="/rest/config/running/ntp">
</ntp>
<openflow xmlns="urn:brocade.com:mgmt:brocade-openflow" y:self="/rest/config/running/openflow">
  <enable y:self="/rest/config/running/openflow/enable">
  </enable>
  <default-behavior y:self="/rest/config/running/openflow/default-behavior">
  </default-behavior>
</openflow>
<logging xmlns="urn:brocade.com:mgmt:brocade-ras" y:self="/rest/config/running/logging">
  <raslog y:self="/rest/config/running/logging/raslog">
    <interface y:self="/rest/config/running/logging/raslog/interface">
    </interface>
    <console>INFO</console>
  </raslog>
  <auditlog y:self="/rest/config/running/logging/auditlog">
    <class y:self="/rest/config/running/logging/auditlog/class/SECURITY">
      <class>SECURITY</class>
    </class>
    <class y:self="/rest/config/running/logging/auditlog/class/CONFIGURATION">
      <class>CONFIGURATION</class>
    </class>
    <class y:self="/rest/config/running/logging/auditlog/class/FIRMWARE">
      <class>FIRMWARE</class>
    </class>
  </auditlog>
  <syslog-facility y:self="/rest/config/running/logging/syslog-facility">
    <local>LOG_LOCAL7</local>
  </syslog-facility>
  <syslog-client y:self="/rest/config/running/logging/syslog-client">
    <localip>CHASSIS_IP</localip>
  </syslog-client>
</logging>
<switch-attributes xmlns="urn:brocade.com:mgmt:brocade-ras" y:self="/rest/config/running/switch-attributes">
  <chassis-name>spine1</chassis-name>
  <host-name>spine1</host-name>
</switch-attributes>
<support xmlns="urn:brocade.com:mgmt:brocade-ras" y:self="/rest/config/running/support">
  <autoupload-param y:self="/rest/config/running/support/autoupload-param">
  </autoupload-param>
  <support-param y:self="/rest/config/running/support/support-param">
  </support-param>
  <autoupload y:self="/rest/config/running/support/autoupload">
  </autoupload>
  <ffdc>true</ffdc>
</support>
<load-balance xmlns="urn:brocade.com:mgmt:brocade-rbridge-lag" y:self="/rest/config/running/load-balance">
</load-balance>
<resource-monitor xmlns="urn:brocade.com:mgmt:brocade-resource-monitor" y:self="/rest/config/running/resource-monitor">
  <cpu y:self="/rest/config/running/resource-monitor/cpu">
    <enable>true</enable>
    <threshold>90</threshold>
    <action>raslog</action>
  </cpu>
  <memory y:self="/rest/config/running/resource-monitor/memory">
    <enable>true</enable>
    <threshold>100</threshold>
    <action>raslog</action>
  </memory>
  <process y:self="/rest/config/running/resource-monitor/process">
    <memory y:self="/rest/config/running/resource-monitor/process/memory">
      <enable>true</enable>
      <alarm>1000</alarm>
      <critical>1200</critical>
    </memory>
  </process>
</resource-monitor>
<snmp-server xmlns="urn:brocade.com:mgmt:brocade-snmp" y:self="/rest/config/running/snmp-server">
  <contact>&quot;Field Support.&quot;</contact>
  <location>&quot;End User Premise.&quot;</location>
  <sys-descr>&quot;Brocade BR-SLX9240 Router&quot;</sys-descr>
  <enable y:self="/rest/config/running/snmp-server/enable">
    <trap y:self="/rest/config/running/snmp-server/enable/trap">
      <trap-flag>true</trap-flag>
    </trap>
  </enable>
  <engineID y:self="/rest/config/running/snmp-server/engineID">
  </engineID>
</snmp-server>
<sysmon xmlns="urn:brocade.com:mgmt:brocade-sysmon" y:self="/rest/config/running/sysmon">
  <fe-access-check y:self="/rest/config/running/sysmon/fe-access-check">
  </fe-access-check>
  <link-crc-monitoring y:self="/rest/config/running/sysmon/link-crc-monitoring">
  </link-crc-monitoring>
  <sfm-walk y:self="/rest/config/running/sysmon/sfm-walk">
  </sfm-walk>
</sysmon>
<system-monitor xmlns="urn:brocade.com:mgmt:brocade-system-monitor" y:self="/rest/config/running/system-monitor">
  <fan y:self="/rest/config/running/system-monitor/fan">
    <threshold y:self="/rest/config/running/system-monitor/fan/threshold">
      <marginal-threshold>1</marginal-threshold>
      <down-threshold>2</down-threshold>
    </threshold>
    <alert y:self="/rest/config/running/system-monitor/fan/alert">
      <state>removed</state>
      <action>raslog</action>
    </alert>
  </fan>
  <power y:self="/rest/config/running/system-monitor/power">
    <threshold y:self="/rest/config/running/system-monitor/power/threshold">
      <marginal-threshold>1</marginal-threshold>
      <down-threshold>2</down-threshold>
    </threshold>
    <alert y:self="/rest/config/running/system-monitor/power/alert">
      <state>removed</state>
      <action>raslog</action>
    </alert>
  </power>
  <temp y:self="/rest/config/running/system-monitor/temp">
    <threshold y:self="/rest/config/running/system-monitor/temp/threshold">
      <marginal-threshold>1</marginal-threshold>
      <down-threshold>2</down-threshold>
    </threshold>
  </temp>
  <cid-card y:self="/rest/config/running/system-monitor/cid-card">
    <threshold y:self="/rest/config/running/system-monitor/cid-card/threshold">
      <marginal-threshold>1</marginal-threshold>
      <down-threshold>2</down-threshold>
    </threshold>
    <alert y:self="/rest/config/running/system-monitor/cid-card/alert">
      <state>none</state>
      <action>none</action>
    </alert>
  </cid-card>
  <compact-flash y:self="/rest/config/running/system-monitor/compact-flash">
    <threshold y:self="/rest/config/running/system-monitor/compact-flash/threshold">
      <marginal-threshold>1</marginal-threshold>
      <down-threshold>0</down-threshold>
    </threshold>
  </compact-flash>
  <MM y:self="/rest/config/running/system-monitor/MM">
    <threshold y:self="/rest/config/running/system-monitor/MM/threshold">
      <marginal-threshold>1</marginal-threshold>
      <down-threshold>0</down-threshold>
    </threshold>
  </MM>
  <LineCard y:self="/rest/config/running/system-monitor/LineCard">
    <threshold y:self="/rest/config/running/system-monitor/LineCard/threshold">
      <marginal-threshold>1</marginal-threshold>
      <down-threshold>2</down-threshold>
    </threshold>
    <alert y:self="/rest/config/running/system-monitor/LineCard/alert">
      <state>none</state>
      <action>none</action>
    </alert>
  </LineCard>
  <SFM y:self="/rest/config/running/system-monitor/SFM">
    <threshold y:self="/rest/config/running/system-monitor/SFM/threshold">
      <marginal-threshold>1</marginal-threshold>
      <down-threshold>2</down-threshold>
    </threshold>
  </SFM>
</system-monitor>
<system-monitor-mail xmlns="urn:brocade.com:mgmt:brocade-system-monitor" y:self="/rest/config/running/system-monitor-mail">
  <fru y:self="/rest/config/running/system-monitor-mail/fru">
  </fru>
  <sfp y:self="/rest/config/running/system-monitor-mail/sfp">
  </sfp>
  <security y:self="/rest/config/running/system-monitor-mail/security">
  </security>
  <interface y:self="/rest/config/running/system-monitor-mail/interface">
  </interface>
</system-monitor-mail>
<telemetry xmlns="urn:brocade.com:mgmt:brocade-telemetry" y:self="/rest/config/running/telemetry">
  <profile y:self="/rest/config/running/telemetry/profile">
    <system-utilization y:self="/rest/config/running/telemetry/profile/system-utilization/default_system_utilization_statistics">
      <name>default_system_utilization_statistics</name>
    </system-utilization>
    <interface y:self="/rest/config/running/telemetry/profile/interface/default_interface_statistics">
      <name>default_interface_statistics</name>
    </interface>
  </profile>
</telemetry>
<line xmlns="urn:brocade.com:mgmt:brocade-terminal" y:self="/rest/config/running/line/vty">
  <sessionid>vty</sessionid>
</line>
<threshold-monitor xmlns="urn:brocade.com:mgmt:brocade-threshold-monitor" y:self="/rest/config/running/threshold-monitor">
  <sfp y:self="/rest/config/running/threshold-monitor/sfp">
    <pause>false</pause>
    <policy y:self="/rest/config/running/threshold-monitor/sfp/policy/">
    </policy>
  </sfp>
  <Cpu y:self="/rest/config/running/threshold-monitor/Cpu">
  </Cpu>
  <Memory y:self="/rest/config/running/threshold-monitor/Memory">
  </Memory>
  <Buffer y:self="/rest/config/running/threshold-monitor/Buffer">
    <limit>70</limit>
  </Buffer>
</threshold-monitor>
<vrf xmlns="urn:brocade.com:mgmt:brocade-vrf" y:self="/rest/config/running/vrf/mgmt-vrf">
  <vrf-name>mgmt-vrf</vrf-name>
</vrf>
<ssh xmlns="urn:brocade.com:mgmt:brocade-sec-services" y:self="/rest/config/running/ssh">
  <server y:self="/rest/config/running/ssh/server">
    <standby y:self="/rest/config/running/ssh/server/standby">
      <enable>false</enable>
    </standby>
    <key y:self="/rest/config/running/ssh/server/key">
      <rsa>2048</rsa>
      <ecdsa>256</ecdsa>
      <dsa>true</dsa>
    </key>
    <use-vrf y:self="/rest/config/running/ssh/server/use-vrf/default-vrf">
      <use-vrf-name>default-vrf</use-vrf-name>
    </use-vrf>
    <use-vrf y:self="/rest/config/running/ssh/server/use-vrf/mgmt-vrf">
      <use-vrf-name>mgmt-vrf</use-vrf-name>
    </use-vrf>
  </server>
  <client y:self="/rest/config/running/ssh/client">
    <source-interface y:self="/rest/config/running/ssh/client/source-interface">
    </source-interface>
  </client>
</ssh>
<telnet xmlns="urn:brocade.com:mgmt:brocade-sec-services" y:self="/rest/config/running/telnet">
  <server y:self="/rest/config/running/telnet/server">
    <standby y:self="/rest/config/running/telnet/server/standby">
      <enable>false</enable>
    </standby>
    <use-vrf y:self="/rest/config/running/telnet/server/use-vrf/default-vrf">
      <use-vrf-name>default-vrf</use-vrf-name>
    </use-vrf>
    <use-vrf y:self="/rest/config/running/telnet/server/use-vrf/mgmt-vrf">
      <use-vrf-name>mgmt-vrf</use-vrf-name>
    </use-vrf>
  </server>
  <client y:self="/rest/config/running/telnet/client">
    <source-interface y:self="/rest/config/running/telnet/client/source-interface">
    </source-interface>
  </client>
</telnet>
<banner xmlns="urn:brocade.com:mgmt:brocade-aaa" y:self="/rest/config/running/banner">
</banner>
<password-attributes xmlns="urn:brocade.com:mgmt:brocade-aaa" y:self="/rest/config/running/password-attributes">
  <character-restriction y:self="/rest/config/running/password-attributes/character-restriction">
  </character-restriction>
  <admin-lockout>false</admin-lockout>
</password-attributes>
<role xmlns="urn:brocade.com:mgmt:brocade-aaa" y:self="/rest/config/running/role">
  <name y:self="/rest/config/running/role/name/admin">
    <name>admin</name>
  </name>
  <name y:self="/rest/config/running/role/name/user">
    <name>user</name>
  </name>
</role>
<radius-server xmlns="urn:brocade.com:mgmt:brocade-aaa" y:self="/rest/config/running/radius-server">
</radius-server>
<tacacs-server xmlns="urn:brocade.com:mgmt:brocade-aaa" y:self="/rest/config/running/tacacs-server">
</tacacs-server>
<ldap-server xmlns="urn:brocade.com:mgmt:brocade-aaa" y:self="/rest/config/running/ldap-server">
</ldap-server>
<aaa xmlns="urn:brocade.com:mgmt:brocade-aaa" y:self="/rest/config/running/aaa">
  <authentication y:self="/rest/config/running/aaa/authentication">
    <login y:self="/rest/config/running/aaa/authentication/login">
      <first>local</first>
    </login>
  </authentication>
  <accounting y:self="/rest/config/running/aaa/accounting">
    <exec y:self="/rest/config/running/aaa/accounting/exec">
      <default y:self="/rest/config/running/aaa/accounting/exec/default">
        <start-stop y:self="/rest/config/running/aaa/accounting/exec/default/start-stop">
          <server-type>none</server-type>
        </start-stop>
      </default>
    </exec>
    <commands y:self="/rest/config/running/aaa/accounting/commands">
      <default y:self="/rest/config/running/aaa/accounting/commands/default">
        <start-stop y:self="/rest/config/running/aaa/accounting/commands/default/start-stop">
          <server-type>none</server-type>
        </start-stop>
      </default>
    </commands>
  </accounting>
</aaa>
<service xmlns="urn:brocade.com:mgmt:brocade-aaa" y:self="/rest/config/running/service">
  <password-encryption>true</password-encryption>
</service>
<username xmlns="urn:brocade.com:mgmt:brocade-aaa" y:self="/rest/config/running/username/admin">
  <name>admin</name>
</username>
<username xmlns="urn:brocade.com:mgmt:brocade-aaa" y:self="/rest/config/running/username/user">
  <name>user</name>
</username>
<cee-map xmlns="urn:brocade.com:mgmt:brocade-qos-cee" y:self="/rest/config/running/cee-map/default">
  <name>default</name>
</cee-map>
<ipv6 xmlns="urn:brocade.com:mgmt:brocade-common-def" y:self="/rest/config/running/ipv6">
  <protocol xmlns="urn:brocade.com:mgmt:brocade-vrrpv3" y:self="/rest/config/running/ipv6/protocol">
  </protocol>
  <route xmlns="urn:brocade.com:mgmt:brocade-ipv6-rtm" y:self="/rest/config/running/ipv6/route">
    <static y:self="/rest/config/running/ipv6/route/static">
      <bfd y:self="/rest/config/running/ipv6/route/static/bfd">
      </bfd>
    </static>
  </route>
  <nd xmlns="urn:brocade.com:mgmt:brocade-ipv6-nd-ra" y:self="/rest/config/running/ipv6/nd">
  </nd>
</ipv6>
<ip xmlns="urn:brocade.com:mgmt:brocade-ip-access-list" y:self="/rest/config/running/ip">
  <access-list y:self="/rest/config/running/ip/access-list">
    <extended y:self="/rest/config/running/ip/access-list/extended/acl_10">
      <name>acl_10</name>
    </extended>
  </access-list>
  <igmp xmlns="urn:brocade.com:mgmt:brocade-igmp-snooping" y:self="/rest/config/running/ip/igmp">
    <ssm-map y:self="/rest/config/running/ip/igmp/ssm-map">
    </ssm-map>
  </igmp>
</ip>
<vlan xmlns="urn:brocade.com:mgmt:brocade-interface" y:self="/rest/config/running/vlan/1">
  <name>1</name>
</vlan>
<vlan xmlns="urn:brocade.com:mgmt:brocade-interface" y:self="/rest/config/running/vlan/10">
  <name>10</name>
</vlan>
<vlan xmlns="urn:brocade.com:mgmt:brocade-interface" y:self="/rest/config/running/vlan/200">
  <name>200</name>
</vlan>
<qos xmlns="urn:brocade.com:mgmt:brocade-qos-mls" y:self="/rest/config/running/qos">
  <map y:self="/rest/config/running/qos/map">
    <cos-mutation y:self="/rest/config/running/qos/map/cos-mutation/all-zero-map">
      <name>all-zero-map</name>
    </cos-mutation>
    <cos-mutation y:self="/rest/config/running/qos/map/cos-mutation/default">
      <name>default</name>
    </cos-mutation>
    <cos-traffic-class y:self="/rest/config/running/qos/map/cos-traffic-class/all-zero-map">
      <name>all-zero-map</name>
    </cos-traffic-class>
    <cos-traffic-class y:self="/rest/config/running/qos/map/cos-traffic-class/default">
      <name>default</name>
    </cos-traffic-class>
    <cos-dscp y:self="/rest/config/running/qos/map/cos-dscp/all-zero-map">
      <name>all-zero-map</name>
    </cos-dscp>
    <cos-dscp y:self="/rest/config/running/qos/map/cos-dscp/default">
      <name>default</name>
    </cos-dscp>
    <traffic-class-cos y:self="/rest/config/running/qos/map/traffic-class-cos/all-zero-map">
      <traffic-class-cos-map-name>all-zero-map</traffic-class-cos-map-name>
    </traffic-class-cos>
    <traffic-class-cos y:self="/rest/config/running/qos/map/traffic-class-cos/default">
      <traffic-class-cos-map-name>default</traffic-class-cos-map-name>
    </traffic-class-cos>
    <traffic-class-mutation y:self="/rest/config/running/qos/map/traffic-class-mutation/all-zero-map">
      <name>all-zero-map</name>
    </traffic-class-mutation>
    <traffic-class-mutation y:self="/rest/config/running/qos/map/traffic-class-mutation/default">
      <name>default</name>
    </traffic-class-mutation>
    <traffic-class-dscp y:self="/rest/config/running/qos/map/traffic-class-dscp/all-zero-map">
      <name>all-zero-map</name>
    </traffic-class-dscp>
    <traffic-class-dscp y:self="/rest/config/running/qos/map/traffic-class-dscp/default">
      <name>default</name>
    </traffic-class-dscp>
    <dscp-mutation y:self="/rest/config/running/qos/map/dscp-mutation/all-zero-map">
      <dscp-mutation-map-name>all-zero-map</dscp-mutation-map-name>
    </dscp-mutation>
    <dscp-mutation y:self="/rest/config/running/qos/map/dscp-mutation/default">
      <dscp-mutation-map-name>default</dscp-mutation-map-name>
    </dscp-mutation>
    <dscp-traffic-class y:self="/rest/config/running/qos/map/dscp-traffic-class/all-zero-map">
      <dscp-traffic-class-map-name>all-zero-map</dscp-traffic-class-map-name>
    </dscp-traffic-class>
    <dscp-traffic-class y:self="/rest/config/running/qos/map/dscp-traffic-class/default">
      <dscp-traffic-class-map-name>default</dscp-traffic-class-map-name>
    </dscp-traffic-class>
    <dscp-cos y:self="/rest/config/running/qos/map/dscp-cos/all-zero-map">
      <dscp-cos-map-name>all-zero-map</dscp-cos-map-name>
    </dscp-cos>
    <dscp-cos y:self="/rest/config/running/qos/map/dscp-cos/default">
      <dscp-cos-map-name>default</dscp-cos-map-name>
    </dscp-cos>
  </map>
  <tx-queue y:self="/rest/config/running/qos/tx-queue">
    <scheduler y:self="/rest/config/running/qos/tx-queue/scheduler">
      <strict-priority y:self="/rest/config/running/qos/tx-queue/scheduler/strict-priority">
      </strict-priority>
    </scheduler>
  </tx-queue>
</qos>
<qos-mpls xmlns="urn:brocade.com:mgmt:brocade-qos-mpls" y:self="/rest/config/running/qos-mpls">
  <map-apply xmlns="urn:brocade.com:mgmt:brocade-apply-qos-mpls" y:self="/rest/config/running/qos-mpls/map-apply">
    <exp-traffic-class y:self="/rest/config/running/qos-mpls/map-apply/exp-traffic-class">
    </exp-traffic-class>
    <traffic-class-exp y:self="/rest/config/running/qos-mpls/map-apply/traffic-class-exp">
    </traffic-class-exp>
    <dscp-exp y:self="/rest/config/running/qos-mpls/map-apply/dscp-exp">
    </dscp-exp>
    <exp-dscp y:self="/rest/config/running/qos-mpls/map-apply/exp-dscp">
    </exp-dscp>
  </map-apply>
</qos-mpls>
<protocol xmlns="urn:brocade.com:mgmt:brocade-interface" y:self="/rest/config/running/protocol">
  <lldp xmlns="urn:brocade.com:mgmt:brocade-lldp" y:self="/rest/config/running/protocol/lldp">
    <advertise y:self="/rest/config/running/protocol/lldp/advertise">
      <dcbx-iscsi-app-tlv>false</dcbx-iscsi-app-tlv>
      <dcbx-tlv>true</dcbx-tlv>
      <optional-tlv y:self="/rest/config/running/protocol/lldp/advertise/optional-tlv">
      </optional-tlv>
    </advertise>
    <system-description>Brocade BR-SLX9240 Router</system-description>
    <disable>false</disable>
  </lldp>
</protocol>
<vlan xmlns="urn:brocade.com:mgmt:brocade-vlan" y:self="/rest/config/running/vlan">
  <dot1q y:self="/rest/config/running/vlan/dot1q">
    <tag y:self="/rest/config/running/vlan/dot1q/tag">
      <native>true</native>
    </tag>
  </dot1q>
</vlan>
<lacp xmlns="urn:brocade.com:mgmt:brocade-lacp" y:self="/rest/config/running/lacp">
</lacp>
<dot1x xmlns="urn:brocade.com:mgmt:brocade-dot1x" y:self="/rest/config/running/dot1x">
  <enable>false</enable>
  <test y:self="/rest/config/running/dot1x/test">
  </test>
</dot1x>
<ip xmlns="urn:brocade.com:mgmt:brocade-common-def" y:self="/rest/config/running/ip">
  <route xmlns="urn:brocade.com:mgmt:brocade-rtm" y:self="/rest/config/running/ip/route">
    <static-route-nh y:self="/rest/config/running/ip/route/static-route-nh/%220.0.0.0/0%22%2C192.168.254.1">
      <static-route-dest>0.0.0.0/0</static-route-dest>
      <static-route-next-hop>192.168.254.1</static-route-next-hop>
    </static-route-nh>
    <static y:self="/rest/config/running/ip/route/static">
      <bfd y:self="/rest/config/running/ip/route/static/bfd">
      </bfd>
    </static>
  </route>
  <import y:self="/rest/config/running/ip/import">
  </import>
</ip>
<sflow xmlns="urn:brocade.com:mgmt:brocade-sflow" y:self="/rest/config/running/sflow">
  <enable>false</enable>
  <source-interface y:self="/rest/config/running/sflow/source-interface">
  </source-interface>
</sflow>
<police-remark-profile xmlns="urn:brocade.com:mgmt:brocade-qos-mqc" y:self="/rest/config/running/police-remark-profile/default">
  <profile-name>default</profile-name>
</police-remark-profile>
<class-map xmlns="urn:brocade.com:mgmt:brocade-qos-mqc" y:self="/rest/config/running/class-map/cee">
  <name>cee</name>
</class-map>
<class-map xmlns="urn:brocade.com:mgmt:brocade-qos-mqc" y:self="/rest/config/running/class-map/default">
  <name>default</name>
</class-map>
<mac xmlns="urn:brocade.com:mgmt:brocade-common-def" y:self="/rest/config/running/mac">
  <receive xmlns="urn:brocade.com:mgmt:brocade-mac-access-list" y:self="/rest/config/running/mac/receive">
    <access-group y:self="/rest/config/running/mac/receive/access-group">
    </access-group>
  </receive>
</mac>
<ip xmlns="urn:brocade.com:mgmt:brocade-common-def" y:self="/rest/config/running/ip">
  <receive xmlns="urn:brocade.com:mgmt:brocade-ip-access-list" y:self="/rest/config/running/ip/receive">
    <access-group y:self="/rest/config/running/ip/receive/access-group">
    </access-group>
  </receive>
  <dhcp xmlns="urn:brocade.com:mgmt:brocade-dhcp" y:self="/rest/config/running/ip/dhcp">
    <relay y:self="/rest/config/running/ip/dhcp/relay">
      <information y:self="/rest/config/running/ip/dhcp/relay/information">
      </information>
    </relay>
  </dhcp>
</ip>
<ipv6 xmlns="urn:brocade.com:mgmt:brocade-common-def" y:self="/rest/config/running/ipv6">
  <receive xmlns="urn:brocade.com:mgmt:brocade-ipv6-access-list" y:self="/rest/config/running/ipv6/receive">
    <access-group y:self="/rest/config/running/ipv6/receive/access-group">
    </access-group>
  </receive>
</ipv6>
<interface xmlns="urn:brocade.com:mgmt:brocade-interface" y:self="/rest/config/running/interface">
  <Ve y:self="/rest/config/running/interface/Ve/100">
    <name>100</name>
  </Ve>
  <Ve y:self="/rest/config/running/interface/Ve/200">
    <name>200</name>
  </Ve>
</interface>
<interface xmlns="urn:brocade.com:mgmt:brocade-interface" y:self="/rest/config/running/interface">
  <Management y:self="/rest/config/running/interface/Management/0">
    <name>0</name>
  </Management>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/1%22">
    <name>0/1</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/2%22">
    <name>0/2</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/3%22">
    <name>0/3</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/4%22">
    <name>0/4</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/5%22">
    <name>0/5</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/6%22">
    <name>0/6</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/7%22">
    <name>0/7</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/8%22">
    <name>0/8</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/9%22">
    <name>0/9</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/10%22">
    <name>0/10</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/11%22">
    <name>0/11</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/12%22">
    <name>0/12</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/13%22">
    <name>0/13</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/14%22">
    <name>0/14</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/15%22">
    <name>0/15</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/16%22">
    <name>0/16</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/17%22">
    <name>0/17</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/18%22">
    <name>0/18</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/19%22">
    <name>0/19</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/20%22">
    <name>0/20</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/21%22">
    <name>0/21</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/22%22">
    <name>0/22</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/23%22">
    <name>0/23</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/24%22">
    <name>0/24</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/25%22">
    <name>0/25</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/26%22">
    <name>0/26</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/27%22">
    <name>0/27</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/28%22">
    <name>0/28</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/29%22">
    <name>0/29</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/30%22">
    <name>0/30</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/31%22">
    <name>0/31</name>
  </Ethernet>
  <Ethernet y:self="/rest/config/running/interface/Ethernet/%220/32%22">
    <name>0/32</name>
  </Ethernet>
  <Port-channel y:self="/rest/config/running/interface/Port-channel/30">
    <name>30</name>
  </Port-channel>
</interface>
<mac-address-table xmlns="urn:brocade.com:mgmt:brocade-mac-address-table" y:self="/rest/config/running/mac-address-table">
  <aging-time y:self="/rest/config/running/mac-address-table/aging-time">
  </aging-time>
  <mac-move y:self="/rest/config/running/mac-address-table/mac-move">
  </mac-move>
</mac-address-table>
<rmon xmlns="urn:brocade.com:mgmt:brocade-rmon" y:self="/rest/config/running/rmon">
</rmon>
<monitor xmlns="urn:brocade.com:mgmt:brocade-span" y:self="/rest/config/running/monitor">
</monitor>
<bridge-domain xmlns="urn:brocade.com:mgmt:brocade-bridge-domain" y:self="/rest/config/running/bridge-domain/10%2Cp2mp">
  <bridge-domain-id>10</bridge-domain-id>
  <bridge-domain-type>p2mp</bridge-domain-type>
</bridge-domain>
</data>

mab@mab-infra:~$
```


### Interface Port-channel:
```
mab@mab-infra:~$ st2 run core.http username=admin password=********** url=http://192.168.254.115:80/rest/config/running/interface/Port-channel/30
.
id: 5a2034487cae220a3a558818
status: succeeded
parameters: 
  password: **********
  url: http://192.168.254.115:80/rest/config/running/interface/Port-channel/30
  username: admin
result: 
  body: "<Port-channel xmlns=\"urn:brocade.com:mgmt:brocade-interface\" xmlns:y=\"http://brocade.com/ns/rest\" y:self=\"/rest/config/running/interface/Port-channel/30\">\r\n  <name>30</name>\r\n  <service-policy xmlns=\"urn:brocade.com:mgmt:brocade-qos-mqc\" y:self=\"/rest/config/running/interface/Port-channel/30/service-policy\">\r\n  </service-policy>\r\n  <protocol xmlns=\"urn:brocade.com:mgmt:brocade-ptp\" y:self=\"/rest/config/running/interface/Port-channel/30/protocol\">\r\n  </protocol>\r\n  <system xmlns=\"urn:brocade.com:mgmt:brocade-packet-timestamp\" y:self=\"/rest/config/running/interface/Port-channel/30/system\">\r\n    <packet-timestamp y:self=\"/rest/config/running/interface/Port-channel/30/system/packet-timestamp\">\r\n    </packet-timestamp>\r\n  </system>\r\n  <priority-tag>false</priority-tag>\r\n  <switchport>true</switchport>\r\n  <switchport y:self=\"/rest/config/running/interface/Port-channel/30/switchport\">\r\n    <mode y:self=\"/rest/config/running/interface/Port-channel/30/switchport/mode\">\r\n      <vlan-mode>trunk</vlan-mode>\r\n    </mode>\r\n    <access y:self=\"/rest/config/running/interface/Port-channel/30/switchport/access\">\r\n    </access>\r\n    <trunk y:self=\"/rest/config/running/interface/Port-channel/30/switchport/trunk\">\r\n      <allowed y:self=\"/rest/config/running/interface/Port-channel/30/switchport/trunk/allowed\">\r\n        <vlan y:self=\"/rest/config/running/interface/Port-channel/30/switchport/trunk/allowed/vlan\">\r\n          <all>false</all>\r\n          <none>false</none>\r\n        </vlan>\r\n      </allowed>\r\n      <tag y:self=\"/rest/config/running/interface/Port-channel/30/switchport/trunk/tag\">\r\n        <native-vlan>true</native-vlan>\r\n      </tag>\r\n    </trunk>\r\n  </switchport>\r\n  <qos xmlns=\"urn:brocade.com:mgmt:brocade-qos-mls\" y:self=\"/rest/config/running/interface/Port-channel/30/qos\">\r\n    <trust y:self=\"/rest/config/running/interface/Port-channel/30/qos/trust\">\r\n      <cos>false</cos>\r\n      <dscp>false</dscp>\r\n    </trust>\r\n    <random-detect y:self=\"/rest/config/running/interface/Port-channel/30/qos/random-detect\">\r\n    </random-detect>\r\n    <drop-monitor y:self=\"/rest/config/running/interface/Port-channel/30/qos/drop-monitor\">\r\n      <enable>false</enable>\r\n    </drop-monitor>\r\n    <flowcontrol y:self=\"/rest/config/running/interface/Port-channel/30/qos/flowcontrol\">\r\n    </flowcontrol>\r\n  </qos>\r\n  <spanning-tree xmlns=\"urn:brocade.com:mgmt:brocade-xstp\" y:self=\"/rest/config/running/interface/Port-channel/30/spanning-tree\">\r\n    <shutdown>false</shutdown>\r\n  </spanning-tree>\r\n  <mac xmlns=\"urn:brocade.com:mgmt:brocade-mac-access-list\" y:self=\"/rest/config/running/interface/Port-channel/30/mac\">\r\n  </mac>\r\n  <ip xmlns=\"urn:brocade.com:mgmt:brocade-ip-access-list\" y:self=\"/rest/config/running/interface/Port-channel/30/ip\">\r\n    <access-group y:self=\"/rest/config/running/interface/Port-channel/30/ip/access-group/acl_10%2Cin\">\r\n      <ip-access-list>acl_10</ip-access-list>\r\n      <ip-direction>in</ip-direction>\r\n    </access-group>\r\n    <arp xmlns=\"urn:brocade.com:mgmt:brocade-dai\" y:self=\"/rest/config/running/interface/Port-channel/30/ip/arp\">\r\n      <inspection y:self=\"/rest/config/running/interface/Port-channel/30/ip/arp/inspection\">\r\n        <trust>false</trust>\r\n      </inspection>\r\n    </arp>\r\n  </ip>\r\n  <ipv6 xmlns=\"urn:brocade.com:mgmt:brocade-interface\" y:self=\"/rest/config/running/interface/Port-channel/30/ipv6\">\r\n  </ipv6>\r\n  <shutdown>false</shutdown>\r\n  <logical-interface xmlns=\"urn:brocade.com:mgmt:brocade-lif\" y:self=\"/rest/config/running/interface/Port-channel/30/logical-interface\">\r\n    <port-channel y:self=\"/rest/config/running/interface/Port-channel/30/logical-interface/port-channel/30.10\">\r\n      <pc-instance-id>30.10</pc-instance-id>\r\n    </port-channel>\r\n  </logical-interface>\r\n</Port-channel>\r\n"
  headers:
    Authentication-Token: Z1A8OktAa0lRT3xyXUVGfWpGfFo6RmJxWEVBe2dLL2k=
    Cache-control: private, no-cache, must-revalidate, proxy-revalidate
    Connection: Keep-Alive
    Content-Type: application/vnd.configuration.resource+xml
    Date: '2017-12-01 00:38:45'
    Keep-Alive: timeout=180, max=100
    Server: SLX-OS Wave WWW
    Transfer-Encoding: chunked
  parsed: false
  status_code: 200
mab@mab-infra:~$
mab@mab-infra:~$
mab@mab-infra:~$ st2 execution get 5a2034487cae220a3a558818 -k body
<Port-channel xmlns="urn:brocade.com:mgmt:brocade-interface" xmlns:y="http://brocade.com/ns/rest" y:self="/rest/config/running/interface/Port-channel/30">
  <name>30</name>
  <service-policy xmlns="urn:brocade.com:mgmt:brocade-qos-mqc" y:self="/rest/config/running/interface/Port-channel/30/service-policy">
  </service-policy>
  <protocol xmlns="urn:brocade.com:mgmt:brocade-ptp" y:self="/rest/config/running/interface/Port-channel/30/protocol">
  </protocol>
  <system xmlns="urn:brocade.com:mgmt:brocade-packet-timestamp" y:self="/rest/config/running/interface/Port-channel/30/system">
    <packet-timestamp y:self="/rest/config/running/interface/Port-channel/30/system/packet-timestamp">
    </packet-timestamp>
  </system>
  <priority-tag>false</priority-tag>
  <switchport>true</switchport>
  <switchport y:self="/rest/config/running/interface/Port-channel/30/switchport">
    <mode y:self="/rest/config/running/interface/Port-channel/30/switchport/mode">
      <vlan-mode>trunk</vlan-mode>
    </mode>
    <access y:self="/rest/config/running/interface/Port-channel/30/switchport/access">
    </access>
    <trunk y:self="/rest/config/running/interface/Port-channel/30/switchport/trunk">
      <allowed y:self="/rest/config/running/interface/Port-channel/30/switchport/trunk/allowed">
        <vlan y:self="/rest/config/running/interface/Port-channel/30/switchport/trunk/allowed/vlan">
          <all>false</all>
          <none>false</none>
        </vlan>
      </allowed>
      <tag y:self="/rest/config/running/interface/Port-channel/30/switchport/trunk/tag">
        <native-vlan>true</native-vlan>
      </tag>
    </trunk>
  </switchport>
  <qos xmlns="urn:brocade.com:mgmt:brocade-qos-mls" y:self="/rest/config/running/interface/Port-channel/30/qos">
    <trust y:self="/rest/config/running/interface/Port-channel/30/qos/trust">
      <cos>false</cos>
      <dscp>false</dscp>
    </trust>
    <random-detect y:self="/rest/config/running/interface/Port-channel/30/qos/random-detect">
    </random-detect>
    <drop-monitor y:self="/rest/config/running/interface/Port-channel/30/qos/drop-monitor">
      <enable>false</enable>
    </drop-monitor>
    <flowcontrol y:self="/rest/config/running/interface/Port-channel/30/qos/flowcontrol">
    </flowcontrol>
  </qos>
  <spanning-tree xmlns="urn:brocade.com:mgmt:brocade-xstp" y:self="/rest/config/running/interface/Port-channel/30/spanning-tree">
    <shutdown>false</shutdown>
  </spanning-tree>
  <mac xmlns="urn:brocade.com:mgmt:brocade-mac-access-list" y:self="/rest/config/running/interface/Port-channel/30/mac">
  </mac>
  <ip xmlns="urn:brocade.com:mgmt:brocade-ip-access-list" y:self="/rest/config/running/interface/Port-channel/30/ip">
    <access-group y:self="/rest/config/running/interface/Port-channel/30/ip/access-group/acl_10%2Cin">
      <ip-access-list>acl_10</ip-access-list>
      <ip-direction>in</ip-direction>
    </access-group>
    <arp xmlns="urn:brocade.com:mgmt:brocade-dai" y:self="/rest/config/running/interface/Port-channel/30/ip/arp">
      <inspection y:self="/rest/config/running/interface/Port-channel/30/ip/arp/inspection">
        <trust>false</trust>
      </inspection>
    </arp>
  </ip>
  <ipv6 xmlns="urn:brocade.com:mgmt:brocade-interface" y:self="/rest/config/running/interface/Port-channel/30/ipv6">
  </ipv6>
  <shutdown>false</shutdown>
  <logical-interface xmlns="urn:brocade.com:mgmt:brocade-lif" y:self="/rest/config/running/interface/Port-channel/30/logical-interface">
    <port-channel y:self="/rest/config/running/interface/Port-channel/30/logical-interface/port-channel/30.10">
      <pc-instance-id>30.10</pc-instance-id>
    </port-channel>
  </logical-interface>
</Port-channel>

mab@mab-infra:~$
```

### Switchport configuration of an interface Port-channel:

```
mab@mab-infra:~$ st2 run core.http username=admin password=********** url=http://192.168.254.115:80/rest/config/running/interface/Port-channel/30/switchport
.
id: 5a2037997cae220a3a55881e
status: succeeded
parameters: 
  password: **********
  url: http://192.168.254.115:80/rest/config/running/interface/Port-channel/30/switchport
  username: admin
result: 
  body: "<switchport xmlns=\"urn:brocade.com:mgmt:brocade-interface\" xmlns:y=\"http://brocade.com/ns/rest\" y:self=\"/rest/config/running/interface/Port-channel/30/switchport\">true</switchport>\r\n<switchport xmlns=\"urn:brocade.com:mgmt:brocade-interface\" xmlns:y=\"http://brocade.com/ns/rest\" y:self=\"/rest/config/running/interface/Port-channel/30/switchport\">\r\n  <mode y:self=\"/rest/config/running/interface/Port-channel/30/switchport/mode\">\r\n    <vlan-mode>trunk</vlan-mode>\r\n  </mode>\r\n  <access y:self=\"/rest/config/running/interface/Port-channel/30/switchport/access\">\r\n  </access>\r\n  <trunk y:self=\"/rest/config/running/interface/Port-channel/30/switchport/trunk\">\r\n    <allowed y:self=\"/rest/config/running/interface/Port-channel/30/switchport/trunk/allowed\">\r\n      <vlan y:self=\"/rest/config/running/interface/Port-channel/30/switchport/trunk/allowed/vlan\">\r\n        <all>false</all>\r\n        <none>false</none>\r\n      </vlan>\r\n    </allowed>\r\n    <tag y:self=\"/rest/config/running/interface/Port-channel/30/switchport/trunk/tag\">\r\n      <native-vlan>true</native-vlan>\r\n    </tag>\r\n  </trunk>\r\n</switchport>\r\n"
  headers:
    Authentication-Token: SC94X1tDLzhIcXtqYlVgfTgwYnhFcGg2T25VeGBQTDQ=
    Cache-control: private, no-cache, must-revalidate, proxy-revalidate
    Connection: Keep-Alive
    Content-Type: application/vnd.configuration.resource+xml
    Date: '2017-12-01 00:52:54'
    Keep-Alive: timeout=180, max=100
    Server: SLX-OS Wave WWW
    Transfer-Encoding: chunked
  parsed: false
  status_code: 200
mab@mab-infra:~/mab_automate/nw_automation_on_slx$ 
mab@mab-infra:~/mab_automate/nw_automation_on_slx$ st2 execution get 5a2037997cae220a3a55881e -k body
<switchport xmlns="urn:brocade.com:mgmt:brocade-interface" xmlns:y="http://brocade.com/ns/rest" y:self="/rest/config/running/interface/Port-channel/30/switchport">true</switchport>
<switchport xmlns="urn:brocade.com:mgmt:brocade-interface" xmlns:y="http://brocade.com/ns/rest" y:self="/rest/config/running/interface/Port-channel/30/switchport">
  <mode y:self="/rest/config/running/interface/Port-channel/30/switchport/mode">
    <vlan-mode>trunk</vlan-mode>
  </mode>
  <access y:self="/rest/config/running/interface/Port-channel/30/switchport/access">
  </access>
  <trunk y:self="/rest/config/running/interface/Port-channel/30/switchport/trunk">
    <allowed y:self="/rest/config/running/interface/Port-channel/30/switchport/trunk/allowed">
      <vlan y:self="/rest/config/running/interface/Port-channel/30/switchport/trunk/allowed/vlan">
        <all>false</all>
        <none>false</none>
      </vlan>
    </allowed>
    <tag y:self="/rest/config/running/interface/Port-channel/30/switchport/trunk/tag">
      <native-vlan>true</native-vlan>
    </tag>
  </trunk>
</switchport>

mab@mab-infra:~$
```



## Operations API:

### Title 1:
```

```

## Operational-state API:

### Title 1:
```

```
