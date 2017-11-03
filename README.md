## Grafana project

I will use the Prometheus server for scraping and store time series data. 
Grafana will collect the time series data and stand for the visialisation of the graphs.

### Architecture
Both Prometheus and Grafana will run i docker container.

## Docker 
Grafana
```
docker rm -f redpill-grafana
docker rmi redpill/grafana
docker build -t redpill/grafana grafana/.
docker run --name redpill-grafana -d -p 3000:3000 redpill/grafana
docker logs -f redpill-grafana
```

Prometheus
```
docker rm -f redpill-prometheus-server
docker rmi redpill/prometheus-server
docker build -t redpill/prometheus-server prometheus/.
docker run --name redpill-prometheus-server -d -p9090:9090 redpill/prometheus-server
docker logs -f redpill-prometheus-server
```