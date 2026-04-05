# smart-campus-mqtt
📌 Smart Campus Monitoring using MQTT & Node-RED
🔹 Description

This project implements a publish-subscribe system using MQTT and Node-RED. It simulates a smart campus environment with sensors publishing temperature, air quality, and system status data.

🔹 Features
Multiple publishers (temperature, air quality, status)
Wildcard subscriber (campus/#)
Real-time dashboard visualization
QoS demonstration
Retained message support
🔹 Technologies Used
Node-RED
Mosquitto MQTT Broker
Node-RED Dashboard
🔹 Topics Used
campus/classroom/temperature
campus/lab/airquality
campus/status
🔹 How it Works
Inject nodes simulate sensors
MQTT broker routes messages
Subscriber listens using wildcard
Dashboard displays live data
🔹 QoS Levels
QoS 0 → Temperature
QoS 1 → Air Quality
QoS 2 → Status
🔹 Retained Messages

Status topic uses retained messages to ensure new subscribers receive the last system state.
