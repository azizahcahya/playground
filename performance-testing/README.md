# Simple web service for performance test

- run `go run main.go` to start

---

## Monitoring information

### How to use

- change directory to monitoring
- run `docker-compose up -d`

### Grafana setting

- use `http://km-prometheus:9090` for prometheus url
- scrape interval set to 3s
- create new panel and use this metric browser

  ```promql
  sum(rate(http_request_count{}[5s])) by (response_code)
  ```

### Note

- firewall rule (so host.docker.internal will work)
- scrape interval for prometheus (on prom and grafana)