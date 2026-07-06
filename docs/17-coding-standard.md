# docs/17-coding-standard.md

# Coding Standard Specification

> **Version:** 1.0.0 Alpha
> **Status:** Draft

---

# Purpose

Dokumen ini mendefinisikan standar penulisan kode untuk seluruh implementasi AI Engineering Team.

Seluruh AI Agent dan AI Coding Assistant wajib mengikuti standar ini agar source code tetap konsisten, mudah dipelihara, mudah diuji, dan mudah dikembangkan.

Dokumen ini berlaku untuk seluruh repository.

---

# Primary Objectives

Standar coding dibuat untuk:

* Menjaga konsistensi kode.
* Mengurangi kompleksitas.
* Mempermudah debugging.
* Mempermudah testing.
* Mempermudah maintenance.
* Mempermudah kolaborasi antar AI Agent.

---

# General Principles

Seluruh implementasi harus mengikuti prinsip berikut:

* Readability First.
* Simplicity Over Complexity.
* Single Responsibility Principle.
* Separation of Concerns.
* Explicit Over Implicit.
* Composition Over Inheritance.
* Blueprint Driven Development.

---

# Code Organization

Source code harus:

* Modular.
* Terstruktur.
* Konsisten.
* Mudah dinavigasi.
* Mudah dipahami.

Satu file hanya memiliki satu tujuan utama.

---

# Naming Convention

Penamaan harus:

* Konsisten.
* Deskriptif.
* Tidak menggunakan singkatan yang tidak jelas.
* Menggunakan istilah yang sesuai dengan domain proyek.

Contoh:

Baik:

* ProjectMemory
* WorkflowEngine
* SecurityAuditReport

Kurang baik:

* PM
* TempData
* Data1
* Utils2

---

# Function Rules

Setiap fungsi harus:

* Memiliki satu tanggung jawab.
* Memiliki nama yang jelas.
* Berukuran sekecil mungkin.
* Tidak memiliki efek samping yang tidak diperlukan.

Fungsi yang terlalu panjang harus dipecah menjadi fungsi yang lebih kecil.

---

# Class Rules

Setiap class harus:

* Memiliki satu tanggung jawab utama.
* Mudah diuji.
* Tidak memiliki dependensi yang tidak diperlukan.
* Tidak menjadi "God Object".

---

# Module Rules

Setiap module harus:

* Berdiri sendiri.
* Memiliki tanggung jawab yang jelas.
* Tidak bergantung pada implementasi internal module lain.

Komunikasi antar module dilakukan melalui interface yang jelas.

---

# Error Handling

Seluruh error harus:

* Ditangani secara eksplisit.
* Memiliki pesan yang jelas.
* Dicatat ke sistem logging.
* Tidak disembunyikan.

Silent failure tidak diperbolehkan.

---

# Logging Rules

Logging harus:

* Informatif.
* Konsisten.
* Tidak mengandung informasi sensitif.
* Memudahkan proses debugging.

---

# Configuration Rules

Seluruh konfigurasi harus:

* Dipisahkan dari source code.
* Tidak menggunakan hardcoded value.
* Dapat diubah tanpa mengubah implementasi.

Secret tidak boleh disimpan di dalam source code.

---

# Dependency Rules

Setiap dependency harus:

* Memiliki tujuan yang jelas.
* Digunakan secara aktif.
* Tidak berlebihan.
* Mudah diperbarui.

Dependency yang tidak digunakan harus dihapus.

---

# Code Reuse

Jika suatu logika dapat digunakan kembali:

* Jadikan reusable component.
* Hindari copy-paste.
* Hindari duplikasi implementasi.

---

# Documentation Rules

Setiap module harus memiliki dokumentasi yang menjelaskan:

* Tujuan.
* Tanggung jawab.
* Interface.
* Cara penggunaan (jika diperlukan).

Dokumentasi harus selalu diperbarui ketika implementasi berubah.

---

# Performance Guidelines

Implementasi harus:

* Efisien.
* Tidak melakukan pekerjaan yang tidak diperlukan.
* Menghindari proses berulang yang tidak perlu.
* Menggunakan sumber daya secara wajar.

Optimisasi prematur harus dihindari.

---

# Security Guidelines

Source code harus:

* Melakukan validasi input.
* Tidak menyimpan secret secara langsung.
* Menggunakan konfigurasi yang aman.
* Menghindari praktik yang berisiko.

---

# AI Coding Rules

AI Coding Assistant wajib:

* Membaca blueprint sebelum menghasilkan kode.
* Mengikuti struktur repository.
* Mengikuti tanggung jawab Agent.
* Tidak membuat implementasi di luar requirement.
* Tidak mengubah arsitektur.

Jika terjadi konflik, blueprint selalu menjadi referensi utama.

---

# Validation Checklist

Sebelum implementasi dianggap selesai:

✓ Struktur kode konsisten.

✓ Penamaan jelas.

✓ Tidak ada duplikasi yang tidak diperlukan.

✓ Error handling tersedia.

✓ Logging tersedia.

✓ Dokumentasi diperbarui.

✓ Blueprint tetap dipatuhi.

---

# Success Criteria

Implementasi dianggap memenuhi Coding Standard apabila:

* Mudah dipahami.
* Mudah diuji.
* Mudah dipelihara.
* Konsisten di seluruh repository.
* Tidak menyimpang dari blueprint.

---

# Design Principles

Coding Standard harus selalu:

* Clean.
* Consistent.
* Maintainable.
* Predictable.
* Testable.
* Blueprint Compliant.

Seluruh implementasi AI Engineering Team harus mengikuti dokumen ini tanpa pengecualian.

---

# Next Document

Dokumen berikutnya:

**docs/18-testing-standard.md**

Dokumen ini mendefinisikan standar pengujian yang wajib diterapkan sebelum workflow dapat dilanjutkan ke tahap berikutnya.

---

# End of Document
