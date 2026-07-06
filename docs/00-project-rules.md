# docs/00-project-rules.md

# Project Rules

> **Version:** 1.0.0 Alpha
> **Status:** Active
> **Priority:** Highest

---

# Purpose

Dokumen ini merupakan aturan utama (Master Rules) yang wajib dipatuhi selama pengembangan proyek.

Seluruh AI Agent, AI Coding Assistant, dan kontributor manusia harus mengikuti aturan dalam dokumen ini.

Dokumen ini memiliki prioritas lebih tinggi dibandingkan dokumen lain apabila terjadi konflik.

---

# Single Source of Truth

Blueprint merupakan sumber kebenaran utama (Single Source of Truth).

Implementasi harus mengikuti blueprint.

Implementasi tidak boleh mengubah blueprint.

Perubahan arsitektur hanya boleh dilakukan dengan memperbarui dokumentasi blueprint terlebih dahulu.

---

# Architecture Integrity

Arsitektur sistem harus tetap konsisten.

Tidak diperbolehkan:

* Menambahkan AI Agent baru.
* Menghapus AI Agent yang telah ditentukan.
* Mengubah tanggung jawab AI Agent.
* Mengubah workflow utama.
* Mengubah hubungan antar Agent.
* Mengubah peran Orchestrator.

Seluruh perubahan tersebut berada di luar ruang lingkup Blueprint v1.0.

---

# Approved Components

Komponen resmi sistem hanya terdiri dari:

Core Controller

* Orchestrator

AI Agents

* Planner Agent
* Architect Agent
* Backend Agent
* Frontend Agent
* QA Agent
* Debug Agent
* Security Auditing Agent
* DevOps Agent
* Reporter Agent

Tidak ada komponen lain yang dianggap sebagai bagian dari arsitektur inti.

---

# Orchestrator Rules

Orchestrator merupakan satu-satunya komponen yang berhak:

* Mengatur workflow.
* Menjalankan Agent.
* Mengirim pekerjaan ke Agent.
* Menerima hasil Agent.
* Mengelola state proyek.
* Mengelola retry.
* Mengelola error.
* Menentukan urutan eksekusi.

AI Agent tidak boleh memanggil AI Agent lain secara langsung.

---

# Agent Rules

Setiap AI Agent wajib mengikuti aturan berikut.

## Single Responsibility

Satu Agent hanya memiliki satu tanggung jawab utama.

Agent tidak boleh mengambil tanggung jawab Agent lain.

---

## Input

Agent hanya bekerja berdasarkan input yang diberikan oleh Orchestrator.

Agent tidak boleh mengambil data dari Agent lain secara langsung.

---

## Output

Setiap Agent wajib menghasilkan output yang terstruktur.

Output harus dapat digunakan oleh Agent berikutnya tanpa modifikasi manual.

---

## Deterministic Behavior

Untuk input yang sama, Agent harus menghasilkan hasil yang konsisten sejauh memungkinkan.

Agent tidak boleh menghasilkan perubahan acak pada arsitektur atau implementasi.

---

# Workflow Rules

Workflow resmi adalah:

User

↓

Orchestrator

↓

Planner

↓

Architect

↓

Backend + Frontend

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

User

Workflow tersebut tidak boleh diubah pada Blueprint v1.0.

---

# Coding Rules

Seluruh implementasi harus:

* Bersih.
* Modular.
* Mudah dipelihara.
* Mudah diuji.
* Mudah diperluas.

Kode harus menghindari:

* Duplikasi.
* Ketergantungan yang tidak diperlukan.
* Kompleksitas berlebihan.
* Hardcode yang tidak diperlukan.

---

# Documentation Rules

Setiap perubahan implementasi harus tetap sesuai dengan blueprint.

Dokumentasi harus selalu diperbarui sebelum perubahan besar dilakukan.

Kode tidak boleh menjadi referensi utama.

Blueprint adalah referensi utama.

---

# AI Coding Rules

Seluruh AI Coding Assistant wajib:

* Membaca README.md.
* Membaca dokumen yang relevan sebelum membuat kode.
* Mengikuti blueprint.
* Tidak membuat asumsi di luar dokumentasi.
* Tidak mengubah arsitektur tanpa instruksi eksplisit.

Jika terdapat konflik, AI harus meminta implementasi mengikuti blueprint, bukan mengubah blueprint.

---

# Scope Control

Blueprint v1.0 hanya berfokus pada sistem inti.

Tidak diperbolehkan menambahkan fitur di luar ruang lingkup tanpa pembaruan blueprint.

Prinsip utama adalah:

**Keep the architecture simple, consistent, and implementation-ready.**

---

# End of Document
