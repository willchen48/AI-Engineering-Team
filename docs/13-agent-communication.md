# docs/13-agent-communication.md

# Agent Communication Protocol

> **Version:** 1.0.0 Alpha
> **Status:** Draft

---

# Purpose

Dokumen ini mendefinisikan standar komunikasi antara Orchestrator dan seluruh AI Agent.

Blueprint v1.0 menggunakan **Orchestrator-Centric Communication Model**, di mana seluruh komunikasi hanya dilakukan melalui Orchestrator.

Dokumen ini menjadi kontrak komunikasi resmi yang wajib dipatuhi oleh seluruh AI Agent.

---

# Communication Principles

Seluruh komunikasi harus mengikuti prinsip berikut:

* Orchestrator sebagai pusat komunikasi.
* Tidak ada komunikasi langsung antar Agent.
* Semua pesan bersifat terstruktur.
* Semua artefak dikirim melalui Orchestrator.
* Seluruh komunikasi dapat ditelusuri (Traceable).
* Seluruh komunikasi harus dapat direproduksi.

---

# Communication Model

```text
User
 │
 ▼
Orchestrator
 │
 ▼
Agent
 │
 ▼
Orchestrator
 │
 ▼
Next Agent
 │
 ▼
User
```

Blueprint v1.0 tidak mengizinkan komunikasi horizontal antar Agent.

---

# Communication Lifecycle

Setiap komunikasi mengikuti siklus berikut:

1. Orchestrator membuat Job.
2. Orchestrator mengirim Job ke Agent.
3. Agent memproses Job.
4. Agent menghasilkan Output.
5. Agent mengirim Output ke Orchestrator.
6. Orchestrator melakukan validasi.
7. Orchestrator menentukan langkah berikutnya.

---

# Standard Message Structure

Setiap Job minimal memiliki informasi berikut:

* Job ID
* Project ID
* Workflow Stage
* Target Agent
* Input Artifacts
* Instructions
* Timestamp

---

# Standard Response Structure

Setiap Agent mengembalikan hasil minimal berisi:

* Job ID
* Project ID
* Agent Name
* Execution Status
* Output Artifacts
* Execution Summary
* Error Information (jika ada)
* Timestamp

---

# Workflow Status

Status standar workflow:

```text
CREATED

QUEUED

RUNNING

COMPLETED

FAILED

CANCELLED
```

Status hanya boleh diubah oleh Orchestrator.

---

# Agent Status

Status eksekusi Agent:

```text
IDLE

WAITING

RUNNING

COMPLETED

FAILED
```

Status Agent dilaporkan kepada Orchestrator.

---

# Artifact Exchange

Seluruh pertukaran artefak mengikuti aturan:

* Agent menerima artefak dari Orchestrator.
* Agent menghasilkan artefak baru.
* Agent tidak mengubah artefak Agent lain.
* Orchestrator menyimpan seluruh versi artefak.

---

# Handoff Protocol

Handoff hanya dapat dilakukan apabila:

* Agent selesai bekerja.
* Output valid.
* Tidak ada error kritis.
* Seluruh artefak tersedia.

Jika salah satu syarat tidak terpenuhi, Orchestrator tidak boleh meneruskan workflow.

---

# Error Communication

Jika Agent mengalami kegagalan, Agent harus mengirimkan:

* Job ID
* Project ID
* Agent Name
* Error Type
* Error Message
* Execution Stage
* Failure Summary

Orchestrator menentukan apakah Job akan diulang atau workflow dihentikan.

---

# Retry Communication

Retry hanya dapat dilakukan oleh Orchestrator.

Setiap retry harus dicatat dalam Execution History.

Agent tidak boleh melakukan retry secara mandiri.

---

# Communication Rules

Seluruh AI Agent wajib:

* Menggunakan format komunikasi standar.
* Tidak membuat komunikasi di luar workflow.
* Tidak menghubungi Agent lain secara langsung.
* Tidak mengubah status workflow.
* Tidak mengubah status Agent lain.

---

# Validation Checklist

Sebelum komunikasi dianggap valid:

✓ Job ID tersedia.

✓ Project ID tersedia.

✓ Agent Name tersedia.

✓ Input lengkap.

✓ Output lengkap.

✓ Status valid.

✓ Timestamp tersedia.

---

# Success Criteria

Communication Protocol dinyatakan berhasil apabila:

* Seluruh Agent menggunakan format yang sama.
* Tidak ada komunikasi langsung antar Agent.
* Seluruh artefak dapat ditelusuri.
* Seluruh workflow dapat diaudit.
* Orchestrator mampu mengendalikan seluruh komunikasi.

---

# Design Principles

Communication Protocol harus selalu:

* Standardized.
* Predictable.
* Traceable.
* Deterministic.
* Blueprint Compliant.
* Orchestrator Driven.

Seluruh komunikasi dalam AI Engineering Team harus mengikuti dokumen ini tanpa pengecualian.

---

# Next Document

Dokumen berikutnya:

**docs/14-project-memory.md**

Dokumen ini menjelaskan bagaimana Orchestrator mengelola state proyek, artefak, riwayat eksekusi, dan memori proyek selama seluruh workflow berlangsung.

---

# End of Document
