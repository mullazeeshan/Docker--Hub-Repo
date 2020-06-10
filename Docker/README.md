Inspiration from Krish Naik's Playlist of Docker [link](https://www.youtube.com/playlist?list=PLZoTAELRMXVNKtpy0U_Mx9N26w8n0hIbs)
![all in one](https://user-images.githubusercontent.com/29397302/84295391-25f54180-ab68-11ea-8109-da69d3964d24.png)


Buildinguilding a docker images we need to install docker 
Using flasgger for ui 

for ubuntu: #apt-get install docker.io

for windows: [link](https://download.docker.com/win/stable/Docker%20Desktop%20Installer.exe)
after installing build a docker images
clone this repo by using git.


go to app folder

## excute commands:

docker build -t diabetis:v1 .  #note v1 '.' is necessary

docker -d -p 5000:5000 --name diabetis diabetis:v1

see if you want to see output remove -d from dockerker build 


## docker commands:

docker images   # to see the images

docker ps       # to see the running contaiers

docker ps -a    # to see all containers

docker rmi <imagename or id>   # to remove the image
  
docker rm -f $(docker ps -a -q)   # to remove alll containers

docker rmi -f $(docker images -q) # to remove all images

docker exec -it <containerid or contiainer name> /bin/bash      # to login to container
  
  
# deploy the image to dockerhub:

first we need to create a account on dockerhub

after building is done .

tag our image to yours dockerhub username:

docker tag diabetis:v1 mullazeeshan/diabetis:v1

then login

docker login

give ur username and password

docker push mullazeeshan/diabetis:v1 

## Deployment in kubernates:

go to this link install lightweight kubernetes

add slave to it

## commands:

#on master

swapoff -a

selinux diable:   

setenforce 0
it asking not installed 
apt install selinux-utils


create a kubernates pod:

kubectl create -f diabetis.yaml

then see nodeport service

kubectl get svc

copy nodeport ex : 336645

http://localhost:nodeport


note:
===
if u are using loadbalancer in cloud then change nodeport to loadbalancer in diabetis.yaml


