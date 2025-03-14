Agus Tini Sridewi / 2306276004 / ADPRO A

# Module 5: Java Profiling
<details>
    <summary><strong> 📷 Jmeter Before and After Optimization Screenshots & Conclusion</strong></summary>

##  Via GUI
### Test Plan 1 (Endpoint /all-student)
Before ⤵️
<img width="1470" alt="all student request (before)" src="https://github.com/user-attachments/assets/ca06fa0b-aa95-40e6-98da-28f8e44b743f" />
After ⤵️
<img width="1470" alt="all student request (after)" src="https://github.com/user-attachments/assets/ca5b26e2-2983-46b7-9158-86621b5ebe62" />

### Test Plan 2 (Endpoint /all-student-name)
Before ⤵️
<img width="1470" alt="all student name (before)" src="https://github.com/user-attachments/assets/17a51355-88ef-4ff2-b14b-33f857c4a493" />
After ⤵️
<img width="1470" alt="all student name (after)" src="https://github.com/user-attachments/assets/61f90b77-6905-48e1-aea1-860b810948fe" />

### Test Plan 3 (Endpoint /highest-gpa)
Before ⤵️
<img width="1470" alt="highest gpa (before)" src="https://github.com/user-attachments/assets/a7572fc3-fb80-41b5-9a63-7d3cdb1e065e" />
After ⤵️
<img width="1470" alt="highest gpa (after)" src="https://github.com/user-attachments/assets/3bb11bee-5108-40ae-9bca-c15205f88b21" />

## Via CLI
### Test Plan 1 (Endpoint /all-student)
Before ⤵️
<img width="1213" alt="all student request terminal (before)" src="https://github.com/user-attachments/assets/60d20435-4ae8-4c81-887d-5bb66443a067" />
After ⤵️
<img width="1151" alt="all student request terminal (after)" src="https://github.com/user-attachments/assets/893372ad-4c75-44bc-ac67-45fe6611826a" />

### Test Plan 2 (Endpoint /all-student-name)
Before ⤵️
<img width="1215" alt="all student name terminal (before)" src="https://github.com/user-attachments/assets/97014991-1d83-473b-ab32-131781dcf586" />
After ⤵️
<img width="1135" alt="all student name terminal (after)" src="https://github.com/user-attachments/assets/afff7e2d-6bce-41a7-a14f-632cb585a9d2" />

### Test Plan 3 (Endpoint /highest-gpa)
Before ⤵️
<img width="1214" alt="highest gpa terminal (before)" src="https://github.com/user-attachments/assets/cb7407dc-f6ca-484e-b1b2-79ec4decaae1" />
After ⤵️
<img width="1129" alt="highest gpa terminal (after)" src="https://github.com/user-attachments/assets/1ed3dda7-82ab-455a-a988-ec5eed40c2ea" />

### Conclusion
- Endpoint: `all-student`

Sebelum optimisasi: Waktu eksekusi rata-rata berada di kisaran ~45.000–46.000 ms.
Sesudah optimisasi: Waktu eksekusi rata-rata turun drastis menjadi hanya ~2.300 ms.
Performance improvement: 94.95%

- Endpoint: `all-student-name`

Sebelum optimisasi: Waktu eksekusi rata-rata berada di kisaran ~700–800 ms.
Sesudah optimisasi: Waktu eksekusi rata-rata turun drastis menjadi hanya ~60–90 ms.
Performance improvement: 90%

- Endpoint: `highest-gpa`

Sebelum optimisasi: Waktu eksekusi rata-rata berada di kisaran ~75 ms.
Sesudah optimisasi: Waktu eksekusi rata-rata turun drastis menjadi hanya ~15 ms.
Performance improvement: 80%

Penggunaan JMeter sebelum dan sesudah optimisasi di atas menunjukkan adanya penurunan waktu respon yang drastis di ketiga endpoint (all-student request, all-student-name, dan highest-gpa). 
Hal ini menandakan bahwa proses optimisasi berhasil meningkatkan efisiensi sistem secara menyeluruh.
</details>

<details>
    <summary><strong> 📌 Reflection </strong></summary>

1. What is the difference between the approach of performance testing with JMeter and profiling with IntelliJ Profiler in the context of optimizing application performance?
   
