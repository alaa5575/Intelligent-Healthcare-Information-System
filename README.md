# iHIS — Intelligent Health Information System

## Integrated Healthcare Information System with Clinical AI

iHIS is a modular healthcare information system designed to integrate core hospital workflows, electronic medical records, clinical services, and AI-assisted clinical decision-support capabilities within a unified platform.

The project combines traditional Hospital Information System (HIS) functionality with an extensible Clinical AI architecture.

---

## Current Version

**Milestone 6 — Clinical AI Integration and Final Submission**

Current application milestone:

`336b198`

This version includes the core healthcare platform, Patient 360 / EMR foundation, and three integrated Clinical AI models.

---

# Project Objectives

iHIS aims to provide a scalable foundation for an AI-ready healthcare information system capable of supporting:

- Patient management
- Doctor management
- Appointment scheduling
- Clinical workflows
- Laboratory services
- Radiology services
- Pharmacy services
- Electronic Medical Record (EMR)
- Patient Problem List
- Patient 360 clinical profile
- Clinical AI integration
- AI-assisted clinical decision support
- Future intelligent healthcare workflows

The architecture is designed to allow additional healthcare modules and AI models to be integrated progressively.

---

# Technology Stack

## Backend

- Python
- Flask
- SQLAlchemy
- Flask-SQLAlchemy
- Flask-Login
- Flask-Migrate
- Alembic

## Frontend

- HTML5
- CSS3
- Bootstrap 5
- Bootstrap Icons
- JavaScript
- Chart.js
- Jinja2

## Database

Development:

- SQLite

The modular SQLAlchemy architecture allows future migration to production-grade relational database systems such as PostgreSQL.

## Artificial Intelligence

The current Clinical AI layer uses:

- TensorFlow / Keras
- PyTorch
- Torchvision
- Ultralytics YOLO
- EfficientNet-B0
- U-Net

---

# Current System Modules

## Authentication & User Management

The system includes authentication and role-aware user management.

Current functionality includes:

- Login
- User authentication
- Session management
- User roles
- Protected application routes

---

## Patient Management

Patient functionality includes:

- Patient registration
- Patient records
- Patient editing
- Patient profile
- Medical Record Number (MRN)
- Patient clinical information
- Patient 360 foundation

---

## Doctor Management

The Doctors module provides:

- Doctor registration
- Doctor records
- Clinical staff management
- Integration with appointment workflows

---

## Appointment Management

The appointment system supports:

- Appointment creation
- Appointment editing
- Appointment cancellation
- Appointment status tracking
- Calendar view
- Today's schedule
- Patient and doctor linkage

---

# Clinical Services

## Laboratory

The Laboratory module provides the foundation for laboratory workflows including:

- Laboratory dashboard
- Laboratory test catalog
- Laboratory orders
- Result workflows
- Patient-linked laboratory information

---

## Radiology

The Radiology module provides the foundation for:

- Radiology orders
- Radiology tests
- Radiology reports
- Patient-linked radiology workflows

Radiology also provides an integration point for imaging AI systems.

---

## Pharmacy

The Pharmacy module provides the foundation for medication and pharmacy-related workflows within the healthcare platform.

---

# Electronic Medical Record

The system contains an EMR foundation designed to progressively create a longitudinal patient record.

Current clinical information architecture includes:

- Patient profile
- Clinical history foundation
- Problem List
- Laboratory information
- Radiology information
- Appointments
- Patient-linked healthcare records

This architecture is intended to support future Patient 360 and AI-assisted clinical workflows.

---

# Problem List

The Problem List module provides structured patient clinical problem documentation.

It forms an important component of the AI-ready Patient 360 architecture.

Relevant implementation includes:

```text
models/problem.py
routes/problems.py
templates/create_problem.html
```

Database schema changes are managed through Flask-Migrate / Alembic migrations.

---

# Clinical AI Command Center

iHIS contains a centralized **Clinical AI Command Center**.

The command center acts as the entry point for AI-assisted clinical applications integrated into the platform.

Current AI modules:

| AI Module | Clinical Area | AI Task | Architecture | Status |
|---|---|---|---|---|
| Dental AI | Dentistry | Image Segmentation | U-Net | Operational |
| Fracture AI | Radiology / Orthopedics | X-Ray Object Detection | YOLO | Operational |
| Skin AI | Dermatology | Binary Image Classification | EfficientNet-B0 | Operational |

The AI architecture is modular so that additional models can be integrated later.

---

# Dental AI

## Clinical Area

Dentistry

## Task

Dental image segmentation

## Architecture

U-Net

## Framework

TensorFlow / Keras

