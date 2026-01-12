# ROS Cycle: Open-Source Menstrual Cycle Tracker

## Overview

ROS Cycle is an open-source, privacy-first menstrual cycle tracker that runs **entirely on the user’s device**. It is designed to provide **transparent, mathematically grounded cycle predictions** without collecting, transmitting, or storing personal health data on external servers.

Unlike many commercial trackers, ROS Cycle does **not claim certainty**. Instead, it models the menstrual cycle using **deterministic rules combined with explicit uncertainty**, presenting predictions as **probability-informed insights rather than guarantees**.

ROS Cycle is suitable for students, privacy-conscious users, and developers interested in explainable health algorithms.

---

## Why ROS Cycle Exists

Most menstrual tracking applications rely on opaque algorithms and centralized data storage. ROS Cycle was created to demonstrate an alternative approach:

* **Privacy by architecture**: All computation is local. No accounts, no cloud, no telemetry.
* **Explainable mathematics**: Every prediction is derived from visible formulas.
* **Educational clarity**: Users and contributors can understand how predictions are generated.
* **Ethical restraint**: The system avoids medical claims or hidden inference.

ROS Cycle is a tracker, not a diagnostic tool.

---

## Core User Inputs

ROS Cycle intentionally limits inputs to what is mathematically defensible in a local-only system.

Required inputs:

1. **Last Menstrual Period start date**
   ( D_0 )

2. **Average cycle length (days)**
   ( \mu_C ), typically between 15 and 45 days

Optional inputs:

3. **Estimated cycle variability (± days)**
   ( \sigma_C )

4. **Average period length (days)**
   ( P ), typically between 3 and 10 days

These parameters define the entire prediction model.

---

## Mathematical Model

ROS Cycle uses a **two-layer model**:

1. A deterministic baseline to anchor the calendar
2. A probabilistic layer to represent biological uncertainty

No learning occurs unless the user explicitly updates inputs.

---

## 1. Cycle Day Index (Deterministic Core)

For any calendar date ( D_n ), the cycle day index is:

[
\text{CycleDay}(D_n) = (D_n - D_0) \bmod \mu_C
]

**How it works:**

* Converts absolute dates into a repeating cycle index
* Anchors all phase calculations

**Input → Output:**

* Input: calendar date
* Output: cycle-relative day number

**Question answered:**

> Where does this date fall within the current cycle?

---

## 2. Baseline Phase Boundaries

Using biological averages, ROS Cycle defines reference phase regions:

* **Menstrual phase**: ( 0 \le d < P )
* **Follicular phase**: ( P \le d < (\mu_C - 14) )
* **Ovulation center**: ( d = (\mu_C - 14) )
* **Luteal phase**: ( (\mu_C - 14) < d < \mu_C )

**How it works:**

* Establishes a non-probabilistic biological scaffold

**Outcome:**

* A phase label for each cycle day

**Question answered:**

> What phase is this day closest to, assuming a typical cycle?

---

## 3. Probabilistic Ovulation Model

Ovulation timing is uncertain even in regular cycles. ROS Cycle models this uncertainty using a Gaussian distribution:

[
P_{ov}(d) = \exp\left( -\frac{(d - (\mu_C - 14))^2}{2(\sigma_C + \delta)^2} \right)
]

Where:

* ( d ) = cycle day index
* ( \sigma_C ) = user-estimated variability
* ( \delta \approx 1–2 ) days (biological noise)

**How it works:**

* Centers likelihood around the expected ovulation day
* Smoothly decreases confidence farther from the center

**Output:**

* Relative ovulation likelihood per cycle day (0–1)

**Question answered:**

> How plausible is ovulation on this day, given uncertainty?

---

## 4. Fertility Probability Bands

Rather than binary fertile / non-fertile labeling, ROS Cycle defines probability bands:

* **High fertility**: ( P_{ov}(d) > 0.6 )
* **Medium fertility**: ( 0.25 < P_{ov}(d) \le 0.6 )
* **Low fertility**: ( P_{ov}(d) \le 0.25 )

**How it works:**

* Maps ovulation probability to fertility relevance

**Outcome:**

* Gradient-based fertility visualization

**Question answered:**

> How biologically favorable is this day for conception?

---

## 5. Confidence Estimation

ROS Cycle displays a confidence score derived from cycle variability:

[
\text{Confidence} = 1 - \frac{\sigma_C}{\mu_C}
]

Values are clamped to the interval ([0,1]).

**How it works:**

* Larger variability reduces confidence
* Shorter, stable cycles increase confidence

**Outcome:**

* Qualitative confidence indicator (Low / Medium / High)

**Question answered:**

> How reliable are these predictions, given cycle stability?

---

## What ROS Cycle Does *Not* Do

* No medical diagnosis
* No hormone inference
* No behavioral tracking
* No background learning
* No cloud-based analytics

All predictions are conditional on user-provided inputs.

---

## PCOD Symptom Checker (Non-Diagnostic)

ROS Cycle includes an optional checklist for common PCOD-related symptoms. The output:

* Summarizes symptom count
* Encourages medical consultation when appropriate
* Explicitly avoids diagnosis

This component does **not** influence cycle predictions.

---

## Output Summary

ROS Cycle generates:

* A 12-month calendar view
* Probability-informed fertile windows
* Ovulation likelihood peaks
* Confidence indicators
* Exportable PDF reports (local only)

---

## Ethical & Technical Guarantees

* Fully client-side execution
* Transparent formulas
* No data transmission
* MIT-licensed open-source code
* Predictable, auditable behavior

---

## Contribution Philosophy

Contributions are welcome, especially those that:

* Improve explainability
* Enhance accessibility
* Extend visualization clarity
* Preserve privacy-first design

Feature proposals that require cloud storage or opaque inference will be carefully reviewed.

---

## Disclaimer

ROS Cycle is an educational and informational tool. Menstrual cycles are influenced by stress, illness, hormonal conditions, and lifestyle factors. Predictions are estimates and may vary. Always consult a qualified healthcare professional for medical concerns.

---

## License

MIT License — free to use, modify, and distribute.

![ROS Cycle Logo](https://github.com/user-attachments/assets/5d7d8465-d727-4325-9b2e-3f415cb45589)
