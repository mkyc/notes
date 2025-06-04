# delete logs from loki

to delete logs have following variables set: 

```yaml
compactor:
  retention_enabled: true
  deletion_mode: filter-and-delete
  retention_delete_delay: 3m
  delete_request_cancel_period: 3m
```

then POST delete query to loki (using PortForward in this example):

```bash
curl -g -X POST 'http://localhost:3100/loki/api/v1/delete?query={someLabel="someValue"}|="someText"&start=1712157603&end=1727968663'
```

and check if logs deletion process is finished by running query:

```bash
curl -X GET http://localhost:3100/loki/api/v1/delete | jq
```

that will present list with something like this: 

```json
[
  {
    "request_id": "83cd8b0a",
    "start_time": 1712157603,
    "end_time": 1727968663,
    "query": "{someLabel=\"someValue\"}|=\"someText\"",
    "status": "received",
    "created_at": 1727968858.753
  }
]
```

and status will change to `processed` after some time (depends on how long the selected period is). 
