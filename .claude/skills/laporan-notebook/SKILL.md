---
name: laporan-notebook
description: Menulis sel markdown pada notebook laporan praktikum berbahasa Indonesia (lesson learnt, jawaban tugas, jawaban HOTS, kesimpulan). Dipakai saat membuat atau menyunting notebook praktikum Komputasi Numerik atau mata kuliah sejenis, termasuk saat mengubah nada tulisan yang terlalu formal, terlalu santai, atau terdengar menggurui. Use when writing or editing Indonesian markdown cells in a lab-report Jupyter notebook.
---

# Menulis Markdown Laporan Praktikum

Sasarannya satu: tulisan terbaca seperti catatan mahasiswa yang mengerjakan sendiri praktikumnya, bukan seperti bab buku teks dan bukan seperti obrolan grup.

## Ragam bahasa

Pakai ragam konsultatif, yaitu setengah resmi seperti dokumentasi kerja.

- Terlalu kaku: "Berdasarkan hasil eksperimen yang telah dilaksanakan, dapat disimpulkan bahwa galat mengalami penurunan."
- Terlalu santai: "galatnya turun drastis banget, keren sih."
- Pas: "galatnya turun dari 2.06e-02 ke 1.22e-11 setelah n dinaikkan ke 4."

Aturan bentuk:

- kalimat aktif, verba kuat. "menganalisis", bukan "melakukan analisis".
- panjang kalimat bervariasi, selingi kalimat pendek.
- satu sapaan saja. Hindari "kita" yang menggurui; pakai bentuk impersonal, dan "saya" hanya untuk keputusan yang memang diambil sendiri (misalnya memilih definisi pengukuran atau menambahkan try/except).
- ikuti kesepakatan visual notebook yang sedang dikerjakan. Bila heading dan kalimat di notebook itu memakai huruf kecil, pertahankan.
- tidak ada em dash sebagai tanda baca, tidak ada emoji.

## Jangan menggurui dan jangan sok tahu

Ini penyebab nilai turun saat laporan dibaca dosen. Tiap klaim harus punya pijakan: angka dari output sendiri, atau sumber yang disebut namanya.

| Hindari | Ganti dengan |
|---|---|
| "masalah yang lebih serius bukan sekadar X, melainkan Y" | "selain X, hasilnya juga menunjukkan Y" |
| "library matematika tidak pernah memakai Taylor polos" | "menurut modul dan Burden & Faires (2011), library matematika biasanya mereduksi argumen lebih dulu" |
| "yang sesungguhnya terjadi adalah konvergensi titik demi titik" | "hasil ukur tadi cocok dengan konvergensi titik demi titik" |
| "inilah alasan analisis frekuensi efektif" | "pada percobaan ini efeknya terlihat: puncak 0.25 masih terbaca meski ada derau" |
| "tiap pilihan membawa galat bawaan yang harus disadari" | "tiap pilihan punya galat bawaannya sendiri" |

Penanda yang menyelamatkan tulisan dari kesan sok tahu: "pada percobaan ini", "untuk ketiga titik yang diuji", "dugaan saya", "menurut penjelasan modul", "sejauh yang saya baca", "berdasarkan Wallace (1992)".

Hindari pula kata mutlak yang tidak dibuktikan sendiri: selalu, pasti, tidak pernah, terbukti, jelas bahwa. Kalau memang terbukti dari tabel, tunjuk tabelnya.

## Istilah teknis

Pakai istilah yang benar-benar dipakai mahasiswa dan dosennya.

1. Kalau modul praktikum memakai istilah Indonesia untuk konsep itu, ikuti modul. Contoh: derau, pias, galat, suku, larik, kisi waktu.
2. Kalau modul tidak menyebut, pakai istilah teknis yang lazim di kelas, biasanya serapan Inggris: library matematika (bukan pustaka matematika), domain frekuensi (bukan ranah frekuensi), window Hamming (bukan jendela Hamming), presisi arbitrer, speedup, overshoot, noise floor.
3. Satu istilah untuk satu konsep sepanjang notebook, termasuk di komentar sel kode. Jangan derau di kode lalu noise di markdown.
4. Singkatan asing diberi kepanjangannya sekali di penyebutan pertama: DCT (discrete cosine transform), THD (total harmonic distortion), RMSE.

## Struktur tiap bagian

**Lesson learnt tiap task**: tiga butir bernomor. Tiap butir memuat minimal satu angka dari output sel di atasnya, lalu alasan singkatnya. Butir ketiga biasanya menghubungkan ke gambar atau ke modul lain.

**Jawaban tugas dan HOTS**: mulai dari tabel atau angka hasil, baru penjelasan, lalu implikasinya. Jawab persis yang ditanyakan soal. Kalau soal minta "berapa digit benar", sebutkan angkanya, jangan cuma menjelaskan konsep.

**Kesimpulan praktikum**: satu tabel perbandingan, lalu tiga sampai empat butir temuan yang mengacu ke angka yang sudah muncul di notebook.

## Konsistensi angka

Tiap angka di markdown harus sama persis dengan output sel kode yang tersimpan.

- Setelah menjalankan ulang notebook, periksa lagi angka di markdown. Yang paling sering berubah: hasil pengukuran waktu.
- Untuk angka yang memang berubah tiap eksekusi, tulis sebagai rentang atau bulatkan, dan sebutkan alasannya. Contoh: "sekitar 0.15 ms" dan "17x sampai 19x", disertai catatan bahwa angkanya berubah tiap eksekusi.
- Temuan tak terduga saat mengerjakan, misalnya OverflowError pada k = 171, justru layak ditulis apa adanya. Itu bukti pekerjaan dikerjakan sendiri.

## Pemeriksaan sebelum commit

1. Pindai kata santai: nggak, cuma, banget, bikin, gede, kayak, doang, jelek, mentok, nempel, kelewat, biar. Termasuk di komentar dan string print pada sel kode.
2. Pindai kalimat menggurui dan kata mutlak yang tidak berpijak pada data.
3. Pindai istilah yang tidak konsisten antara markdown dan sel kode.
4. Cek tiap angka markdown terhadap output tersimpan.
5. Cek em dash dan emoji, harus nol.
6. Baca nyaring satu paragraf. Kalau terdengar seperti orang yang sedang menceramahi, tulis ulang jadi laporan pengamatan.

## Pesan commit

Satu baris, tanpa badan pesan. Contoh: `feat: modul 2`, `style: samakan istilah notebook modul 2`. Tanpa baris co-authored dan tanpa tautan sesi.
