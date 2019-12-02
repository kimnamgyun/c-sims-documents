---
description: >-
  The RPM package is suitable for installation on Red Hat, CentOS and other
  RPM-based systems.
---

# Install Wazuh agent with RPM packages

{% hint style="info" %}
Many of the commands described below need to be executed with root user privileges.
{% endhint %}

## Adding the repository

Set up the repository by running the following commands according to your distribution:

### CentOS 6/RHEL 6, CentOS 7/RHEL 7, Fedora 22 or greater and Amazon Linux

```text
cat > /etc/yum.repos.d/wazuh.repo <<\EOF
[wazuh_repo]
gpgcheck=1
gpgkey=https://packages.wazuh.com/key/GPG-KEY-WAZUH
enabled=1
name=Wazuh repository
baseurl=https://packages.wazuh.com/3.x/yum/
protect=1
EOF
```

### CentOS 5/RHEL 5

```text
cat > /etc/yum.repos.d/wazuh.repo <<\EOF
[wazuh_repo]
gpgcheck=1
gpgkey=http://packages.wazuh.com/key/GPG-KEY-WAZUH-5
enabled=1
name=Wazuh repository
baseurl=http://packages.wazuh.com/3.x/yum/5/$basearch/
protect=1
EOF
```

### SUSE 12

```text
rpm --import https://packages.wazuh.com/key/GPG-KEY-WAZUH
cat > /etc/zypp/repos.d/wazuh.repo <<\EOF
[wazuh_repo]
gpgcheck=1
gpgkey=https://packages.wazuh.com/key/GPG-KEY-WAZUH
enabled=1
name=Wazuh repository
baseurl=https://packages.wazuh.com/3.x/yum/
protect=1
EOF
```

### SUSE 11

```text
rpm --import https://packages.wazuh.com/key/GPG-KEY-WAZUH-5
cat > /etc/zypp/repos.d/wazuh.repo <<\EOF
[wazuh_repo]
gpgcheck=1
gpgkey=http://packages.wazuh.com/key/GPG-KEY-WAZUH-5
enabled=1
name=Wazuh repository
baseurl=http://packages.wazuh.com/3.x/yum/5/$basearch/
protect=1
EOF
```

## Installing agent

1. On your terminal, install the Wazuh agent as follows:

* Using the `yum` package manager:

```text
yum install wazuh-agent
```

*  Using the `zypper` package manager:

```text
zypper install wazuh-agent
```

2. \(Optional\) Disable the Wazuh repository:

It is recommended that the Wazuh repository be disabled in order to prevent accidental upgrades. To do this, use the following command:

*  Using the `yum` package manager:

```text
sed -i "s/^enabled=1/enabled=0/" /etc/yum.repos.d/wazuh.repo
```

*  Using the `zypper` package manager:

```text
Using the zypper package manager:
```

{% hint style="info" %}
Now that the agent is installed, the next step is to register and configure it to communicate with the manager
{% endhint %}

