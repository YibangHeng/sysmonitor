# sysmonitor

Monitor local computer status using Grafana, Prometheus, and node_exporter.

## Install node_exporter

1. Download node_exporter from [Releases page](https://github.com/prometheus/node_exporter/releases).

2. Unzip and move node_exporter to /usr/local/bin.

   ```sh
   tar -xzvf ${node_exporter}.tar.gz
   sudo install -t /usr/local/bin /path/to/node_exporter
   ```

   > Note  
   > Replace `${node_exporter}` and `/path/to/node_exporter` with the name of your downloaded file.

3. Create a system service for node_exporter.

   ```sh
   sudo cp node_exporter.service /etc/systemd/system/node_exporter.service
   sudo systemctl daemon-reload
   sudo systemctl start node_exporter
   sudo systemctl enable node_exporter
   ```

4. Open browser and go to [http://localhost:9100](http://localhost:9100) to check node_exporter status.

## Deploy Prometheus and Grafana with docker compose

```sh
$ docker compose up -d
Creating network "prometheus-grafana_default" with the default driver
Creating volume "prometheus-grafana_prom_data" with default driver
...
Creating grafana    ... done
Creating prometheus ... done
Attaching to prometheus, grafana

```
