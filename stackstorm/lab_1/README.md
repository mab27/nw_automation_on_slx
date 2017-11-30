# Lab_1

## Overview:
- Invoking actions from the **network_essentials** pack.
- Sections:
    - [Getters (show commands)]()
    	- [get_os_version]()
      	- [validate_interface_state]()
      	- [validate_L2_port_channel_state]()
      	- [ping]()
      	- [execute_cli (to get an arbitrary list of show commands)]()
    - [Setters (configuration commands)]()
    	- [create_vlan / delete_vlan]()
		- [create_ve / delete_ve]()
		- [set_intf_admin_state]()
    	- [create_acl / delete_acl]()
    	- [add_ipv4_rule_acl]()
    	- [apply_acl / remove_acl]()
      	- [execute_cli (to send an arbitrary list of config commands)]()

## Getters (show commands):

### get_os_version:
```
mab@mab-infra:~$ st2 run network_essentials.get_os_version mgmt_ip=spine1 username=admin password=**********
.....
id: 5a1be5a57cae220c046518c5
status: succeeded
parameters: 
  mgmt_ip: spine1
  password: '********'
  username: admin
result: 
  exit_code: 0
  result:
    result: 17s.1.00a
  stderr: 'st2.actions.python.GetOsVersion: INFO     successfully connected to spine1 to get OS Version

    st2.actions.python.GetOsVersion: INFO     Closing connection to spine1 after finding OS -- all done!

    '
  stdout: ''
mab@mab-infra:~$
mab@mab-infra:~$ st2 execution get 5a1be5a57cae220c046518c5 -k result.result
17s.1.00a
mab@mab-infra:~$
```

### validate_interface_state:

- State of a physical interface:

```
mab@mab-infra:~$ st2 run network_essentials.validate_interface_state mgmt_ip=spine1 username=admin password=********** intf_type=ethernet intf_name=0/5 intf_state=up
........
id: 5a1bedeb7cae220c046518c8
status: succeeded
parameters: 
  intf_name: 0/5
  intf_state: up
  intf_type: ethernet
  mgmt_ip: spine1
  password: '********'
  username: admin
result: 
  exit_code: 0
  result:
    intf: true
    state: up
  stderr: 'st2.actions.python.ValidateInterfaceState: INFO     successfully connected to spine1 to validate interface state

    st2.actions.python.ValidateInterfaceState: INFO     Successfully Validated port channel/physical interface state as up

    st2.actions.python.ValidateInterfaceState: INFO     closing connection to spine1 after Validating interface state -- all done!

    '
  stdout: ''
mab@mab-infra:~$
```

- State of a port-channel interface:

```
mab@mab-infra:~$ st2 run network_essentials.validate_interface_state mgmt_ip=spine1 username=admin password=********** intf_type=port_channel intf_name=30 intf_state=up
.......
id: 5a1bf0c97cae220c046518d1
status: succeeded
parameters: 
  intf_name: '30'
  intf_state: up
  intf_type: port_channel
  mgmt_ip: spine1
  password: '********'
  username: admin
result: 
  exit_code: 0
  result:
    intf: true
    state: up
  stderr: 'st2.actions.python.ValidateInterfaceState: INFO     successfully connected to spine1 to validate interface state

    st2.actions.python.ValidateInterfaceState: INFO     Successfully Validated port channel/physical interface state as up

    st2.actions.python.ValidateInterfaceState: INFO     closing connection to spine1 after Validating interface state -- all done!

    '
  stdout: ''
mab@mab-infra:~$
```

### validate_L2_port_channel_state:

```
mab@mab-infra:~$ st2 run network_essentials.validate_L2_port_channel_state mgmt_ip=spine1 username=admin password=********** port_channel_id=30
......
id: 5a1bf1387cae220c046518d4
status: succeeded
parameters: 
  mgmt_ip: spine1
  password: '********'
  port_channel_id: '30'
  username: admin
result: 
  exit_code: 0
  result:
    member-ports:
    - ethernet 0/5
    - ethernet 0/7
    state: in_sync
  stderr: 'st2.actions.python.ValidateL2PortChannelState: INFO     successfully connected to spine1 to validate l2 port channel

    st2.actions.python.ValidateL2PortChannelState: INFO     closing connection to spine1 after validation of port channel -- all done!

    '
  stdout: ''
mab@mab-infra:~$
mab@mab-infra:~$ st2 execution get 5a1bf1387cae220c046518d4 -k result.member-ports
[u'ethernet 0/5', u'ethernet 0/7']
mab@mab-infra:~$
mab@mab-infra:~$ st2 execution get 5a1bf1387cae220c046518d4 -k result.state
in_sync
mab@mab-infra:~$  
```

