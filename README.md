# ROS Cycle: Open-Source Menstrual Cycle Tracker


## Overview

ROS Cycle is an open-source, privacy-focused web application aimed at helping women and girls track their menstrual health. Developed as a student-friendly project, it offers a straightforward interface to log menstrual cycle information and gain insights into future cycles and fertility patterns. All data processing occurs locally on your device to ensure your privacy; no information is stored or sent to external servers.

With ROS Cycle, users can:
- **Log Key Details**: Input the date of the last period, average cycle length, and period duration.
- **Predict Future Cycles**: Access predicted menstrual cycles for the next 12 months in a clear calendar format.
- **Estimate Ovulation Windows**: Learn about fertility patterns with estimated ovulation periods.
- **Check PCOD Symptoms**: Complete a simple questionnaire to evaluate potential PCOD symptoms, with advice to consult a healthcare professional.

ROS Cycle is more than just a tracker; it’s a learning companion for menstrual health, built to evolve through community-driven input and updates.

## Why We Built ROS Cycle

The goal of ROS Cycle is to provide a simple, accessible, and privacy-centered tool for menstrual health awareness, especially for students and those who prioritize data privacy. Many menstrual tracking apps collect sensitive data, which can be concerning. ROS Cycle addresses this by:
- **Prioritizing Privacy**: All data is processed and stored locally, ensuring personal information never leaves your device.
- **Promoting Education**: With clear predictions and PCOD symptom insights, it allows users to learn about their bodies without needing medical expertise.
- **Fostering Community**: As an open-source project, ROS Cycle welcomes contributions from developers, students, and health enthusiasts to improve features and accessibility.

Our aim is to create a reliable, clear, and user-friendly tool that simplifies menstrual health while respecting user privacy.

![ROS Cycle Logo](https://github.com/user-attachments/assets/5d7d8465-d727-4325-9b2e-3f415cb45589)

## Current Features

- **Cycle Prediction**: Enter your last period date, cycle length (15 to 45 days), and period duration (3 to 10 days) to generate a 12-month prediction.
- **Calendar View**: Shows predicted periods and fertile days in a responsive grid with tooltips for clarity.
- **PCOD Symptom Checker**: A questionnaire to identify potential PCOD symptoms, with results included in the PDF export (not a medical diagnosis).
- **PDF Export**: Creates a compact PDF report with cycle details, PCOD insights, and a disclaimer, processed via a Web Worker for performance.
- **Offline Support**: A service worker caches resources (like jsPDF and fonts) for offline access.
- **Accessibility**: ARIA attributes, keyboard navigation, and high-contrast colors ensure inclusivity for screen reader and keyboard users.
- **Responsive Design**: Optimized for both mobile and desktop, with adjusted badge sizes and grid layouts for smaller screens.

## Aims and Objectives

ROS Cycle aims to:
1. **Empower Users**: Offer clear and easy-to-understand cycle predictions to support menstrual health awareness.
2. **Ensure Privacy**: Maintain a fully local, client-side architecture to protect sensitive health data.
3. **Encourage Open-Source Growth**: Allow community contributions to add features such as reminders, wellness tips, or links with health apps.
4. **Support Education**: Act as a learning tool for students and young users, with clear disclaimers about its non-medical nature.
5. **Scale Gracefully**: Set the groundwork for future enhancements while keeping the app lightweight and user-friendly.

## Future Vision

ROS Cycle plans to grow into a comprehensive, privacy-first platform for menstrual health. While the current version is a lightweight web app, we hope to use advanced technologies to strengthen its capabilities while remaining open-source and privacy-centric. Possible future directions include:

### Advanced Predictive Algorithms
- **Game Theory**: Develop algorithms (e.g., using Python’s `nashpy`) to create personalized reminders or health recommendations based on user behavior and preferences. For example, game theory could determine the best times to send reminders to increase user engagement without being intrusive.
- **Machine Learning**: Include lightweight machine learning models (e.g., TensorFlow Lite) to predict menstrual irregularities or hormonal imbalances based on historical cycle data, lifestyle inputs, or biometric data. These models would function locally to maintain privacy, possibly using frameworks like TinyML for edge devices.

### Smartwatch Integration
- **Wearable Connectivity**: Link ROS Cycle to smartwatches (e.g., through Google Fit, Apple HealthKit) to gather real-time health data like heart rate, blood pressure, or activity levels. Future wearables may feature sensors for non-invasive hormonal tracking (e.g., cortisol or estrogen from sweat or optical sensors), allowing predictions of hormonal imbalances.
- **Edge AI**: Utilize on-device AI processing (e.g., with TPUs or NPUs in new smartwatches) to evaluate health data locally, ensuring privacy. For example, a smartwatch app could identify cycle irregularities by correlating biometric data with user logs.

### Enhanced Privacy with Edge Computing
- **Local Data Storage**: Expand local storage options (e.g., IndexedDB, SQLite) for ongoing cycle tracking without relying on cloud services.
- **Edge AI**: Deploy AI models on the device using frameworks like ONNX Runtime or TensorFlow Lite, avoiding the need for data transmission to servers. This aligns with new trends in edge computing for health applications.
- **Encrypted Exports**: Provide users the option to export encrypted cycle data (e.g., in ICS or JSON format) for secure sharing or backup.

### Community-Driven Features
- **Personalized Insights**: Offer wellness tips (e.g., diet, exercise) customized to cycle phases, contributed by the open-source community.
- **Multilingual Support**: Make the app available in multiple languages to reach a wider audience.
- **Integration with Health Platforms**: Allow optional connections with privacy-aware health apps (e.g., open-source fitness trackers) for complete health tracking.

### Technological Feasibility
These advancements are possible within 5 to 10 years, given:
- **Wearable Sensors**: Research on non-invasive hormonal tracking (e.g., via sweat sensors) is advancing, with prototypes anticipated by 2030.
- **Edge AI**: TPUs and NPUs are becoming common in mobile devices (e.g., Google’s Coral, Apple’s Neural Engine). Smartwatches with similar capabilities are likely within 2028 to 2030.
- **ML Frameworks**: Lightweight models (e.g., TensorFlow Lite) are already compatible with edge devices, and open-source tools like PyTorch Mobile are progressing.
- **Privacy Standards**: Open-source communities (e.g., Linux Foundation’s EdgeX) are creating frameworks for secure, local health data management.

Our long-term vision is to transform ROS Cycle into a privacy-first, AI-enhanced health assistant that operates on wearables, predicts health patterns accurately, and empowers users through open-source collaboration—all while keeping data local and secure.

## Getting Started

To try ROS Cycle:
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/ros-cycle.git
   ```
2. Serve the app locally (e.g., using Python’s HTTP server):
   ```bash
   cd ros-cycle
   python -m http.server 8000
   ```
3. Open http://localhost:8000 in a browser. 
4. Follow the steps to log your cycle and export a PDF report.

## Contributing

ROS Cycle relies on community contributions! To help out:
- Fork the repository and create a branch (e.g., feature/your-feature).
- Submit pull requests to the dev branch (not main).
- Follow the MIT License and code of conduct.
- Suggest features like reminders, wellness tips, or advanced predictions.

See CONTRIBUTING.md for guidelines.

## License

ROS Cycle is licensed under the MIT License, so it remains free and open for everyone to use, modify, and share.

## Acknowledgments

Built with care by students for students, inspired by the need for privacy-focused health tools. Special thanks to the open-source community for resources like jsPDF and support for menstrual health awareness.

ROS Cycle is a prototype for educational purposes. Predictions are estimates and may vary due to factors like stress, diet, or hormonal changes. Always consult a healthcare professional for medical advice.
