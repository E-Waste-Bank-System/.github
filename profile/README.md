# ♻️ E-Waste Hub

A smart, full-stack platform for e-waste collection, classification, and management. Combines AI-powered image classification, price estimation, a modern admin dashboard, and a user-friendly mobile app.

---

## 🗂️ Monorepo Structure

```
/ebs-system
 ├── ebs-app/                   # Mobile Application
 ├── ebs-web/                   # Admin Web Dashboard (Next.js 15 + Tailwind + ShadcnUI)
 ├── ebs-api/                   # Express.js Backend API (TypeScript)
 ├── ebs-ai/                    # Computer Vision Model (YOLOv11 - PyTorch)
 └── README.md                  # Main documentation file
```

---

## 🚀 Quickstart

1. **Clone the repository**
   ```bash
   git clone https://github.com/E-Waste-Bank-System/<repo>
   cd <repo>
   ```

2. **Install dependencies for each service**
   ```bash
   cd ebs-api && npm install
   cd ../ebs-web && npm install
   cd ../ebs-ai/src && pip install -r requirements.txt
   ```

3. **Configure environment variables**
   - See `.env.example` in each service for required variables.

4. **Run services locally**
   - **API:** `cd ebs-api && npm run dev`
   - **Web:** `cd ../ebs-web && npm run dev`
   - **Mobile:** Open `ebs-app` in Android Studio and run the app
   - **Model:** `cd ../ebs-ai/src && python app.py`

---

## 📱 Mobile App
- **Kotlin + Jetpack Compose:** Native Android application for e-waste collection
- **Features:** 
  - Camera integration for e-waste scanning
  - Real-time price estimation
  - Collection scheduling
  - User profile & history
  - Push notifications

## 🖥️ Web Dashboard
- **Next.js 15 + Tailwind + ShadcnUI:** Modern admin dashboard for e-waste management
- **Features:**
  - Real-time analytics and reporting
  - E-waste inventory management
  - User management and permissions
  - Collection scheduling oversight
  - Price management and history

## 🧠 AI 
- **E-Waste Detection Model:** YOLOv11-based image classification for e-waste type detection. Exposes a Flask API for inference.
- **Regression model:** Price estimation for e-waste items.
- **Gemini:** AI-powered assistant for e-waste information and guidance

---

## 🔗 Integration

- The **admin dashboard** and **mobile app** consume endpoints from the **backend API** for all management features.
- **Authentication** is JWT-based (via Supabase Auth).
- The **AI model** is called by the API for image classification and price estimation.

---

<!-- ## 📸 Dashboard Screenshots

_Add screenshots of the dashboard and main features here_

--- -->

## 👥 Contributors

| Name                      | Role                                               |
|---------------------------|----------------------------------------------------|
| Aldo Nitehe Lase          | Mobile App & Regression Model Developer            |
| Axel David                | Backend Engineer & CV Model Developer              |
| Farhan Rizki Fauzi        | UI/UX Designer & Deployment                        |

---

## 📚 References

- [Jetpack Compose](https://developer.android.com/develop/ui/compose/documentation)
- [YOLOv11 Docs](https://docs.ultralytics.com/)
- [Supabase Docs](https://supabase.com/docs)
- [Next.js 15](https://nextjs.org/)
- [Google Cloud Run](https://cloud.google.com/run)
- [Tailwind CSS v4](https://tailwindcss.com/)
- [ShadcnUI](https://ui.shadcn.com/)

---

**For detailed setup and usage, see the README in each subdirectory.**