### Ping:

```
mab@mab-infra:~$ st2 run network_essentials.ping_vrf_targets mgmt_ip=spine1 username=admin password=********** targets=172.16.10.116
.....
id: 5a1c2c2d7cae220c046518e3
status: succeeded
parameters: 
  mgmt_ip: spine1
  password: '********'
  targets:
  - 172.16.10.116
  username: admin
result: 
  exit_code: 0
  result: "[\n    {\n        \"ip_address\": \"172.16.10.116\",\n        \"packet loss\": \"0%\",\n        \"packets received\": \"4\",\n        \"packets transmitted\": \"4\",\n        \"result\": \"pass\"\n    }\n]"
  stderr: 'st2.actions.python.CheckPing: INFO     successfully executed cli ping 172.16.10.116 vrf default-vrf count 4 datagram-size 56 timeout 1

    '
  stdout: 'SSH connection established to spine1:22

    Interactive SSH session established

    Successful ping to 172.16.10.116

    '
mab@mab-infra:~$ 
```

### execute_cli (to get an arbitrary list of show commands):
```
mab@mab-infra:~$ st2 run network_essentials.execute_cli mgmt_ip=spine1 username=admin password==********** cli_cmd="show interface port-channel 30","show access-list ip".....
id: 5a1fe0707cae220a3a558791
status: succeeded
parameters: 
  cli_cmd:
  - show interface port-channel 30
  - show access-list ip
  mgmt_ip: spine1
  password: '********'
  username: admin
result: 
  exit_code: 0
  result:
    show access-list ip: "Interface Port-channel 30\n   Inbound access-list is acl_10 (From User)\n   Outbound access-list is not set\n"
    show interface port-channel 30: "Port-channel 30 is up, line protocol is up\nHardware is AGGREGATE, address is 78a6.e13a.9487\n    Current address is 78a6.e13a.9487\nInterface index (ifindex) is 671088670\nMinimum number of links to bring Port-channel up is 1\nMTU 1548 bytes\nLineSpeed Actual     : 200000 Mbit\nAllowed Member Speed : 100000 Mbit\nPriority Tag disable\nLast clearing of show interface counters: 3d00h02m\nQueueing strategy: fifo\nFEC Mode - Disabled\nReceive Statistics:\n    54894 packets, 4579320 bytes\n    Unicasts: 37607, Multicasts: 17268, Broadcasts: 19\n    64-byte pkts: 0, Over 64-byte pkts: 54894, Over 127-byte pkts: 0\n    Over 255-byte pkts: 0, Over 511-byte pkts: 0, Over 1023-byte pkts: 0\n    Over 1518-byte pkts(Jumbo): 0\n    Runts: 0, Jabbers: 0, CRC: 0, Overruns: 0\n    Errors: 0, Discards: 0\nTransmit Statistics:\n    54885 packets, 4728780 bytes\n    Unicasts: 37606, Multicasts: 17268, Broadcasts: 11\n    Underruns: 0\n    Errors: 0, Discards: 0\nRate info:\n    Input 0.000000 Mbits/sec, 0 packets/sec, 0.00% of line-rate\n    Output 0.000000 Mbits/sec, 0 packets/sec, 0.00% of line-rate\nTime since last interface status change: 2d23h54m\n"
  stderr: 'st2.actions.python.CliCMD: INFO     successfully connected to spine1 to find execute CLI [u''show interface port-channel 30'', u''show access-list ip'']

    st2.actions.python.CliCMD: INFO     successfully connected to spine1 to find execute CLI [u''show interface port-channel 30'', u''show access-list ip'']

    st2.actions.python.CliCMD: INFO     successfully executed cli show interface port-channel 30

    st2.actions.python.CliCMD: INFO     successfully executed cli show access-list ip

    st2.actions.python.CliCMD: INFO     closing connection to spine1 after executions cli cmds -- all done!

    st2.actions.python.CliCMD: INFO     closing connection to spine1 after executions cli cmds -- all done!

    '
  stdout: 'SSH connection established to spine1:22

    Interactive SSH session established

    '
mab@mab-infra:~$ 
```


