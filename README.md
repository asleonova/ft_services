# ft_services

This project is clusturing a docker-compose application and deploying it with Kubernetes. Services include an nginx, an FTPS, a Wordpress and a PHPMyAdmin working with a MySQL database, and a Grafana linked to an InfluxDB database for monitoring. The script builds the custom Docker images for each of those, before deploying and exposing them all with custom yaml files.

### Pre-installation:

Make sure you have **Docker ToolBox** installed on your computer, that you have **Filezilla app** for checking the work of FTPS server and **minikube**.

Quick installation of **minikube**:

```
brew install minikube
```

*__!!! Make sure you also have enough space available on your hardware!!!__*

### Usage:

After cloning the repo, simply execute the setup file:
```
./setup.sh
```

Run it again once it's installed the requirements.


http://coding-girl.ru/wp-content/uploads/2021/03/services.png
