# 🫀 Real-Time ECG Acquisition, R-Peak Detection, Heart Rate & HRV in MATLAB

> Real-time ECG signal acquisition using ESP32 and AD8232, processed in MATLAB with R-peak detection, heart rate calculation, HRV analysis, and frequency domain analysis.

![Platform](https://img.shields.io/badge/Platform-MATLAB-orange)
![Hardware](https://img.shields.io/badge/Hardware-ESP32%20%2B%20AD8232-blue)
![Communication](https://img.shields.io/badge/Communication-UART%20Serial-green)
![Course](https://img.shields.io/badge/Course-Digital%20Signal%20Processing-purple)
![University](https://img.shields.io/badge/University-NUST-red)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📌 Overview

This project implements a **real-time ECG acquisition and analysis system** using an **ESP32 microcontroller** and **AD8232 ECG sensor**, with full signal processing performed in **MATLAB**. Developed as a semester project for the Digital Signal Processing course at NUST SEECS, the system captures cardiac biopotential signals, transmits them to MATLAB via UART serial communication, and performs a complete DSP pipeline including filtering, R-peak detection, heart rate calculation, HRV estimation, and frequency domain analysis.

---

## ✨ Features

- 📡 **Real-Time ECG Acquisition** — continuous signal capture using AD8232 + ESP32 at 250 Hz
- 📈 **Live Waveform Plotting** — real-time ECG visualization in MATLAB dashboard
- 🔺 **R-Peak Detection** — adaptive algorithm for accurate QRS complex identification
- ❤️ **Heart Rate Calculation** — BPM computed from RR intervals in real time
- 📊 **HRV Analysis** — Heart Rate Variability estimation from time-domain RR intervals
- 🔁 **Frequency Domain Analysis** — FFT/DTFT of ECG signal with labeled spectrum plot
- 🗄️ **MIT-BIH Dataset Integration** — verified ECG dataset used for frequency domain validation
- 🔇 **Multi-stage Filtering** — baseline wander removal, Butterworth bandpass filter, 50Hz notch filter

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **MATLAB** | Signal processing, filtering, visualization, HRV analysis |
| **ESP32** | Microcontroller for ECG data acquisition |
| **AD8232** | ECG analog front-end sensor module |
| **UART Serial (115200 baud)** | Real-time data transmission to MATLAB |
| **MIT-BIH Arrhythmia Database** | Verified ECG dataset for frequency domain analysis |

---

## ⚙️ System Architecture

```
Electrodes (Lead-II configuration)
            │
            ▼
      AD8232 ECG Sensor
   (Amplification + Filtering)
            │
            ▼
    ESP32 ADC (12-bit, 250Hz)
            │
     UART Serial (COM13)
       115200 baud rate
            │
            ▼
         MATLAB
   ┌────────────────────┐
   │ Rolling Buffer      │
   │ Baseline Removal    │
   │ Butterworth Filter  │
   │ 50Hz Notch Filter   │
   │ R-Peak Detection    │
   │ BPM Calculation     │
   │ HRV Estimation      │
   │ FFT Analysis        │
   │ Live Visualization  │
   └────────────────────┘
```

---

## 🧠 DSP Pipeline

1. **Baseline Wander Removal** — moving median filter eliminates low-frequency drift
2. **Bandpass Filtering** — Butterworth filter isolates ECG frequency band (0.5–40 Hz)
3. **Notch Filtering** — 50 Hz notch filter removes power line interference
4. **R-Peak Detection** — adaptive thresholding on filtered signal
5. **Heart Rate** — BPM calculated from consecutive RR intervals
6. **HRV** — standard deviation and time-domain metrics of RR intervals
7. **Frequency Domain** — FFT computed on MIT-BIH dataset signal, spectrum plotted and labeled

---

## 📋 ECG Dataset Used

| Parameter | Value |
|---|---|
| **Dataset** | MIT-BIH Arrhythmia Database |
| **Source** | PhysioNet (physionet.org/content/mitdb) |
| **Sampling Rate** | 360 Hz |
| **Signal Type** | Normal sinus rhythm |

---

## 👥 Team & Roles

| Name | Roll No | Role |
|---|---|---|
| Ahmed Shabbir Choudhary | 465206 | DSP Simulation & Algorithm — ECG cycle display, R-peak detection, HRV, FFT analysis |
| Shazaib Ahmed | 467695 | DSP Simulation & Algorithm — Hardware validation, ADC/DAC interfacing |
| Ahmad Shahzad | 455338 | Embedded Programming — Hardware interfacing, sensor connections |
| M. Hammad Ammar | 457400 | Embedded Programming — Circuit assembly, ESP32 integration |
| Armeen Ahmed | 461190 | Project Management — Planning, documentation, component procurement |

---

## 🏫 Course Information

- **Course:** Digital Signal Processing
- **Instructor:** Dr. Tauseef Ur Rehman
- **University:** NUST SEECS, Islamabad
- **Semester:** Spring 2026

---

## 🔮 Future Enhancements

- Add arrhythmia classification using machine learning
- Implement wireless Bluetooth transmission for portable ECG monitoring
- Develop a real-time MATLAB GUI dashboard with patient data logging
- Extend to multi-lead ECG acquisition for comprehensive cardiac analysis
