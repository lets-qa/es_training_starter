# Elasticsearch 101

A quickstart guide for running Elasticsearch and related tools with Docker.

---

## Setup

Run Elasticsearch and supporting services:

```sh
docker-compose up -d
```

---

## Services

- **Elasticsearch:** [http://localhost:9200](http://localhost:9200)
- **Kibana (Dev Tools):** [http://localhost:5601](http://localhost:5601)
- **Elasticvue:** [http://localhost:9280](http://localhost:9280)
- **Elastic Head:** [http://localhost:9100](http://localhost:9100)

---

## Additional Tools

- [Elasticvue](https://elasticvue.com/)
- [Elasticsearch Head](https://github.com/mobz/elasticsearch-head)

---

## Example: Cluster Health Check

```sh
curl -X GET "localhost:9200/_cluster/health?pretty"
```

Sample output:
```json
{
  "cluster_name" : "docker-cluster",
  "status" : "red",
  "timed_out" : false,
  "number_of_nodes" : 1,
  "number_of_data_nodes" : 1,
  "active_primary_shards" : 0,
  "active_shards" : 0,
  "relocating_shards" : 0,
  "initializing_shards" : 0,
  "unassigned_shards" : 6,
  "delayed_unassigned_shards" : 0,
  "number_of_pending_tasks" : 0,
  "number_of_in_flight_fetch" : 0,
  "task_max_waiting_in_queue_millis" : 0,
  "active_shards_percent_as_number" : 0.0
}
```

---

## Troubleshooting

- If you get Kibana disk space issues, increase your allocation in Docker.

