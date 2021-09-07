This repository contains files that make up Kubernetes cluster developed for my thesis work.
The cluster can not be deploy because of the inconsistency of some parameters present in the yaml files correlated
to the environment where i deployed the cluster.
The university assigned me a server where i installed VMWare EXSi hypervisor thanks to which i created 6 VMs.
Four of these composed Kubernetes cluster while the other two were used for iSCSI server and reverse proxy, like HAproxy.
Thesis's target was to handle Guacamole microservices through Kubernetes cluster permitting students and teachers to connect
remotly to PC's laboratory.


Guacamole directory contains the deployment of the main microservices like Guacamole,Guacd and postgreSQL that mounts
a disk thanks to ISCSi protocol.The others file concern the ingress resource , used for route incoming request to guacamole service,
and HPA resources used for scale guacd deployment based on particular metric generated by prometheus adapter.

Monitoring directory contains the prometheus adapter configuration file to create the custom metric and grafana ingress
to permit the visualization of the metrics in a specific dashboard.
All the rest resources are taken from kube-prometheus repository.


Nginx directory contains nginx_controller deployment and the relative service so that connections from reverse proxy,place outside the cluster,
come redirects in the right service based on hostname requested.

Stress directory contains the deployment relative to the selenium HUB and to chrome-node used for execute Selenium script.
These resources have been assigned to a specific node , added only to run stress test.
The ingress resource is used for connect the user to the web panel of the selenium hub in order to check the 
configurations of the node registered to the HUB.


![ScreenShot](https://github.com/dredge17/Kubernetes_Guacamole/blob/master/projetc_scheme.png)