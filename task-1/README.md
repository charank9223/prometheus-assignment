## Run Node Exporter on local machine

Steps followed  to install node exporter on linux node

1. Download node exporter binary from below official source

wget https://github.com/prometheus/node_exporter/releases/download/v1.5.0/node_exporter-1.5.0.linux-amd64.tar.gz --no-check-certificate

2. extract the binary 

tar -xzvf node_exporter-1.5.0.linux-amd64.tar.gz

3. change directory to node_exporter-1.5.0.linux-amd64

4. Run the binary as background proecess

nohup ./node_exporter &

5. we can see the metrics at curl http://localhost:9100/metrics endpoint 

![task-1](https://user-images.githubusercontent.com/105341216/216103204-c301ba99-2e60-4f51-b2ef-cac804278c26.png)

