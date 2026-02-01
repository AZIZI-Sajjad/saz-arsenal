# saz-kubernetes

#plateform/Windows-Linux-MAC
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/kubernetes

## kubernetes - Installation on Debian/Ubuntu 
```
sudo su
grep -E --color 'vmx|svm' /proc/cpuinfo
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube
mkdir -p /usr/local/bin/
install minikube /usr/local/bin/
minikube profile list
minikube status
minikube start --driver=<driver_name>
```

