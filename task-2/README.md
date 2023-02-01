## Run Node Exporter on local machine

Steps followed to install prometheus on linux node

1. Download prometheus binary from below official source.

    wget https://github.com/prometheus/prometheus/releases/download/v2.37.5/prometheus-2.37.5.linux-amd64.tar.gz --no-check-certificate

2. Extract the binary. 

    tar xzvf prometheus-2.37.5.linux-amd64.tar.gz

3. Change directory to prometheus-2.37.5.linux-amd64 folder. 

4. Create a directory to store the data

    mkdir prom_data

5. Configure the prometheus.yml to add the nodes to be scraped. 

6. Run the prometheus as background proccess.

    nohup ./prometheus --config.file=prometheus.yml --storage.tsdb.path ./prom_data &

7. We can access prometheus from  http://localhost:9090/  and we can see that two jobs(prometheus, linux-node) are added and metrics are getting scraped from endpoints.

![task-2](https://user-images.githubusercontent.com/37712815/216111619-d5fc4acf-74ce-4907-a5b3-cdd4b3b66580.png)
