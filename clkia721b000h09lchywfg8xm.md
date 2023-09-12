---
title: "MQTT(Part - 2): How to create connection and how to write code in MQT?"
seoTitle: "How to create a connection and how to write code in MQT?"
seoDescription: "Learn how to establish MQTT connections and write code with a step-by-step guide, perfect for beginners diving into MQTT protocol programming."
datePublished: Tue Jul 25 2023 12:36:49 GMT+0000 (Coordinated Universal Time)
cuid: clkia721b000h09lchywfg8xm
slug: mqttpart-2-how-to-create-connection-and-how-to-write-code-in-mqt
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689418040478/23e62bcb-ed00-4305-bb8f-9bfe78fa1540.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689423521812/7da46ef2-d11b-4fb3-8e63-c9ac11bdcbb6.png
tags: iot, python3, automation, mqtt, python-beginner

---

### `File:`

* ### `MQTT_send_data.py`:
    

```basic
import json
import time
import paho.mqtt.client as mqtt

SUB_TOPIC = "/api/blaze"
PUB_TOPIC = "/api/minipc"


def on_connect(client, userdata, flags, rc):
    client.subscribe(SUB_TOPIC)


def on_message(client, userdata, message):
    print("[ message ]", message.payload.decode())


def on_publish(client, userdata, result):  # create function for callback
    print("[ publish ] Data is Published")


mqtt_client = mqtt.Client("send_data123", clean_session=True)
mqtt_client.on_connect = on_connect
mqtt_client.on_message = on_message
mqtt_client.connect(host='send.local', port=1883)
mqtt_client.loop_start()

while True:
    cmd = int(input("\n1) Turn ON Light\n2)Turn OFF Light\n3)Exit\nEnter your option :"))
    if cmd == 1:
        mqtt_client.publish(PUB_TOPIC, "light_on")
    elif cmd == 2:
        mqtt_client.publish(PUB_TOPIC, "light_off")
    else:
        break
mqtt_client.loop_stop()
```

### `Explain the MQTT_send_data.py:`

1. `SUB_TOPIC:`
    
    * `SUB_TOPIC` represents the topic string for subscribing to MQTT messages.
        
    * In this specific case, the value of `SUB_TOPIC` is `"/api/blaze"`. This topic represents the category or identifier under which you expect to receive messages.
        
2. `PUB_TOPIC:`
    
    * `PUB_TOPIC` represents the topic string for publishing MQTT messages.
        
    * In the provided code, the value of `PUB_TOPIC` is `"/api/minipc"`. This topic identifies the category or destination for your published messages.
        
3. `Parameters:`
    
    * `client`: The MQTT client instance that triggered the callback.
        
    * `userdata`: Any user-defined data that was passed to the MQTT client.
        
    * `flags`: A dictionary of flags indicating the status of the connection.
        
    * `rc`: The resulting code indicates the connection status.
        
    * `message`: An MQTTMessage object that contains information about the received message.
        
    * `result`: A result code indicating the status of the publish operation.
        
4. `Function Logic:`
    
    * The `on_connect` function subscribes to a specific MQTT topic using the `client.subscribe()` method.
        
    * The topic to which the client subscribes is specified by the `SUB_TOPIC` variable.
        
    * The `client.subscribe()` method establishes a subscription to the topic, allowing the client to receive messages published under that topic.
        
    * In the provided code, the `on_message` function simply prints the payload of the received message using `message.payload.decode()`. The `decode()` method is used to convert the payload from bytes to a string before printing.
        
    * You can customize the logic inside the `on_message` function to process the received message according to your application requirements.
        
    * In the provided code, the `on_publish` function simply prints a confirmation message indicating that the data has been published.
        
5. `mqtt_client = mqtt.Client("send_data123", clean_session=True)`:
    
    * The client ID `"send_data123"` is passed as an argument, which provides a unique identifier for the client.
        
6. `mqtt_client.on_connect = on_connect`:
    
    * This line assigns the `on_connect` callback function to the MQTT client's `on_connect` attribute.
        
7. `mqtt_client.on_message = on_message`:
    
    * This line assigns the `on_message` callback function to the MQTT client's `on_message` attribute.
        
8. `mqtt_client.connect(host='tenxertech.local', port=1883)`:
    
    * The `host` parameter specifies the hostname or IP address of the MQTT broker (in this case, `'send.local'`).
        
    * The `port` parameter specifies the port number on which the MQTT broker is listening (default MQTT port is `1883`).
        
