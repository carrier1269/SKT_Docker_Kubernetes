```html:ku.html
Kubenetes 설치 (minicube) 

curl -LO https://storage.googleapis.com/minikube/releases/v1.22.0/minikube-linux-amd64 
sudo install minikube-linux-amd64 /usr/local/bin/minikube 

CLI 도구의 설치 

curl -LO https://dl.k8s.io/release/v1.22.1/bin/linux/amd64/kubectl 

sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl 
```
```html:ku1.html
minikube start --driver=docker
# 쿠버네티스 실행하기, driver module은 도커로 설정
```
![image](https://user-images.githubusercontent.com/58325946/217416911-7507500e-1f6e-455d-9660-0ca3cc22b451.png)
```html:ku2.html


```
