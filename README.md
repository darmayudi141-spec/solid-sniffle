graph TD
    A([MULAI]) --> B[/Input Email & WA/]
    B --> C[Registrasi Akun & Verifikasi OTP]
    C --> D[/Isi Biodata & Unggah Dokumen/]
    D --> E[Validasi Otomatis Format & Ukuran]
    E --> F{Format Valid?}
    
    F -- TIDAK --> G[Tampilkan Pesan Error]
    G --> D
    
    F -- YA --> H[Generate Tagihan & Nomor VA]
    H --> I[/Transaksi Bayar via VA / E-Wallet/]
    I --> J[Webhook: Auto-Update Status LUNAS]
    J --> K[Pemeriksaan Berkas oleh Verifikator]
    K --> L{Dokumen Valid?}
    
    L -- TIDAK --> M[Input Catatan Revisi Dokumen]
    L -- YA --> N[System Approve & Generate Kartu Ujian]
    
    M --> O[Kirim Notifikasi WA / Email]
    N --> O
    
    O --> P{Status Check}
    P -- REVISI --> Q[/Perbaiki & Unggah Dokumen Revisi/]
    Q --> K
    
    P -- DISETUJUI --> R[/Unduh Kartu Ujian / Bukti Lunas/]
    R --> S([SELESAI])
```eof
