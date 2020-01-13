# install golang
`sudo apt update
sudo apt install golang`
# install JDK
`sudo apt install openjdk`

# deploy MQ
use tar to unzip
## ActiveMQ
START
`cd {where}/bin
sudo bash activemq start`
STOP
`sudo bash activemq stop`
## Kafka
`cd {where}
bin/zookeeper-server-start.sh config/zookeeper.properties
bin/kafka-server-start.sh config/server.properties`

# deploy edgex
enter where the tar is 
`tar -xzvf edgex-***`
then u will get a folder name goPath
add this folder to gopath
`sudo vi /etc/profile`
add a new line in the end of this file
`export GOPATH:{where ur goPath is}`
use install script for 0MQ to install zeromq, location is not required.

# install git
`sudo apt install git`

# install mongodb
`sudo apt install mongodb`

# clone project
git clone

