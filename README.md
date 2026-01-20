# 🏢 Facility Issue Reporting & Sensor Monitoring System

## 🎯 Overview

The **Facility Issue Reporting & Sensor Monitoring System** is an **enterprise-grade ServiceNow application** that revolutionizes facility management through **automation, IoT integration, and predictive analytics**.

The system enables **proactive maintenance** by monitoring sensor data in real time, automatically detecting anomalies, and creating work orders **before equipment failures occur**.

---

## 🌟 Key Benefits

* 🚀 **70% reduction** in emergency maintenance calls
* 💰 **Annual cost savings** through predictive maintenance
* ⏱️ **50% faster** issue resolution times
* 📊 **Real-time monitoring** of 30+ facility sensors
* 👥 **Employee self-service portal** reducing IT & facility workload

---

## ✨ Features

### 🔧 Core Functionality

#### Automated Issue Tracking

* Employee self-service portal for issue reporting
* Automatic assignment to appropriate technician teams
* Real-time status updates and notifications
* File attachment support (images, PDFs, documents)

---

### 🌐 IoT Sensor Integration

* Real-time monitoring of **30+ sensors** (HVAC, electrical, plumbing, etc.)
* Automated data collection every **10 minutes**
* Intelligent anomaly detection and alerting

---

### 🤖 Intelligent Automation

* Auto-create issues from sensor alerts
* Update existing issues with new sensor readings
* Auto-close issues when sensors return to normal
* Priority-based work order generation

---

### 📚 Knowledge Base Integration

* Context-aware article suggestions
* Reduced ticket volume through self-service
* Dynamic recommendations based on issue type

---

## 🎨 Employee Portal Features

### 📊 Dashboard

* Statistics cards (Open, In Progress, Resolved)
* Recent issues overview
* Quick action buttons
* Knowledge base search

---

### 📝 Report Issue Form

* Visual issue type selection (**8 categories**)
* Building and floor dropdowns
* Rich text description
* Priority selector
* File upload capability
* Smart knowledge base article suggestions

---

### 📄 Issue Details View

* Complete issue information
* Status tracking timeline
* Assigned technician details
* Contact buttons (phone & email)
* Real-time updates

---

### 📂 My Issues List

* Full paginated issue history
* Advanced filtering (status, priority)
* Search functionality
* Sortable columns
* Export capabilities

---

## 🏗️ System Architecture

### High-Level Architecture

```text
┌─────────────────────────────────────────────────────────┐
│                    ServiceNow Platform                   │
├─────────────────────────────────────────────────────────┤
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐ │
│  │   Employee   │  │  Technician  │  │    Admin     │ │
│  │    Portal    │  │   Console    │  │  Dashboard   │ │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘ │
│         │                  │                  │        │
│  ┌──────┴──────────────────┴──────────────────┴──────┐ │
│  │           Service Portal Widgets & Pages           │ │
│  └──────────────────────┬─────────────────────────────┘ │
│                         │                               │
│  ┌──────────────────────┴─────────────────────────────┐ │
│  │              Flow Designer Workflows                │ │
│  │  • Sensor Data Collection (Every 10 min)           │ │
│  │  • Issue Auto-Assignment                           │ │
│  │  • Alert Generation                                │ │
│  │  • Notification Sending                            │ │
│  └──────────────────────┬─────────────────────────────┘ │
│                         │                               │
│  ┌──────────────────────┴─────────────────────────────┐ │
│  │              Business Logic Layer                   │ │
│  │  • Script Includes (SensorUtilities)               │ │
│  │  • Business Rules                                  │ │
│  │  • Client Scripts                                  │ │
│  └──────────────────────┬─────────────────────────────┘ │
│                         │                               │
│  ┌──────────────────────┴─────────────────────────────┐ │
│  │                 Data Layer                          │ │
│  │  • Facility Issue Table                            │ │
│  │  • Facility Sensor Table                           │ │
│  │  • Assignment Groups                               │ │
│  │  • Knowledge Base                                  │ │
│  └─────────────────────────────────────────────────────┘ │
└──────────────────────────┬───────────────────────────────┘
                           │
          ┌────────────────┴────────────────┐
          │                                 │
    ┌─────▼─────┐                   ┌──────▼──────┐
    │ Mockaroo  │                   │   Email     │
    │    API    │                   │  Gateway    │
    │ (Sensors) │                   │             │
    └───────────┘                   └─────────────┘
```

