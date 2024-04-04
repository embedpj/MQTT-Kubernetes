##  Setting up one pod of MQTT in kubernetes
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

