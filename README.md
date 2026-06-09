# ForgeTrack-Digital-Shopfloor-Tracker
A modular, web-based production execution and tool lifecycle monitoring framework designed to digitize legacy paper-based industrial forging shop floors
# ForgeTrack: Digital Production & Tool Monitoring System for Forging Shops

![ForgeTrack Dashboard Interface](Aditya’s Forging Shop Digital Tracker.png)

An advanced, data-driven manufacturing execution prototype designed to eliminate manual tracking overhead, minimize tool downtime, and bring real-time operational visibility to legacy forging shop floors. Developed and validated through in-plant observations at **Vanaz Engineers Ltd.**

---

## 📌 Project Overview & Industry 4.0 Context
Traditional forging environments frequently suffer from disconnected workflows, manual data entry bottlenecks, lost paperwork, and a lack of granular visibility into tooling lifecycles. 

**ForgeTrack** bridges this gap as a localized digital manufacturing execution solution. By aligning with **Industry 4.0 principles (Cyber-Physical Systems and Data-Driven Manufacturing)**, it converts erratic shop-floor activities into structured, actionable data pools.

### Key Transformations:
* **Manual System:** Fragmented logs, delayed end-of-day reports, untracked tool wear, high risk of recording errors.
* **ForgeTrack System:** Instantaneous task logging, real-time analytics, automated tool lifecycle alerting, and standardized data exports.

---

## ⚙️ Core Engineering Features

### 1. Intelligent Operator Data Capture
* **Automated Validation Logic:** Features auto-fill validation patterns to streamline operator ID logging and shift-wise attendance records.
* **Timestamp Verification:** Automatically logs precise submission times to maintain an unalterable operational audit trail.

### 2. Predictive Tool Lifecycle Management
* **Wear Tracking Metrics:** Tracks real-time machine tool operations and component allocations.
* **Automated Tool Life Alerts:** Flags imminent degradation or milestone breaches to prompt predictive maintenance windows, preventing catastrophic tool failure during high-volume forging runs.

### 3. Analytics & Manufacturing Intelligence
* **Dynamic Productivity Tracking:** Built-in charting engines map out daily output trends (`Tasks per Day`) visually.
* **Standardized Compliance Auditing:** Embeds native documentation guidelines for safety protocols and workstation procedures.
* **Enterprise Data Integration:** Converts multi-variable manufacturing histories into cleanly formatted, downloadable Excel reports via structural client-side compilation logic.

---

## 🛠️ Technology Stack & Software Architecture

* **Front-End UI/UX:** HTML5, CSS3 (Custom responsive grid layout tailored with high-contrast, icon-based operational cues for low-digital-literacy environments).
* **System & Execution Logic:** Vanilla JavaScript (ES6+) utilizing secure client-side Web Storage engines for reliable localized state maintenance.
* **Data Analytics Engines:** Chart.js (Dynamic relational trend rendering).
* **File Compilation Matrices:** SheetJS / XLSX.js (Structured tabular extraction for production reporting).

---

README.md with technical project architecture
## 📂 Repository Structure

```text
├── index.html                                    # Core application viewport & responsive interface
├── README.md                                     # Professional technical documentation
├── Aditya’s Forging Shop Digital Tracker.png     # Interface preview graphic
└── Documentation/                                # Academic project background & corporate research reports
