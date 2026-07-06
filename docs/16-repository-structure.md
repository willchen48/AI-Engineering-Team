# docs/16-repository-structure.md

# Repository Structure Specification

> **Version:** 1.0.0 Alpha
> **Status:** Draft

---

# Purpose

Dokumen ini mendefinisikan struktur repository resmi AI Engineering Team.

Seluruh implementasi wajib mengikuti struktur ini.

Perubahan struktur repository hanya boleh dilakukan melalui pembaruan blueprint.

---

# Objectives

Struktur repository dirancang agar:

* Mudah dipahami.
* Konsisten.
* Modular.
* Mudah dipelihara.
* Mudah diperluas.
* Mendukung pengembangan berbasis AI Agent.

---

# Repository Layout

```text
ai-engineering-team/
│
├── README.md
│
├── docs/
│
├── prompts/
│
├── src/
│   ├── orchestrator/
│   ├── planner/
│   ├── architect/
│   ├── backend/
│   ├── frontend/
│   ├── qa/
│   ├── debug/
│   ├── security/
│   ├── devops/
│   ├── reporter/
│   ├── shared/
│   ├── models/
│   ├── services/
│   ├── storage/
│   ├── config/
│   └── utils/
│
├── tests/
│
├── artifacts/
│
├── projects/
│
├── logs/
│
├── scripts/
│
├── docker/
│
├── requirements.txt
│
├── docker-compose.yml
│
└── .env.example
```

---

# Root Directory

Root repository hanya berisi:

* Dokumentasi
* Source Code
* Artefak
* Konfigurasi
* Deployment
* Testing

Tidak diperbolehkan membuat folder acak di root repository.

---

# docs/

Berisi seluruh blueprint proyek.

Folder ini merupakan referensi utama implementasi.

AI Coding Assistant wajib membaca folder ini sebelum menghasilkan kode.

---

# prompts/

Berisi prompt resmi yang digunakan setiap AI Agent.

Setiap Agent memiliki satu prompt utama.

Contoh:

* planner.md
* architect.md
* backend.md
* frontend.md
* qa.md
* debug.md
* security.md
* devops.md
* reporter.md

---

# src/

Berisi seluruh implementasi aplikasi.

Setiap Agent memiliki direktori sendiri.

Tidak boleh mencampurkan implementasi antar Agent.

---

# src/orchestrator/

Berisi seluruh implementasi Orchestrator.

Contoh:

* Workflow Engine
* State Manager
* Job Dispatcher
* Artifact Manager
* Execution Controller

---

# src/planner/

Implementasi Planner Agent.

---

# src/architect/

Implementasi Architect Agent.

---

# src/backend/

Implementasi Backend Agent.

---

# src/frontend/

Implementasi Frontend Agent.

---

# src/qa/

Implementasi QA Agent.

---

# src/debug/

Implementasi Debug Agent.

---

# src/security/

Implementasi Security Auditing Agent.

---

# src/devops/

Implementasi DevOps Agent.

---

# src/reporter/

Implementasi Reporter Agent.

---

# src/shared/

Berisi komponen yang digunakan bersama.

Contoh:

* Constants
* Enums
* Interfaces
* Shared Models

---

# src/models/

Berisi model data aplikasi.

Model digunakan secara konsisten di seluruh sistem.

---

# src/services/

Berisi service umum yang digunakan oleh beberapa komponen.

---

# src/storage/

Berisi implementasi penyimpanan data.

Contoh:

* Database
* Artifact Storage
* Project Memory Storage

---

# src/config/

Berisi konfigurasi aplikasi.

Tidak boleh menyimpan secret secara langsung.

---

# src/utils/

Berisi utility umum.

Utility harus bersifat reusable.

---

# tests/

Berisi seluruh pengujian.

Contoh:

* Unit Test
* Integration Test
* Workflow Test

---

# artifacts/

Berisi seluruh artefak proyek.

Contoh:

* Requirement Analysis
* Technical Specification
* QA Report
* Security Report
* Final Report

Artefak dipisahkan berdasarkan Project ID.

---

# projects/

Berisi metadata seluruh proyek.

---

# logs/

Berisi log sistem.

Contoh:

* Workflow Log
* Agent Log
* Error Log
* Audit Log

---

# scripts/

Berisi script otomatisasi.

Contoh:

* Build
* Setup
* Migration
* Maintenance

---

# docker/

Berisi konfigurasi Docker.

Contoh:

* Dockerfile
* Container Configuration

---

# Configuration Files

Repository minimal memiliki:

* requirements.txt
* docker-compose.yml
* .env.example

Seluruh konfigurasi harus terdokumentasi.

---

# Repository Rules

Repository harus:

* Konsisten.
* Mudah dinavigasi.
* Tidak memiliki duplikasi struktur.
* Memisahkan implementasi setiap Agent.
* Memisahkan artefak dengan source code.

---

# Validation Checklist

Repository dianggap valid apabila:

✓ Struktur sesuai blueprint.

✓ Seluruh Agent memiliki direktori.

✓ Dokumentasi tersedia.

✓ Testing dipisahkan.

✓ Artefak dipisahkan.

✓ Konfigurasi dipisahkan.

✓ Logging dipisahkan.

---

# Design Principles

Repository harus selalu:

* Modular.
* Clean.
* Predictable.
* Scalable.
* Maintainable.
* Blueprint Compliant.

Struktur repository merupakan fondasi implementasi dan harus tetap konsisten sepanjang pengembangan.

---

# Next Document

Dokumen berikutnya:

**docs/17-coding-standard.md**

Dokumen ini mendefinisikan standar penulisan kode yang wajib diikuti oleh seluruh implementasi AI Engineering Team.

---

# End of Document
