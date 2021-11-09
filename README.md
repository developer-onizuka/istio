# istio

```
$ curl -L https://istio.io/downloadIstio | sh -
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   101  100   101    0     0    150      0 --:--:-- --:--:-- --:--:--   149
100  4549  100  4549    0     0   5088      0 --:--:-- --:--:-- --:--:--  5088

Downloading istio-1.11.4 from https://github.com/istio/istio/releases/download/1.11.4/istio-1.11.4-linux-amd64.tar.gz ...

Istio 1.11.4 Download Complete!

Istio has been successfully downloaded into the istio-1.11.4 folder on your system.

Next Steps:
See https://istio.io/latest/docs/setup/install/ to add Istio to your Kubernetes cluster.

To configure the istioctl client tool for your workstation,
add the /home/hisayuki/Desktop/istio-1.11.4/bin directory to your environment path variable with:
	 export PATH="$PATH:/home/hisayuki/Desktop/istio-1.11.4/bin"

Begin the Istio pre-installation check by running:
	 istioctl x precheck 

Need more information? Visit https://istio.io/latest/docs/setup/install/ 

$ ls
istio-1.11.4

$ cd istio-1.11.4/
$ export PATH=$PATH:$HOME/Desktop/istio-1.11.4/bin
$ istioctl install
This will install the Istio 1.11.4 default profile with ["Istio core" "Istiod" "Ingress gateways"] components into the cluster. Proceed? (y/N) y
✔ Istio core installed                                                          
✔ Istiod installed                                                              
✔ Ingress gateways installed                                                    
✔ Installation complete                                                         
Thank you for installing Istio 1.11.  Please take a few minutes to tell us about your install/upgrade experience!  https://forms.gle/kWULBRjUv7hHci7T6
```
```
$ kubectl get ns --show-labels
$ kubectl get ns default --show-labels
$ kubectl label namespaces default istio-injection=enabled
$ kubectl get ns default --show-labels
NAME      STATUS   AGE   LABELS
default   Active   11d   istio-injection=enabled,kubernetes.io/metadata.name=default
```
```
$ kubectl get pods
NAME                                                              READY   STATUS    RESTARTS       AGE
employee-test-5c8b8b6778-cmqmn                                    2/2     Running   0              10m
employee-test-5c8b8b6778-s2tss                                    2/2     Running   0              10m
mongo-test-677764f949-8cnpn                                       2/2     Running   0              10m
nginx-test-7bd87548c9-9n6x5                                       2/2     Running   0              9m57s
nginx-test-7bd87548c9-mnmwx                                       2/2     Running   0              9m57s
```
```
$ cd ~/Desktop/istio-1.11.4/samples/addons

$ kubectl apply -f .

$ kubectl get pod -n istio-system
NAME                                   READY   STATUS    RESTARTS   AGE
grafana-68cc7d6d78-h5lzs               1/1     Running   0          96s
istio-ingressgateway-8dbb57f65-ck26g   1/1     Running   0          50m
istiod-7859559dd-fm48d                 1/1     Running   0          51m
jaeger-5d44bc5c5d-gccqg                1/1     Running   0          96s
kiali-fd9f88575-pwvz4                  1/1     Running   0          96s
prometheus-77b49cb997-z8hxv            2/2     Running   0          95s

$ kubectl get services -n istio-system
NAME                   TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)                                      AGE
grafana                ClusterIP      10.99.253.178    <none>        3000/TCP                                     86s
istio-ingressgateway   LoadBalancer   10.108.210.157   <pending>     15021:30468/TCP,80:31701/TCP,443:32689/TCP   50m
istiod                 ClusterIP      10.106.19.192    <none>        15010/TCP,15012/TCP,443/TCP,15014/TCP        51m
jaeger-collector       ClusterIP      10.99.26.141     <none>        14268/TCP,14250/TCP,9411/TCP                 85s
kiali                  ClusterIP      10.99.179.7      <none>        20001/TCP,9090/TCP                           85s
prometheus             ClusterIP      10.99.161.179    <none>        9090/TCP                                     84s
tracing                ClusterIP      10.108.74.27     <none>        80/TCP,16685/TCP                             85s
zipkin                 ClusterIP      10.101.155.214   <none>        9411/TCP                                     85s
```

```
$ kubectl port-forward svc/kiali -n istio-system 20001
```
