---
project: airise
description: "AIFR-AI – AI-powered fabric defect detection system for Katty Fashion. CNN/YOLO-based real-time quality inspection on Jetson edge devices, integrated with MinIO/NiFi/Spark infrastructure. EU Horizon Europe – AIRISE Open Call 1."
type: eu-project
po: "@ps.tech"
lead: "@el.tech"
sprint: S1
sprint_start: 2026-03-09
sprint_end: 2026-03-20
depends_on: []
tags: [eu-project, ai, computer-vision, yolo, cnn, textile, defect-detection, jetson, edge-ai, minio, fastapi, nextjs, synthetic-data, grad-cam, shap]
team:
  frontend: alexandru.bejenari@katty-fashion.ro
  backend: razvan.boita@katty-fashion.ro
  tech_lead: el.tech@katty-fashion.ro
  product_owner: ps.tech@katty-fashion.ro
external:
  tutor: Muhammad Ahmed Ullah Khan [DFKI]
  controller: Luis Usatorre [TECNALIA]
budget:
  total: 85714
  eu_funded: 59999.6
  currency: EUR
trl_start: 5
blockers:
  - "Lipsa datelor reale: insuficiente imagini cu defecte textile pentru antrenament robust → prioritizare generare date sintetice"
  - "Comunicare lentă: cicluri de comunicare mai lente decât anticipat → remediat prin cadru kanban săptămânal"
---

# Project Kanban

<!-- Valid statuses: Todo, In Progress, Review, Done -->
<!-- Effort format: Nd (e.g. 1d, 0.5d, 3d) -->

<!-- BLOCAJE ACTIVE (din raportarea Sprint 1):
  ⚠️  Lipsa datelor reale — KF nu a colectat suficiente imagini cu defecte reale.
      Soluție: generare de date sintetice (prioritate ridicată).
  ⚠️  Comunicare lentă — progres întârziat de cicluri de comunicare interne.
-->

| Task | Assignee | Effort | Start | End | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Project scope definition & AIRISE initialisation report review | @ps.tech | 1d | 2026-03-09 | 2026-03-09 | Done |
| Setup repository structure and KF-CPTO kanban integration | @alexandru.bejenari | 1d | 2026-03-09 | 2026-03-09 | Done |
| Define system architecture: edge (Jetson) + cloud (MinIO/NiFi/Spark) | @el.tech | 3d | 2026-03-09 | 2026-03-11 | In Progress |
| Define streaming architecture — Plan B (Async Playback) selectat ca variantă recomandată | @el.tech | 1d | 2026-03-10 | 2026-03-10 | In Progress |
| ⚠️ [BLOCKER] Audit dataset existent — evaluare volum și calitate imagini defecte reale disponibile | @ps.tech | 1d | 2026-03-11 | 2026-03-11 | In Progress |
| ⚠️ [BLOCKER] Strategie generare date sintetice — prioritizare GAN/augmentare pentru suplimentare dataset | @el.tech | 2d | 2026-03-12 | 2026-03-13 | Todo |
| Design data ingestion pipeline: Apache NiFi + MinIO on-premise | @razvan.boita | 2d | 2026-03-11 | 2026-03-12 | Todo |
| Design data preprocessing pipeline: Apache Spark + augmentation strategy | @razvan.boita | 2d | 2026-03-13 | 2026-03-14 | Todo |
| Define defect taxonomy and annotation schema (Damage, Hole, Knot, Line, Oil Stain, Stain, Wrinkle) | @ps.tech | 1d | 2026-03-13 | 2026-03-13 | Todo |
| Define CNN/YOLO model architecture for fabric defect detection | @el.tech | 3d | 2026-03-13 | 2026-03-17 | Todo |
| Integrate model explainability: Grad-CAM + SHAP pentru vizualizare decizii AI | @el.tech | 2d | 2026-03-17 | 2026-03-18 | Todo |
| Backend: FastAPI playback API (Plan B) — endpoints for defect results + annotations | @razvan.boita | 3d | 2026-03-16 | 2026-03-18 | Todo |
| Backend: PostgreSQL/Supabase schema for defect events and annotations | @razvan.boita | 2d | 2026-03-19 | 2026-03-20 | Todo |
| Frontend: PlaybackAnnotator UI — defect review and validation interface | @alexandru.bejenari | 3d | 2026-03-16 | 2026-03-18 | Todo |
| Frontend: TextileViewer component — live WebRTC defect stream view | @alexandru.bejenari | 2d | 2026-03-19 | 2026-03-20 | Todo |
| Jetson setup: YOLO multiprocess detector (4x parallel, 100+ FPS target) | @el.tech | 2d | 2026-03-19 | 2026-03-20 | Todo |
| Define S3 storage strategy: MinIO on-premise (active) + Cloudflare R2 (archive) | @razvan.boita | 1d | 2026-03-20 | 2026-03-20 | Todo |
| Define ELK stack monitoring: model prediction logs + feedback loop | @el.tech | 1d | 2026-03-20 | 2026-03-20 | Todo |
| Create architecture diagrams and technical documentation | @alexandru.bejenari | 1d | 2026-03-20 | 2026-03-20 | Todo |
| Prepare KPI tracking dashboard (F1 ≥70-80%, inferență ≤1000ms, deșeuri -20%) | @ps.tech | 1d | 2026-03-21 | 2026-03-21 | Todo |
| Define model retraining pipeline (target: retraining within 48h of new data) | @el.tech | 2d | 2026-03-23 | 2026-03-24 | Todo |
| Prepare dissemination content: LinkedIn technical deep-dive post (mid-implementation) | @ps.tech | 1d | 2026-03-25 | 2026-03-25 | Todo |
