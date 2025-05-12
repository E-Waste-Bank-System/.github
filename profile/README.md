# ♻️ E-Waste Bank System Monorepo

A smart, full-stack platform for e-waste collection, classification, and management. Combines AI-powered image classification, price estimation, a modern admin dashboard, and a user-friendly mobile app.

---

## 🗂️ Monorepo Structure

```
/ebs-system
 ├── ebs-api/                   # Express.js Backend API (TypeScript)
 ├── ebs-web/                   # Admin Web Dashboard (Next.js 15 + Tailwind + ShadcnUI)
 ├── object-classification-model/# Computer Vision Model (YOLOv11 - PyTorch)
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
   cd ../object-classification-model/src && pip install -r requirements.txt
   ```

3. **Configure environment variables**
   - See `.env.example` in each service for required variables.

4. **Run services locally**
   - **API:** `cd ebs-api && npm run dev`
   - **Web:** `cd ../ebs-web && npm run dev`
   - **Model:** `cd ../object-classification-model/src && python app.py`

---

## ✨ Modern Dashboard UI/UX

- **Stat cards** for quick metrics
- **Monthly detections chart** (Bar chart)
- **Recent articles and detections**
- **Personalized topbar** with greeting, date, user avatar, and theme switch
- **Notification bell** (UI only, ready for integration)
- **Responsive, mobile-friendly design**
- **Powered by ebs-api backend**

**Customizing the Dashboard UI:**
- UI components: `ebs-web/components/ui/`
- Topbar: `ebs-web/components/ui/topbar.tsx`
- Stat cards & layout: `ebs-web/app/dashboard/page.tsx`

---

## 🧠 AI & Backend

- **ebs-api:** REST API for authentication, articles, detections, validations, and statistics. Integrates with Supabase (PostgreSQL + Auth) and Google Cloud Storage.
- **object-classification-model:** YOLOv11-based image classification for e-waste type detection. Exposes a Flask API for inference.
- **Regression model:** (if present) Price estimation for e-waste items.

---

## 🔗 Integration

- The **admin dashboard** (`ebs-web`) consumes endpoints from **ebs-api** for all management features.
- **Authentication** is JWT-based (via Supabase Auth).
- **AI model** is called by the API for image classification and price estimation.

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

- [YOLOv11 Docs](https://docs.ultralytics.com/)
- [Supabase Docs](https://supabase.com/docs)
- [Next.js 15](https://nextjs.org/)
- [Google Cloud Run](https://cloud.google.com/run)
- [Tailwind CSS v4](https://tailwindcss.com/)
- [ShadcnUI](https://ui.shadcn.com/)

---

**For detailed setup and usage, see the README in each subdirectory.**
