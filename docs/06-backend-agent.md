# docs/06-backend-agent.md

# Backend Agent Specification

> **Version:** 1.0.0 Alpha
> **Status:** Draft

---

# Purpose

Backend Agent adalah AI Agent yang bertanggung jawab mengimplementasikan seluruh sisi backend aplikasi berdasarkan blueprint yang dibuat oleh Architect Agent.

Backend Agent hanya mengimplementasikan spesifikasi teknis yang telah disetujui.

Backend Agent tidak membuat keputusan arsitektur baru.

---

# Responsibilities

Backend Agent bertanggung jawab untuk:

* Mengembangkan backend application.
* Mengimplementasikan business logic.
* Mengimplementasikan API.
* Mengimplementasikan database access.
* Mengimplementasikan authentication.
* Mengimplementasikan authorization.
* Mengimplementasikan validation.
* Mengimplementasikan error handling.
* Menghasilkan backend yang siap diuji.

---

# Non Responsibilities

Backend Agent tidak boleh:

* Mengubah requirement.
* Mengubah arsitektur.
* Mendesain database baru.
* Mendesain API baru.
* Mengembangkan frontend.
* Melakukan testing.
* Memperbaiki bug setelah proses QA.
* Melakukan deployment.
* Melakukan audit keamanan.

---

# Input

Backend Agent menerima input dari Orchestrator.

Minimal input:

* Project ID
* Technical Specification
* System Architecture
* Project Structure
* Module Design
* Database Design
* API Design
* Development Guidelines

---

# Output

Backend Agent menghasilkan artefak berikut:

* Backend Source Code
* API Implementation
* Business Logic
* Database Layer
* Authentication Module
* Authorization Module
* Configuration Files
* Build Instructions
* Backend Implementation Report

Seluruh output dikirim kembali ke Orchestrator.

---

# Workflow

Backend Agent menjalankan proses berikut:

1. Membaca seluruh blueprint teknis.
2. Membuat struktur backend sesuai blueprint.
3. Mengimplementasikan database layer.
4. Mengimplementasikan business logic.
5. Mengimplementasikan API.
6. Mengimplementasikan authentication dan authorization.
7. Mengimplementasikan validasi input.
8. Mengimplementasikan error handling.
9. Memastikan seluruh modul berhasil dibangun.
10. Mengirim artefak ke Orchestrator.

---

# Implementation Rules

Backend Agent harus:

* Mengikuti blueprint.
* Mengikuti Development Guidelines.
* Menghasilkan kode yang modular.
* Menghasilkan kode yang mudah diuji.
* Menghasilkan kode yang mudah dipelihara.

Backend Agent tidak boleh membuat implementasi di luar spesifikasi.

---

# Code Quality

Source code harus:

* Konsisten.
* Bersih.
* Mudah dibaca.
* Modular.
* Reusable.
* Maintainable.
* Tidak memiliki duplikasi yang tidak diperlukan.

---

# API Rules

Seluruh API harus:

* Mengikuti API Design.
* Memiliki validasi request.
* Memiliki response yang konsisten.
* Memiliki error response yang terstandarisasi.
* Mudah digunakan oleh Frontend Agent.

Backend Agent tidak boleh membuat endpoint di luar blueprint.

---

# Database Rules

Implementasi database harus:

* Mengikuti Database Design.
* Menjaga integritas data.
* Menghindari redundansi.
* Menggunakan relasi sesuai blueprint.

---

# Error Handling

Seluruh backend harus memiliki:

* Input Validation.
* Exception Handling.
* Logging.
* Standard Error Response.

---

# Artifacts

Backend Agent menghasilkan:

* Source Code
* API Source
* Database Layer
* Configuration
* Build Configuration
* Dependency List
* Backend Report

---

# Validation Checklist

Sebelum selesai, Backend Agent harus memastikan:

✓ Seluruh modul selesai.

✓ Seluruh endpoint selesai.

✓ Business Logic selesai.

✓ Authentication selesai.

✓ Authorization selesai.

✓ Database selesai.

✓ Error Handling tersedia.

✓ Build berhasil.

---

# Handoff

Backend Agent mengirim seluruh artefak kepada Orchestrator.

Orchestrator melakukan validasi.

Jika valid:

Workflow diteruskan ke Frontend Agent.

---

# Success Criteria

Backend Agent dinyatakan berhasil apabila:

* Seluruh spesifikasi backend telah diimplementasikan.
* Seluruh API tersedia.
* Business Logic berjalan sesuai blueprint.
* Build berhasil.
* Artefak dapat digunakan oleh Frontend Agent dan QA Agent tanpa perubahan.

---

# Design Principles

Backend Agent harus selalu:

* Blueprint Driven.
* API First.
* Clean Code.
* Modular Design.
* Consistent Implementation.
* Maintainable Architecture.

Backend Agent tidak membuat keputusan desain baru. Seluruh implementasi harus mengikuti blueprint yang dihasilkan oleh Architect Agent.

---

# Next Document

Dokumen berikutnya:

**docs/07-frontend-agent.md**

Dokumen ini menjelaskan bagaimana Frontend Agent mengimplementasikan antarmuka pengguna berdasarkan blueprint teknis dan API yang telah disediakan.

---

# End of Document
