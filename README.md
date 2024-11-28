# expense-k8

kubectl replace -f manifest.yml

kubectl port-forward pod/<pod-name> <local-port>:<pod-port>
kubectl port-forward pod/frontend-54d95895f5-kq92r 8080:8080

http://main.durgasri.com:32604/#/

kubectl get svc
kubectl describe service frontend

kubectl port-forward pod/frontend-54d95895f5-4fd9f 8080:8080
kubectl port-forward pod/frontend-54d95895f5-wqtp9 8080:8080
```
➜  frontend git:(main) ✗ kubectl get svc
NAME       TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
backend    ClusterIP      10.152.183.106   <none>        8080/TCP         175m
frontend   LoadBalancer   10.152.183.55    172.16.0.1    8080:32604/TCP   14m
mysql      ClusterIP      10.152.183.100   <none>        3306/TCP         12h
➜  frontend git:(main) ✗ kubectl describe service frontend
Name:                     frontend
Namespace:                expense
Labels:                   <none>
Annotations:              <none>
Selector:                 component=frontend,project=expense,tier=web
Type:                     LoadBalancer
IP Family Policy:         SingleStack
IP Families:              IPv4
IP:                       10.152.183.55
IPs:                      10.152.183.55
LoadBalancer Ingress:     172.16.0.1 (VIP)
Port:                     <unset>  8080/TCP
TargetPort:               8080/TCP
NodePort:                 <unset>  32604/TCP                ### node port
Endpoints:                10.1.76.37:8080,10.1.76.20:8080
Session Affinity:         None
External Traffic Policy:  Cluster
Internal Traffic Policy:  Cluster
Events:
  Type    Reason        Age                 From             Message
  ----    ------        ----                ----             -------
  Normal  nodeAssigned  4m6s (x5 over 14m)  metallb-speaker  announcing from node "main" with protocol "layer2"
➜  frontend git:(main) ✗
```
```
➜  frontend git:(main) ✗ kubectl port-forward pod/frontend-54d95895f5-kq92r 8080:8080
Forwarding from 127.0.0.1:8080 -> 8080
Forwarding from [::1]:8080 -> 8080

```

chandrahari296/mysql:v1.0
chandrahari296/backend:v1.0
chandrahari296/frontend:v2.0