## Setters (configuration commands):

### create_vlan / delete_vlan:
```
mab@mab-infra:~$ st2 run network_essentials.create_vlan mgmt_ip=spine1 username=admin password=********** vlan_id=200 vlan_desc="Customer BigCompany"
......
id: 5a201c967cae220a3a5587ee
status: succeeded
parameters: 
  mgmt_ip: spine1
  password: '********'
  username: admin
  vlan_desc: Customer BigCompany
  vlan_id: '200'
result: 
  exit_code: 0
  result:
    vlan: true
  stderr: 'st2.actions.python.CreateVlan: INFO     Successfully connected to spine1 to create interface vlans

    st2.actions.python.CreateVlan: INFO     Creating Vlans

    st2.actions.python.CreateVlan: INFO     Closing connection to spine1 after creating vlan -- all done!

    '
  stdout: ''
mab@mab-infra:~$
```

- Check on the device (via ssh):
```
spine1# show running-config vlan 200
vlan 200
 router-interface Ve 200
 description Customer BigCompany
!
spine1# 
```

### create_ve / delete_ve:
```
mab@mab-infra:~$ st2 run network_essentials.create_ve mgmt_ip=spine1 username=admin password=********** vlan_id=200 ip_address=10.2.2.1/24
........
id: 5a201d107cae220a3a5587f1
status: succeeded
parameters: 
  ip_address:
  - 10.2.2.1/24
  mgmt_ip: spine1
  password: '********'
  username: admin
  vlan_id: '200'
result: 
  exit_code: 0
  result:
    assign_ip: null
    create_ve: null
    pre_validation_ip: true
  stderr: 'st2.actions.python.CreateVe: INFO     successfully connected to spine1 to create Ve

    st2.actions.python.CreateVe: INFO     Creating VE 200 on rbridge-id None

    st2.actions.python.CreateVe: INFO     Assiging IP address 10.2.2.1/24 to VE 200 on rbridge-id None

    st2.actions.python.CreateVe: INFO     Admin state setting on Ve 200 is successfull

    st2.actions.python.CreateVe: INFO     closing connection to spine1 after creating Ve -- all done!

    '
  stdout: ''
mab@mab-infra:~$
```

- Check on the device (via ssh):
```
spine1# show running-config interface Ve 200
interface Ve 200
 ip proxy-arp
 ip address 10.2.2.1/24
 no shutdown
!
spine1# 
```

### set_intf_admin_state:
```
mab@mab-infra:~$ st2 run network_essentials.set_intf_admin_state mgmt_ip=spine1 username=admin password=********** intf_type=ethernet intf_name=0/1 intf_desc="ESX 110"
.......
id: 5a201ff77cae220a3a5587f4
status: succeeded
parameters: 
  intf_desc: ESX 110
  intf_name: 0/1
  intf_type: ethernet
  mgmt_ip: spine1
  password: '********'
  username: admin
result: 
  exit_code: 0
  result:
    interface: true
  stderr: 'st2.actions.python.SetIntfAdminState: INFO     successfully connected to spine1 to enable interface

    st2.actions.python.SetIntfAdminState: INFO     Setting admin state on intf-type-ethernet intf-name-0/1

    st2.actions.python.SetIntfAdminState: INFO     closing connection to spine1 after configuring enable interface -- all done!

    '
  stdout: ''
mab@mab-infra:~$
```

