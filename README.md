# COVID‑19 Realtime Dashboard

> A real-time IoT-powered COVID‑19 dashboard built using Node‑RED, MQTT, and ESP8266 (NodeMCU), designed to track global and Sri Lankan COVID‑19 statistics.

---

## Table of Contents

- [Overview](#overview)  
- [Features](#features)  
- [Setup & Quickstart](#setup--quickstart)  
- [Architecture & Components](#architecture--components)  
- [Customization](#customization)  
- [License](#license)  
- [Contact](#contact)

---

## Overview

This project provides a **real-time COVID‑19 dashboard** that leverages IoT principles to monitor pandemic trends, with a primary focus on Sri Lanka alongside global data. It functions through:

- Smart data aggregation from public APIs  
- IoT communication using **MQTT**  
- Interactive UI via **Node‑RED** dashboards  
- Client display powered by **ESP8266 (NodeMCU)**, serving as a localized server interface

This channelized setup enables live monitoring on both dashboards and physical IoT endpoints.

---

## Features

- **Daily and cumulative COVID data** for global and Sri Lankan stats (cases, recoveries, deaths)  
- **IoT integration** using:
  - **Node‑RED**: Data orchestration & dashboard creation  
  - **MQTT Broker**: Messaging middleware for real-time updates  
  - **ESP8266 (NodeMCU)**: Hosts a local access point with server webpage for mobile/IoT clients  

---

## Setup & Quickstart

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Anjanamb/COVID-19-Realtime-Dashbord.git
   cd COVID-19-Realtime-Dashbord
   ```

2. **Install & Launch Node‑RED**
   - Ensure Node.js and Node‑RED are installed.
   - Run:
     ```bash
     node-red
     ```
   - Import the project's `flows.json` flow into Node‑RED.

3. **Configure the MQTT Broker**
   - Use a local or cloud-based MQTT broker.
   - Confirm Node‑RED flows point to the correct broker endpoint.

4. **Flash the ESP8266**
   - Deploy the ESP8266 client code to your NodeMCU module.
   - The module should connect to your Wi-Fi and subscribe to MQTT topics.

5. **Access the Dashboard**
   - Open the Node‑RED dashboard in a browser via `http://localhost:1880/ui` (default port) or as configured.
   - Access ESP8266 dashboard via its generated hotspot or served IP.

---

## Architecture & Components

```
[ Public COVID APIs ]
         ↓
     Node‑RED (flows.json)
         ↓ (via MQTT)
   ┌────────────┐     ┌──────────────┐
   │  Node‑RED  │     │  ESP8266     │
   │ Dashboard  │     │ Local Server │
   └────────────┘     └──────────────┘
         ↓                   ↓
     Web Browser         Mobile Client
```

- **Node‑RED**:
  - Orchestrates data fetching, processing, and UI display.
- **MQTT Broker**:
  - Connects Node‑RED and ESP8266 via publish/subscribe topics.
- **ESP8266 (NodeMCU)**:
  - Acts as both an MQTT subscriber and a local web server for mobile access.

---

## Customization

- **Add New Data Sources**:
  - Modify Node‑RED flows to fetch additional APIs or data endpoints.
- **Extend ESP8266 UI**:
  - Upgrade the served webpage on the NodeMCU with richer analytics or new display components.
- **Deploy Remotely**:
  - Host MQTT or Node‑RED dashboards on Raspberry Pi or cloud VMs for broader access.

---

## License

This project is open‑source under the **MIT License**.

---

## Contact

- **Author**: Anjana Bandara (`Anjanamb`)  
- Built using IoT tools like Node‑RED, MQTT, and ESP8266.

---
