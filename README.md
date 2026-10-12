# Jal Mitra (ಜಲ ಮಿತ್ರ) 💧

> **Water Quality Reporting & Grievance Redressal System for a Village / Ward**  
> **Course:** VTU 1BCP308 — Community / Societal Project | **Topic 54** (incorporating Topic 28 features)  
> **Credit:** 1 Credit (30 Hours Total) | **Grading:** CIE: 50 Marks | SEE: 50 Marks (Practical)

[![VTU 1BCP308](https://img.shields.io/badge/VTU-1BCP308%20Community%20Project-blue.svg)](https://vtu.ac.in)
[![SDG 6](https://img.shields.io/badge/UN%20SDG-6%3A%20Clean%20Water%20%26%20Sanitation-00AED9.svg)](https://sdgs.un.org/goals/goal6)
[![PO Alignment](https://img.shields.io/badge/Program%20Outcome-PO6%20(Engineer%20%26%20Society)-orange.svg)](#course-outcomes--rubric-breakdown)
[![Bilingual](https://img.shields.io/badge/Languages-English%20%7C%20%E0%B2%95%E0%B2%A8%E0%B3%8D%E0%B2%A8%E0%B2%A1-green.svg)](#bilingual-support)
[![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)](#license)

---

## 📌 Table of Contents
1. [Project Overview & Societal Relevance](#-project-overview--societal-relevance)
2. [Course Outcomes & VTU Rubric Breakdown](#-course-outcomes--vtu-rubric-breakdown)
3. [Key System Features](#-key-system-features)
   - [Citizen Side (Mobile-First PWA)](#1-citizen-side-mobile-first-pwa)
   - [Authority Side (Gram Panchayat / PDO / Ward Member)](#2-authority-side-gram-panchayat--pdo--ward-member)
   - [Core Logic: Rule-Based Hotspot Alert](#3-core-logic-rule-based-hotspot-alert-engine)
4. [Benchmarking: How Jal Mitra Solves Real Gaps](#-benchmarking-how-jal-mitra-solves-real-gaps)
5. [Ethics, Neutrality & Pitfalls Avoided](#-ethics-neutrality--pitfalls-avoided)
6. [Team Collaboration & Role Division (30-Hour Plan)](#-team-collaboration--role-division-30-hour-plan)
7. [Tech Stack & Architecture](#-tech-stack--architecture)
8. [Getting Started (Collaborator Setup)](#-getting-started-collaborator-setup)
9. [Deliverables Checklist for CIE & SEE](#-deliverables-checklist-for-cie--see)

---

## 🌍 Project Overview & Societal Relevance

Drinking water contamination (sewage seepage, turbid runoff during monsoons, pipe bursts, and overhead tank neglect) is a major public health hazard in rural Gram Panchayats and peri-urban wards across Karnataka. 

Current grievance mechanisms (such as calling the local water valve lineman, physical petitions at the Panchayat office, or distant call centers like Parihara/Janaspandana) face severe limitations:
* **High friction:** Rural citizens often lack the time or digital literacy to navigate bureaucratic portals.
* **The "Unilateral Closure" trap:** Line staff often mark grievances as "Resolved" on paper without real verification.
* **Absence of spatial intelligence:** Outbreaks of waterborne contamination are rarely detected early because isolated complaints are not aggregated into contamination clusters.

**Jal Mitra (ಜಲ ಮಿತ್ರ)** is a lightweight, mobile-first Progressive Web App (PWA) designed to bridge the communication gap between ward/village residents and local governance (Panchayat Development Officers, Ward Engineers, and Pani Samitis). It prioritizes **under-60-second reporting**, **bilingual accessibility (English & Kannada)**, **citizen-confirmed resolution**, and **automated outbreak hotspot detection**.

---

## 📊 Course Outcomes & VTU Rubric Breakdown

According to the official **VTU 1BCP308 syllabus guidelines**:

> **Critical Note for Collaborators:** Most marks (**CO1, CO2, CO4, CO5**) evaluate **fieldwork, stakeholder interviews, and community evidence**, not just lines of code. Only **CO6** is about the software prototype. An amazing app without signed survey sheets and PDO interview notes will lose marks!

| Course Outcome (CO) | Focus Area | What the Examiners Will Ask For | Deliverable Evidence |
| :--- | :--- | :--- | :--- |
| **CO1** | Community Identification | Identifying water quality issues in a designated ward or village | Photos of water points, location profile, team visit record |
| **CO2** | Problem Formulation & Baseline Study | Analyzing existing solutions (Parihara helpline, Janaspandana, manual petitions) and identifying why they fail | Baseline report comparing existing grievance mechanisms |
| **CO4** | Feasibility, Ethics & Social Impact | Considering political neutrality, cost, privacy, and public safety | Privacy design (anonymized ticket IDs, neutral language) |
| **CO5** | Stakeholder Engagement & Feedback | Conducting field interviews and testing the solution with real residents | **Survey of 20–30 residents** + **Signed/recorded interview with PDO/Ward Member** |
| **CO6** | Prototype Demonstration | Building a working, functional product that addresses the problem statement | **Jal Mitra working PWA prototype** |

---

## ⚡ Key System Features

### 1. Citizen Side (Mobile-First PWA)
* **Zero-Install Access:** Works on any smartphone browser with offline capability.
* **< 60-Second Grievance Reporting:**
  * **6 Standard Categories:**
    1. *Discoloured or turbid water* (ಬಣ್ಣಗೆಟ್ಟ ಅಥವಾ ಕಲಕಿದ ನೀರು)
    2. *Bad smell or taste* (ಕೆಟ್ಟ ವಾಸನೆ ಅಥವಾ ರುಚಿ)
    3. *Sewage mixing / drainage leakage* (ಒಳಚರಂಡಿ ನೀರು ಮಿಶ್ರಣ)
    4. *Pipeline leakage / burst* (ಪೈಪ್‌ಲೈನ್ ಸೋರಿಕೆ)
    5. *No water supply / irregular supply* (ನೀರು ಸರಬರಾಜು ಇಲ್ಲ)
    6. *Overhead tank / borewell contamination* (ಟ್ಯಾಂಕ್ / ಕೊಳವೆಬಾವಿ ಕಲ್ಮಶ)
  * Geo-location pinning (via device GPS) and ward/village dropdown selection.
  * Photo capture / file upload proof.
  * Simple free-text description and citizen mobile number for status updates.
* **Public Tracking by Complaint ID:**
  * Track any ticket via a unique code (`JM-2026-XXXX`).
  * Live visual timeline: `Reported` ➔ `Acknowledged` ➔ `Assigned` ➔ `In Progress` ➔ `Resolved` ➔ `Citizen-Confirmed`.
* **Two-Way Citizen Confirmation:**
  * Authorities *cannot* close a complaint unilaterally. When marked "Resolved" by field staff, the citizen must inspect and click **"Confirm Fixed"** or **"Reopen with Remark"**.
* **Observation Log (Topic 28 Borrow):**
  * Allows residents or village volunteers to log sensory metrics (Colour, Odour, Taste, Turbidity scale) and optional Field Test Kit (pH/TDS) values without faking laboratory data.
* **Community Awareness Hub:**
  * Practical, culturally contextual guides on water boiling duration, bleaching powder dosage (chlorination per 1,000L), overhead tank cleaning frequency, and nearest Jal Jeevan Mission water testing laboratory contacts.
* **Bilingual Support (English & ಕನ್ನಡ):**
  * Instant toggle across the entire UI for rural usability.

---

### 2. Authority Side (Gram Panchayat / PDO / Ward Member)
* **Operational Queue:** Filter complaints by Ward, Category, Date, and Urgency.
* **Interactive Geo-Map (Leaflet.js + OpenStreetMap):**
  * Color-coded map markers showing open, in-progress, and resolved complaints across the ward.
* **Action Workflow & Audit Trail:**
  * Assign complaints to specific linemen/contractors.
  * Mandatory remarks required for every status transition, recording timestamps and resolution duration.
* **One-Click Reports & Analytics:**
  * Summary metrics: Total reports, average resolution time (SLA), and category breakdown.
  * Export clean CSV data and printable PDF summary for monthly Gram Panchayat meetings.

---

### 3. Core Logic: Rule-Based Hotspot Alert Engine
Rather than relying on black-box or fabricated machine learning, Jal Mitra implements a deterministic, clinically grounded **spatial-temporal outbreak detection rule**:

$$\text{Alert Triggered} \iff \text{Complaints in Ward } W \ge 3 \quad \text{within} \quad \Delta t \le 7\text{ days}$$

When 3 or more contamination complaints occur in the same ward within a 7-day sliding window:
1. The dashboard raises a **High-Priority Contamination Hotspot Alert (⚠️ ಕೆಂಪು ಎಚ್ಚರಿಕೆ)**.
2. Flags the primary category (e.g., "Cluster Alert: 4 reports of Sewage Mixing in Ward 3").
3. Prompts the PDO to issue a localized precautionary advisory (e.g., recommend boiling water immediately while emergency pipe inspection proceeds).

---

## 🔍 Benchmarking: How Jal Mitra Solves Real Gaps

| Dimension | JJM-WQMIS Portal | Karnataka Parihara (RDWSD) | mWater (Global) | **Jal Mitra (This Project)** |
| :--- | :--- | :--- | :--- | :--- |
| **Intended User** | Certified lab chemists & engineers | General citizens (Call Center / Web) | NGO researchers | **Village residents & Gram Panchayat PDO** |
| **Submission Time** | > 8 mins (complex lab forms) | 3–5 min voice queue | 5–10 min survey | **< 60 seconds (Mobile PWA)** |
| **Language UI** | English / Hindi | English / Limited Kannada | English | **Native English & Kannada (ಕನ್ನಡ) Toggle** |
| **Closure Model** | Administrative sign-off | Unilateral official closure | Surveyor signs off | **Two-Way Citizen Confirmation** |
| **Outbreak Detection** | Manual retrospective reports | None | Map filters | **Automated Rule Engine ($\ge$3 in 7 days)** |
| **Water Guidance** | Lab report values | None | Survey data | **Household advisory (boiling, chlorination)** |

---

## 🛡️ Ethics, Neutrality & Pitfalls Avoided

To satisfy **CO4** and comply with project rubrics, Jal Mitra enforces strict design constraints:
1. **Political Neutrality & Anonymity:**
   * Complaints are visible by **Ticket ID and Ward name only**.
   * Citizen phone numbers and personal names are kept strictly confidential.
   * The platform **does not rank, shame, or blame individual officials**; it is designed as a constructive operational collaboration tool with the local administration.
2. **Scientific Safety & Liability Disclaimer:**
   * The application explicitly states:
     > *"This platform records community reports and sensory observations. It does not certify water as '100% safe' or 'potable'. For microbiological and chemical testing, refer to the accredited Gram Panchayat / Jal Jeevan Mission laboratory."*
3. **Spam & Duplicate Prevention:**
   * Client-side cooldown rate-limiting and duplicate detection for identical category submissions within the same 2-hour window.

---

## 👥 Team Collaboration & Role Division (30-Hour Plan)

For team collaboration on GitHub, divide responsibilities across the following roles:

```
                            ┌─────────────────────────────────┐
                            │    30-Hour Project Allocation   │
                            └────────────────┬────────────────┘
                                             │
      ┌──────────────────┬───────────────────┼───────────────────┬──────────────────┐
      ▼                  ▼                   ▼                   ▼                  ▼
┌──────────────┐   ┌──────────────┐   ┌──────────────┐   ┌──────────────┐   ┌──────────────┐
│  Field Visit │   │   Problem    │   │  Core PWA    │   │  Kannada UI  │   │ Pilot User   │
│ & Interviews │   │  Statement   │   │  Prototype   │   │  & Hotspot   │   │ Testing &    │
│  (6-7 Hours) │   │  (3-4 Hours) │   │ (10-12 Hours)│   │  (3 Hours)   │   │ Report (4h)  │
└──────────────┘   └──────────────┘   └──────────────┘   └──────────────┘   └──────────────┘
```

### Recommended Team Roles
* **Member 1 (Fieldwork & Stakeholder Lead — CO1, CO4, CO5):**
  * Conduct the Gram Panchayat / Ward visit.
  * Conduct the interview with the Panchayat Development Officer (PDO) or water valve lineman.
  * Collect signed/recorded survey responses from 20–30 residents.
* **Member 2 (Frontend & PWA Lead — CO6):**
  * Build the mobile-first citizen reporting interface and tracking timeline.
  * Implement the English $\leftrightarrow$ Kannada localization dictionary (`src/locales`).
  * Ensure responsive, fast-loading PWA behaviour.
* **Member 3 (Logic, Geo-Mapping & Analytics Lead — CO6):**
  * Integrate Leaflet.js with OpenStreetMap for geo-tagged pin visualization.
  * Implement the sliding-window Hotspot Alert Rule Engine.
  * Implement CSV and printable summary export functionality.
* **Member 4 (Pilot Testing & Documentation Lead — CO2, CO5):**
  * Formulate the approved problem statement and baseline comparative study.
  * Run pilot usability tests with 3–5 real residents and record their qualitative feedback.
  * Compile the final VTU project report and presentation slides.

---

## 💻 Tech Stack & Architecture

* **Frontend:** Modern lightweight React / Vite PWA (mobile-first, zero-install)
* **Styling:** Modular Vanilla CSS design system (clean, responsive, high-contrast accessible layout)
* **Mapping:** Leaflet.js with OpenStreetMap tiles (100% free, no API billing required)
* **State & Persistence:** LocalStorage / IndexedDB with preloaded demo data for realistic demonstrations
* **Localization:** Custom zero-dependency i18n dictionary for English and Kannada (`ಕನ್ನಡ`)
* **Analytics/Export:** Client-side CSV generation & print-optimized report view

---

## 🚀 Getting Started (Collaborator Setup)

### Prerequisites
* [Node.js](https://nodejs.org/) (v18.0 or higher recommended)
* `git` installed on your system

### Installation & Local Run
```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/JAL-MITRA.git
cd JAL-MITRA

# 2. Install dependencies (once package.json is initialized)
npm install

# 3. Copy environment configuration
cp .env.example .env

# 4. Start the local development server
npm run dev
```

Visit `http://localhost:5173` in your browser. Open Developer Tools (F12) and toggle device emulation (Mobile view) to test the citizen experience.

---

## 📋 Deliverables Checklist for CIE & SEE

- [ ] **CO1:** Formatted team list & photos of the visit to the Gram Panchayat / Ward water source.
- [ ] **CO2:** Approved Problem Statement document and Baseline Comparison Matrix.
- [ ] **CO4:** Ethical neutrality and public health disclaimer statement.
- [ ] **CO5 (Resident Survey):** Questionnaire filled by 20–30 village/ward residents.
- [ ] **CO5 (Stakeholder Interview):** Written summary of interview with the PDO or water supply lineman.
- [ ] **CO6 (Prototype):** Jal Mitra PWA running with sample complaint tracking, map view, Kannada UI, and hotspot alert demonstration.
- [ ] **CO6 (Pilot Feedback):** Post-prototype feedback forms from at least 3 users.

---

## 📜 License
This project is developed under the **MIT License** for academic and societal public-good purposes under **VTU 1BCP308**.
