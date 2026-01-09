🌎 Language: English | [Español](README.es.md)

# Spatial Crime Analysis in Mexico City

Geospatial analysis of crime in Mexico City using **network-based KDE** and **Getis-Ord Gi***.
This project generates **hotspot** and **coldspot** maps of crime from robbery events, following a **network-constrained spatial analysis** methodology.

---

## 🚨 Interactive Dashboard

> 📊 **Live interactive dashboard:**
> 👉 [🔗 CLICK HERE TO OPEN THE DASHBOARD](https://hectoralfa.github.io/Spatial-Crime-Analysis-CDMX/)

Or use this button:

[![Open interactive dashboard](https://img.shields.io/badge/Open%20dashboard-Interactive-blue?style=for-the-badge\&logo=Tableau)](https://hectoralfa.github.io/Spatial-Crime-Analysis-CDMX/)

---

## 🧩 Overview

This project analyzes the **spatial distribution of robbery crimes in Mexico City** using the **road network** as the primary spatial support. Through the use of:

* Road network analysis
* Lixel-based segmentation
* Graph representations
* **Network-based Kernel Density Estimation (KDE)**
* **Getis-Ord Gi*** statistic for hotspot detection

an **interactive dashboard** is built to explore high-risk areas for the most common robbery categories:
**public transportation robbery, street robbery, and business robbery** across Mexico City’s road network.

The main goal is to provide a useful tool for:

* **Public policy design and evaluation**
* **Security analytics, risk assessment, and urban planning**

---

## 🎯 Project Objective

To develop a **geospatial digital tool** that:

* Collects, processes, and analyzes **road network data and robbery events**
* Estimates the **concentration of criminal events along the network**, not just in continuous space
* Identifies **high-risk street segments** using statistical methods (Getis-Ord Gi*)
* Enables **clear and accessible visualization** through an **interactive dashboard**

> 🔗 Quick access: [Open interactive dashboard](https://hectoralfa.github.io/Spatial-Crime-Analysis-CDMX/)

---

## 🧠 Context and Motivation

The study of crime and violence requires an **integrated perspective** that combines:

* **Social and economic** factors
* Characteristics of the **urban environment**
* The structure and connectivity of the **road network**

Instead of analyzing only point patterns, this project focuses on **where daily life actually happens: streets and roads**. This allows for:

* More accurate **risk exposure estimation**
* Detection of **crime corridors**
* Evidence-based **urban safety and planning decisions**

---

## 🗺️ Road Network Analysis

The core of the project is the **road network of Mexico City**, built using:

* Data from **INEGI** (Mexico’s national statistics agency)

The network is preprocessed to:

* Fix disconnected segments
* Homogenize topology
* Prepare the data for lixel-based and graph-based analysis

---

## 📏 Lixels: Network Segmentation

Once cleaned, the network is divided into small, uniform segments called **lixels** (line + pixel).

### Why is this useful?

* Enables **fine-grained and homogeneous** analysis
* Facilitates computing **crime densities per segment**
* Improves localization of **where exactly crimes concentrate**

Each lixel becomes an individual analytical unit for risk estimation.

---

## 🔗 Graph Representation

The road network is also represented as a **graph**:

* **Nodes** → intersections
* **Edges** → street segments

This representation allows:

* Modeling **urban connectivity**
* Understanding how phenomena **propagate through the network**
* Integrating graph-based metrics (distances, accessibility, shortest paths, etc.)

---

## 📈 Network-based Kernel Density Estimation (KDE)

To analyze whether crimes concentrate in specific areas, this project uses **Kernel Density Estimation (KDE)**, but instead of applying it to continuous space, it is applied:

> ✅ **Directly on the road network**, using lixels as the spatial support.

### What does KDE do here?

* Each crime event generates a localized influence over the network
* Overlapping influences increase the estimated density
* The result is a **street-segment-level crime intensity map**

The method considers:

* **Bandwidth**: controls the size of the influence area
* **Kernel type**: Epanechnikov kernel is used because it:

  * Minimizes the **Mean Integrated Squared Error (MISE)**
  * Has **compact support**, reducing computational cost

---

## 🔥 Hotspot Detection: Getis-Ord Gi*

While KDE shows where high concentrations exist, it does not indicate whether they are **statistically significant**.

To address this, the **Getis-Ord Gi*** statistic is applied to the lixels to:

* Distinguish visually dense areas from
* Those that are **statistically significant compared to their neighbors**

The results are visualized as:

* 🔴 **Hot spots**: significantly high concentrations
* 🔵 **Cold spots**: significantly low concentrations

These outputs feed directly into the interactive dashboard.

---

## 🧪 Data Sources

Crime database:

* Investigation records from the **Mexico City Attorney General’s Office**
* Includes **three robbery categories**: street robbery, public transport robbery, and business robbery
* Spatial coverage: **Mexico City**
* Time span: **January–December 2023**
---

## 🧮 Tools and Technologies

Main tools used:

* 📦 **R**

  * **`spNetwork`** package for network-based KDE
* Spatial and statistical analysis libraries
* 📊 **d3.js** for interactive visualizations
* 🌐 **HTML/CSS/JavaScript** for the dashboard interface

---

## 📂 Repository Structure

```text
.
├── estilos/
│   ├── general.css
│   └── mapa.css
├── imagenes/
├── scripts/
│   ├── capa.js
│   ├── card-capas.js
│   ├── eventos_selector.js
│   ├── footer.js
│   ├── geocoder.js
│   ├── header.js
│   ├── main.js
│   ├── mapa_config.js
│   └── restablecer.js
├── scripts_r/
│   ├── crime_analysis.R
│   └── funciones.R
├── docs/
│   └── metodologia.md
├── index.html
└── README.md
```

---

## 🎓 Academic Relevance

This project demonstrates:

* Network-constrained spatial crime modeling
* Integration of KDE with spatial autocorrelation statistics
* Urban-scale risk modeling
* Reproducible and modular spatial analysis

Potential extensions:

* Spatio-temporal modeling
* Cross-city generalization
* Comparative kernel analysis
* Integration with socio-economic indicators

---

## 💼 Industry Relevance

This project showcases:

* End-to-end geospatial system design
* Risk mapping for urban safety
* Interactive data products
* Scalable spatial analytics

It can be used as a base for:

* Crime prevention systems
* Urban risk dashboards
* Public safety monitoring
* Smart city analytics

---

## 👤 Author

**Héctor Miguel Olivares García**
Actuary | Data Scientist | Geospatial & NLP Analytics

