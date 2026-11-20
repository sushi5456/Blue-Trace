<div align="center">

# 🌊 BluTrace
### AI-Powered Maritime Oil Spill Detection & Vessel Trajectory Investigation

[![Smart India Hackathon](https://img.shields.io/badge/Smart%20India%20Hackathon-2026-0052CC?style=for-the-badge&logo=hackthebox&logoColor=white)](https://www.sih.gov.in/)
[![Live Deployment](https://img.shields.io/badge/Live%20Demo-Render-46E3B7?style=for-the-badge&logo=render&logoColor=black)](https://blutrace-frontend.onrender.com/)
[![React](https://img.shields.io/badge/Frontend-React%20%7C%20Leaflet-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](#tech-stack)
[![License](https://img.shields.io/badge/Status-SIH%202026%20Prototype-FF6B00?style=for-the-badge)](#)

**An interactive geospatial intelligence dashboard for detecting marine oil slicks via Sentinel-1 SAR imagery and identifying responsible vessels through AIS trajectory correlation.**

[🌐 View Live Application](https://blutrace-frontend.onrender.com/) · [🐛 Report Bug](https://github.com/sushi5456/blutrace-frontend/issues) · [✨ Request Feature](https://github.com/sushi5456/blutrace-frontend/issues)

</div>

---

## 📌 Table of Contents
- [Problem Statement & Vision](#-problem-statement--vision)
- [Core Capabilities](#-core-capabilities)
- [System Architecture](#-system-architecture)
- [Tech Stack](#-tech-stack)
- [Repository Structure](#-repository-structure)
- [Local Setup & Installation](#-local-setup--installation)
- [Environment Configuration](#-environment-configuration)
- [Author & Maintainer](#-author--maintainer)

---

## 🎯 Problem Statement & Vision

Illegal bilge dumping and accidental offshore oil spills cause severe ecological and economic damage, yet manual satellite inspection delays maritime enforcement by days. 

**BluTrace** bridges this gap for **Smart India Hackathon (SIH) 2026** by combining **Synthetic Aperture Radar (SAR)** dark-spot detection with **Automated Identification System (AIS)** vessel tracking. This repository houses the **command-and-control frontend**, enabling coastal authorities to inspect oil slick polygons, replay vessel paths, and isolate high-probability suspect ships in minutes.

---

## 🚀 Core Capabilities

| Feature | Description |
| :--- | :--- |
| **🗺️ Interactive Geospatial Map** | High-performance maritime map built with **Leaflet** supporting multi-layer GeoJSON overlays, coastal boundaries, and zoom-level clustering. |
| **🛰️ SAR Oil Slick Visualization** | Renders AI-segmented oil spill polygons derived from **Sentinel-1 SAR** imagery alongside confidence scores and estimated slick area ($\text{km}^2$). |
| **🚢 AIS Vessel Trajectory Tracking** | Plots historical and live ship routes, speed, heading, and MMSI metadata to cross-reference vessels passing near spill coordinates. |
| **⚖️ Suspect Scoring Engine UI** | Ranks candidate vessels using spatial-temporal proximity and drift-back modeling to highlight the most probable source. |
| **📊 Incident Triage & Filtering** | Filter marine alerts by detection date, severity level, confidence threshold, and Exclusive Economic Zone (EEZ) sector. |

---

## 🏗️ System Architecture

```text
┌─────────────────────────┐      ┌──────────────────────────┐      ┌──────────────────────────┐
│  Sentinel-1 SAR & AIS   │ ───▶ │   BluTrace Backend API   │ ───▶ │   BluTrace Frontend UI   │
│  (GEE / PostGIS / ML)   │      │   (FastAPI + GeoPandas)  │      │   (React + Leaflet)      │
└─────────────────────────┘      └──────────────────────────┘      └──────────────────────────┘
   • Dark-spot segmentation         • Drift & proximity scoring       • Interactive map layers
   • Vessel MMSI telemetry          • GeoJSON serialization           • Suspect ranking & alerts
