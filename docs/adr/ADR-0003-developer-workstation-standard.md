# ADR-0003: Developer Workstation Standard

## Status

Proposed

## Context

DevOS berkembang dari pengalaman operasi nyata, bukan teori kosong. Selama audit workstation dan migrasi repository, pola yang berulang muncul: cache menumpuk, backup perlu disiplin, struktur `D:\Dev` harus jelas, dan perubahan repository harus tetap dapat diaudit.

Investigasi terhadap OpenCode dan 9router menunjukkan bahwa AI tools harus diperlakukan sebagai bagian dari workflow workstation, bukan sekadar aplikasi tambahan. OpenCode dipakai untuk interaksi repository-aware dan 9router dipakai sebagai lapisan routing model, sehingga keduanya butuh standar penggunaan yang konsisten, aman, dan mudah direproduksi.

Pengalaman cleanup cache dan backup memperlihatkan bahwa workstation developer perlu standar yang membatasi risiko dari file sementara, state lokal, dan artefak regenerable. Pengalaman migrasi repository juga menunjukkan bahwa tanpa aturan workstation yang eksplisit, struktur folder, konteks proyek, dan lokasi data pendukung cepat menjadi tidak seragam.

Struktur `D:\Dev` menjadi penting sebagai boundary operasional: workspace utama, script, AI assets, cache, backup, dan project area harus punya peran yang jelas. Tanpa standardisasi, audit menjadi lambat dan recovery menjadi tidak pasti.

## Problem

Tanpa standard workstation yang eksplisit, DevOS bergantung pada kebiasaan manual dan ingatan operator.

Masalah yang muncul:

- audit workstation sulit diulang karena kondisi mesin tidak seragam
- cache cleanup dilakukan ad hoc, bukan sebagai praktik standar
- backup ada, tetapi tidak selalu terhubung ke keputusan operasional
- penggunaan AI tools tidak punya batasan jelas antara workspace, prompt, dan routing
- `D:\Dev` dapat berubah menjadi area campur aduk antara data aktif, data sementara, dan data cadangan
- migrasi repository menjadi mahal karena konteks lokal tidak terstruktur

## Design Principles

- Safety first: perubahan workstation harus bisa dibatalkan atau direkonstruksi
- Reproducibility: setup dan recovery harus bisa diulang dengan hasil serupa
- Auditability: lokasi data, tools, dan backup harus mudah ditelusuri
- Separation of concerns: workspace, cache, backup, dan AI tools harus dipisah secara konseptual
- Minimal drift: struktur lokal harus selaras dengan repository taxonomy dan documentation taxonomy
- Tool neutrality: standard harus berlaku untuk OpenCode, 9router, dan AI tools lain tanpa bergantung pada satu vendor

## Decision

Tetapkan Developer Workstation Standard sebagai standar operasional untuk environment DevOS.

Standard ini menetapkan bahwa:

- audit workstation adalah langkah dasar sebelum perubahan besar
- cache cleanup adalah aktivitas rutin untuk artefak regenerable
- backup adalah bagian dari workflow, bukan tindakan reaktif
- `D:\Dev` adalah root operasional utama untuk workspace developer
- AI tools dipakai lewat pola penggunaan yang aman, terdokumentasi, dan dapat diaudit
- migrasi repository harus mengikuti struktur yang konsisten dengan repository taxonomy DevOS
- OpenCode dan 9router diperlakukan sebagai bagian dari toolchain workstation yang diatur oleh standard ini

ADR ini menetapkan prinsip dan batasan, bukan langkah implementasi teknis.

## Consequences

- Workflow workstation menjadi lebih seragam
- Cleanup cache dan backup lebih mudah diaudit
- Penggunaan AI tools lebih konsisten lintas sesi dan lintas agent
- Struktur `D:\Dev` menjadi lebih jelas untuk operator dan reviewer
- Migrasi repository berikutnya akan lebih mudah karena boundary kerja sudah didefinisikan
- Standard baru menambah beban dokumentasi, tetapi mengurangi ambiguitas operasional

## Alternatives Considered

- Biarkan workstation dikelola lewat kebiasaan individual
- Jadikan backup dan cache cleanup sebagai catatan informal, bukan standard
- Dokumentasikan OpenCode dan 9router hanya di README, tanpa standard workstation
- Perlakukan `D:\Dev` sebagai detail lokal yang tidak perlu distandardisasi
- Pisahkan migrasi repository dari standard workstation
