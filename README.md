# Smart Campus Monitoring System using MQTT and Node-RED
## Demo Video
[Watch the demo video](https://drive.google.com/file/d/1SNplAIE0ZmRFA6LldQxY9suRqpyOWr7U/view?usp=drive_link)
## Demonstration
This project demonstrates a working MQTT-based publish–subscribe system with real-time dashboard visualization.

## Overview
This project implements a publish–subscribe system using the MQTT protocol and Node-RED. It simulates a smart campus environment where multiple sensors publish real-time data, and a subscriber processes and visualizes this data through a dashboard.

## Objectives
- Implement a publish–subscribe architecture using MQTT
- Use multiple publishers and a wildcard subscriber
- Visualize real-time data using a dashboard
- Demonstrate QoS levels and retained messages

## System Architecture

### Publishers
The system includes three publishers:
- Temperature sensor (classroom)
- Air quality sensor (lab)
- System status publisher

Each publisher uses an Inject node and a Function node to generate and publish data.

### MQTT Broker
- Broker used: Mosquitto
- Runs locally on port 1883
- Responsible for routing messages between publishers and subscribers

### Subscriber
- A single MQTT IN node subscribes using the wildcard topic:

campus/#

- Switch nodes filter messages based on topics and route them to appropriate dashboard components.

### Topics Used

campus/classroom/temperature
campus/lab/airquality
campus/status


## Dashboard
The Node-RED dashboard displays:
- Temperature using a gauge
- Air quality using a line chart
- System status using a text field

The dashboard updates in real time as messages are received.

## QoS Implementation
Different Quality of Service (QoS) levels are used:
- QoS 0: Temperature (fast, no guarantee)
- QoS 1: Air quality (at least once delivery)
- QoS 2: Status (exactly once delivery)

## Retained Messages
The status topic uses retained messages so that new subscribers immediately receive the latest system state.

## Project Structure

smart-campus-mqtt/
│
├── flows.json
├── README.md
├── screenshots/
│ ├── flow.png
│ ├── dashboard.png
│
├── logs/
│ └── logs.txt
│
└── report/
└── report.md


## How to Run

### Prerequisites
- Node.js
- Node-RED
- Mosquitto MQTT Broker

### Steps
1. Start Mosquitto broker:

mosquitto

2. Start Node-RED:

node-red

3. Open Node-RED:

http://localhost:1880

4. Import `flows.json`
5. Click Deploy
6. Open dashboard:

http://localhost:1880/ui


## Sample Output

Example messages:

campus/classroom/temperature → 24.56
campus/lab/airquality → 110
campus/status → System Active


## Conclusion
This project demonstrates the MQTT publish–subscribe model with multiple publishers, a wildcard subscriber, and real-time data visualization. It also showcases QoS levels and retained messages for reliable communication.
