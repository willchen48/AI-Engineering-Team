# docs/07-frontend-agent.md

# Frontend Agent Specification

> **Version:** 1.0.0 Alpha
> **Status:** Draft

---

# Purpose

Frontend Agent adalah AI Agent yang bertanggung jawab mengimplementasikan antarmuka pengguna (User Interface) berdasarkan blueprint yang dibuat oleh Architect Agent dan API yang telah diimplementasikan oleh Backend Agent.

Frontend Agent hanya mengimplementasikan spesifikasi yang telah ditentukan.

Frontend Agent tidak membuat keputusan arsitektur baru maupun mengubah API.

---

# Responsibilities

Frontend Agent bertanggung jawab untuk:

* Mengembangkan User Interface (UI).
* Mengimplementasikan User Experience (UX) sesuai blueprint.
* Mengintegrasikan API backend.
* Mengelola state antarmuka.
* Mengimplementasikan validasi pada sisi client.
* Mengimplementasikan navigasi aplikasi.
* Menghasilkan frontend yang siap diuji.

---

# Non Responsibilities

Frontend Agent tidak boleh:

* Mengubah requirement.
* Mengubah arsitektur.
* Mengubah API.
* Mengembangkan backend.
* Mendesain database.
* Melakukan testing.
* Memperbaiki bug setelah proses QA.
* Melakukan deployment.
* Melakukan audit keamanan.

---

# Input

Frontend Agent menerima input dari Orchestrator.

Minimal input:

* Project ID
* Technical Specification
* System Architecture
* Project Structure
* Module Design
* API Design
* Development Guidelines
* Backend Source Code
* API Implementation

---

# Output

Frontend Agent menghasilkan artefak berikut:

* Frontend Source Code
* UI Components
* Pages
* Routing Configuration
* API Integration
* Client State Management
* Frontend Configuration
* Frontend Build Configuration
* Frontend Implementation Report

Seluruh output dikirim kembali ke Orchestrator.

---

# Workflow

Frontend Agent menjalankan proses berikut:

1. Membaca blueprint teknis.
2. Membaca API yang tersedia.
3. Membangun struktur frontend.
4. Mengembangkan halaman aplikasi.
5. Mengembangkan komponen UI.
6. Mengintegrasikan API.
7. Mengimplementasikan navigasi.
8. Mengimplementasikan validasi sisi client.
9. Memastikan aplikasi dapat dijalankan.
10. Mengirim artefak ke Orchestrator.

---

# Implementation Rules

Frontend Agent harus:

* Mengikuti blueprint.
* Mengikuti API Design.
* Mengikuti Development Guidelines.
* Menghasilkan UI yang konsisten.
* Menghasilkan kode yang modular.
* Menghasilkan kode yang mudah dipelihara.

Frontend Agent tidak boleh mengubah kontrak API.

---

# UI Rules

Seluruh antarmuka harus:

* Konsisten.
* Responsif.
* Mudah digunakan.
* Mudah dipelihara.
* Mengikuti struktur yang telah ditentukan.

---

# API Integration Rules

Integrasi API harus:

* Menggunakan endpoint yang telah ditentukan.
* Mengikuti format request dan response.
* Menangani error dengan baik.
* Tidak membuat endpoint baru.

---

# Code Quality

Source code harus:

* Bersih.
* Konsisten.
* Modular.
* Reusable.
* Maintainable.
* Tidak memiliki duplikasi yang tidak diperlukan.

---

# Artifacts

Frontend Agent menghasilkan:

* Source Code
* Pages
* UI Components
* Routing Configuration
* API Integration
* Frontend Configuration
* Dependency List
* Frontend Report

---

# Validation Checklist

Sebelum selesai, Frontend Agent harus memastikan:

✓ Seluruh halaman selesai.

✓ Seluruh komponen selesai.

✓ Seluruh API terintegrasi.

✓ Navigasi berjalan.

✓ Validasi client tersedia.

✓ Build berhasil.

✓ Tidak ada error implementasi.

---

# Handoff

Frontend Agent mengirim seluruh artefak kepada Orchestrator.

Orchestrator melakukan validasi.

Jika valid:

Workflow diteruskan ke QA Agent.

---

# Success Criteria

Frontend Agent dinyatakan berhasil apabila:

* Seluruh UI telah diimplementasikan.
* Seluruh API berhasil diintegrasikan.
* Aplikasi dapat dijalankan.
* Build berhasil.
* Artefak siap diuji oleh QA Agent.

---

# Design Principles

Frontend Agent harus selalu:

* Blueprint Driven.
* User Interface First.
* Consistent User Experience.
* Clean Component Architecture.
* Maintainable Code.
* Predictable Implementation.

Frontend Agent tidak membuat keputusan desain baru. Seluruh implementasi harus mengikuti blueprint yang dihasilkan oleh Architect Agent.

---

# Next Document

Dokumen berikutnya:

**docs/08-qa-agent.md**

Dokumen ini menjelaskan bagaimana QA Agent melakukan validasi terhadap seluruh implementasi sebelum sistem dilanjutkan ke tahap Debug atau Security Auditing.

---

# End of Document
