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

The minicube dashboard opens automatically where you see your pods running. Even after killing the services, it relaunches correctly, the info from databases is not lost. You can check that by running pkill command, e.g.:
```
kubectl exec deploy/grafana -- pkill grafana
```

Here's how everything in the cluster is interconnected:
<p align="center">
  <img src="http://coding-girl.ru/wp-content/uploads/2021/03/services.png" width="50%" />
  

<table style="padding:10px">
  <tr>
    <td> 
         <img src="http://coding-girl.ru/wp-content/uploads/2021/03/dashboard.png"  alt="1" width = 288px height = 288px ></td>
      
 <td><img src="http://coding-girl.ru/wp-content/uploads/2021/03/main_page.png" align="right" alt="2" width = 288px height = 288px></td>
   <td><img src="http://coding-girl.ru/wp-content/uploads/2021/03/wp.png" alt="3" width = 288px height = 288px></td>
    
  </tr>
</table>
                                                      
                                                                                
