## Download and run Thanos Sidecar, configure it to read TSDB from local prometheus without bucket config

1. Add the external labels to prometheus.yml and restart the prometheus service.
   ```bash
    global:
      external_labels:
        cluster: local
    ```
2. Run thanos side-car container by using docker
    ```bash
    docker run -d --net=host \  
    --name prometheus-sidecar \
    quay.io/thanos/thanos:v0.28.0 \
    sidecar \
    --http-address 0.0.0.0:19090 \
    --grpc-address 0.0.0.0:19190 \
    --tsdb.path /home/charan/assignments/prometheus/prometheus-2.37.5.linux-amd64/prom_data \
    --prometheus.url http://localhost:9090
    ```
3. We can three targets added to prometheus.
![task3-1](https://user-images.githubusercontent.com/37712815/216128804-04259405-398d-483c-b3cc-0913595db8ed.png)

4. We can see metrics at sidecar endpoint http://localhost:19090/metrics 
![task-3-2](https://user-images.githubusercontent.com/37712815/216128831-930df4fb-a670-4f78-b9db-50cc3e9c6590.png)