9. `mqtt_client.loop_start()`:
    
    * The loop is responsible for maintaining the MQTT connection, handling callbacks, and processing incoming and outgoing messages.
        
10. `while True:`:
    
    * This creates an infinite loop, which continues until a the `break` statement is encountered.
        
11. `cmd = int(input("\n1) Turn ON Light\n2)Turn OFF Light\n3)Exit\nEnter your option :"))`:
    
    * The `input()` function captures the user's input as a string, and `int()` is used to convert it to an integer.
        
12. `if cmd == 1:`:
    
    * If the user enters `1`, indicating the option to turn on the light, the following block of code executes:
        
        * `mqtt_client.publish(PUB_TOPIC, "light_on")`: This publishes the message `"light_on"` to the `PUB_TOPIC` topic using the MQTT client's `publish()`method. The message is sent to the MQTT broker.
            
13. `elif cmd == 2:`:
    
    * If the user enters `2`, indicating the option to turn off the light, the following block of code executes:
        
        * `mqtt_client.publish(PUB_TOPIC, "light_off")`: This publishes the message `"light_off"` to the `PUB_TOPIC` topic using the MQTT client's `publish()` method.
            
14. `mqtt_client.loop_stop()`:
    
    * This line stops the MQTT client loop, ending the client's connection and cleaning up system resources.
        

* ### `MQTT_received_data.py:`
    

```basic
import paho.mqtt.client as mqtt
import queue

COMMANDS = queue.Queue()

PUB_TOPIC = "/api/blaze"
SUB_TOPIC = "/api/minipc"


def on_connect(client, userdata, flags, rc):
    print("[ info ] connected")


def on_message(client, userdata, message):
    global COMMANDS
    cmd = message.payload.decode()
    print("[ message ] ", cmd)
    COMMANDS.put(cmd)


def on_publish(client, userdata, result):  # create function for callback
    print("[ publish ] Data is Published")


def main():
    # def on_log(client,userdata, flags, rc):
    mqtt_client = mqtt.Client("received_data123", clean_session=True)
    # mqtt_client.on_log = on_log
    mqtt_client.on_connect = on_connect
    mqtt_client.on_message = on_message
    mqtt_client.connect(host='send.local', port=1883)
    mqtt_client.subscribe(SUB_TOPIC)
    mqtt_client.loop_start()
    while True:
        if COMMANDS.qsize():
            cmd = COMMANDS.get()
            print("CMD :", cmd)
            if cmd == "light_on":
                print("light is on")


if __name__ == "__main__":
    main()
```

### `Explain the MQTT_received_data.py:`

1. `COMMANDS = queue.Queue():`
    
    * The `Queue` class is a built-in class provided by the `queue` module.
        
    * This provides methods for adding elements to the queue (`put()`), removing elements from the queue (`get()`), checking if the queue is empty (`empty()`), and more.
        
    * The `COMMANDS` object can be used to search commands or data into the queue and process them later.
        
2. `global COMMANDS`:
    
    * The `global` keyword is used to indicate that the `COMMANDS` variable is a global variable.
        
3. `cmd = message.payload.decode()`:
    
    * This line decodes the payload of the received MQTT message using the `decode()` method. Then put those in the `cmd` variable.
        
4. `COMMANDS.put(cmd)`:
    
    * This line pushes the received command (`cmd`) into the `COMMANDS` queue using the `put()` method.
        
5. `mqtt_client.subscribe(SUB_TOPIC):`
    
    * the MQTT client subscribes to the specified topic (`SUB_TOPIC`) on the MQTT broker. This enables the client to receive messages published `on` that particular topic.
        
6. `if COMMANDS.qsize():`:
    
    * The `qsize()` method is used to check if the `COMMANDS` queue has any commands in it.
        
7. `cmd = COMMANDS.get()`:
    
    * The `get()` method is used to dequeue a command from the `COMMANDS` queue.
        

### `Output:`

* `The sending data image:` In here I giving the inputs.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689424663982/29eebf20-1c20-45bf-999c-62d96f5cb4ac.png align="center")

* `The receiving data image:` By giving inputs, it gives outputs.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689424928709/d5c3fc11-7a3a-4b1e-95ba-39e18606e51b.png align="center")

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">Both client name should be different.</div>
</div>