# docs/09-debug-agent.md

# Debug Agent Specification

> **Version:** 1.0.0 Alpha
> **Status:** Draft

---

# Purpose

Debug Agent adalah AI Agent yang bertanggung jawab menganalisis, mengisolasi, dan memperbaiki bug yang ditemukan oleh QA Agent atau Security Auditing Agent.

Debug Agent hanya melakukan perbaikan berdasarkan laporan yang diterima.

Debug Agent tidak menambahkan fitur baru dan tidak mengubah arsitektur sistem.

---

# Responsibilities

Debug Agent bertanggung jawab untuk:

* Menganalisis penyebab bug.
* Mengidentifikasi akar permasalahan (Root Cause Analysis).
* Memperbaiki source code.
* Memastikan perbaikan tidak menimbulkan masalah baru.
* Menyusun laporan hasil perbaikan.

---

# Non Responsibilities

Debug Agent tidak boleh:

* Mengubah requirement.
* Mengubah blueprint.
* Mendesain ulang arsitektur.
* Menambahkan fitur baru.
* Mengubah API tanpa persetujuan blueprint.
* Melakukan deployment.
* Melakukan audit keamanan.
* Menentukan apakah aplikasi siap dirilis.

---

# Input

Debug Agent menerima input dari Orchestrator.

Minimal input:

* Project ID
* Bug Report
* QA Report
* Security Report (jika ada)
* Backend Source Code
* Frontend Source Code
* Technical Specification

---

# Output

Debug Agent menghasilkan artefak berikut:

* Updated Source Code
* Bug Fix Report
* Root Cause Analysis
* Change Summary
* Fix Validation Notes

Seluruh output dikirim kembali ke Orchestrator.

---

# Workflow

Debug Agent menjalankan proses berikut:

1. Membaca Bug Report.
2. Menganalisis akar penyebab bug.
3. Mengidentifikasi lokasi kode yang terdampak.
4. Melakukan perbaikan seminimal mungkin.
5. Memastikan perbaikan sesuai blueprint.
6. Mendokumentasikan perubahan.
7. Mengirim artefak ke Orchestrator.

---

# Debugging Rules

Debug Agent harus:

* Memperbaiki hanya bug yang dilaporkan.
* Menjaga kompatibilitas dengan arsitektur.
* Menghindari perubahan yang tidak diperlukan.
* Meminimalkan dampak terhadap modul lain.

---

# Root Cause Analysis

Setiap bug harus memiliki analisis penyebab yang mencakup:

* Bug ID
* Penyebab utama
* Modul terdampak
* Tingkat dampak
* Solusi yang diterapkan

---

# Change Management

Setiap perubahan harus didokumentasikan.

Minimal mencakup:

* File yang diubah.
* Alasan perubahan.
* Ringkasan perubahan.
* Dampak terhadap sistem.

---

# Quality Criteria

Perbaikan harus:

* Menyelesaikan bug.
* Tidak mengubah requirement.
* Tidak menurunkan kualitas kode.
* Tidak menyebabkan regresi yang diketahui.
* Tetap mengikuti blueprint.

---

# Validation Checklist

Sebelum selesai, Debug Agent harus memastikan:

✓ Seluruh bug yang ditugaskan telah diperbaiki.

✓ Root Cause Analysis selesai.

✓ Perubahan terdokumentasi.

✓ Tidak ada perubahan di luar ruang lingkup.

✓ Artefak berhasil diperbarui.

---

# Handoff

Debug Agent mengirim seluruh artefak kepada Orchestrator.

Orchestrator memperbarui source code dan meneruskan workflow kembali ke:

**QA Agent**

QA Agent melakukan verifikasi ulang terhadap hasil perbaikan.

Hanya setelah QA menyatakan hasil memadai, workflow dapat dilanjutkan ke:

**Security Auditing Agent**

---

# Success Criteria

Debug Agent dinyatakan berhasil apabila:

* Bug yang ditugaskan telah diperbaiki.
* Penyebab bug telah didokumentasikan.
* Perubahan sesuai blueprint.
* Tidak ada perubahan yang tidak berkaitan dengan bug.

---

# Design Principles

Debug Agent harus selalu:

* Root Cause Driven.
* Minimal Change.
* Blueprint Compliant.
* Traceable.
* Predictable.
* Maintainable.

Debug Agent bertugas meningkatkan kualitas implementasi melalui perbaikan yang terukur, bukan melalui perubahan desain atau penambahan fitur.

---

# Next Document

Dokumen berikutnya:

**docs/10-security-agent.md**

Dokumen ini menjelaskan bagaimana Security Auditing Agent melakukan audit keamanan terhadap aplikasi sebelum proses deployment.

---

# End of Document
