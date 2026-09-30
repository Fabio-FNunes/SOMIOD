# SOMIOD - Systems Integration Project (25/26)

This repository contains the files for the Systems Integration Project (Academic Year 2025/2026). The project implements **SOMIOD**, a Service-Oriented Middleware for IoT Interoperability.

## Context & How It Works
SOMIOD serves as a middleware (bridge) that facilitates the exchange of data and alerts between different closed IoT systems, ensuring interoperability regardless of the manufacturers. It organizes data in a strict hierarchical structure: **Application -> Container -> Content-Instance / Subscription**.

The system is designed to persist data and notify interested parties in real-time. When a new `Content-Instance` is created, the middleware triggers a dispatch logic that checks for active subscriptions and sends out asynchronous notifications.

**Case Study: Smart Prison Management System**
To validate the middleware, a prison management scenario was implemented:
- **Monitor (App A):** Listens actively to MQTT topics and visually reflects the state of the prison cells (e.g., Green for Open, Red for Closed). It also features a Lockdown mode for emergencies.
- **Controller (App B):** A remote control application used by guards to send HTTP requests to the middleware, commanding the cells to open or close, either individually or en masse.

## Technologies Used
- **Core Framework:** C# with ASP.NET Web API (RESTful API)
- **Database:** SQL Server (accessed via ADO.NET / SqlClient)
- **Messaging & Notifications:** MQTT Protocol (Mosquitto broker, M2Mqtt library) and HTTP/HTTPS (Webhooks)
- **Data Formats & Validation:** XML (validated via XSD Schema) and JSON
- **API Documentation:** Swagger (via Swashbuckle)

## Project Structure
- `Data/`: Contains database scripts and related data files.
- `Other/`: Miscellaneous project resources.
- `Project/`: Main source code, including the SOMIOD ASP.NET API, the Monitor, and the Controller applications.
- `Report/`: Contains the detailed project report (`IS_Project_Report_2025-2026.pdf`).

## Authors
- Bernardo Inácio (2222402 / 2023111672)
- Fábio Nunes (2231014 / 2023124850)
- Francisco Crespo (2221482 / 2022132013)
- Martim Ribeiro (2231018 / 2024113378)
