## Overview
This project demonstrates how to log PLC process data into an SQL database for industrial automation applications.  
It simulates data collection from a PLC via OPC-UA and stores machine status, alarms, and production counts into Microsoft SQL Server.  
The goal is to provide a **reference project** for engineers interested in **IT/OT integration** and **Industry 4.0 solutions**.

---

## Features
- Connects to PLC/OPC-UA server
- Logs real-time data (tags, alarms, counters) into SQL database
- Stores data in structured tables for easy analysis
- Provides sample datasets (`/data`) for testing without hardware
- Includes SQL schema (`/db/schema.sql`) to set up tables quickly
- Python scripts with clear comments

---

## Repository Structure

plc-data-logger-sql/
│
├── data/ # Sample datasets (CSV, JSON)
├── db/ # Database schema and queries
│ └── schema.sql
├── scripts/ # Python logging scripts
│ └── logger.py
├── docs/ # Documentation and screenshots
│ └── architecture.png
└── README.md # Project description

## How It Works
1. **PLC / OPC-UA Server** generates real-time data.  
2. **Python Logger Script** reads tags from OPC-UA.  
3. **SQL Database** stores the data in structured tables.  
4. **Visualization Layer** (Power BI / Ignition / WinCC) can connect to SQL for dashboards.  
![Architecture](docs/architecture.png)

---

## Example Data
Sample dataset included (`/data/plc_logs.csv`):

| Timestamp           | MachineID | Status | AlarmCode | Counter |
|---------------------|-----------|--------|-----------|---------|
| 2025-09-01 08:00:00 | Press01   | RUN    | 0         | 1250    |
| 2025-09-01 08:05:00 | Press01   | STOP   | 101       | 1250    |
| 2025-09-01 08:10:00 | Press01   | RUN    | 0         | 1265    |

---

## Getting Started
### Prerequisites
- Python 3.9+
- `opcua` Python library (`pip install opcua`)
- SQL Server (or PostgreSQL/MySQL with small changes)
- Git

### Run the Logger
```bash
git clone https://github.com/username/plc-data-logger-sql.git
cd plc-data-logger-sql/scripts
python logger.py
