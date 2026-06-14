# 🛡️ IncidentIQ — Smarter SRE Incident Resolution

IncidentIQ is an advanced, AI-powered Site Reliability Engineering (SRE) platform designed to dramatically reduce Mean Time to Resolution (MTTR). By combining state-of-the-art Large Language Models (LLMs) like **Claude** (via the Anthropic SDK) with an **Organizational Memory Bank** (powered by Vectorize.io's Hindsight), IncidentIQ retains, recalls, and updates organizational knowledge from every past outage, runbook, and postmortem.

Built with ❤️ by **Shravani Dhuri** and **Tanya Garg**.

---

## 🚀 Key Features

*   **🔍 AI-Powered Root Cause Triage:** Instantly analyze production alerts. The built-in SRE Copilot ranks probable root causes by confidence and generates immediate mitigation and diagnostic commands.
*   **🧠 Hindsight Memory Bank:** Seamless integration with Hindsight Memory. Automatically indexes, recalls, and searches past incidents, runbooks, and postmortems in real-time, bringing historical knowledge directly into the active triage channel.
*   **🕸️ Interactive Dependency & Incident Graph:** An interactive, node-based visualization of your system topology, active incidents, and related services, built using **React Flow**.
*   **📑 One-Click Blameless Postmortems:** Instantly generate complete, professional postmortems from active incident timelines, impact details, and root causes using **Claude** (with optional/legacy backend support for **Gemini**).
*   **📚 Context-Aware Runbooks:** Automatically suggests relevant runbooks based on incident similarity, complete with diagnostic commands that SREs can copy and execute.
*   **📊 Reliability Analytics Dashboard:** Deep visibility into system health, including MTTR trends, service uptime reliability percentages, incident severity frequencies, and memory reuse rates.
*   **⌨️ Global Command Palette:** Access search and commands anywhere using the `⌘K` (or `Ctrl+K`) shortcut.

---

## 🛠️ Technology Stack

*   **Framework & Language:** [Next.js 15 (App Router)](https://nextjs.org/) & [TypeScript](https://www.typescriptlang.org/)
*   **Styling & UI:** [Tailwind CSS](https://tailwindcss.com/), [Framer Motion](https://www.framer.com/motion/), [Radix UI](https://www.radix-ui.com/), and [Lucide React](https://lucide.dev/)
*   **Data Visualizations:** [React Flow](https://reactflow.dev/) (Knowledge Graph) & [Recharts](https://recharts.org/) (Analytics)
*   **Global State Management:** [Zustand](https://zustand-demo.pmnd.rs/)
*   **Database & Authentication:** [Firebase Firestore & Auth](https://firebase.google.com/)
*   **AI Models & Client Integrations:**
    *   **Anthropic SDK:** Claude 3.5 Sonnet / 4.5 for active streaming incident copilot reasoning and postmortem generation.
    *   **Google Generative AI (Optional):** Pre-built SDK integrations for Gemini 2.5 Pro (`lib/gemini.ts`) available for multi-LLM setup.
    *   **Vectorize Hindsight Client:** `@vectorize-io/hindsight-client` for organizational memory retention.

---

## 📂 Project Structure

```text
InsidentlQ/
├── app/
│   ├── (dashboard)/            # Dashboard layout and page routes
│   │   ├── analytics/          # MTTR, reliability, and SRE analytics
│   │   ├── dashboard/          # Main dashboard overview
│   │   ├── incidents/          # Incident feeds, new incident form, details
│   │   ├── knowledge-graph/    # React Flow system topology map
│   │   ├── memory/             # Memory Vault database
│   │   └── runbooks/           # Runbooks storage and search
│   ├── api/                    # Serverless API routes (AI & Hindsight memory)
│   ├── globals.css             # Main styling & animations
│   ├── layout.tsx              # Root context and metadata
│   └── page.tsx                # High-fidelity Landing Page
├── components/
│   ├── dashboard/              # AICopilot, IncidentFeed, and MemoryEngine
│   └── layout/                 # Navigation, Command Palette
├── context/                    # AuthContext for Firebase
├── lib/                        # Claude, Gemini, Firebase, Hindsight, and Mock Data utilities
├── store/                      # Zustand Stores (incident and UI state)
├── types/                      # TypeScript definitions
└── package.json                # Dependencies and scripts
```

---

## ⚙️ Environment Configuration

To configure the external API services, create a `.env.local` file in the root directory and define the following variables:

```bash
# Claude AI (Anthropic)
ANTHROPIC_API_KEY=your_claude_api_key

# Google Gemini (Generative AI)
GEMINI_API_KEY=your_gemini_api_key

# Vectorize Hindsight Memory
HINDSIGHT_API_KEY=your_hindsight_api_key
HINDSIGHT_BANK_ID=incidentiq-global-bank

# Firebase Configuration
NEXT_PUBLIC_FIREBASE_API_KEY=your_firebase_api_key
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id
```

---

## 🚀 Getting Started

Follow these steps to run the application locally on your machine:

### 1. Clone & Install Dependencies
```bash
git clone https://github.com/bahuli1203/InsidentlQ.git
cd InsidentlQ
npm install
```

### 2. Run the Development Server
```bash
npm run dev
```
Open [http://localhost:3000](http://localhost:3000) with your browser to see the landing page and start exploring.

### 3. Build for Production
To build the application for production deployment, run:
```bash
npm run build
npm run start
```