## Model

```text
services/ai/dental/model/dental_ai_v2.keras
```

## Main Components

```text
routes/dental_ai.py
services/ai/dental/inference.py
templates/dental_ai.html
```

The module accepts dental images and performs AI-assisted segmentation.

The output is intended for experimental clinical decision-support workflows and requires professional clinical interpretation.

---

# Fracture AI

## Clinical Area

Radiology / Orthopedics

## Task

X-ray object detection

## Architecture

YOLO

## Framework

Ultralytics / PyTorch

## Model

```text
services/ai/fracture/model/best.pt
```

## Main Components

```text
routes/fracture_ai.py
services/ai/fracture/inference.py
templates/fracture_ai.html
```

The current model contains the following trained classes:

```text
fractured
hand
hardware
hip
leg
shoulder
```

The module provides AI-assisted object detection for musculoskeletal X-ray workflows.

Detected classes must not be interpreted as an autonomous clinical diagnosis.

---

# Skin AI

## Clinical Area

Dermatology

## Task

Melanoma vs Nevus classification

## Architecture

EfficientNet-B0

## Framework

PyTorch / Torchvision

## Model

```text
services/ai/skin/model/efficientnet_b0_ham10000_binary.pth
```

## Main Components

```text
routes/skin_ai.py
services/ai/skin/inference.py
templates/skin_ai.html
```

The model performs binary dermoscopic image classification:

```text
0 → Nevus
1 → Melanoma
```

The interface displays the predicted class and model probabilities.

The output is intended for research and clinical decision support only.

---

# AI Registry

The Clinical AI modules are centrally registered through:

```text
services/ai/registry.py
```

The registry provides metadata about each AI module including:

- Model name
- Specialty
- AI task
- Task type
- Architecture
- Framework
- Model version
- Operational status
- Application route
- Clinical role

This design allows future AI modules to be added without tightly coupling them to the dashboard.

---

# Project Structure

A simplified representation of the current project structure:

```text
ihis_project/
│
├── app.py
├── config.py
├── extensions.py
├── requirements.txt
├── seed.py
├── reset_admin.py
├── README.md
│
├── auth/
├── dashboard/
├── database/
├── migrations/
├── models/
├── reports/
├── routes/
├── services/
├── static/
├── templates/
├── tests/
├── uploads/
└── instance/
```

Clinical AI structure:

```text
services/
└── ai/
    │
    ├── registry.py
    │
    ├── dental/
    │   ├── inference.py
    │   └── model/
    │       └── dental_ai_v2.keras
    │
    ├── fracture/
    │   ├── inference.py
    │   └── model/
    │       └── best.pt
    │
    └── skin/
        ├── inference.py
        └── model/
            └── efficientnet_b0_ham10000_binary.pth
```

---

# Installation Guide

## 1. Clone the Repository

Clone the project from GitHub:

```bash
git clone git@github.com:khalawy/IHIS.git
```

Then enter the project directory:

```bash
cd IHIS
```

If HTTPS is preferred:

```bash
git clone https://github.com/khalawy/IHIS.git
cd IHIS
```

---

# 2. Create a Virtual Environment

## macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

## Windows

```bash
python -m venv venv
venv\Scripts\activate
```

---

# 3. Install Dependencies

Upgrade pip first:

```bash
python -m pip install --upgrade pip
```

Then install project dependencies:

```bash
pip install -r requirements.txt
```

The installation includes both the Flask application dependencies and the libraries required by the Clinical AI modules.

Because TensorFlow and PyTorch compatibility can depend on the operating system, Python version, CPU/GPU architecture, and hardware acceleration environment, team members may need environment-specific installation adjustments if a package installation fails.

---

# 4. Database Setup

The local SQLite database is intentionally excluded from Git.

Each developer should create their own local database from the project's database schema and migrations.

Do not share or commit local `.db` files.

First ensure the virtual environment is active.

Run:

```bash
flask --app app db upgrade
```

This applies the available database migrations.

If the project requires initial seeded data, run:

```bash
python seed.py
```

The exact seed behavior depends on the current project seed configuration.

---

# 5. Run the Application

Start the Flask development server:

```bash
flask --app app run --debug --port 5001
```

Open:

```text
http://127.0.0.1:5001
```

The application should now be available locally.

---

# Development Workflow for Team Members

Before starting new work:

```bash
git checkout main
git pull origin main
```

For a new feature, creating a separate branch is recommended:

```bash
git checkout -b feature/feature-name
```

Example:

```bash
git checkout -b feature/pharmacy-enhancement
```

After making changes:

```bash
git add .
git commit -m "Describe the implemented change"
```