- Check on the device (via ssh):
```
spine1# show interface ethernet 0/1
Ethernet 0/1 is up, line protocol is up (connected)
Hardware is Ethernet, address is 78a6.e13a.9405
    Current address is 78a6.e13a.9405
Pluggable media present
Description: ESX 110
Interface index (ifindex) is 201335040
MTU 1548 bytes
Maximum Speed        : 100G
LineSpeed Actual     : 100000 Mbit
LineSpeed Configured : Auto, Duplex: Full
Priority Tag disable
Last clearing of show interface counters: 1w1d00h
Queueing strategy: fifo
FEC Mode - RS-FEC
Receive Statistics:
    125 packets, 14625 bytes
    Unicasts: 0, Multicasts: 125, Broadcasts: 0
    64-byte pkts: 0, Over 64-byte pkts: 125, Over 127-byte pkts: 0
    Over 255-byte pkts: 0, Over 511-byte pkts: 0, Over 1023-byte pkts: 0
    Over 1518-byte pkts(Jumbo): 0
    Runts: 0, Jabbers: 0, CRC: 0, Overruns: 0
    Errors: 0, Discards: 0
Transmit Statistics:
    131 packets, 15229 bytes
    Unicasts: 0, Multicasts: 129, Broadcasts: 2
    Underruns: 0
    Errors: 0, Discards: 0
Rate info:
    Input 0.000000 Mbits/sec, 0 packets/sec, 0.00% of line-rate
    Output 0.000000 Mbits/sec, 0 packets/sec, 0.00% of line-rate
Time since last interface status change: 00:02:33

spine1# 
```

- Validate Interf:ace state via **validate_interface_state** action:
```
mab@mab-infra:~$ st2 run network_essentials.validate_interface_state  mgmt_ip=spine1 username=admin password=********** intf_type=ethernet intf_name=0/1 intf_state=up
......
id: 5a20213f7cae220a3a5587f7
status: succeeded
parameters: 
  intf_name: 0/1
  intf_state: up
  intf_type: ethernet
  mgmt_ip: spine1
  password: '********'
  username: admin
result: 
  exit_code: 0
  result:
    intf: true
    state: up
  stderr: 'st2.actions.python.ValidateInterfaceState: INFO     successfully connected to spine1 to validate interface state

    st2.actions.python.ValidateInterfaceState: INFO     Successfully Validated port channel/physical interface state as up

    st2.actions.python.ValidateInterfaceState: INFO     closing connection to spine1 after Validating interface state -- all done!

    '
  stdout: ''
mab@mab-infra:~
```

### create_acl / delete_acl:
```
mab@mab-infra:~$ st2 run network_essentials.create_acl mgmt_ip=spine1 username=admin password=********** acl_type=extended acl_name=acl_10
...
id: 5a1c3eb47cae220c04651900
status: succeeded
parameters: 
  acl_name: acl_10
  acl_type: extended
  mgmt_ip: spine1
  password: **********
  username: admin
result: 
  exit_code: 0
  result: true
  stderr: 'st2.actions.python.CreateAcl: INFO     successfully connected to spine1

    st2.actions.python.CreateAcl: INFO     Creating ip ACL acl_10 of type extended

    st2.actions.python.CreateAcl: INFO     Successfully created ACL acl_10 in spine1

    '
  stdout: ''
mab@mab-infra:~$ 
```

### add_ipv4_rule_acl:

