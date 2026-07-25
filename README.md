<a id="readme-top"></a>

<!-- PROJECT SHIELDS -->
<div align="center">
  
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![Top ECSOC 2026](https://img.shields.io/badge/Top_ECSOC_2026-FFD700?style=for-the-badge&logoColor=black)](#)

</div>

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/kRamu81/MedTrack_Application">
    <img src="public/medtrack-logo.svg" alt="MedTrack Logo" width="340">
  </a>

  <p align="center">
    <strong>A Full-Stack Medical Equipment Management & Tracking System</strong>
    <br />
    <a href="https://github.com/kRamu81/MedTrack_Application"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://discord.gg/F7TUpgPzJ">Join Discord</a>
    ·
    <a href="https://github.com/kRamu81/MedTrack_Application/issues">Report Bug</a>
    ·
    <a href="https://github.com/kRamu81/MedTrack_Application/issues">Request Feature</a>
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#core-features">Core Features</a></li>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage & Test Accounts</a></li>
    <li><a href="#ai-assistant-beta">AI Assistant (Beta)</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->
## About The Project

MedTrack is a **Full-Stack Medical Equipment Management Platform** that helps hospitals manage their equipment inventory, maintenance schedules, and equipment orders efficiently. It now also features an AI-powered assistant for equipment Q&A and document drafting.

The system is designed with a microservice-oriented backend and a responsive React frontend, created specifically for the **MedTrack Case Study 06** during the Elite Summer of Code (ECSoc).

### Core Features
The system supports three major roles:
* 🏥 **Hospital**: Manage inventory, schedule maintenance, and order equipment.
* 🔧 **Technician**: View and complete assigned maintenance tasks.
* 🚚 **Supplier**: Fulfill equipment orders and update delivery status.
* 🤖 **AI Assistant**: Chat with a RAG-grounded assistant to ask questions about equipment/maintenance/orders, and draft purchase orders or reports in plain language — with human approval required before anything is submitted.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Built With

* [![React][React.js]][React-url]
* [![Tailwind][Tailwind.css]][Tailwind-url]
* [![Spring][Spring.io]][Spring-url]
* [![Java][Java.com]][Java-url]
* [![LangChain][LangChain.js]][LangChain-url]
* [![LLM API][LLM.api]][LLM-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

* Java 17 or higher
* Node.js (v16+)
* npm (v8+)
* Maven
* `OPENAI_API_KEY` environment variable (for the AI Service)
* Python 3.10+ (for the AI Service microservice)

### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/kRamu81/MedTrack_Application.git
   ```
2. **Start the Backend**
   ```sh
   cd Backend
   mvn spring-boot:run
   ```
   * **API URL**: `http://localhost:8081`
   * **H2 Console**: `http://localhost:8081/h2-console` (JDBC: `jdbc:h2:mem:medtrackdb`, User: `sa`)

3. **Start the Frontend**
   ```sh
   # Open a new terminal in the root directory
   npm install
   npm start
   ```
   * **App URL**: `http://localhost:3000/MedTrack_Application`

4. **Start the AI Service (Separate Python Microservice)**
   ```sh
   cd ai-service
   # Ensure your .env contains OPENAI_API_KEY=your_api_key
   pip install -r requirements.txt
   uvicorn main:app --port 8000
   ```
   * **API URL**: `http://localhost:8000`

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- USAGE EXAMPLES -->
## Usage & Test Accounts

Use the following default accounts to test the different role dashboards:

| Role | Email | Password |
|------|-------|----------|
| Hospital Admin | `hospital@medtrack.com` | `admin123` |
| Technician | `tech@medtrack.com` | `tech123` |
| Supplier | `supplier@medtrack.com` | `supply123` |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- AI ASSISTANT -->
## AI Assistant (Beta)

MedTrack now includes a conversational AI assistant grounded in live platform data (via RAG and pgvector/Elasticsearch kNN) to help orchestrate tasks across all roles.

* **How to access:** Click the 🤖 icon in the bottom right of any role dashboard.
* **Example Prompt:** *"Draft a purchase order for 3 replacement infusion pump batteries at City General."*
* **Important Guardrail:** All AI-drafted actions require explicit human review. A user must click "Approve & Submit" before any change takes effect. The agent NEVER writes directly to the database. All AI interactions are logged to the `ai-events` Kafka topic for auditing.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

Please see our [CONTRIBUTING.md](CONTRIBUTING.md) file for full details on how to get started, assign yourself an issue, and submit a Pull Request.

**Quick Steps:**
1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#readme-top">back to top</a>)</p>



