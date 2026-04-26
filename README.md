# Air_Quality_Analysis--Nairobi-City
Air quality analysis using OpenAQ data from Providence Academy, Nairobi. Covers data cleaning, time series plots, correlation heatmap, and WHO guideline assessment. Results show daily mean PM2.5 at 7.01 µg/m³, within safe limits, highlighting links between pollution patterns and local weather cycles.

# Air Quality Analysis – Providence Academy, Nairobi

##  Project Overview
This project analyzes air quality data from **OpenAQ**, a global open-source air quality platform.  
Nairobi has several monitoring stations, but I chose to focus on **Providence Academy** to keep the analysis scoped and manageable.  
The goal is to demonstrate practical data cleaning, visualization, and interpretation techniques using Python, while assessing air quality against international health standards.

---

##  Data Cleaning
The raw dataset contained multiple metadata fields.  
To streamline analysis, I kept only the essential columns:
- `parameter` (e.g., pm25, temperature, humidity)  
- `value` (measurement values)  
- `unit` (measurement units)  
- `datetimeLocal` (local timestamp)  
- `latitude`, `longitude` (location coordinates)  

I also converted `datetimeLocal` into a proper datetime format, enabling time series plotting and resampling.

---

##  Analyses Performed

### 1. Time Series Plots
I plotted **PM2.5**, **temperature**, and **relative humidity** across a 24-hour period.  
- **PM2.5**: Concentrations were low in the morning but spiked in the evening, peaking at 16.2 µg/m³ around 21:00.  
- **Temperature**: Followed a typical diurnal cycle, rising to ~27°C midday before declining at night.  
- **Relative Humidity**: Showed an inverse pattern to temperature, dropping to ~44% in the afternoon before rising again in the evening.  

**Impact:** These plots highlight how pollution events align with daily weather cycles and human activity patterns.

---

### 2. Correlation Heatmap
I computed correlations between all parameters (`pm1`, `pm25`, `temperature`, `relativehumidity`, `um003`) and visualized them in a heatmap.  
- **Strong Positive Correlations**: PM1, PM2.5, and particle count (um003) were almost perfectly correlated (>0.97).  
- **Strong Negative Correlation**: Temperature and humidity showed a clear inverse relationship (-0.92).  
- **Weak Correlations**: PM values had little direct correlation with temperature or humidity.  

**Impact:** This confirms that particulate matter metrics are consistent with each other, while meteorological conditions follow expected inverse patterns.

---

### 3. Air Quality Assessment
I calculated the **daily mean PM2.5 concentration** and compared it against the **WHO guideline of 15 µg/m³**.  
- **Result:** Daily mean PM2.5 = **7.01 µg/m³**  
-  Within WHO guideline for daily exposure.  

**Impact:** Despite short-term evening spikes, overall air quality at Providence Academy was within safe limits during the measured period.

---

##  Tools & Libraries
- **pandas** – data cleaning and manipulation  
- **matplotlib** – plotting time series  
- **seaborn** – correlation heatmap visualization  
- **numpy** – numerical operations  

---

##  Key Takeaways
- Air quality analysis requires both **pollution metrics** and **meteorological context**.  
- PM2.5 levels were safe overall, but evening spikes highlight the importance of continuous monitoring.  
- Correlation analysis confirms expected relationships: particulate matter metrics align closely, while temperature and humidity are inversely related.  

This project demonstrates how **open data + Python analysis** can provide actionable insights into environmental health.

---

## Data Source
Data provided by [OpenAQ](https://openaq.org/), an open-source air quality data platform.
