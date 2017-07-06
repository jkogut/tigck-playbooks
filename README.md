# tigck-playbooks
Ansible playbooks for TICK+G (Telegraf, InfluxDB, Chronograf, Kapacitor + Granafa) stack



Install InfluxDB with ansible:
-----------------------------

Edit host section and add your influxDB server, then run playbook with:


`ansible-playbook install-influx-monitoring.yml`


*Example output for server: my-influxdDB-server* 

```
PLAY ***************************************************************************

TASK [setup] *******************************************************************
ok: [my-influxdDB-server]

TASK [influx : Install libselinux-python] **************************************
changed: [my-influxdDB-server]

TASK [influx : Create a influxdb.repo file] ************************************
changed: [my-influxdDB-server]

TASK [influx : Update /etc/yum.repos.d/influxdb.repo file] *********************
changed: [my-influxdDB-server]

TASK [influx : Install influxdb] ***********************************************
changed: [my-influxdDB-server]

TASK [influx : Enable and start influxdb] **************************************
changed: [my-influxdDB-server] => (item=/bin/systemctl daemon-reload)
changed: [my-influxdDB-server] => (item=/bin/systemctl enable influxdb.service)
changed: [my-influxdDB-server] => (item=/bin/systemctl start influxdb.service)

TASK [influx : Create testdb in influxDB] **************************************
changed: [my-influxdDB-server]
 [WARNING]: Consider using get_url module rather than running curl
 
 
 PLAY RECAP *********************************************************************
 my-influxdDB-server               : ok=7    changed=6    unreachable=0    failed=0   
```
