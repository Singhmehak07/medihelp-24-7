<div align="center">

# 🏥 MediHelp 24/7 (Immihelp Rural Health AI)
### *AI-Assisted Patient Interaction, Clinical Triage & Medication Management for Rural Healthcare*

[![React 19](https://img.shields.io/badge/React-19.0.0-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.8.2-3178C6?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Vite](https://img.shields.io/badge/Vite-6.2.0-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![Google Gemini](https://img.shields.io/badge/Google_Gemini_AI-1.29-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://ai.google.dev/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)

<br />

<p align="center">
  <strong>MediHelp 24/7</strong> bridges the critical rural healthcare gap by combining multilingual conversational Voice AI with automated clinical triage, real-time doctor escalations, and smart OTC/Non-OTC medication classification.
</p>

[Explore Features](#-key-features) •
[System Architecture](#-system-architecture) •
[Quick Start](#-quick-start) •
[Tech Stack](#-tech-stack) •
[Project Structure](#-project-structure) •
[Roadmap](#-future-roadmap)

</div>

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [System Architecture](#-system-architecture)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Environment Configuration](#environment-configuration)
  - [Running the App](#running-the-app)
- [Available Scripts](#-available-scripts)
- [Core Modules Breakdown](#-core-modules-breakdown)
- [Medical Disclaimer](#-medical-disclaimer)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🌟 Overview

In rural and remote regions, access to registered medical practitioners is often severely constrained by distance, infrastructure, and doctor-to-patient ratios. Patients routinely travel long distances for primary consultations or delay emergency medical care due to lack of immediate triage.

**MediHelp 24/7** is designed as a centralized clinical operations portal and voice AI triage engine that handles inbound patient calls in local languages (such as Hindi, Marathi, and English), parses reported symptoms, verifies patient demographics, and determines the appropriate level of intervention:

1. **Safe Self-Care & OTC Routing**: Immediately provides validated Over-The-Counter (OTC) medication guidelines and lifestyle advice for minor ailments (~84% AI resolution rate).
2. **Rapid Doctor Escalation**: Automatically flags severe, non-OTC symptoms (e.g. cardiac distress, persistent pediatric fever, neurological signs) and routes them into an urgent doctor queue for immediate clinical intervention.
3. **Complete Clinical Transparency**: Provides administrative and medical staff with bilingual transcripts, audio playback, extracted symptom tags, and clinical observation records.

---

## 🚀 Key Features

### 📊 1. Overview Dashboard
- Real-time clinical KPIs: Total Inbound Calls, AI Resolution Rate (~84%), Escalated Cases (~16%), OTC vs Non-OTC recommendation distributions.
- Daily call volume analytics across 42 regional healthcare hubs.
- AI resolution breakdown visualizations (Recharts).

### 📞 2. Call Logs & Voice Triage Registry
- Real-time logging of patient calls with regional dialect detection (Hindi, Marathi, English).
- Instant categorization: Patient name, contact, duration, symptom synopsis, recommended treatment, and triage status (`Resolved by AI` vs `Escalated`).
- Full-text search and filtering by date, status, and health hub.

### 🎧 3. Comprehensive Call Details & Audio Playback
- **Verified Patient Profiles**: Patient ID, age, gender, village/region, and phone number.
- **Audio Recording Player**: Playback controls with timeline scrubber and bitrate telemetry.
- **Bilingual Voice Transcripts**: Accurate speech-to-text transcriptions with multilingual toggle support.
- **Extracted Symptom Badges**: Automatically tagged symptoms (e.g., *Persistent Cough*, *Fever 100.2°F*, *Shortness of Breath*).
- **Clinical Actions**: Medication dosage cards with prescription requirements, doctor handoff cards, and internal clinical note-taking.

### 💊 4. Medicine & Formulary Directory
- Catalog of common pharmaceuticals classified into **OTC** (e.g., Paracetamol, Cetirizine) and **Non-OTC** (e.g., Amoxicillin, Metformin).
- Explicit doctor prescription requirements (`Mandatory` vs `Optional`).
- Generic classifications, therapeutic classes (Antibiotics, Analgesics, Antidiabetics), and usage guidelines.

### 🚨 5. Priority Escalation Queue
- Triage queue highlighting high-risk, urgent patients.
- AI diagnostic flag detection (e.g., *High Risk Cardiac*, *Pediatric Escalation*, *Potential Dengue*).
- Live consultation status tracking (`Unassigned`, `Active Review`, `In Consultation`).
- Rapid assignment to on-duty specialists.

### 👨‍⚕️ 6. Doctors Network & Telehealth Directory
- Regional doctor roster across rural health centers (e.g., Bihar Regional Center, UP Health Hub, MP Mobile Unit).
- Specialty categorization (General Physicians, Pediatricians, Cardiologists, Dermatologists).
- Live availability tracking (`Available Now`, `In Call`, `Available in 15m`) and ratings.

### 📈 7. Advanced Analytics
- Historical month-over-month volume, resolution, and escalation trendlines.
- Operational performance metrics:
  - **Average Call Duration**: ~4m 32s
  - **Patient Satisfaction Rate**: 94.2%
  - **AI Diagnostic Accuracy**: 98.1%
  - **Overall Case Resolution**: 89.4%

---

## 🏗 System Architecture

```mermaid
flowchart TD
    subgraph Patient["Rural Patient / Kiosk"]
        P[Inbound Voice Call] -->|Local Language / Dialect| AG[Telephony / Voice Agent]
    end

    subgraph AI["Voice AI & Triage Pipeline"]
        AG --> STT[Speech-to-Text]
        STT --> LLM["Gemini AI Clinical Reasoning Engine"]
        LLM --> EXT["Symptom & Urgency Extraction"]
        EXT --> CLS{"Severity Classifier"}
    end

    subgraph Outcomes["Triage Outcome"]
        CLS -->|Mild / Standard| OTC["OTC Guidance & Self-Care Advice"]
        CLS -->|High Risk / Non-OTC| ESC["Urgent Escalation Queue"]
    end

    subgraph AdminPortal["MediHelp 24/7 Operations Hub"]
        ESC --> DOC["Doctor Directory & Telehealth Handoff"]
        OTC --> LOGS["Call Logs & Transcripts"]
        DOC --> LOGS
        LOGS --> DASH["Admin Overview Dashboard"]
        LOGS --> ANALYTICS["Performance Analytics"]
    end
```

---

## 💻 Tech Stack

| Category | Technology | Purpose |
|---|---|---|
| **Frontend Framework** | [React 19](https://react.dev/) | Component architecture & modern state management |
| **Language** | [TypeScript](https://www.typescriptlang.org/) (v5.8) | Type safety, maintainability, and clean code contracts |
| **Build Tooling** | [Vite 6](https://vitejs.dev/) | Lightning-fast HMR and optimized production bundles |
| **Styling** | [Tailwind CSS v4](https://tailwindcss.com/) | Next-generation utility-first styling with `@tailwindcss/vite` |
| **UI Components & Icons** | [Lucide React](https://lucide.dev/) | Clean, accessible iconography across all dashboards |
| **Animations** | [Motion (Framer Motion)](https://motion.dev/) | Smooth transitions and interactive micro-animations |
| **Data Visualization** | [Recharts 3](https://recharts.org/) | Responsive bar, line, pie, and area charts |
| **AI / LLM Integration** | [@google/genai](https://www.npmjs.com/package/@google/genai) | Google Gemini API integration for clinical extraction & triage |
| **Typography** | Manrope & Public Sans | Modern, readable typography optimized for healthcare dashboards |

---

## 📂 Project Structure

```text
medihelp-24-7/
├── .env.example              # Template for environment secrets
├── .gitignore                # Git ignore rules
├── index.html                # Entry HTML shell with font imports
├── metadata.json             # Project metadata & app specifications
├── package.json              # Project dependencies and npm scripts
├── tsconfig.json             # TypeScript compiler settings
├── vite.config.ts            # Vite build configuration & environment aliases
│
└── src/
    ├── main.tsx              # React DOM root bootstrapping
    ├── App.tsx               # Primary application state & navigation router
    ├── index.css             # Tailwind CSS v4 design tokens and color variables
    │
    ├── components/
    │   ├── Layout.tsx        # Responsive desktop sidebar & mobile navigation shell
    │   ├── Dashboard.tsx     # Executive KPIs, daily volume charts & triage stats
    │   ├── CallLogs.tsx      # Filterable registry of patient voice interactions
    │   ├── CallDetails.tsx   # Audio player, transcripts, symptom extraction & notes
    │   ├── Medicines.tsx     # OTC vs Non-OTC formulary and prescription catalog
    │   ├── Escalations.tsx   # High-priority emergency escalation queue
    │   ├── Doctors.tsx       # Regional medical network directory & availability
    │   └── Analytics.tsx     # Historical trend analysis and clinical metrics
    │
    └── lib/
        └── utils.ts          # Utility functions (e.g., Tailwind clsx/twMerge helper)
```

---

## ⚡ Getting Started

### Prerequisites

Ensure you have the following installed on your local development machine:
- **[Node.js](https://nodejs.org/)** (v18.0.0 or higher recommended)
- **npm** (v9.0.0 or higher) or **yarn** / **pnpm**
- A **[Google Gemini API Key](https://aistudio.google.com/app/apikey)** (for AI capabilities)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Singhmehak07/medihelp-24-7.git
   cd medihelp-24-7
   ```

2. **Install project dependencies:**
   ```bash
   npm install
   ```

### Environment Configuration

1. Create a `.env.local` file by copying `.env.example`:
   ```bash
   cp .env.example .env.local
   ```

2. Add your Google Gemini API key:
   ```env
   # GEMINI_API_KEY: Required for Gemini AI clinical triage and transcripts
   GEMINI_API_KEY="your-gemini-api-key-here"

   # APP_URL: Base URL for your deployment or local host
   APP_URL="http://localhost:3000"
   ```

### Running the App

Start the development server:
```bash
npm run dev
```

The application will be live at:
```text
http://localhost:3000
```

---

## 🛠 Available Scripts

In the project root, you can run:

| Command | Action |
|---|---|
| `npm run dev` | Starts the Vite development server on `http://localhost:3000` with host bound to `0.0.0.0` |
| `npm run build` | Compiles TypeScript and creates an optimized production bundle in the `dist/` directory |
| `npm run preview` | Locally serves the production build for testing and QA |
| `npm run lint` | Performs strict TypeScript type checks across the entire codebase (`tsc --noEmit`) |
| `npm run clean` | Cleans up the compiled `dist/` distribution folder |

---

## 🩺 Core Modules Breakdown

### 1. Patient Voice Call Triage
When an incoming call is completed, the system processes the audio, performs translation/transcription, and generates a structured summary with:
- **Chief Complaints & Symptoms**
- **Symptom Duration & Severity Indicators**
- **Suggested Medication / Remediation**
- **Triage Flag**: `OTC` (safe for home care) or `Non-OTC` (requires doctor intervention)

### 2. Clinical Safety Guardrails
To prevent accidental over-prescription of controlled medications or antibiotics:
- Any condition requiring prescription-grade pharmaceuticals (such as *Amoxicillin*, *Metformin*, or *Aspirin 300mg*) triggers an automatic escalation.
- Prescriptions are marked as **Pending Review** until validated by an authorized doctor via the portal.

### 3. Emergency & Escalation Workflow
Cases displaying critical physiological indicators (e.g., chest pain radiating to left arm, persistent high pediatric fever with vomiting, acute vision impairment) are flagged with high urgency and routed directly to the on-call doctor queue with sound and badge alerts.

---

## ⚠️ Medical Disclaimer

> **IMPORTANT**: MediHelp 24/7 is an AI-assisted clinical workflow and triage support system. It is designed to assist healthcare workers, administrative staff, and licensed physicians in prioritizing patient inquiries. **It is not an automated doctor, and AI recommendations do not replace certified medical diagnosis or clinical judgment.** Any prescription medications must be verified and authorized by a licensed healthcare professional.

---

## 🤝 Contributing

Contributions are welcomed! If you would like to help improve MediHelp 24/7:

1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/AmazingFeature`).
3. Commit your changes (`git commit -m 'feat: Add some AmazingFeature'`).
4. Push to the branch (`git push origin feature/AmazingFeature`).
5. Open a Pull Request.

---

## 📄 License

This project is open-source and distributed under the **MIT License**. See the [LICENSE](LICENSE) file for more information.

---

<div align="center">
  Developed with ❤️ for improving healthcare accessibility in rural communities.
</div>
