## Prerequisites

* Logstash 2.1.1
* Elasticsearch 2.1.1
* Kibana 4.3.1

## Loading the data

- Edit the logstash config file, `logstash/parking-meters.conf` and make the following changes:

 - Set `input.file.path` to the absolute path to `data/parking-meters.csv`
 - Set `output.elasticsearch.template` to the absolute path to `elasticsearch/template.json`
 - Set `output.elasticsearch.hosts` to host(s) in your Elasticsearch cluster. You can procure an Elasticsearch cluster from [Found](https://www.elastic.co/found).


- Run logstash:
```sh
logstash --config logstash/parking-meters.conf
```

## Visualizing the data

1. Open Kibana in your browser

2. (First time only) Go to _Settings > Objects_, then click the Import button. Upload the file `kibana/export.json`

3. Go to _Dashboard_, then click the icon for loading saved dashboards (looks like an open folder), then select "Pasadena Parking"
