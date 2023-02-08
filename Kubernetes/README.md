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
sudo usermod -aG docker $USER && newgrp docker

minikube start --driver=docker
# 유저모드로 진입해서 minikube를 실행하면, docker images를 다운받는 것을 확인할 수 있다.
```
![image](https://user-images.githubusercontent.com/58325946/217417321-6d4c97a4-d387-4f0b-9ec3-e9cd1aef0841.png)
```html:ku3.html
minikube status
# minikube 상태 확인하기

kubectl get pod -n kube-system

minikube delete

minikube start --driver=docker

cd ..
vi pod.yaml

# vi file editor
apiVersion: v1 # kubernetes resource 의 API Version 
kind: Pod # kubernetes resource name 
metadata: # 메타데이터 : name, namespace, labels, annotations 등을 포함 
  name: counter 
spec: # 메인 파트 : resource 의 desired state 를 명시 
  containers: 
  - name: count # container 의 이름 
    image: busybox # container 의 image 
    args: [/bin/sh, -c, 'i=0; while true; do echo "$i: $(date)"; i=$((i+1)); sleep 1; done'] # 해당 image 의 entrypoint 의 args 로 입력하고 싶은 부분 
# vi file editor

kubectl apply -f  pod.yaml

kubectl get pod

kubectl get pod -n kube-system

kubectl get pod -a
```
![image](https://user-images.githubusercontent.com/58325946/217422983-c4863d32-d053-4feb-822e-f3a6dcd9a89f.png)
