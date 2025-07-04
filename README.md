# Dependency-Aware Assessment Generator

An experimental **agentic AI system** designed to generate targeted assessments based on a learner’s desired concept. By leveraging a **concept graph**, the system first identifies prerequisite knowledge and then uses AI to generate diagnostic questions — ensuring foundational understanding before progression.

This project is under active development and aims to integrate **LangGraph-based agentic reasoning** with the **MERN stack** for scalable educational applications.

---

## Status

> This project is currently in early development. Features and APIs are subject to frequent changes.
> Both **frontend** and **backend** are independently functional.  
> **Integration between frontend and backend is in progress.** Current workflows are being tested in isolation.

---

## Project Overview

### Goal

To assist learners by:
- Automatically determining the prerequisites for any given concept using a structured knowledge graph.
- Using an agentic AI workflow to generate **diagnostic assessments** tailored to those prerequisites.
- Encouraging mastery learning by identifying gaps before a learner advances.

---

## How to Run the Project

### 1. Clone the Repository

### 2. Add Your Hugging Face Token

* Create a `.env` file in the **`backend/`** directory.
* Add the following line to the `.env` file:

```env
MONGO_URI = <your_mongo_atlas_uri>(Create an atlas account, create a cluster and add its uri string here)
OPENROUTER_API_KEY= your_openrouter_api_key
JWT_SECRET=your_backend_secret_key(Please generate it from web)
EMAIL_USER=your_gmail_id
EMAIL_PASS=your_gmail_app_password
```

> Make sure the `.env` file is located inside the `backend/` folder.
> Note the the password being used in EMAIL_PASS is not your gmail password but is the app password created for this purpose after enabling 2 factor authentication.

* Create another `.env` file in the **`frontend/`** directory.
* Add the following line to the `.env` file:
VITE_API_URL = link_to_express_framework

> Note that if you are running it locally, the link will be http://localhost:5000
> Note that the accepted localhost frontend runs on port 5173. Change it in index.ts to your desired port.

---

### 3. Start the Application

#### In Terminal 1 (Frontend)

```bash
cd frontend
npm install
npm run build
npm run dev
```

This will launch the frontend on local host.

#### In Terminal 2 (Backend)

```bash
cd backend
npm install
npm run build
npm run start
```

---
## Deployment
Modify the backend/package.json to change scripts build from the windows specific copy to a general cp function instead. 
Deployment is on Render and Netlify.

## What Happens Now

In the current development state:

- The frontend allows concept input and renders UI components.

- The backend generates diagnostic questions, scores responses, stores questions and answers in MongoDB, and identifies weak prerequisite topics.

> The connection between frontend input and backend services is wired together for specific features, but both parts function correctly when tested separately for all features.

---
## Contributions

- **Nikita S Raj Kapini** : Building the backend for question generation, data storage with MongoDB, and response analysis; Integration of frontend with backend

- **Shreyas Mene** : Developing the frontend user interface using Vite + React

- **Yeddalu Pushkala** : Developing and integrating a chatbot (help assistant) with the frontend interface

- **Manda Rani** : Designing UI components for registration and login pages  

- **Nakshtra Bandary** : Preparing project documentation, including UML diagrams, SRS, and system design documentation ; Integrating the UI of login and registration with the dashboard and developing backend functionality to ensure seamless authentication and user management.


---

## Documentation

* UML diagrams for the system architecture and flow are available in the `Documentation/` folder.

---

## Tech Stack

* **Frontend**: React (TypeScript)
* **Backend**: Node.js + Express
* **Database**: MongoDB
* **AI/LLM**: Hugging Face and Open Router Model (via API)
* **Agent Framework**: LangGraph (planned)
