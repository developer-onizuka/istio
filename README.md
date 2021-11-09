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