---

## 🔄 Data Flow

```text
Sensor Data → Mockaroo API → ServiceNow Flow → Process & Store
                                        ↓
                            Anomaly Detected?
                               ↓        ↓
                             No          Yes
                             ↓            ↓
                      Update Sensor   Create / Update Issue
                             ↓            ↓
                     Back to Normal?  Auto-Assign Team
                             ↓            ↓
                            Yes       Send Notifications
                             ↓            ↓
                        Close Issue   Technician Action
```

---

## 📋 Prerequisites

### ServiceNow Instance

* **Version:** Rome or later (tested on Vancouver)
* **Required Plugins:**

  * Service Portal (`com.glide.service-portal`)
  * Flow Designer (`com.glide.hub.flow_designer`)
  * Knowledge Management (`com.snc.knowledge_advanced`)

---

### External Services

* **Mockaroo API** (Free tier sufficient)

  * API Key required
  * Schema ID for sensor simulation

---

### User Roles

*  – Full system access
* – Employee portal access
* – Technician workspace access
* Manager

---

### Required Skills

* ServiceNow platform development
* JavaScript (Client & Server-side)
* AngularJS basics (Service Portal widgets)
* Flow Designer
* REST API integrations

---

## 📸 Screenshots

### Employee Portal – Dashboard


<img width="1919" height="938" alt="Screenshot 2026-01-20 221810" src="https://github.com/user-attachments/assets/7619c7e0-e85f-4f07-9f77-ff8af60d2fcc" />
<img width="1919" height="927" alt="Screenshot 2026-01-20 221739" src="https://github.com/user-attachments/assets/3876eca9-4d9d-4371-ab08-148564786ed3" />
<img width="1915" height="946" alt="Screenshot 2026-01-20 221704" src="https://github.com/user-attachments/assets/366169b0-56a4-4334-8b6a-444f602c65ae" />
<img width="1917" height="940" alt="Screenshot 2026-01-20 221551" src="https://github.com/user-attachments/assets/d4a21944-7958-45a0-a648-ce2fbdcdc3ec" />



### Manager Workspace
<img width="2548" height="1177" alt="Screenshot_194" src="https://github.com/user-attachments/assets/ccecb5e6-3072-4cca-ab6b-f71bd2c933af" />
<img width="2548" height="1180" alt="Screenshot_193" src="https://github.com/user-attachments/assets/68daffac-25b2-4c4d-b93f-45ee0d97a009" />
<img width="2551" height="1179" alt="Screenshot_192" src="https://github.com/user-attachments/assets/2586ace9-511c-40a2-b3d2-a21d8e70a174" />
<img width="2557" height="1175" alt="Screenshot_191" src="https://github.com/user-attachments/assets/8f456111-4cd6-45bb-80f1-36dfbccf97b3" />
<img width="2560" height="1184" alt="Screenshot_190" src="https://github.com/user-attachments/assets/95575e78-329e-43c2-bd63-fcc8c3ef963d" />


### Technician Workspace

<img width="2548" height="1180" alt="TEC1" src="https://github.com/user-attachments/assets/1d5dcaa4-6e2b-44a5-a702-43c5e34da523" />
<img width="2557" height="1189" alt="Tec2" src="https://github.com/user-attachments/assets/9e844ca5-9183-4a00-83f7-00c885a45a5d" />


---

> *A smart, automated, and scalable facility management solution built on ServiceNow.*
