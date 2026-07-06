# docs/02-architecture.md

# System Architecture

> **Version:** 1.0.0 Alpha
> **Status:** Draft

---

# Purpose

Dokumen ini mendefinisikan arsitektur inti AI Engineering Team.

Dokumen ini menjelaskan bagaimana setiap komponen saling berhubungan, bagaimana alur eksekusi dijalankan, dan batas tanggung jawab masing-masing komponen.

Dokumen ini merupakan referensi utama sebelum implementasi dimulai.

---

# Architecture Style

AI Engineering Team menggunakan arsitektur:

**Orchestrator-Centric Multi-Agent Architecture**

Pada arsitektur ini, seluruh AI Agent bersifat independen dan tidak saling berkomunikasi secara langsung.

Seluruh koordinasi dilakukan oleh Orchestrator.

---

# Architecture Principles

Arsitektur dibangun berdasarkan prinsip berikut.

* Single Responsibility Principle
* Separation of Concerns
* Loose Coupling
* High Cohesion
* Artifact-Driven Workflow
* Deterministic Execution
* Documentation First
* Blueprint Before Implementation

---

# Core Architecture

```text
                        USER
                          │
                          ▼
                  ORCHESTRATOR
                          │
                          ▼
                  Planner Agent
                          │
                          ▼
                 Architect Agent
                          │
              ┌───────────┴───────────┐
              ▼                       ▼
      Backend Agent          Frontend Agent
              └───────────┬───────────┘
                          ▼
                     QA Agent
                          │
                   Bug Detected?
                  ┌───────┴────────┐
                  │                │
                 YES              NO
                  ▼                ▼
           Debug Agent     Security Auditing
                  │                │
                  └────────┬───────┘
                           ▼
                     DevOps Agent
                           │
                           ▼
                    Reporter Agent
                           │
                           ▼
                          USER
```

---

# Component Responsibilities

## User

Memulai proyek dengan memberikan kebutuhan sistem.

User tidak berinteraksi langsung dengan AI Agent.

Semua komunikasi dilakukan melalui Orchestrator.

---

## Orchestrator

Merupakan pusat kendali sistem.

Bertanggung jawab untuk:

* Menjalankan workflow.
* Mengatur urutan eksekusi.
* Mengirim pekerjaan.
* Menerima hasil.
* Mengelola status proyek.
* Mengelola retry.
* Mengelola error.
* Mengelola artefak.

---

## AI Agents

Seluruh AI Agent hanya menerima pekerjaan dari Orchestrator.

AI Agent tidak boleh:

* Memanggil Agent lain.
* Mengubah workflow.
* Mengatur urutan eksekusi.
* Mengakses state Agent lain secara langsung.

---

# Communication Model

Seluruh komunikasi mengikuti pola berikut.

```text
User
   │
   ▼
Orchestrator
   │
   ▼
Agent
   │
   ▼
Orchestrator
   │
   ▼
Next Agent
```

Tidak ada komunikasi horizontal antar Agent.

---

# Artifact Flow

Setiap Agent menerima artefak sebagai input.

Setelah pekerjaan selesai, Agent menghasilkan artefak baru.

Contoh alur artefak:

```text
Requirement
      │
      ▼
Requirement Analysis
      │
      ▼
Technical Specification
      │
      ▼
Architecture Design
      │
      ▼
Source Code
      │
      ▼
Test Report
      │
      ▼
Bug Fix Report
      │
      ▼
Security Report
      │
      ▼
Deployment Package
      │
      ▼
Final Report
```

Tidak ada Agent yang mengubah artefak milik Agent lain secara langsung.

---

# Execution Model

Workflow bersifat berurutan.

Urutan eksekusi:

1. Planner
2. Architect
3. Backend
4. Frontend
5. QA
6. Debug (jika diperlukan)
7. Security Auditing
8. DevOps
9. Reporter

Setiap tahap harus selesai sebelum tahap berikutnya dimulai.

---

# State Management

Seluruh state proyek dikelola oleh Orchestrator.

State meliputi:

* Project Status
* Current Stage
* Active Task
* Artifact List
* Execution History
* Error Log

AI Agent bersifat stateless terhadap workflow.

---

# Error Handling

Jika sebuah Agent gagal:

1. Orchestrator mencatat error.
2. Orchestrator melakukan retry sesuai kebijakan.
3. Jika retry gagal, workflow dihentikan.
4. Reporter mencatat kegagalan proyek.

Agent tidak boleh melakukan retry sendiri.

---

# Security Boundary

Security Auditing Agent hanya melakukan audit.

Security Auditing Agent tidak boleh:

* Memperbaiki kode.
* Mengubah konfigurasi.
* Mengubah artefak.

Hasil audit dikirim ke Orchestrator.

Jika ditemukan masalah, Orchestrator mengarahkan pekerjaan ke Debug Agent.

---

# Scalability

Blueprint v1.0 menggunakan satu Orchestrator.

Di masa depan, implementasi dapat ditingkatkan tanpa mengubah arsitektur dasar, selama tetap mempertahankan:

* Orchestrator sebagai pusat kendali.
* Workflow utama.
* Tanggung jawab setiap Agent.
* Model komunikasi.

---

# Architecture Constraints

Implementasi wajib mematuhi batasan berikut:

* Tidak boleh menambahkan AI Agent baru.
* Tidak boleh mengubah urutan workflow.
* Tidak boleh membuat komunikasi langsung antar Agent.
* Tidak boleh memindahkan tanggung jawab Orchestrator ke Agent.
* Tidak boleh memindahkan tanggung jawab Agent ke Orchestrator.

---

# Architecture Goals

Arsitektur ini dirancang agar:

* Mudah dipahami.
* Mudah diimplementasikan.
* Mudah diuji.
* Mudah dipelihara.
* Mudah diperluas pada versi berikutnya.
* Konsisten dengan seluruh blueprint.

---

# Next Document

Dokumen berikutnya:

**docs/03-orchestrator.md**

Dokumen ini akan menjelaskan spesifikasi lengkap Orchestrator, termasuk peran, lifecycle, workflow engine, state management, routing, dan kontrak input/output.

---

# End of Document
