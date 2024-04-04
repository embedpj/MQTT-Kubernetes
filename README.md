##  Setting up one pod of MQTT in kubernetes cluster
create a new folder "mosquitto" 
add the three file

  > mosquitto-config.yaml <br>
  > service.yaml <br>
  > deployment.yaml <br>
 
run the command to start container
```
kubectl apply -f mosquitto/
```

run the command to see the pods & services
```
kubectl get pods,deployments,services -o wide
```
You can test on a network pc by

C:\Program Files\mosquitto>mosquitto_pub -h 192.xxx.xxx.134 -p 31883 -t house/12 -m "testing ok"

C:\Program Files\mosquitto>mosquitto_sub -h 192.xxx.xxx.134 -p 31883 -t house/#  
***testing ok***

## Kubernetes HA (High Availability) testing  
Started one instance of MQTT. Placed on worker2 (VM2) decided by kuberenetes
Shut down the worker2 (VM2).   
Kuberenetes restarted the pod on worker1 (VM1) that was available.

![image](https://github.com/embedpj/MQTT-Kubernetes/assets/14286200/6c9ef01a-2bd9-4366-8095-af804db59bbf)

