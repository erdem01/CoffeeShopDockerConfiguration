# CoffeeShopDockerConfiguration

## To Build Image
sudo docker build -t erdemc/coffeeshopproxy .

## List Images
docker images
docker image ls

## To Create Container
sudo docker run -d --name coffeeshopproxy erdemc/coffeeshopproxy<br/>
sudo docker run -d -v /home/erdems/DockerWorkspace/coffeeShop/mysql/datadir:/var/lib/mysql --name coffeeshopdb erdemc/coffeeshopdb

### Share log file with current
sudo docker run -d -v /home/erdems/DockerWorkspace/coffeeShop/springboot/logs:/usr/src/coffeeshop/logs --name coffeeshopservices erdemc/coffeeshopservices

## To Start Container
sudo docker start coffeeshopdb

## To Stop Container
sudo docker stop coffeeshopdb

### Force Stop Container
sudo docker kill coffeeshopdb

## List Runnning Containers
docker ps<br/>
docker ps -a

## Start bash command on running container
sudo docker exec -it coffeeshopdb bash

## Check nginx status
service nginx status
lsof -i :8081

## Create Docker network
sudo docker network create coffeeshopnetwork<br/>
sudo docker network create --subnet 172.20.0.0/16  coffeeshopnetwork<br/>

### List Created Networks
sudo docker network ls

### Run container on a docker network
sudo docker run -d --name coffeeshopproxy2 --net=coffeeshopnetwork erdemc/coffeeshopproxy

### Connect Container to a Network
sudo docker network connect --ip 172.21.0.3 coffeeshopnetwork coffeeshopdb

### Checkout Network Configuration of a Container
sudo docker network inspect coffeeshopnetwork

### Disconnect Container from a Network
sudo docker network disconnect coffeeshopnetwork coffeeshopdb

### Delete a Network
sudo docker network rm coffeeshopnetwork
