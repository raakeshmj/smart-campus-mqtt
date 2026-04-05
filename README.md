# Smart Campus Monitoring using MQTT & Node-RED

## Description
This project implements a publish-subscribe system using MQTT and Node-RED. It simulates a smart campus environment with sensors publishing temperature, air quality, and system status data.

## Features
* **Multiple publishers:** Handles temperature, air quality, and status data streams.
* **Wildcard subscriber:** Utilizes `campus/#` to capture all related topics efficiently.
* **Real-time dashboard visualization:** Displays live metrics through an intuitive interface.
* **QoS demonstration:** Implements varying Quality of Service levels based on data criticality.
* **Retained message support:** Ensures persistence of critical system states.

## Technologies Used
* **Node-RED**
* **Mosquitto MQTT Broker**
* **Node-RED Dashboard**

## How It Works
1. **Simulation:** Inject nodes simulate physical sensors.
2. **Routing:** The MQTT broker handles routing the published messages.
3. **Subscription:** A central subscriber listens for all campus data using a wildcard topic.
4. **Visualization:** The Node-RED Dashboard displays the live data streams.

## Technical Configuration

### Topics Used
* `campus/classroom/temperature`
* `campus/lab/airquality`
* `campus/status`

### Quality of Service (QoS) Levels
* **QoS 0** (At most once) -> Temperature
* **QoS 1** (At least once) -> Air Quality
* **QoS 2** (Exactly once) -> Status

### Retained Messages
The `campus/status` topic utilizes retained messages to ensure that any new subscribers immediately receive the last known system state upon connection.
