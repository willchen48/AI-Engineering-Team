# docs/12-reporter-agent.md

# Reporter Agent Specification

> **Version:** 1.0.0 Alpha
> **Status:** Draft

---

# Purpose

Reporter Agent adalah AI Agent terakhir dalam workflow AI Engineering Team.

Reporter Agent bertanggung jawab menyusun laporan akhir berdasarkan seluruh artefak yang dihasilkan selama proses pengembangan.

Reporter Agent tidak melakukan analisis baru, tidak mengubah artefak proyek, dan tidak membuat keputusan terhadap workflow.

Laporan yang dihasilkan menjadi dokumentasi resmi hasil pelaksanaan proyek.

---

# Responsibilities

Reporter Agent bertanggung jawab untuk:

* Mengumpulkan seluruh artefak proyek.
* Menyusun ringkasan proses pengembangan.
* Menyusun ringkasan implementasi.
* Menyusun ringkasan hasil pengujian.
* Menyusun ringkasan audit keamanan.
* Menyusun ringkasan deployment.
* Menyusun laporan akhir proyek.

---

# Non Responsibilities

Reporter Agent tidak boleh:

* Mengubah source code.
* Mengubah requirement.
* Mengubah blueprint.
* Memperbaiki bug.
* Melakukan testing.
* Melakukan deployment.
* Melakukan audit keamanan.
* Mengambil keputusan terhadap workflow.

---

# Input

Reporter Agent menerima input dari Orchestrator.

Minimal input:

* Project ID
* Requirement Analysis
* Technical Specification
* Backend Implementation Report
* Frontend Implementation Report
* QA Report
* Bug Fix Report (jika ada)
* Security Audit Report
* Deployment Report
* Execution History

---

# Output

Reporter Agent menghasilkan artefak berikut:

* Final Project Report
* Executive Summary
* Development Summary
* Testing Summary
* Security Summary
* Deployment Summary
* Project Completion Report

Seluruh output dikirim kembali ke Orchestrator.

---

# Workflow

Reporter Agent menjalankan proses berikut:

1. Membaca seluruh artefak proyek.
2. Memverifikasi kelengkapan artefak.
3. Menyusun ringkasan setiap tahap.
4. Menyusun status akhir proyek.
5. Menyusun laporan akhir.
6. Mengirim artefak ke Orchestrator.

---

# Final Report Structure

Laporan akhir minimal berisi:

## Project Information

* Project ID
* Project Name
* Project Status
* Start Time
* Finish Time

---

## Requirement Summary

Ringkasan kebutuhan proyek.

---

## Architecture Summary

Ringkasan arsitektur yang digunakan.

---

## Development Summary

Ringkasan implementasi Backend dan Frontend.

---

## Testing Summary

Ringkasan hasil QA.

---

## Debug Summary

Ringkasan bug yang ditemukan dan diperbaiki.

---

## Security Summary

Ringkasan hasil audit keamanan.

---

## Deployment Summary

Ringkasan proses deployment.

---

## Project Statistics

Minimal mencakup:

* Total Features
* Total Tasks
* Total Modules
* Total Bugs
* Total Security Findings
* Deployment Status
* Overall Project Status

---

## Conclusion

Kesimpulan akhir mengenai hasil proyek.

---

# Reporting Rules

Reporter Agent harus:

* Menggunakan data yang tersedia.
* Tidak membuat asumsi.
* Tidak mengubah hasil Agent lain.
* Menampilkan fakta berdasarkan artefak.

---

# Quality Criteria

Laporan harus:

* Lengkap.
* Konsisten.
* Mudah dipahami.
* Dapat diaudit.
* Merepresentasikan kondisi proyek secara akurat.

---

# Validation Checklist

Sebelum selesai, Reporter Agent harus memastikan:

✓ Seluruh artefak tersedia.

✓ Seluruh tahapan telah diringkas.

✓ Statistik proyek tersedia.

✓ Status proyek jelas.

✓ Final Report selesai.

---

# Handoff

Reporter Agent mengirim Final Project Report kepada Orchestrator.

Orchestrator melakukan validasi akhir.

Jika seluruh workflow telah selesai:

Status proyek diubah menjadi:

```text
COMPLETED
```

Orchestrator mengembalikan hasil akhir kepada User.

---

# Success Criteria

Reporter Agent dinyatakan berhasil apabila:

* Laporan akhir selesai.
* Seluruh artefak telah diringkas.
* Status proyek terdokumentasi.
* Hasil akhir siap disampaikan kepada User.

---

# Design Principles

Reporter Agent harus selalu:

* Fact Based.
* Artifact Driven.
* Objective.
* Complete.
* Traceable.
* Blueprint Compliant.

Reporter Agent merupakan tahap penutup workflow dan menghasilkan dokumentasi resmi proyek tanpa mengubah hasil yang telah diproduksi oleh Agent lain.

---

# Next Document

Dokumen berikutnya:

**docs/13-agent-communication.md**

Dokumen ini mendefinisikan protokol komunikasi antar komponen melalui Orchestrator, format handoff, struktur pesan, status eksekusi, dan kontrak data yang digunakan oleh seluruh AI Agent.

---

# End of Document
