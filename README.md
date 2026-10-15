# LaboDev — Rilis Beta

Repo ini **hanya berisi artefak rilis** (installer Windows) untuk LaboDev.
Kode sumber ada di repo privat `Ikhsandi-Ramadani/LaboDev`.

## Cara rilis

Rilis **Beta** dipublikasikan otomatis dari branch `feat/windows-installer` oleh
workflow "Windows quality" di repo LaboDev. Setiap rilis memuat:

- `LaboDev-Setup-x64.exe` — installer Windows (self-contained)
- `LaboDev-Setup-x64.exe.sha256` — checksum SHA-256 untuk verifikasi berkas

Selalu verifikasi checksum sebelum menjalankan installer:

```powershell
Get-FileHash .\LaboDev-Setup-x64.exe -Algorithm SHA256
```

## Catatan teknis

Commit awal ini diperlukan karena GitHub membalas HTTP 409 ("Git Repository is empty")
untuk repo tanpa commit, sehingga langkah pembuatan tag rilis di workflow gagal.
