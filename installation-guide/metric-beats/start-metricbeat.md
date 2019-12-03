# Start Metricbeat

 Run Metricbeat by issuing the appropriate command for your platform. If you are accessing a secured Elasticsearch cluster, make sure you’ve configured credentials as described in Configure Metricbeat.

### 1. DEB and RPM

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

### Test the Metricbeat installation

To verify that your server’s statistics are present in Elasticsearch, issue the following command:

```text
curl -XGET 'http://localhost:9200/metricbeat-*/_search?pretty'
```

 Make sure that you replace `localhost:9200` with the address of your Elasticsearch instance.

