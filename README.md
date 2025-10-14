ROS Cycle, Open Source Menstrual Cycle Tracker

ROS Cycle is an open source project that helps women and girls understand their menstrual health. The application makes it easy to log the date of the last period, the cycle length, and the duration of periods. It then uses this information to predict future cycles.

With these details, ROS Cycle can:

- Predict menstrual cycles for the next 12 months.
- Show cycle dates in a clear calendar view.
- Estimate ovulation windows, helping users understand their fertility patterns.

The goal of ROS Cycle is to offer a simple, open, and privacy-friendly tool for menstrual awareness. Because it’s open source, the project can grow with new features like personalized health insights, reminders, wellness tips, or even connections to healthcare apps.

ROS Cycle is not just a tracker; it’s a learning companion for menstrual health, with potential for growth through community-driven updates and improvements.
<img width="1200" height="1200" alt="ROSCYCLE" src="https://github.com/user-attachments/assets/5d7d8465-d727-4325-9b2e-3f415cb45589" />
Usage Guide for ROS Cycle

Welcome to the ROS Cycle Usage Guide! This page will help you use our privacy-first period tracking web app to monitor your menstrual cycle and check for possible PCOD symptoms. ROS Cycle is a student-built, open-source prototype designed for easy use on all devices, including phones, tablets, and laptops. Follow these steps to get started, view your calendar, and understand your results.

Table of Contents

Getting Started

Step-by-Step Instructions

Step 1: Enter Basic Info

Step 2: Check PCOD Symptoms

Step 3: Add Period Details

Step 4: View Your Calendar

Tips for Best Experience

Troubleshooting

Feedback and Support

Getting Started

Visit the App: Open ROS Cycle in your browser. It works on Chrome, Safari, Firefox, and more.

Device Compatibility: The app is fully responsive, adjusting to your screen size on any device.

Offline Use: Once loaded, ROS Cycle works offline due to its Service Worker. Make sure to load it while connected to the internet.

Privacy Note: No data is stored online. Everything remains on your device for maximum privacy.

Step-by-Step Instructions

Step 1: Enter Basic Info

What to Do:

On the welcome screen, enter your name (a nickname is fine) in the text field.

You can optionally provide your date of birth; this is only used for age guidance and is not stored.

If you prefer, skip the date of birth by leaving it blank.

Options:

Click Skip to move to the next step without entering your information.

Click Check for PCOD to assess symptoms first.

Click Continue to move on to period details.

Tips:

Use a valid date format (YYYY-MM-DD) for your date of birth.

If your age is outside the range of 9 to 55 years, you’ll see a prompt to confirm or correct it.

Step 2: Check PCOD Symptoms

What to Do:

Answer questions about common PCOD symptoms (like irregular periods or acne) by checking the relevant boxes.

Click Submit to see your results, which estimate a low, medium, or high chance of PCOD based on your answers.

Click ← Back to return to Step 1 if needed.

Understanding Results:

Low (0–2 symptoms): Low likelihood of PCOD.

Medium (3–5 symptoms): Consider consulting a doctor.

High (6+ symptoms): Strongly recommend seeing a healthcare provider.

Results will appear in a popup with a summary of selected symptoms.

Important: This is not a medical diagnosis. Always consult a professional for health concerns.

Tip: Use the keyboard (Tab to navigate, Space to check boxes) or tap on mobile for better accessibility.

Step 3: Add Period Details

What to Do:

Enter the start date of your last period (YYYY-MM-DD).

Specify your average cycle length (days between periods, typically 28; range is 15 to 45).

Enter your average period length (days of bleeding, typically 5; range is 3 to 10).

Click Create my calendar to generate predictions.

Click ← Back to return to the PCOD checker.

Tips:

Make sure the last period date is not in the future.

If your cycle or period length is outside the typical range, consult a healthcare provider as it may impact prediction accuracy.

Step 4: View Your Calendar

What to Do:

View your 12-month prediction calendar, showing period (pink) and fertile (mint) days.

Navigate months using the ← (previous) and → (next) buttons.

Click Update to revise period details or Start Over to reset everything.

Understanding the Calendar:

Period Days: Marked in pink based on your cycle and period length.

Fertile Days: Marked in mint, estimated around ovulation (cycle day 14 ± 5 days).

Hover or tap a day to see a tooltip with details (e.g., “Period day: 2025-11-05”).

Tips:

Use arrow keys for navigation (left/right for months, Tab for days).

Predictions are estimates and may vary due to stress, diet, or hormonal changes.

Tips for Best Experience

Mobile Use: Tap buttons gently; they’re designed for touch with minimum targets of 48px.

Dark Mode: Switch to dark mode via the footer link for better visibility in low light.

Accessibility: Use keyboard navigation (Tab, Enter, Escape) or screen readers as ARIA labels are included.

Performance: The app loads in less than 500ms on most devices. Clear your browser cache if it feels slow.

Updates: Check the Home page for new features, such as the upcoming export functionality.

Troubleshooting

Issue: Calendar doesn’t load.

Fix: Ensure all fields in Step 3 are valid. Check if the date entered is in the past and that the cycle is between 15 and 45 days.

Issue: Tooltip overflows on mobile.

Fix: Tooltips are optimized to show below days on small screens. If the issue continues, report it via GitHub Issues.

Issue: App not loading offline.

Fix: Load the app once while online to cache files using the Service Worker. Check if your browser supports Service Workers; modern browsers like Chrome and Safari work best.

Issue: PCOD results seem inaccurate.

Fix: The checker is a basic tool and is not a diagnosis. Consult a doctor for professional advice.

Feedback and Support

Report Issues: Found a bug or have a suggestion? Open an issue on GitHub Issues.

Contribute: Want to help improve ROS Cycle? See the Contributing Guidelines for how to submit code or ideas.

Contact: Reach out to @alwin-m or check Alwin’s Portfolio for more information.

Disclaimer: ROS Cycle is a student-built prototype and not medically approved. Predictions are estimates and may vary.

Happy tracking! Explore the Home page to learn more about ROS Cycle or contribute to make it even better!
