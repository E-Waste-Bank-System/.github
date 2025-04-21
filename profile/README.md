# 📦 E-Waste Bank System

A smart e-waste collection and management system powered by AI-based classification (YOLOv11) and regression-based price estimation. Users submit electronic waste (e-waste) via a mobile app, and administrators manage submissions, pricing, and content through a modern admin dashboard.

## 🏐 Monorepo Structure

```
/bank-sampah-elektronik
 ├── ebs-api/ # Express.js Backend API (TypeScript)
 ├── ebs-web/ # Admin Web Dashboard (Next.js 15 + Tailwind + ShadcnUI)
 ├── ebs-app/ # Android Mobile App (Kotlin)
 ├── object-classification-model/ # Computer Vision Model (YOLOv11 - PyTorch)
 ├── regression-model/ # Price Estimation Model (Regression - PyTorch)
 └── README.md # Main documentation file
```

## 🌐 Live Services Overview

| Service               | Tech Stack                      | Deployment Platform     |
|----------------------|----------------------------------|--------------------------|
| REST API             | TypeScript + Express             | Google Cloud Run         |
| AI Inference         | Python (YOLOv11, Regression)     | Google Cloud Run         |
| Admin Dashboard      | Next.js 15 + Tailwind + ShadcnUI | Vercel / Netlify         |
| Mobile App           | Kotlin (Native Android)          | APK Build                |
| Auth & Database      | Supabase (PostgreSQL + Auth)     | Supabase Cloud           |
| File & Model Storage | Google Cloud Storage (GCS)       | GCS Buckets              |

---

## 🚀 Quickstart Development Guide

### 1. Clone Repository

```bash
git clone https://github.com/E-Waste-Bank-System/<repo>
cd <repo>
```

---

### 2. Install Depedencies

#### Backend API
cd ebs-api && npm install

#### Admin Web
cd ../ebs-web && npm install

#### Regression Model
cd ../regression-model && pip install -r requirements.txt

### Classification Model
cd ../object-classification-model && pip install -r requirements.txt

---

## 🔁 System Flow (Diagram)
```
[Mobile App]
     ↓ Upload image
[ebs-api] (Express)
     → [object-classification-model] (YOLOv11)
     → [regression-model] (PyTorch)
     ↓ Receive prediction + price
     → Store in Supabase (DB)
     → Upload image to GCS
```

---

## 🧠 Tech Stack

🔹 Backend API

    Express.js (TypeScript)

    Supabase SDK (Auth & DB)

    Multer (file upload)

    Google Cloud Storage

    Python shell (child_process)

🔹 CV Classification

    YOLOv11 model (.pt)

    Ultralytics

    Flask (API serving)

    Google Cloud Run

🔹 Price Regression

    PyTorch Regression Model (.pt)

    Flask or FastAPI

    Trained using e-waste data

🔹 Admin Web Dashboard

    Next.js 15 (App Router)

    Tailwind CSS v4

    ShadcnUI components

    Supabase client (for session management)

🔹 Mobile App

    Kotlin Android App

    Upload images, choose pickup date

    View classified result and estimated price

    Authentication using Supabase





                                
