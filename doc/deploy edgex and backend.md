# install JDK
```
sudo apt update
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

# run edgex  (choose one of them)
## 1. use binary 
(DO NOTIFY ME if u got problems)

use install script for 0MQ to install zeromq, location is not required.   
<https://github.com/Eating-Bread-On-Sofa/ebos-doc/blob/master/doc/install%20script%20for%200MQ>
    
install mongodb  
`sudo apt install mongodb`
    
download edgex-binary.tar.gz and decompress    
~~https://github.com/Eating-Bread-On-Sofa/ebos-doc/releases/tag/edgexFiles~~

<https://github.com/Eating-Bread-On-Sofa/ebos-doc/releases/download/v1.0/edgex.tar.gz>

### run edgex-go
```
cd edgex-go/bin
bash edgex-launch.sh
```
### run device-modbus-go
```
cd device-modbus-go/bin
sudo bash edgex-launch.sh
```
### run device-random
```
cd device-random/cmd
sudo ./device-random
```
----------------------------
## ~~2. use src~~
(if u have problems running with bin)

use install script for 0MQ to install zeromq, location is not required.     
<https://github.com/Eating-Bread-On-Sofa/ebos-doc/blob/master/doc/install%20script%20for%200MQ>
    
install mongodb  
```sudo apt install mongodb```

install golang    
```sudo apt install golang```
    
download edgex-modbus-int8-version.tar.gz     
<https://github.com/Eating-Bread-On-Sofa/ebos-doc/releases/tag/edgexFiles> 

    
enter where the tar.gz is and decompress   
```tar -xzvf edgex-***```    

then u will get a folder named goPath, add this folder to gopath environment variable  
`sudo vi /etc/profile`             

add a new line in the end of this file  
`export GOPATH:{where ur goPath is}`  
### run edgex-go
```
cd {where goPath is}/src/edegx-go
make run
```
### run device-modbus-go
```
cd {where goPath is}/src/device-modbus-go/bin
sudo bash edgex-launch.sh
```
---------------------------------
## 3. use docker compose
u can use docker-compose to simplify this work, and plz see <https://github.com/edgexfoundry/edgex-go>

docker is needed and docker compose is also recommanded, you can also get docker-compose.yml here    
<https://github.com/Eating-Bread-On-Sofa/ebos-doc/tree/master/dockerComposeFiles>
```
cd {where docker compose.yml}
sudo docker-compose up -d
```
if u find error when you start docker, plz use `sudo docker-compose up` instead and find logs

# install git
`sudo apt install git`

# clone project or download
use git clone

or

download jar from release in each repo
# run micro service
## use source code  
make sure you are in the right branch. if not, git checkout  
install maven `sudo apt install maven`

START! cd to where directory is and `mvn sping-boot:run`

## use JAR
java -jar xxx.jar  
see releases in each repo
