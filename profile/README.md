# 📦 E-Waste Bank System

A smart e-waste collection and management system powered by AI-based classification (YOLOv11) and regression-based price estimation. Users submit electronic waste (e-waste) via a mobile app, and administrators manage submissions, pricing, and content through a modern admin dashboard.

## 🏐 Project Structure

```
/bank-sampah-elektronik
├── ebs-api/                                     # REST API (TypeScript + Express)
├── ebs-web/                                     # Admin dashboard (Svelte 5)
├── ebs-app/                                     # Mobile Application (Kotlin)
├── object-classification-models/                # E-waste Classification Models (YOLOv11)
└── README.md               # This file
```

## 🌐 Live Services

| Service | Stack | Deployment |
|---------|-------|------------|
| REST API | Express + TypeScript | Google Cloud Run |
| AI Inference | Python + YOLOv11/PT | Google Cloud Run |
| Admin Web | Sveltekit + Tailwind 4 | Netlify |
| Auth & DB | Supabase (PostgreSQL) | Supabase Cloud |
| File Storage | Google Cloud Storage | GCS Buckets |

## 🧠 Tech Stack

### Backend
- Express.js (TypeScript)
- Supabase (Auth & Database)
- Google Cloud Storage (media & model files)
- Multer (file upload)
- child_process to run Python inference

### AI Models
- YOLOv11 .pt model (for object detection)
- PyTorch regression .pt model (for price estimation)

### Frontend Admin
- Sveltekit (Svelte 5)
- Tailwind CSS v4
- ShadcnUI-svelte (modern UI components
- Supabase client (auth & session)

### Deployment
- Google Cloud Run (API & ML services)
- Supabase (auth/db)
- Google Cloud Storage (uploads, models)
- Docker for containerization

## 📆 Features

### User (via Mobile App)
- Upload e-waste images
- Auto-classify object using YOLOv8
- Estimate price using regression model
- Choose pickup schedule and payment

### Admin Web
- Login & dashboard stats
- View & approve/reject e-waste submissions
- Manage users (block/unblock)
- Create/edit content (tips, news, etc)
- Manage pricing per e-waste category

## 📋 Repository Layout

| Folder | Description |
|--------|-------------|
| backend/ | All backend routes, controllers, and services |
| frontend-admin/ | Svelte 5 admin dashboard with auth, tables, and forms |
| ai-models/ | Python scripts for inference (YOLO & regression) |
| infra/ | Cloud Run deployment setup, Dockerfiles, CI/CD configs |

## 🚀 Getting Started

### 1. Clone Project

```bash
git clone https://github.com/your-org/bank-sampah-elektronik.git
cd bank-sampah-elektronik
```

### 2. Setup Environment Files

Create .env in:
- /backend
- /frontend-admin
- /ai-models

Use the provided .env.example as a reference.

### 3. Install Dependencies

```bash
cd backend && npm install
cd ../frontend-admin && npm install
cd ../ai-models && pip install -r requirements.txt
```

### 4. Run Locally (Dev Mode)

```bash
cd backend && npm run dev
cd ../frontend-admin && npm run dev
```

## 🔄 Service Communication Flow

```
[User Mobile App]
     ↓ upload image
[Backend API] ---(POST)---> [Python: detect.py]
     ↓ result
[Backend API] ---(POST)---> [Python: predict_price.py]
     ↓ estimated price
[Supabase] ← stores transaction metadata
[GCS] ← stores uploaded images + .pt model files
```

## 🚪 Deployment Notes

- Backend & AI run as stateless containers on Google Cloud Run
- Models are downloaded from GCS buckets at runtime if not cached
- All uploads (user images, etc.) are stored in Google Cloud Storage
- Admin frontend can be deployed via Vercel, Cloudflare Pages, or GCP

## 📖 Documentation

- Supabase: https://supabase.com/docs
- YOLO11: https://docs.ultralytics.com
- Svelte 5 : https://svelte.dev/docs/svelte/overview
- Google Cloud Run: https://cloud.google.com/run
- ShadcnUI-vue: https://next.shadcn-svelte.com/

## 👨‍💼 Contributors

| Name | Role |
|------|------|
| Axel David | Classification Model Developer and Backend Engineer |
| Aldo Nitehe Lase | Regression Model Developer and Mobile App Developer |
| Farhan Rizki Fauzi | UI/UX Designer |
                                
