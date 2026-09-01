# Workstation Policy

## Struktur folder
- `D:\Dev\Projects` untuk source code dan project aktif
- `D:\Dev\AI` untuk model, dataset, cache, download, dan workspace AI
- `D:\Dev\ToolCache` untuk cache tool developer
- `D:\Dev\SDK` untuk SDK dan toolchain
- `D:\Dev\Docker` untuk data Docker lokal
- `D:\Dev\Scripts` untuk otomasi dan utility
- `D:\Dev\Downloads` untuk staging file masuk
- `D:\Dev\Archives` untuk arsip lama
- `D:\Dev\Temp` untuk file sementara
- `D:\Dev\Backup` untuk backup workstation
- `D:\Dev\Documents` untuk dokumen kerja

## Aturan workspace
- Workspace utama: `D:\Dev`
- Project aktif selalu di `D:\Dev\Projects`
- Jangan taruh source code di Desktop atau Downloads
- AI asset tetap dipisah dari source code

## Aturan project
- Satu project satu folder root
- README wajib ada
- Konfigurasi project disimpan dekat source code
- Path absolut di config harus dihindari bila bisa

## Aturan cache
- Cache developer masuk `D:\Dev\ToolCache`
- Cache bisa dibersihkan bila regenerable
- Jangan campur cache dengan source code

## Aturan backup
- Backup konfigurasi masuk `D:\Dev\Backup`
- Backup source code hanya bila perlu dan diberi label jelas
- Jangan simpan backup aktif di folder project

## Aturan cleanup
- Boleh bersihkan cache, temp, download staging, dan archive lama yang sudah dipastikan aman
- Jangan bersihkan project, model, workspace, atau backup aktif
- Jika ragu, statusnya verifikasi dulu
