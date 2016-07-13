# custom_elasticsearch_ranking
This is samples of how to custom ranking algorithm of Elastic Search

## Preliminary

### elasticsearch

```
wget https://download.elastic.co/elasticsearch/release/org/elasticsearch/distribution/zip/elasticsearch/2.3.4/elasticsearch-2.3.4.zip
unzip elasticsearch-2.3.4.zip
echo "script.inline: true" >> elasticsearch-2.3.4/config/elasticsearch.yml
echo "script.indexed: true" >> elasticsearch-2.3.4/config/elasticsearch.yml
elasticsearch-2.3.4/bin/plugin install mobz/elasticsearch-head
elasticsearch-2.3.4/bin/plugin install analysis-kuromoji
elasticsearch-2.3.4/bin/elasticsearch
...
```

### kibana

```
# OSX
wget https://download.elastic.co/kibana/kibana/kibana-4.5.2-darwin-x64.tar.gz
tar zxvf kibana-4.5.2-darwin-x64.tar.gz
kibana-4.5.2-darwin-x64/bin/kibana plugin --install elastic/sense
kibana-4.5.2-darwin-x64/bin/kibana
...
```

## Demo

```
open http://localhost:5601/app/sense
```

### Stemming

see [here](http://localhost:5601/app/sense?load_from=https://raw.githubusercontent.com/sosuke-k/custom_elasticsearch_ranking/master/porter_stemming.json)

### Scoring

see [here](http://localhost:5601/app/sense?load_from=https://raw.githubusercontent.com/sosuke-k/custom_elasticsearch_ranking/master/term_statistics.json)

### Synonyms

see [here](http://localhost:5601/app/sense?load_from=https://raw.githubusercontent.com/sosuke-k/custom_elasticsearch_ranking/master/synonym_filter.json)

### POS

see [here](http://localhost:5601/app/sense?load_from=https://raw.githubusercontent.com/sosuke-k/custom_elasticsearch_ranking/master/stop_posfilter.json)
