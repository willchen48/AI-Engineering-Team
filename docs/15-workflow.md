# docs/15-workflow.md

# Workflow Specification

> **Version:** 1.0.0 Alpha
> **Status:** Draft

---

# Purpose

Dokumen ini mendefinisikan workflow resmi AI Engineering Team.

Workflow merupakan urutan eksekusi yang mengatur bagaimana sebuah permintaan pengguna diproses hingga menjadi perangkat lunak yang siap digunakan.

Seluruh implementasi wajib mengikuti workflow ini.

---

# Workflow Principles

Workflow dibangun berdasarkan prinsip berikut:

* Sequential Execution
* Orchestrator Controlled
* Artifact Driven
* Deterministic
* Traceable
* Repeatable

Workflow tidak boleh diubah tanpa perubahan blueprint.

---

# Primary Workflow

```text
User
 │
 ▼
Orchestrator
 │
 ▼
Planner Agent
 │
 ▼
Architect Agent
 │
 ├──────────────┐
 ▼              ▼
Backend     Frontend
 └──────┬───────┘
        ▼
     QA Agent
        │
   Bug Found?
 ┌──────┴──────┐
 │             │
Yes            No
 │             │
 ▼             ▼
Debug     Security Audit
 │             │
 └──────┬──────┘
        ▼
   DevOps Agent
        │
        ▼
 Reporter Agent
        │
        ▼
      User
```

---

# Workflow Stages

Workflow terdiri dari tahapan berikut:

1. Project Initialization
2. Requirement Planning
3. Architecture Design
4. Backend Development
5. Frontend Development
6. Quality Assurance
7. Debugging (Optional)
8. Security Auditing
9. Deployment
10. Final Reporting
11. Project Completion

---

# Stage 1

## Project Initialization

Dilakukan oleh:

Orchestrator

Tujuan:

* Membuat Project ID.
* Membuat Workflow.
* Menginisialisasi Project Memory.
* Menyiapkan Job pertama.

Output:

Project Created.

---

# Stage 2

## Requirement Planning

Dilakukan oleh:

Planner Agent

Output:

* Requirement Analysis
* Feature List
* Task List
* Project Scope

---

# Stage 3

## Architecture Design

Dilakukan oleh:

Architect Agent

Output:

* Technical Specification
* Architecture Design
* API Design
* Database Design
* Development Guidelines

---

# Stage 4

## Backend Development

Dilakukan oleh:

Backend Agent

Output:

* Backend Source Code
* API Implementation
* Business Logic

---

# Stage 5

## Frontend Development

Dilakukan oleh:

Frontend Agent

Output:

* Frontend Source Code
* UI Components
* API Integration

---

# Stage 6

## Quality Assurance

Dilakukan oleh:

QA Agent

Output:

* QA Report
* Bug Report
* Test Report

Keputusan:

* Lulus → Security Auditing
* Gagal → Debug Agent

---

# Stage 7

## Debugging

Dilakukan oleh:

Debug Agent

Output:

* Updated Source Code
* Bug Fix Report
* Root Cause Analysis

Setelah selesai:

Workflow kembali ke QA Agent untuk validasi ulang.

---

# Stage 8

## Security Auditing

Dilakukan oleh:

Security Auditing Agent

Output:

* Security Audit Report
* Vulnerability Report
* Risk Assessment

Keputusan:

* Aman → DevOps
* Tidak aman → Debug Agent

---

# Stage 9

## Deployment

Dilakukan oleh:

DevOps Agent

Output:

* Build Package
* Deployment Report
* Verification Report

---

# Stage 10

## Final Reporting

Dilakukan oleh:

Reporter Agent

Output:

* Final Project Report
* Executive Summary
* Project Statistics

---

# Stage 11

## Project Completion

Dilakukan oleh:

Orchestrator

Aktivitas:

* Memvalidasi seluruh artefak.
* Menutup workflow.
* Mengubah status proyek menjadi COMPLETED.
* Mengirim hasil kepada User.

---

# Workflow Decision Rules

Hanya Orchestrator yang berhak:

* Memulai workflow.
* Menghentikan workflow.
* Mengulang workflow.
* Mengubah status workflow.
* Menentukan Agent berikutnya.

AI Agent tidak memiliki kewenangan tersebut.

---

# Failure Flow

Jika terjadi kegagalan:

```text
Agent Failed
      │
      ▼
Orchestrator
      │
      ▼
Retry Policy
      │
      ▼
Retry Success?
   │          │
  Yes        No
   │          │
   ▼          ▼
Continue    FAILED
```

---

# Completion Criteria

Workflow dinyatakan selesai apabila:

* Seluruh tahap selesai.
* Seluruh artefak tersedia.
* Deployment berhasil.
* Final Report selesai.
* Status proyek menjadi COMPLETED.

---

# Validation Checklist

Workflow dianggap valid apabila:

✓ Seluruh stage dijalankan sesuai urutan.

✓ Tidak ada stage yang dilewati.

✓ Seluruh artefak tersedia.

✓ Tidak ada komunikasi langsung antar Agent.

✓ Workflow dapat diaudit.

---

# Design Principles

Workflow harus selalu:

* Predictable.
* Deterministic.
* Traceable.
* Repeatable.
* Blueprint Driven.
* Orchestrator Controlled.

Workflow merupakan inti operasional AI Engineering Team dan menjadi dasar implementasi seluruh sistem.

---

# Next Document

Dokumen berikutnya:

**docs/16-repository-structure.md**

Dokumen ini mendefinisikan struktur repository resmi yang harus digunakan selama implementasi proyek.

---

# End of Document
