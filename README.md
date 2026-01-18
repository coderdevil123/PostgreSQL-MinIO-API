# PostgreSQL + MinIO (Self-Hosted Backend Foundation)

This repository contains a **local-first, self-hosted backend setup** using:

- **PostgreSQL** – relational database
- **MinIO** – S3-compatible object storage
- **Docker Compose** – container orchestration

This setup is designed as a **replacement for Supabase Cloud**, while keeping:
- Full data ownership
- Minimal infrastructure complexity
- Easy migration & rollback
- Clear separation of concerns

---

## 🧠 Why This Setup?

We were previously using **Supabase Cloud** primarily for:
- PostgreSQL (database)
- Supabase Storage (images/files)

We are **not using**:
- Supabase Auth
- Supabase Realtime subscriptions

Self-hosting the full Supabase stack introduces unnecessary operational overhead.
Instead, this setup runs **only what we actually need**.

### Benefits
- No vendor lock-in
- Fewer services to maintain
- Easier security auditing
- Better control over data & backups
- Same PostgreSQL compatibility as Supabase

---

## 🏗 Architecture Overview


- PostgreSQL stores structured data
- MinIO stores images/files
- Database stores only file URLs (not binaries)

---

## 📦 Services

### PostgreSQL
- Image: `postgres:15`
- Database: `pristine_db`
- Persistent volume enabled
- Fully compatible with Supabase PostgreSQL exports

### MinIO
- S3-compatible object storage
- Used as a replacement for Supabase Storage
- Supports public and private buckets
- Persistent volume enabled

---

## 🚀 Getting Started (Local Setup)

### Prerequisites
- Docker
- Docker Compose

---

### 1️⃣ Start Services

```bash
docker compose up -d
