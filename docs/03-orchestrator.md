# docs/03-orchestrator.md

# Orchestrator Specification

> **Version:** 1.0.0 Alpha
> **Status:** Draft

---

# Purpose

Orchestrator adalah pusat kendali AI Engineering Team.

Seluruh workflow, komunikasi, state proyek, dan eksekusi AI Agent dikendalikan oleh Orchestrator.

Orchestrator tidak mengembangkan software secara langsung.

Tugas Orchestrator adalah memastikan setiap AI Agent bekerja pada waktu yang tepat, dengan input yang benar, dan menghasilkan output yang dapat diteruskan ke tahap berikutnya.

---

# Responsibilities

Orchestrator bertanggung jawab untuk:

* Membuat workflow proyek.
* Menjalankan workflow.
* Mengelola Project State.
* Mengatur urutan eksekusi Agent.
* Mengirim input ke Agent.
* Menerima output dari Agent.
* Menyimpan artefak proyek.
* Melakukan validasi handoff.
* Mengelola retry.
* Mengelola error.
* Mengakhiri workflow.

---

# Non Responsibilities

Orchestrator tidak boleh:

* Mendesain arsitektur aplikasi.
* Menulis source code.
* Menguji aplikasi.
* Memperbaiki bug.
* Melakukan audit keamanan.
* Melakukan deployment.
* Menyusun laporan proyek.

Seluruh pekerjaan tersebut merupakan tanggung jawab AI Agent terkait.

---

# Managed Agents

Orchestrator hanya mengelola Agent berikut:

1. Planner Agent
2. Architect Agent
3. Backend Agent
4. Frontend Agent
5. QA Agent
6. Debug Agent
7. Security Auditing Agent
8. DevOps Agent
9. Reporter Agent

---

# Workflow Engine

Workflow utama:

```text
User
 ↓
Planner
 ↓
Architect
 ↓
Backend
 ↓
Frontend
 ↓
QA
 ↓
Debug (jika diperlukan)
 ↓
Security Auditing
 ↓
DevOps
 ↓
Reporter
 ↓
Completed
```

Workflow ini merupakan workflow resmi Blueprint v1.0.

---

# Project Lifecycle

Setiap proyek memiliki lifecycle berikut:

```text
CREATED

↓

PLANNING

↓

ARCHITECTURE

↓

BACKEND_DEVELOPMENT

↓

FRONTEND_DEVELOPMENT

↓

QUALITY_ASSURANCE

↓

DEBUGGING (Optional)

↓

SECURITY_AUDIT

↓

DEPLOYMENT

↓

REPORTING

↓

COMPLETED
```

Jika terjadi kegagalan permanen:

```text
FAILED
```

---

# Project State

Orchestrator menyimpan state proyek.

Minimal state yang harus tersedia:

* Project ID
* Project Name
* Current Stage
* Current Agent
* Workflow Status
* Active Task
* Completed Tasks
* Artifact List
* Execution History
* Error History
* Retry Count
* Start Time
* Last Updated
* Finish Time

---

# Artifact Management

Setiap Agent menghasilkan artefak.

Orchestrator bertanggung jawab untuk:

* Menyimpan artefak.
* Memberikan artefak ke Agent berikutnya.
* Menjaga versi artefak.
* Menjaga konsistensi artefak.

Artefak tidak boleh dikirim langsung antar Agent.

---

# Agent Execution

Sebelum menjalankan Agent:

Orchestrator harus:

* Memastikan input tersedia.
* Memastikan workflow valid.
* Memastikan state sesuai.
* Memastikan artefak lengkap.

Setelah Agent selesai:

Orchestrator harus:

* Memvalidasi output.
* Menyimpan artefak.
* Memperbarui state.
* Menentukan Agent berikutnya.

---

# Handoff Rules

Setiap perpindahan pekerjaan disebut handoff.

Handoff hanya dapat dilakukan jika:

* Agent selesai.
* Output valid.
* Tidak ada error kritis.
* State berhasil diperbarui.

Jika salah satu gagal:

Workflow dihentikan.

---

# Retry Policy

Jika Agent gagal:

1. Catat error.
2. Tambahkan Retry Count.
3. Jalankan ulang Agent sesuai kebijakan.
4. Jika retry gagal, ubah status menjadi FAILED.

Agent tidak boleh melakukan retry sendiri.

---

# Error Management

Semua error dicatat oleh Orchestrator.

Minimal informasi:

* Error ID
* Project ID
* Agent
* Stage
* Timestamp
* Error Message
* Retry Count
* Final Status

---

# Execution Rules

Orchestrator hanya boleh menjalankan satu tahap workflow dalam satu waktu.

Agent berikutnya tidak boleh dijalankan sebelum tahap sebelumnya selesai.

Workflow harus selalu bersifat deterministik.

---

# Communication Rules

Semua komunikasi mengikuti pola:

```text
Orchestrator

↓

Agent

↓

Orchestrator
```

Tidak ada komunikasi langsung antar Agent.

---

# Decision Rules

Orchestrator berhak menentukan:

* Agent berikutnya.
* Apakah Debug diperlukan.
* Apakah workflow dapat dilanjutkan.
* Apakah workflow gagal.
* Apakah proyek selesai.

Agent tidak memiliki hak mengambil keputusan terhadap workflow.

---

# Completion Criteria

Workflow dinyatakan selesai apabila:

* Semua Agent telah selesai.
* Seluruh artefak tersedia.
* Deployment berhasil.
* Reporter menghasilkan laporan akhir.

Status proyek berubah menjadi:

```text
COMPLETED
```

---

# Design Principles

Orchestrator harus:

* Stateless terhadap logika bisnis aplikasi.
* State-aware terhadap workflow proyek.
* Mudah diuji.
* Mudah dipelihara.
* Dapat diperluas tanpa mengubah kontrak Agent.

---

# Next Document

Dokumen berikutnya:

**docs/04-planner-agent.md**

Dokumen ini akan menjelaskan spesifikasi lengkap Planner Agent, termasuk tanggung jawab, input, output, workflow, artefak, dan kontrak data.

---

# End of Document