Push the feature branch:

```bash
git push origin feature/feature-name
```

This workflow helps prevent multiple team members from directly modifying the same files on `main`.

---

# Important Git Rules

Do not commit local development artifacts such as:

```text
venv/
__pycache__/
*.pyc
instance/
.env
database/*.db
.DS_Store
```

These files are excluded through `.gitignore`.

Before every commit, developers should run:

```bash
git status
```

and verify the files that will be included.

---

# AI Model Files

The current repository includes the model files required by the three operational Clinical AI modules:

```text
services/ai/dental/model/dental_ai_v2.keras

services/ai/fracture/model/best.pt

services/ai/skin/model/efficientnet_b0_ham10000_binary.pth
```

These model files are required for local AI inference.

Do not rename or move them without updating the corresponding inference code.

---

# Clinical AI Safety

The AI modules integrated into iHIS are intended for:

- Research
- Education
- Prototype development
- Clinical decision-support experimentation

They are **not autonomous diagnostic systems**.

AI predictions must be interpreted in the appropriate clinical context and reviewed by qualified healthcare professionals.

The current implementation should not be used as a substitute for professional medical diagnosis, treatment decisions, or validated medical-device software.

---

# AI Governance Direction

The architecture is designed to support future healthcare AI governance capabilities including:

- Human-in-the-loop review
- Model version tracking
- AI inference audit trails
- Patient-linked AI analysis
- Confidence tracking
- Clinician validation
- Model registry
- Explainability
- Monitoring
- Bias evaluation
- Data privacy controls

---

# Future Development

Planned future improvements may include:

- Patient-linked AI Analysis records
- AI results integrated into Patient 360
- Clinician review and approval workflows
- AI inference audit trail
- Model monitoring
- Explainable AI
- Advanced EMR
- Enhanced pharmacy workflows
- Advanced radiology workflows
- Nursing workflows
- Reporting and analytics
- Notification system
- Role-based dashboards
- PostgreSQL migration
- Containerized deployment
- Cloud deployment
- API layer
- Additional Clinical AI models
- AI agents and workflow orchestration
- RAG-based clinical knowledge systems

---

# Current Submission Status

The current application milestone represents the final working version prepared for the present project submission.

Application checkpoint:

```text
Milestone 6
Clinical AI Integration and Final Submission
Commit: 336b198
```

Future improvements should be developed after this checkpoint so that the submitted version remains reproducible.

---

# Disclaimer

iHIS is currently an academic, research, and prototype healthcare software project.

The system and its AI components have not been presented as validated medical devices and should not be used independently for real-world diagnosis or treatment decisions.


---

# Quick Start

## تشغيل المشروع بسرعة على جهاز تم إعداده مسبقًا

إذا كان المشروع موجودًا بالفعل وتم تثبيت جميع المتطلبات سابقًا:

### macOS / Linux

افتح Terminal داخل مجلد المشروع ثم نفّذ:

```bash
source venv/bin/activate
flask --app app run --debug --port 5001
```

### Windows

```bash
venv\Scripts\activate
flask --app app run --debug --port 5001
```

ثم افتح المتصفح على:

```text
http://127.0.0.1:5001
```

---

## First-Time Setup

إذا كنت تشغّل المشروع لأول مرة بعد تنزيله من GitHub:

```bash
git clone git@github.com:khalawy/IHIS.git
cd IHIS
```

### macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
flask --app app db upgrade
python seed.py
flask --app app run --debug --port 5001
```

### Windows

```bash
python -m venv venv
venv\Scripts\activate
python -m pip install --upgrade pip
pip install -r requirements.txt
flask --app app db upgrade
python seed.py
flask --app app run --debug --port 5001
```

ثم افتح:

```text
http://127.0.0.1:5001
```

---

## Daily Start — Mohamed's Mac

للتشغيل اليومي على جهاز التطوير الحالي:

```bash
cd ihis_project
source venv/bin/activate
flask --app app run --debug --port 5001
```

ثم:

```text
http://127.0.0.1:5001
```

إذا كان الـTerminal يظهر بالفعل:

```text
(venv)
```

فلا تحتاج إلى تفعيل البيئة مرة أخرى، وشغّل مباشرة:

```bash
flask --app app run --debug --port 5001
```

---

## Stop the Server

لإيقاف Flask Server:

```text
Ctrl + C
```

---

## Important

The local SQLite database is not stored in GitHub.

For a new installation, initialize the database using:

```bash
flask --app app db upgrade
python seed.py
```

Do not commit local database files, virtual environments, `.env` files, or `__pycache__` directories to GitHub.