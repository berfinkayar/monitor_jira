# Case 4
The purpose of this case is to monitor and interpret activities occuring in JIRA.

## Prerequisites
Make sure Docker is installed on your system. If not, you can download and install it from [here](https://docs.docker.com/get-docker/).

## Getting Started
1. Clone this repository.
```bash
git clone http://52.59.214.22/berfin-kayar/hafta-4/gun-2/
```
2. In the project directory, run the following command and start the services.
```bash
docker-compose up -d
```
3. You can access JIRA in your web browser at `http://localhost:8080`. 

## Connecting JIRA with Prometheus
1. In JIRA go to Administration > Manage Apps . Install the 'Prometheus Exporter for JIRA' add-on. 
2. You can access Prometheus in your web browser at `http://localhost:9090`. Prometheus configurations are already done in prometheus.yml, therefore you will be seeing that JIRA and Grafana are up, at Status > Targets.

![alt text](/screenshots/prometheus.png)

## Connecting Grafana with Prometheus
1. Grafana is accessable in your web browser at `http://localhost:3000`. Login by entering "admin" for both username and password. 
2. Go to 'add data source' and click Prometheus and enter its address. ("http://prometheus:9090") (not localhost, since they're both run in separate containers and can't be reached via localhost)
3. You can now create your dashboard on Grafana with the data you fetched from JIRA. You can also use a template for JIRA. For the template below go to Dashboards > New > Import and enter the dashboard id of 5249. 

![alt text](/screenshots/dashboard-1.png)
![alt text](/screenshots/dashboard-2.png)

And these are some queries I've run and got panels of.

![alt text](/screenshots/dashboard-3.png)
