# Lab_1

## Overview:
- Invoking actions from the **network_essentials** pack.
- Sections:
    - [Getters (show commands)](https://github.com/mab27/nw_automation_on_slx/tree/master/stackstorm/labs/lab_1#getters-show-commands)
    	- [get_os_version](https://github.com/mab27/nw_automation_on_slx/tree/master/stackstorm/labs/lab_1#get_os_version)
      	- [validate_interface_state](https://github.com/mab27/nw_automation_on_slx/tree/master/stackstorm/labs/lab_1#validate_interface_state)
      	- [validate_L2_port_channel_state](https://github.com/mab27/nw_automation_on_slx/tree/master/stackstorm/labs/lab_1#validate_l2_port_channel_state)
      	- [ping](https://github.com/mab27/nw_automation_on_slx/tree/master/stackstorm/labs/lab_1#ping)
      	- [execute_cli (to get an arbitrary list of show commands)]()
    - [Setters (configuration commands)](https://github.com/mab27/nw_automation_on_slx/tree/master/stackstorm/labs/lab_1#setters-configuration-commands)
    	- [create_acl]()
    	- [add_ipv4_rule_acl]()
    	- [apply_acl]()
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

### create_acl:

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

### apply_acl:

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
```

### set_:

```
```

### set_:

```
```