---
description: >-
  The DEB packages are suitable for Debian, Ubuntu, and other Debian-based
  systems.
---

# Install agent with DEB packages

{% hint style="info" %}
Many of the commands described below need to be executed with root user privileges.
{% endhint %}

## Adding the repository

The first step to installing the Wazuh agent is to add the Wazuh repository to your server. Alternatively, if you prefer to download the wazuh-agent package directly

1. To perform this procedure, the `curl`, `apt-transport-https` and `lsb-release` packages must be installed on your system. If they are not already present, install them using the commands below:

```
apt-get install curl apt-transport-https lsb-release
```

2. Install the Wazuh repository GPG key:

```text
curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | apt-key add -
```

3. Add the repository:

```text
echo "deb https://packages.wazuh.com/3.x/apt/ stable main" | tee /etc/apt/sources.list.d/wazuh.list
```

4. Update the package information:

```text
apt-get update
```

## Installing agent

1. On your terminal, install the Wazuh agent:

```text
apt-get install wazuh-agent
```

2. \(Optional\) Disable the Wazuh updates:

It is recommended that the Wazuh repository be disabled in order to prevent accidental upgrades. To do this, use the following command:

```text
sed -i "s/^deb/#deb/" /etc/apt/sources.list.d/wazuh.list
apt-get update
```

 Alternately, you can set the package state to `hold`, which will stop updates \(although you can still upgrade it manually using `apt-get install`\).

```text
echo "wazuh-agent hold" | sudo dpkg --set-selections
```

{% hint style="info" %}
Now that the agent is installed, the next step is to register and configure it to communicate with the manager.
{% endhint %}