```
mab@mab-infra:~$ st2 run network_essentials.add_ipv4_rule_acl mgmt_ip=spine1 username=admin password=********** acl_name=acl_10 source=50.50.50.0/0.0.0.255 destination=60.60.60.0/0.0.0.255  protocol_type=udp seq_id=10 action=deny count=true log=true
...
id: 5a1c43c97cae220c0465190f
status: succeeded
parameters: 
  acl_name: acl_10
  action: deny
  count: 'true'
  destination: 60.60.60.0/0.0.0.255
  log: 'true'
  mgmt_ip: spine1
  password: '********'
  protocol_type: udp
  seq_id: 10
  source: 50.50.50.0/0.0.0.255
  username: admin
result: 
  exit_code: 0
  result:
    result: 'True'
  stderr: 'st2.actions.python.Add_Ipv4_Rule_Acl: INFO     successfully connected to spine1

    st2.actions.python.Add_Ipv4_Rule_Acl: INFO     successfully identified the acl_type as extended

    st2.actions.python.Add_Ipv4_Rule_Acl: INFO     seq_id for the rule is 10

    st2.actions.python.Add_Ipv4_Rule_Acl: INFO     Adding rule on access list- acl_10

    st2.actions.python.Add_Ipv4_Rule_Acl: INFO     Successfully added rule on acl_10

    st2.actions.python.Add_Ipv4_Rule_Acl: INFO     closing connection to spine1 after adding rule access-list-- all done!

    '
  stdout: ''
mab@mab-infra:~$ 
mab@mab-infra:~$ st2 run network_essentials.add_ipv4_rule_acl mgmt_ip=spine1 username=admin password=********** acl_name=acl_10 source=55.55.55.0/0.0.0.255 destination=65.65.65.0/0.0.0.255  protocol_type=udp seq_id=20 action=deny count=true log=true
...
id: 5a1c43e67cae220c04651912
status: succeeded
parameters: 
  acl_name: acl_10
  action: deny
  count: 'true'
  destination: 65.65.65.0/0.0.0.255
  log: 'true'
  mgmt_ip: spine1
  password: '********'
  protocol_type: udp
  seq_id: 20
  source: 55.55.55.0/0.0.0.255
  username: admin
result: 
  exit_code: 0
  result:
    result: 'True'
  stderr: 'st2.actions.python.Add_Ipv4_Rule_Acl: INFO     successfully connected to spine1

    st2.actions.python.Add_Ipv4_Rule_Acl: INFO     successfully identified the acl_type as extended

    st2.actions.python.Add_Ipv4_Rule_Acl: INFO     seq_id for the rule is 20

    st2.actions.python.Add_Ipv4_Rule_Acl: INFO     Adding rule on access list- acl_10

    st2.actions.python.Add_Ipv4_Rule_Acl: INFO     Successfully added rule on acl_10

    st2.actions.python.Add_Ipv4_Rule_Acl: INFO     closing connection to spine1 after adding rule access-list-- all done!

    '
  stdout: ''
mab@mab-infra:~$ 
mab@mab-infra:~$ st2 run network_essentials.add_ipv4_rule_acl mgmt_ip=spine1 username=admin password=********** acl_name=acl_10 source=58.58.58.0/0.0.0.255 destination=68.68.68.0/0.0.0.255  protocol_type=udp seq_id=30 action=deny count=true log=true
...
id: 5a1c44017cae220c04651915
status: succeeded
parameters: 
  acl_name: acl_10
  action: deny
  count: 'true'
  destination: 68.68.68.0/0.0.0.255
  log: 'true'
  mgmt_ip: spine1
  password: '********'
  protocol_type: udp
  seq_id: 30
  source: 58.58.58.0/0.0.0.255
  username: admin
result: 
  exit_code: 0
  result:
    result: 'True'
  stderr: 'st2.actions.python.Add_Ipv4_Rule_Acl: INFO     successfully connected to spine1

    st2.actions.python.Add_Ipv4_Rule_Acl: INFO     successfully identified the acl_type as extended

    st2.actions.python.Add_Ipv4_Rule_Acl: INFO     seq_id for the rule is 30

    st2.actions.python.Add_Ipv4_Rule_Acl: INFO     Adding rule on access list- acl_10

    st2.actions.python.Add_Ipv4_Rule_Acl: INFO     Successfully added rule on acl_10

    st2.actions.python.Add_Ipv4_Rule_Acl: INFO     closing connection to spine1 after adding rule access-list-- all done!

    '
  stdout: ''
mab@mab-infra:~$
```

### apply_acl / remove_acl:

```
mab@mab-infra:~$ st2 run network_essentials.apply_acl mgmt_ip=spine1 username=admin password=********** acl_name=acl_10 intf_type=port_channel intf_name=30 acl_direction=in 
......
id: 5a1c450d7cae220c04651918
status: succeeded
parameters: 
  acl_direction: in
  acl_name: acl_10
  intf_name:
  - 30
  intf_type: port_channel
  mgmt_ip: spine1
  password: '********'
  username: admin
result: 
  exit_code: 0
  result:
    result:
    - true
  stderr: "st2.actions.python.Apply_Acl: INFO     successfully connected to spine1\nst2.actions.python.Apply_Acl: INFO     successfully identified the access group type as ip\nst2.actions.python.Apply_Acl: INFO     Applying ACL acl_10 on int-type - port_channel int-name- 30\nst2.actions.python.Apply_Acl: INFO     Successfully applied acl_10 ACL on interface port_channel 30 \nst2.actions.python.Apply_Acl: INFO     closing connection to spine1 after applying access-list-- all done!\n"
  stdout: ''
mab@mab-infra:~$
```

