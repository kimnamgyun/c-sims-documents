# Start Metricbeat

 Run Metricbeat by issuing the appropriate command for your platform. If you are accessing a secured Elasticsearch cluster, make sure you’ve configured credentials as described in Configure Metricbeat.

### 1. Deb and Rpm

```text
sudo service metricbeat start
```

### 2. Win

```text
PS C:\Program Files\Metricbeat> Start-Service metricbeat
```

 By default the log files are stored in `C:\ProgramData\metricbeat\Logs`.



{% hint style="info" %}
On Windows, statistics about system load and swap usage are currently not captured.
{% endhint %}

