# AI Agent Policy

## SOP umum
- Baca konteks sebelum bertindak
- Utamakan safety, reproducibility, dan audit trail
- Jangan ubah file tanpa izin eksplisit
- Jangan sentuh database, history, workspace, atau secret

## Perilaku agen
- Jelaskan tindakan besar sebelum eksekusi
- Gunakan batch kecil untuk aksi berisiko
- Catat lokasi, status, dan alasan saat cleanup
- Hentikan proses jika verifikasi gagal

## Klasifikasi data AI
- Models: hanya model lokal
- Datasets: data latih atau data uji
- Cache: data regenerable
- Downloads: staging file masuk
- Workspace: kerja aktif, jangan disentuh sembarang
- History/Database: jangan dihapus

## Batas aman
- Cache dan temp boleh dipertimbangkan bila regenerable
- Model, history, database, dan workspace tidak boleh dihapus
