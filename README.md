# Smart Cold-Chain Assurance for Vaccines using Predictive Excursion Modelling

**Team Number:** 15

**Team Members:**

| Name | Student ID |
|---|---|
| Kairav Vashi | 2520030582 |
| A. Yoshik | 2520030574 |
| P. Sai Harshith Reddy | 2520030375 |

**Course:** Cloud Infrastructure and Services (25CS2206E) — A.Y. 2026–2027
**Section:** 2

**Guide:** Dr. Y. Harika Devi, Assistant Professor, Department of Computer Science and Engineering

---

## Project Description

Vaccine effectiveness depends on maintaining appropriate temperature conditions throughout storage and transportation. Conventional data loggers often reveal temperature deviations only after delivery, leaving limited opportunity for timely corrective action.

This project proposes an IoT-based cold-chain monitoring system integrated with AWS cloud services to track environmental conditions and anticipate potential temperature excursions during last-mile vaccine distribution.

An ESP32 collects temperature and humidity readings using DS18B20 and DHT22 sensors, detects container openings through a reed switch, and records location using a NEO-6M GPS module. Sensor readings are securely transmitted to AWS IoT Core through MQTT using X.509 certificates. IoT Rules route the data to AWS Lambda for processing and predictive risk assessment based on temperature trends, door-opening events and location. Amazon DynamoDB stores monitoring records, while Amazon SNS delivers proactive alerts to responsible personnel. Amazon S3 supports historical data storage, Amazon Cognito provides authenticated access, Amazon EventBridge schedules periodic checks, and Amazon CloudWatch monitors system performance.

The proposed prototype will be evaluated using simulated rural transport routes to assess excursion prediction and alert timeliness. Expected outcomes include improved cold-chain visibility, earlier intervention and reduced risk of vaccine wastage.

## Hardware Components

| Component | Purpose |
|---|---|
| ESP32 | Main controller — reads sensors and publishes telemetry |
| DS18B20 | Temperature sensing |
| DHT22 | Temperature and humidity sensing |
| Reed switch | Container door open/close detection |
| NEO-6M GPS module | Location tracking during transport |

## AWS Services Used

| Service | Role |
|---|---|
| AWS IoT Core | Secure MQTT connectivity and device certificates (X.509) |
| AWS IoT Rules | Routing of sensor messages to downstream services |
| AWS Lambda | Validation, excursion prediction and alert logic |
| Amazon DynamoDB | Real-time storage of temperature readings and device state |
| Amazon SNS | SMS and e-mail excursion alerts |
| Amazon CloudWatch | Logs, metrics and alarms for system monitoring |
| Amazon API Gateway | REST API serving the dashboard |
| Amazon S3 | Dashboard hosting and raw data archive |
| Amazon Cognito | Authenticated access |
| Amazon EventBridge | Scheduled periodic checks |

## Repository Structure

```
├── .gitignore
├── README.md          # Project front page (team info & project description)
├── src/               # All active source code files
│   ├── assets/        # Images, media, icons
│   └── components/    # Core code modules
├── docs/              # Diagrams, wireframes, and project reports (Abstract, Presentation)
└── tests/             # Any test scripts or QA files
```

## Status

Proposal stage — Abstract and Presentation are in `docs/`. Prototype implementation and evaluation on simulated rural transport routes are planned next.
