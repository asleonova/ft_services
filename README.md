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
  <img src="http://coding-girl.ru/wp-content/uploads/2021/03/services.png" width="100%" />
  
  
The main page:
<p align="center">
  <img src="http://coding-girl.ru/wp-content/uploads/2021/03/main_page.png" width="100%" />
</p>

Minikube dashboard:
<p align="center">
  <img src="http://coding-girl.ru/wp-content/uploads/2021/03/dashboard.png width="100%" />
</p>

| Italic             |  Block letters |
:-------------------------:|:-------------------------:
![]("http://coding-girl.ru/wp-content/uploads/2021/03/services.png")  |  ![](outputs/output_Biotouch/18-15_02-02-2018/Identification/BLOCK_LETTERS/BLOCK_LETTERS_movementPoints_cmc.png)
![](outputs/output_Biotouch/18-15_02-02-2018/Verification/ITALIC/ITALIC_movementPoints_notbalanced_roc.png)  |  ![](outputs/output_Biotouch/18-15_02-02-2018/Verification/BLOCK_LETTERS/BLOCK_LETTERS_movementPoints_notbalanced_roc.png)
![](outputs/output_Biotouch/18-15_02-02-2018/Verification/ITALIC/ITALIC_movementPoints_notbalanced_frrVSfpr.png)  |  ![](outputs/output_Biotouch/18-15_02-02-2018/Verification/BLOCK_LETTERS/BLOCK_LETTERS_movementPoints_notbalanced_frrVSfpr.png)                                                                       
                                                                                