- Check on the device (via ssh):
```
spine1# show access-list interface port-channel 30 in 
ip access-list acl_10 on Port-channel 30 at Ingress (From User)
    seq 10 deny udp 50.50.50.0 0.0.0.255 60.60.60.0 0.0.0.255 count log (Active)
    seq 20 deny udp 55.55.55.0 0.0.0.255 65.65.65.0 0.0.0.255 count log (Active)
    seq 30 deny udp 58.58.58.0 0.0.0.255 68.68.68.0 0.0.0.255 count log (Active)

spine1# 
```

### execute_cli (to send an arbitrary list of config commands)
```
mab@mab-infra:~$ st2 run network_essentials.execute_cli mgmt_ip=spine1 username=admin password=********** cli_cmd="interface ve 200","ip address 10.2.2.1/24","no shutdown" config_operation=true
......
id: 5a2003f97cae220a3a5587b2
status: succeeded
parameters: 
  cli_cmd:
  - interface ve 200
  - ip address 10.2.2.1/24
  - no shutdown
  config_operation: true
  mgmt_ip: spine1
  password: '********'
  username: admin
result: 
  exit_code: 0
  result:
    output: 'config term

      Entering configuration mode terminal

      spine1(config)# interface ve 200

      spine1(config-if-Ve-200)# ip address 10.2.2.1/24

      spine1(config-if-Ve-200)# no shutdown

      spine1(config-if-Ve-200)# end

      spine1# '
  stderr: 'st2.actions.python.CliCMD: INFO     successfully connected to spine1 to find execute CLI [u''interface ve 200'', u''ip address 10.2.2.1/24'', u''no shutdown'']

    st2.actions.python.CliCMD: INFO     successfully connected to spine1 to find execute CLI [u''interface ve 200'', u''ip address 10.2.2.1/24'', u''no shutdown'']

    st2.actions.python.CliCMD: INFO     successfully executed config cli [u''interface ve 200'', u''ip address 10.2.2.1/24'', u''no shutdown'']

    st2.actions.python.CliCMD: INFO     closing connection to spine1 after executions cli cmds -- all done!

    st2.actions.python.CliCMD: INFO     closing connection to spine1 after executions cli cmds -- all done!

    '
  stdout: 'SSH connection established to spine1:22

    Interactive SSH session established

    '
mab@mab-infra:~$
mab@mab-infra:~$ st2 run network_essentials.execute_cli mgmt_ip=spine1 username=admin password=********** cli_cmd="show running-config interface ve 200".....
id: 5a20040a7cae220a3a5587b5
status: succeeded
parameters: 
  cli_cmd:
  - show running-config interface ve 200
  mgmt_ip: spine1
  password: '********'
  username: admin
result: 
  exit_code: 0
  result:
    show running-config interface ve 200: "interface Ve 200\n ip proxy-arp\n ip address 10.2.2.1/24\n no shutdown\n!"
  stderr: 'st2.actions.python.CliCMD: INFO     successfully connected to spine1 to find execute CLI [u''show running-config interface ve 200'']

    st2.actions.python.CliCMD: INFO     successfully connected to spine1 to find execute CLI [u''show running-config interface ve 200'']

    st2.actions.python.CliCMD: INFO     successfully executed cli show running-config interface ve 200

    st2.actions.python.CliCMD: INFO     closing connection to spine1 after executions cli cmds -- all done!

    st2.actions.python.CliCMD: INFO     closing connection to spine1 after executions cli cmds -- all done!

    '
  stdout: 'SSH connection established to spine1:22

    Interactive SSH session established

    '
mab@mab-infra:~$
```

### set_:

```
```

### set_:

```
```