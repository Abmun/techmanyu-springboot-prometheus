# techmanyu-springboot-prometheus

Steps to run on docker:

//build the solution jar
mvn clean package

//create image
docker build -t techmanyu-springboot-prometheus .

//run docker container
docker-compose up -d

---------------------------

Above steps will run techmanyu-service and expose on port 9000

Prometheus Metrics Endpoint-
http://localhost:9000/prometheus or http://techmanyu-service:9000/prometheus

Prometheus Service will run on a new container on port 9090
http://localhost:9090

AlertManager will run on a new container on port 9093
http://localhost:9093

Grafana will run on a new container on port 3000
http://localhost:3000
Creds - admin/admin

----------------------------
Service Details-
----------------
Prometheus will have 1 alert rule configured for Instance down Alert.
Metrics from techmanyu-service will be scraped by prometheus in real time

AlertManager.yml has placeholder for webhook API URL and slack channel name. Configure it as per environment.

Grafana data source needs to be configured.
