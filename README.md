```html:docker.html
sudo apt-get update 

sudo apt-get upgrade 

sudo apt-get install apt-transport-https ca-certificates curl gnupg lsb-release 

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg 

echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null 

sudo apt-get update 

sudo apt-get install docker-ce docker-ce-cli containerd.io 

sudo docker run hello-world 

sudo usermod -a -G docker $USER 

sudo service docker restart 

docker pull ubuntu:18.04 

docker images 

docker ps 

docker ps -a 

docker run -it --name demo1 ubuntu:18.04 /bin/bash 

docker run -it -d --name demo2 ubuntu:18.04 

docker ps 

docker exec -it demo2 /bin/bash 

docker run --name demo3 -d busybox sh -c "while true; do $(echo date); sleep 1; done" 

docker logs demo3 

docker logs demo3 -f 

docker stop demo3 

docker stop demo2 

docker stop demo1 

docker rm demo3 

docker rm demo2 

docker rm demo1 

docker images 

# busybox, ubuntu 가 있는 것을 확인하실 수 있습니다. 

docker rmi ubuntu 
  
```
