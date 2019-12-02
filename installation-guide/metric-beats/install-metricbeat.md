# Install Metricbeat

You should install Metricbeat as close as possible to the service you want to monitor. For example, if you have four servers with MySQL running, it’s recommended that you run Metricbeat on each server. This allows Metricbeat to access your service from localhost and does not cause any additional network traffic or prevent Metricbeat from collecting metrics when there are network problems. Metrics from multiple Metricbeat instances will be combined on the Elasticsearch server.

{% hint style="info" %}
If you use Apt or Yum, you can install Metricbeat from our repositories to update to the newest version more easily. See our download page for other installation options, such as 32-bit images.
{% endhint %}

##  **1. deb**

```text
curl -L -O https://artifacts.elastic.co/downloads/beats/metricbeat/metricbeat-7.4.2-amd64.deb
sudo dpkg -i metricbeat-7.4.2-amd64.deb
```

##  2. **rpm**

```text
curl -L -O https://artifacts.elastic.co/downloads/beats/metricbeat/metricbeat-7.4.2-x86_64.rpm
sudo rpm -vi metricbeat-7.4.2-x86_64.rpm
```

## **3. Win**

1.  Download the Metricbeat Windows zip file from the downloads page.
2.  Extract the contents of the zip file into `C:\Program Files`.
3.  Rename the `metricbeat-<version>-windows`\` directory to `Metricbeat`.
4.  Open a PowerShell prompt as an Administrator \(right-click the PowerShell icon and select **Run As Administrator**\).
5. From the PowerShell prompt, run the following commands to install Metricbeat as a Windows service:

```text
PS > cd 'C:\Program Files\Metricbeat'
PS C:\Program Files\Metricbeat> .\install-service-metricbeat.ps1
```

{% hint style="success" %}
If script execution is disabled on your system, you need to set the execution policy for the current session to allow the script to run. For example: `PowerShell.exe -ExecutionPolicy UnRestricted -File .\install-service-metricbeat.ps1`
{% endhint %}

 Before starting Metricbeat, you should look at the configuration options in the configuration file, for example `C:\Program Files\Metricbeat\metricbeat.yml`

