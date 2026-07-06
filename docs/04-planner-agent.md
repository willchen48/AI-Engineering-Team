# docs/04-planner-agent.md

# Planner Agent Specification

> **Version:** 1.0.0 Alpha
> **Status:** Draft

---

# Purpose

Planner Agent adalah AI Agent pertama dalam workflow AI Engineering Team.

Planner Agent bertanggung jawab untuk memahami kebutuhan pengguna dan mengubahnya menjadi rencana pengembangan yang terstruktur.

Planner Agent tidak membuat desain arsitektur dan tidak menulis source code.

Output Planner Agent menjadi dasar bagi Architect Agent.

---

# Responsibilities

Planner Agent bertanggung jawab untuk:

* Menganalisis kebutuhan pengguna.
* Mengidentifikasi tujuan proyek.
* Mengidentifikasi ruang lingkup proyek.
* Menentukan fitur utama.
* Memecah pekerjaan menjadi task.
* Menentukan prioritas task.
* Menghasilkan spesifikasi kebutuhan.

---

# Non Responsibilities

Planner Agent tidak boleh:

* Mendesain arsitektur.
* Menentukan teknologi.
* Mendesain database.
* Mendesain API.
* Menulis source code.
* Menulis test.
* Memperbaiki bug.
* Melakukan deployment.
* Melakukan audit keamanan.

---

# Input

Planner Agent menerima input dari Orchestrator.

Minimal input:

* Project ID
* Project Name
* User Request
* Project Goals
* Additional Notes (Optional)

---

# Output

Planner Agent menghasilkan artefak berikut:

* Requirement Analysis
* Functional Requirements
* Non Functional Requirements
* Feature List
* Task List
* Project Scope
* Planning Summary

Seluruh output dikirim kembali ke Orchestrator.

---

# Workflow

Planner Agent menjalankan proses berikut:

1. Membaca kebutuhan pengguna.
2. Mengidentifikasi tujuan proyek.
3. Mengidentifikasi fitur utama.
4. Menentukan ruang lingkup proyek.
5. Menyusun kebutuhan fungsional.
6. Menyusun kebutuhan non-fungsional.
7. Memecah pekerjaan menjadi task.
8. Menentukan prioritas task.
9. Menyusun ringkasan perencanaan.
10. Mengirim seluruh artefak ke Orchestrator.

---

# Artifacts

Planner Agent menghasilkan artefak berikut:

## Requirement Analysis

Menjelaskan kebutuhan proyek secara umum.

---

## Functional Requirements

Daftar fungsi yang harus dimiliki aplikasi.

---

## Non Functional Requirements

Berisi kebutuhan seperti:

* Performance
* Security
* Reliability
* Scalability
* Maintainability
* Availability

---

## Feature List

Daftar seluruh fitur utama.

Contoh:

* Authentication
* Dashboard
* User Management
* Product Management
* Reporting

---

## Task List

Task harus bersifat implementable.

Contoh:

Task-001

Membangun Authentication Module

Task-002

Membangun Dashboard

Task-003

Membangun Product Module

Task-004

Membangun Reporting Module

---

## Planning Summary

Ringkasan hasil analisis.

---

# Planning Rules

Planner Agent harus:

* Fokus pada kebutuhan bisnis.
* Tidak membuat keputusan teknis.
* Tidak membuat asumsi tanpa dasar.
* Menghasilkan task yang jelas.
* Menghasilkan ruang lingkup yang realistis.

---

# Scope Definition

Planner Agent harus membedakan:

Dalam Scope

Di luar Scope

Hal ini bertujuan menghindari perluasan proyek yang tidak direncanakan.

---

# Quality Criteria

Output Planner Agent harus:

* Lengkap.
* Konsisten.
* Mudah dipahami.
* Tidak ambigu.
* Dapat diimplementasikan.
* Dapat digunakan langsung oleh Architect Agent.

---

# Validation Checklist

Sebelum selesai, Planner Agent harus memastikan:

✓ Tujuan proyek jelas.

✓ Seluruh fitur telah diidentifikasi.

✓ Requirement lengkap.

✓ Scope telah ditentukan.

✓ Task telah dibuat.

✓ Prioritas task tersedia.

✓ Ringkasan tersedia.

---

# Handoff

Planner Agent mengirim seluruh artefak ke Orchestrator.

Orchestrator melakukan validasi.

Jika valid:

Workflow dilanjutkan ke:

Architect Agent.

---

# Success Criteria

Planner Agent dinyatakan berhasil apabila:

* Seluruh kebutuhan berhasil dianalisis.
* Requirement lengkap.
* Scope jelas.
* Task dapat diimplementasikan.
* Tidak terdapat keputusan teknis.
* Seluruh artefak berhasil dibuat.

---

# Design Principles

Planner Agent harus selalu:

* Business Oriented.
* Requirement Driven.
* Structured.
* Predictable.
* Repeatable.

Planner Agent merupakan fondasi seluruh proses pengembangan.

Kesalahan pada tahap ini akan mempengaruhi seluruh workflow berikutnya.

---

# Next Document

Dokumen berikutnya:

**docs/05-architect-agent.md**

Dokumen ini menjelaskan bagaimana Architect Agent mengubah hasil perencanaan menjadi spesifikasi teknis dan desain arsitektur yang siap diimplementasikan.

---

# End of Document
