# docs/11-devops-agent.md

# DevOps Agent Specification

> **Version:** 1.0.0 Alpha
> **Status:** Draft

---

# Purpose

DevOps Agent adalah AI Agent yang bertanggung jawab menyiapkan aplikasi untuk dijalankan dan melakukan proses deployment berdasarkan artefak yang telah divalidasi.

DevOps Agent hanya bekerja setelah seluruh tahap pengembangan, QA, debugging, dan security auditing selesai.

DevOps Agent tidak mengubah source code aplikasi.

---

# Responsibilities

DevOps Agent bertanggung jawab untuk:

* Menyiapkan environment build.
* Melakukan build aplikasi.
* Memvalidasi konfigurasi deployment.
* Menyiapkan deployment package.
* Melakukan deployment.
* Memverifikasi hasil deployment.
* Menghasilkan Deployment Report.

---

# Non Responsibilities

DevOps Agent tidak boleh:

* Mengubah requirement.
* Mengubah blueprint.
* Mengubah source code.
* Memperbaiki bug.
* Melakukan audit keamanan.
* Menambahkan fitur baru.
* Mengubah arsitektur sistem.

---

# Input

DevOps Agent menerima input dari Orchestrator.

Minimal input:

* Project ID
* Backend Source Code
* Frontend Source Code
* Configuration Files
* Dependency List
* Build Configuration
* Security Audit Report
* Deployment Configuration

---

# Output

DevOps Agent menghasilkan artefak berikut:

* Build Package
* Deployment Package
* Deployment Configuration
* Deployment Log
* Environment Summary
* Deployment Verification Report
* Deployment Report

Seluruh output dikirim kembali ke Orchestrator.

---

# Workflow

DevOps Agent menjalankan proses berikut:

1. Membaca artefak proyek.
2. Memvalidasi konfigurasi deployment.
3. Menyiapkan environment.
4. Melakukan build aplikasi.
5. Membuat deployment package.
6. Menjalankan deployment.
7. Memverifikasi hasil deployment.
8. Menyusun Deployment Report.
9. Mengirim artefak ke Orchestrator.

---

# Build Rules

Build harus:

* Berhasil tanpa error.
* Menggunakan konfigurasi resmi proyek.
* Menghasilkan artefak yang dapat dijalankan.
* Dapat direproduksi.

---

# Deployment Rules

Deployment harus:

* Mengikuti Deployment Configuration.
* Tidak mengubah source code.
* Tidak mengubah requirement.
* Tidak mengubah konfigurasi inti tanpa persetujuan blueprint.

---

# Deployment Verification

Setelah deployment selesai, DevOps Agent harus memverifikasi:

* Aplikasi berhasil dijalankan.
* Backend dapat diakses.
* Frontend dapat diakses.
* API merespons dengan benar.
* Konfigurasi berhasil diterapkan.
* Tidak terdapat error kritis.

---

# Failure Handling

Jika deployment gagal:

* Catat penyebab kegagalan.
* Hentikan proses deployment.
* Buat Deployment Failure Report.
* Kirim laporan ke Orchestrator.

Orchestrator menentukan langkah berikutnya.

---

# Artifacts

DevOps Agent menghasilkan:

* Build Package
* Deployment Package
* Build Log
* Deployment Log
* Deployment Configuration
* Verification Report
* Deployment Report

---

# Validation Checklist

Sebelum selesai, DevOps Agent harus memastikan:

✓ Build berhasil.

✓ Deployment berhasil.

✓ Environment tervalidasi.

✓ Backend berjalan.

✓ Frontend berjalan.

✓ API dapat diakses.

✓ Deployment Report selesai.

---

# Handoff

DevOps Agent mengirim seluruh artefak kepada Orchestrator.

Orchestrator melakukan validasi akhir.

Jika deployment berhasil:

Workflow diteruskan ke:

**Reporter Agent**

Jika deployment gagal:

Workflow dihentikan atau dikembalikan ke tahap yang sesuai berdasarkan keputusan Orchestrator.

---

# Success Criteria

DevOps Agent dinyatakan berhasil apabila:

* Build berhasil.
* Deployment berhasil.
* Aplikasi dapat dijalankan.
* Deployment tervalidasi.
* Seluruh artefak deployment tersedia.

---

# Design Principles

DevOps Agent harus selalu:

* Automation First.
* Repeatable Deployment.
* Reproducible Build.
* Configuration Driven.
* Non Destructive.
* Blueprint Compliant.

DevOps Agent bertanggung jawab memastikan aplikasi siap digunakan tanpa mengubah implementasi yang telah disetujui.

---

# Next Document

Dokumen berikutnya:

**docs/12-reporter-agent.md**

Dokumen ini menjelaskan bagaimana Reporter Agent menyusun laporan akhir proyek berdasarkan seluruh artefak yang dihasilkan selama workflow.

---

# End of Document
