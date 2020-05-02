# install golang
```
sudo apt update
sudo apt install golang
```
# install JDK
```
sudo apt install openjdk-8-jdk
```

# deploy MQ
use tar to unzip, plz download from official website  
u just need to choose one of them. ActiveMq is default in project. U need to modify config if u choose other MQ.
## 1. ActiveMQ
START  
```
cd {where}/bin  
sudo bash activemq start
```  
STOP  
`sudo bash activemq stop`

visit <http://localhost:8161> to check status
## 2. Kafka
```
cd {where}  
bin/zookeeper-server-start.sh config/zookeeper.properties  
bin/kafka-server-start.sh config/server.properties
```  

# deploy edgex
THERE ARE TWO METHODS  
1. Native binaries

    download this tar.gz  
    <https://github.com/Eating-Bread-On-Sofa/ebos-doc/releases/tag/edgexFiles>

    enter where the tar.gz is and decompress   
    `tar -xzvf edgex-***`  

    then u will get a folder named goPath  
    add this folder to gopath environment variable  
    `sudo vi /etc/profile`  

    add a new line in the end of this file  
    `export GOPATH:{where ur goPath is}`  

    use install script for 0MQ to install zeromq, location is not required.  
    <https://github.com/Eating-Bread-On-Sofa/ebos-doc/blob/master/doc/install%20script%20for%200MQ>
    
    install mongodb  
    `sudo apt install mongodb`
---------------------
2. Docker  
u can use docker-compose to simplify this work, and plz see <https://github.com/edgexfoundry/edgex-go>

docker is needed and docker compose is also recommanded

# install git
`sudo apt install git`

# clone project
use git clone

# run edgex
## 1. use src
```
cd {where goPath is}
```
### run edgex-go
```
cd src/edgex-go
make run
```
### run device-modbus-go
```
cd src/device-modbus-go/bin
sudo bash edgex-launch.sh
```

## 2. use docker compose
```
cd {where docker compose.yml}
sudo docker-compose up -d
```
if u find error when you start docker, plz use `sudo docker-compose up` instead and find logs
# run micro service
## use source code  
make sure you are in the right branch. if not, git checkout  
install maven `sudo apt install maven`

START! cd to where directory is and `mvn sping-boot:run`

## use JAR
