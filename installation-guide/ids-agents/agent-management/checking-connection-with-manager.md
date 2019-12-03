# Checking connection with Manager

 Before you check the agent’s connection with the manager, first ensure the agent is pointing to the manager’s IP address. This is set in /var/ossec/etc/ossec.conf using the `<client>` XML tag.

```text
<ossec_config>
  <client>
    <server>
      <address>10.0.0.10</address> 
      <protocol>udp</protocol>
    </server>
  </client>
</ossec_config>
```

This will set 10.0.0.10 as the Wazuh Manager server. Once this is done, you will need restart the Agent:

1. For Systemd:

```text
systemctl restart wazuh-agent
```

2. For SysV Init:

```text
service wazuh-agent restart
```

After you register the agent and it has successfully connected, you can see a list of agents that are connected to the manager with:

```text
After you register the agent and it has successfully connected, you can see a list of agents that are connected to the manager with:
```

You can also check to see if an agent connected correctly by verifying if the UDP connection to the manager is established:

```text
netstat -vatunp|grep ossec-agentd
```

The result should match the agent and manager IP addresses.

