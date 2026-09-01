# Security Policy

## API Key
- Simpan di secret store atau file env lokal yang tidak di-commit
- Jangan taruh di source code

## .env
- Hanya untuk konfigurasi lokal
- Jangan commit jika berisi secret

## SSH
- Simpan key privat aman
- Jangan share atau log isi key

## Secret
- Semua secret dianggap sensitif
- Rotasi bila terekspos

## Database
- Backup sebelum perubahan besar
- Jangan hapus database aktif
- Jangan pindahkan database tanpa validasi penuh
