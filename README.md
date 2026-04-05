Smart Campus Monitoring using MQTT and Node-RED
Description
This project implements a publish-subscribe system using MQTT and Node-RED. It simulates a smart campus environment with sensors publishing temperature, air quality, and system status data.

Features
Multiple publishers (temperature, air quality, status)

Wildcard subscriber (campus/#)

Real-time dashboard visualization

QoS demonstration

Retained message support

Technologies Used
Node-RED

Mosquitto MQTT Broker

Node-RED Dashboard

How It Works
Simulation: Inject nodes are used to simulate physical sensors.

Routing: The MQTT broker handles routing the published messages.

Subscription: A central subscriber listens for all campus data using a wildcard topic.

Visualization: The Node-RED Dashboard displays the live data streams.

Technical Details
Topics Used
campus/classroom/temperature

campus/lab/airquality

campus/status

Quality of Service (QoS) Levels
QoS 0: Temperature

QoS 1: Air Quality

QoS 2: Status

Retained Messages
The campus/status topic utilizes retained messages to ensure that any new subscribers immediately receive the last known system state upon connection.
