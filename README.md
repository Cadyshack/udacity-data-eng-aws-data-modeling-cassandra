# Cassandra Docker Compose Setup

## Usage

Start Cassandra:
```bash
docker-compose up -d
```

Stop Cassandra:
```bash
docker-compose down
```

View logs:
```bash
docker-compose logs -f
```

## Connect from Python

```python
from cassandra.cluster import Cluster

cluster = Cluster(['127.0.0.1'])
session = cluster.connect()
```

## Data Persistence

Data is stored in `./data` directory and persists between container restarts.

## Notes

- Cassandra takes 30-60 seconds to fully start
- Port 9042 is exposed for CQL connections
- The healthcheck ensures the service is ready before reporting as healthy