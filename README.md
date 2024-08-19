# Sound-System-Device

# 🎯 Angle of Arrival (AoA) Project

This project focuses on designing a low-cost, low-power device capable of solving the Angle of Arrival (AoA) problem using a resource-constrained microcontroller. The results of this project are not just theoretical—our device was successfully implemented to accurately determine the direction of a sound source in real-time.

![Project Demo](https://media.giphy.com/media/xUPGcJhEOMnXO5Xg8k/giphy.gif)

## 📑 Table of Contents
- [🌟 Project Overview](#-project-overview)
- [🛠️ Hardware Setup](#️-hardware-setup)
- [🎛️ Software Capabilities](#-software-capabilities)
- [🚀 Results & Achievements](#-results--achievements)
- [🔧 How to Use](#-how-to-use)
- [🤖 Future Work](#-future-work)
- [📝 License](#-license)

## 🌟 Project Overview

In this project, we utilized three microphones arranged in a triangular configuration to track the angle of a sound source in a 2D plane. The microphones were interfaced with an ARM M4F core (TM4C123GH6PMI microcontroller) via an Analog-to-Digital Converter (ADC). By detecting time differences in the arrival of sound signals at each microphone, the microcontroller calculates the precise angle of the sound source.

The device is equipped with a command-line interface, allowing users to interact with the system, configure settings, and retrieve angle data in real-time. The interface supports various commands to adjust thresholds, display ambient noise levels, and more.

### Key Features:
- **Real-time AoA Calculation**: Uses three microphones to determine the angle of a sound source.
- **Interactive Shell Interface**: Customize settings and view real-time data through a command-line interface.
- **Efficient Resource Utilization**: Implemented on a resource-constrained microcontroller, proving that complex problems can be solved with minimal hardware.

## 🛠️ Hardware Setup

Here’s a breakdown of the hardware components used in this project:

- **Microcontroller**: ARM M4F core (TM4C123GH6PMI)
- **Microphones**: 3 CMC-9745-44P electret microphones in a triangular array
- **Op-Amp**: LM2902 quad op-amp for signal amplification
- **Resistors and Capacitors**: Various resistors and capacitors for biasing, filtering, and stabilization
- **PCB**: 80x120cm FR4 PC board with careful layout considerations to minimize noise

### Circuit Schematic:
![Circuit Diagram](https://user-images.githubusercontent.com/example.png)

## 🎛️ Software Capabilities

The software is designed to handle the audio processing requirements and provide a user-friendly interface for system configuration:

### Audio Processing:
- **Continuous Signal Processing**: The microphones' inputs are continuously processed at a combined conversion rate of 1 Msps.
- **Time Difference of Arrival (TDoA)**: Calculates TDoA to determine the angle of arrival.
- **Event Detection**: Identifies and processes sound events in real-time.

### Command Line Interface:
- **Threshold Adjustment**: Set or view the minimum detection threshold.
- **Noise Level Display**: Retrieve and display the ambient noise level.
- **Angle Reporting**: Get the most recent angle of arrival or enable automatic reporting of new events.
- **Advanced Settings**: Adjust backoff, holdoff, and hysteresis parameters.

## 🚀 Results & Achievements

The project was successfully completed with the following outcomes:

- **Precision**: The device accurately calculates the angle of a sound source within the constraints of the hardware.
- **User Interaction**: The shell interface proved to be a robust tool for system configuration and real-time data monitoring.
- **Scalability**: The design is scalable, with optional 3D AoA measurements using an additional microphone.


## 🔧 How to Use

1. **Connect the Hardware**: Assemble the circuit as per the schematic and connect the microcontroller to your system via USB.
2. **Load the Firmware**: Flash the provided firmware onto the TM4C123GH6PMI microcontroller.
3. **Access the Interface**: Open a serial terminal with the settings `115200 baud, 8N1, no hardware handshaking`.
4. **Execute Commands**: Use the shell commands to configure and interact with the system.

### Sample Command:
```bash
> aoa always
