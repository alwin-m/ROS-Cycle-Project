<div align="center">


<img src="https://github.com/user-attachments/assets/5d7d8465-d727-4325-9b2e-3f415cb45589" width="120" alt="ROS Cycle Logo" />

# 🌸 ROS Cycle

### Free Period Tracker & Menstrual Cycle Calendar

**Track Your Cycle — Privately, Transparently, and on Your Terms**

[![License: MIT](https://img.shields.io/badge/License-MIT-rose.svg?style=flat-square)](https://opensource.org/licenses/MIT)
[![Open Source](https://img.shields.io/badge/Open%20Source-Yes-brightgreen?style=flat-square)](https://github.com/)
[![Privacy First](https://img.shields.io/badge/Privacy-First-blueviolet?style=flat-square)](#)
[![No Cloud](https://img.shields.io/badge/Cloud-None-red?style=flat-square)](#)
[![Platform](https://img.shields.io/badge/Platform-Web%20%7C%20Local-blue?style=flat-square)](#)

[✨ Features](#-features) · [📐 How It Works](#-how-it-works) · [🚀 Getting Started](#-getting-started) · [🛡️ Privacy](#️-privacy-first-by-design) · [🤝 Contribute](#-contributing)

---

</div>

## 🌺 What is ROS Cycle?

**ROS Cycle** is an open-source, privacy-first menstrual cycle tracker that runs **entirely on your device**. No accounts. No cloud. No telemetry. Just honest, math-backed predictions you can actually understand.

Unlike commercial trackers that hide their logic behind black-box algorithms, ROS Cycle is built on **transparent, explainable mathematics** — so you always know *how* and *why* a prediction is made.

> **ROS Cycle is a tracker, not a diagnostic tool.** Predictions are estimates based on your inputs, not medical advice.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🗓️ **12-Month Calendar View** | See your entire predicted cycle year at a glance |
| 🌡️ **Probabilistic Fertile Windows** | Gradient fertility bands instead of misleading binary labels |
| 🎯 **Ovulation Likelihood Peaks** | Gaussian-modeled peak estimates with uncertainty baked in |
| 📊 **Confidence Indicators** | Know how reliable your predictions are, based on your cycle stability |
| 📄 **Exportable PDF Reports** | Generate and save reports — fully local, never uploaded |
| 🩺 **PCOD Symptom Checklist** | Optional, non-diagnostic symptom awareness tool |
| 🔒 **100% On-Device** | Zero data transmission. Always. |

---

## 📐 How It Works

ROS Cycle uses a **two-layer mathematical model**: a deterministic core anchored to your cycle data, layered with probabilistic reasoning to represent real biological uncertainty.

### Inputs

| Input | Symbol | Required |
|---|---|---|
| Last Menstrual Period start date | `D₀` | ✅ Yes |
| Average cycle length (days) | `μ_C` | ✅ Yes |
| Estimated cycle variability (± days) | `σ_C` | Optional |
| Average period length (days) | `P` | Optional |

---

### 1. 🔢 Cycle Day Index

For any calendar date `Dₙ`, the cycle-relative day is:

```
CycleDay(Dₙ) = (Dₙ − D₀) mod μ_C
```

Converts any absolute date into a repeating cycle position, anchoring all phase calculations.

---

### 2. 🌿 Phase Boundaries

| Phase | Range |
|---|---|
| 🔴 Menstrual | `0 ≤ d < P` |
| 🟡 Follicular | `P ≤ d < (μ_C − 14)` |
| 🟢 Ovulation Center | `d = (μ_C − 14)` |
| 🔵 Luteal | `(μ_C − 14) < d < μ_C` |

---

### 3. 📈 Probabilistic Ovulation Model

Ovulation is never certain. ROS Cycle models it with a Gaussian distribution:

```
P_ov(d) = exp( −(d − (μ_C − 14))² / 2(σ_C + δ)² )
```

- `δ ≈ 1–2 days` of biological noise is always included
- Confidence smoothly decreases the further a day is from the expected ovulation center
- Output: a likelihood value between **0 and 1** per cycle day

---

### 4. 🌈 Fertility Probability Bands

| Band | Condition |
|---|---|
| 🔴 High Fertility | `P_ov(d) > 0.6` |
| 🟠 Medium Fertility | `0.25 < P_ov(d) ≤ 0.6` |
| 🟢 Low Fertility | `P_ov(d) ≤ 0.25` |

No false certainty. Just gradients that reflect reality.

---

### 5. 🧮 Confidence Score

```
Confidence = 1 − (σ_C / μ_C)    [clamped to 0–1]
```

| Confidence | Meaning |
|---|---|
| High | Short, stable, predictable cycle |
| Medium | Some variability present |
| Low | High variability — predictions less reliable |

---

## 🚀 Getting Started

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/ros-cycle.git

# Navigate into the project
cd ros-cycle

# Install dependencies
npm install

# Start the app locally
npm start
```

> ⚡ Everything runs in your browser or on your machine. No backend, no server, no sign-up.

---

## 🛡️ Privacy First by Design

ROS Cycle was built around a core principle: **your health data belongs to you, and only you.**

- ✅ All computation is **local-only**
- ✅ **No accounts** required
- ✅ **No cloud storage**, no sync, no telemetry
- ✅ **No behavioral tracking** or background learning
- ✅ Fully **auditable open-source code**
- ✅ Predictable, **deterministic outputs** given the same inputs

---

## 🩺 PCOD Symptom Checker

ROS Cycle includes an optional symptom awareness checklist for common PCOD-related symptoms.

- Summarizes symptom count
- Encourages you to speak with a healthcare professional when appropriate
- **Does not** influence cycle predictions
- **Does not** perform any diagnosis

---

## 📤 Output Summary

- 🗓️ 12-month cycle calendar
- 🎯 Probability-informed fertile windows
- 📈 Ovulation likelihood peaks
- 📉 Cycle confidence indicators
- 📄 Local-only exportable PDF reports

---

## 🤝 Contributing

Contributions are warmly welcome! We especially value work that:

- 💡 Improves **explainability** of predictions
- ♿ Enhances **accessibility**
- 📊 Extends **visualization clarity**
- 🔒 Preserves the **privacy-first** architecture

### How to Contribute

```bash
# Fork the repo, then:
git checkout -b feature/your-feature-name
git commit -m "feat: describe your change"
git push origin feature/your-feature-name
# Open a Pull Request 🎉
```

> ⚠️ Feature proposals requiring cloud storage or opaque inference models will be carefully reviewed to ensure they align with ROS Cycle's core values.

---

## ⚠️ Disclaimer

ROS Cycle is an **educational and informational tool**. Menstrual cycles are influenced by stress, illness, hormonal conditions, medications, and lifestyle factors. All predictions are **estimates** and may vary significantly.

**Always consult a qualified healthcare professional for medical concerns.**

---

## 📄 License

```
MIT License — free to use, modify, and distribute.
```

See [`LICENSE`](./LICENSE) for full terms.

---

<div align="center">

Made with 🌸 for privacy, transparency, and cycle awareness.

**ROS Cycle — because your data should stay yours.**

</div>