JMeter digunakan untuk melakukan performance testing dengan mensimulasikan beban pengguna, guna mengukur bagaimana sistem merespons dalam kondisi nyata. Ia lebih berfokus pada aspek eksternal 
seperti response time, throughput, dan kestabilan sistem. Sedangkan IntelliJ Profiler bekerja di level internal aplikasi. Ia memberikan insight detail tentang bagian mana dari kode yang paling 
banyak mengonsumsi CPU, alokasi memori, dan bahkan mendeteksi thread contention. Jadi, kalau JMeter memberi tahu "aplikasi lambat", IntelliJ Profiler menjawab "kode bagian mana yang bikin lambat".

2. How does the profiling process help you in identifying and understanding the weak points in your application?

Profiling membantu saya dalam mengidentifikasi dan memahami titik lemah aplikasi dengan memberikan informasi detail mengenai bagian mana dari kode yang paling banyak memakan sumber daya, 
seperti waktu eksekusi, alokasi memori, dan aktivitas thread. Dari hasil profiling tersebut, saya dapat melihat metode atau fungsi mana yang lambat, terlalu sering dipanggil, 
atau menyebabkan beban berlebih pada sistem. Dengan begitu, saya bisa fokus memperbaiki bagian-bagian yang menjadi penyebab utama penurunan performa aplikasi.

3. Do you think IntelliJ Profiler is effective in assisting you to analyze and identify bottlenecks in your application code?

Ya, sangat efektif. Terutama untuk mendeteksi bottleneck yang tidak bisa diketahui hanya dari hasil pengujian luar seperti JMeter.
Fitur visualisasi timeline CPU, memory snapshots, dan analysis terhadap garbage collection membantu saya mengetahui apakah sebuah 
performa lambat berasal dari kode saya, query database, atau alokasi memori berlebihan.

4. What are the main challenges you face when conducting performance testing and profiling, and how do you overcome these challenges?

Tantangan utama dalam performance testing dan profiling adalah memahami hasil profiling. 
Selain itu, saat mengubah kode untuk meningkatkan performa, ada risiko fitur yang sudah berjalan jadi terganggu.
Untuk mengatasi hal ini, saya berupaya memahami pattern umum dari profiling report dengan saksama agar memperoleh hasil yang akurat.

5. What are the main benefits you gain from using IntelliJ Profiler for profiling your application code?
   
Manfaat utama dari IntelliJ Profiler antara lain:
- Identifikasi Bottleneck Spesifik: Bisa langsung tahu metode atau class mana yang menyebabkan performa buruk.
- Deteksi Memory Leak: Terutama saat melihat memory snapshot, kita bisa menemukan object yang tertahan terlalu lama di heap.
- Analisis Thread dan CPU Usage: Membantu memahami apakah aplikasi kita mengalami deadlock atau thread starvation.
- Integrasi IDE: Karena langsung terintegrasi dengan IntelliJ, proses profiling dan debugging jadi seamless dan praktis.

6. How do you handle situations where the results from profiling with IntelliJ Profiler are not entirely consistent with findings from performance testing using JMeter?

Kalau hasil dari JMeter dan IntelliJ Profiler tidak selaras, pertama-tama saya cek ulang apakah skenario test dan dataset-nya sama. 
Bisa jadi perbedaannya muncul karena load yang dihasilkan JMeter memicu bottleneck yang tidak terjadi di local profiling. 
Untuk mengatasi ketidakkonsistenannya, saya gabungkan data dari keduanya dan bila perlu, tambahkan observasi lewat logs dan tracing tools.

7. What strategies do you implement in optimizing application code after analyzing results from performance testing and profiling? How do you ensure the changes you make do not affect the application's functionality?
   Strategi yang saya terapkan antara lain:
- Refactor metode yang berat — misalnya mengganti nested loop dengan struktur data yang lebih efisien.
- Optimasi query ke database — memastikann proses interaksi dengan database mempercepat eksekusi query.
- Optimasi Memori: Mengatasi kebocoran memori untuk menekan penggunaan sumber daya yang berlebihan.

Agar fungsionalitas aplikasi tetap berjalan dengan baik setelah optimasi, saya biasanya menerapkan beberapa langkah penting. 
Pertama, saya melakukan pengujian secara menyeluruh setiap kali ada perubahan yang diterapkan. 
Kemudian, saya membandingkan hasil kinerja sebelum dan sesudah proses optimasi untuk melihat apakah ada peningkatan yang signifikan. 
Terakhir, saya juga memantau performa aplikasi secara langsung setelah perubahan diterapkan, guna memastikan bahwa perbaikan yang dilakukan benar-benar memberikan dampak positif
</details>

