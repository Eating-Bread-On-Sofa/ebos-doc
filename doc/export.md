# 导出层配置
* POST TO http://localhost:48071/api/v1/registration
 ```json
 {
"name":"gateway inst",
"addressable":{
    "name":"mqtt", 
    "protocol":"tcp",
    "address":"172.17.0.1",
    "port":1883,
    "publisher":"Publisher1", 
    "user":"user",
    "password":"user",
    "topic":"topic_"
    },
"format":"JSON",
"enable":true,
"destination":"MQTT_TOPIC"
}
 ```