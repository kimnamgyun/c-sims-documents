# Configure Metricbeat

 To configure Metricbeat, you edit the configuration file. The default configuration file is called  /etc/_metricbeat_ /_metricbeat_. _yml_. The location of the file varies by platform.

 There’s also a full example configuration file called `metricbeat.reference.yml` that shows all non-deprecated options.

{% hint style="info" %}
 See the Config File Format section of the _Beats Platform Reference_ for more about the structure of the config file.
{% endhint %}

To configure Metricbeat:

1.  Configure the output. Metricbeat supports a variety of outputs, but typically you’ll either send events directly to Elasticsearch, or to Logstash for additional processing.

To send output directly to Elasticsearch \(without using Logstash\), set the location of the Elasticsearch installation: 

If you’re running Elasticsearch on your own hardware, set the host and port where Metricbeat can find the Elasticsearch installation. For example:

```text
output.elasticsearch:
hosts: ["myEShost:9200"]
```

2. If you plan to use the sample Kibana dashboards provided with Metricbeat, configure the Kibana endpoint. You can skip this step if Kibana is running on the same host as Elasticsearch.

```text
setup.kibana:
host: "mykibanahost:5601" 
```

3. If you’re running Elasticsearch on your own hardware, specify your Elasticsearch and Kibana credentials:

```text
output.elasticsearch:
  hosts: ["myEShost:9200"]
  username: "filebeat_internal"
  password: "YOUR_PASSWORD" 
setup.kibana:
  host: "mykibanahost:5601"
  username: "my_kibana_user"  
  password: "YOUR_PASSWORD"
```









