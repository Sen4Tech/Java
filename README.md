# Proyek Java — Sen4Tech

README singkat agar mudah menjalankan dan membuka kode di Eclipse.

## Persyaratan
- Java JDK (disarankan LTS: Java 11 atau Java 17). Pastikan `java -version` dan `javac -version` bekerja.
- Git (untuk clone repo).
- Eclipse IDE for Java Developers (atau Eclipse IDE for Java and  DSL/EE sesuai kebutuhan).
- (Opsional) Maven atau Gradle jika proyek menggunakan salah satu.

## Clone repository
```bash
git clone https://github.com/Sen4Tech/Java.git
cd Java
```

## Cara membuka di Eclipse

Berikut beberapa cara tergantung tipe proyek di repo (standar Java, Maven, atau Gradle).

1. Buka Eclipse
   - Pastikan Eclipse menggunakan JDK yang benar: Window → Preferences → Java → Installed JREs. Pilih JDK (bukan JRE) dan pastikan JAVA_HOME mengarah ke JDK jika perlu.

2. Jika proyek adalah proyek Maven (ada file `pom.xml`):
   - File → Import...
   - Pilih Maven → Existing Maven Projects → Next
   - Browse ke folder hasil clone (folder `Java`) → Finish
   - Tunggu Eclipse mengunduh dependency dan membangun project.
   - Untuk menjalankan kelas dengan `main`:
     - Buka file Java yang berisi `public static void main(String[] args)`, klik kanan → Run As → Java Application.
   - Jika ingin menjalankan maven dari Eclipse: Run As → Maven build... (atur goal, mis. `clean package`).

3. Jika proyek adalah Gradle (ada `build.gradle` atau `gradlew`):
   - File → Import...
   - Pilih Gradle → Existing Gradle Project → Next
   - Pilih folder proyek → Finish
   - Jika diminta, gunakan wrapper (recommended) atau local Gradle.
   - Jalankan kelas main seperti biasa: klik kanan → Run As → Java Application.
   - Atau jalankan tugas Gradle: Run As → Gradle Task.

4. Jika proyek hanya file .java (tanpa build tool):
   - File → Import...
   - Pilih General → Existing Projects into Workspace jika ada file `.project`/Eclipse, atau
   - Pilih General → File System → Next → pilih folder `src` atau seluruh folder proyek → Finish.
   - Atau buat New → Java Project, lalu tambahkan source folder dan file.
   - Pastikan Build Path menunjuk ke JDK: Project → Properties → Java Build Path → Libraries.
   - Jalankan main: klik kanan pada file → Run As → Java Application.

5. Setting Run Configuration (opsional)
   - Run → Run Configurations...
   - Buat Java Application baru, tentukan Project dan Main class, atur VM arguments atau program arguments bila perlu.
   - Simpan dan gunakan untuk menjalankan ulang.

## Troubleshooting umum di Eclipse
- "Could not find or load main class" → Pastikan package declaration cocok dan Run Configuration menunjuk ke class dengan package lengkap (mis. com.example.Main).
- Error dependency Maven/Gradle → Right-click project → Maven → Update Project... (untuk Maven) atau Gradle → Refresh Gradle Project.
- Eclipse tidak menggunakan JDK yang benar → Periksa Installed JREs dan Project → Properties → Java Compiler / Installed JREs.
- Project tidak terlihat sebagai Maven/Gradle → Hapus project dari workspace (pilih "Do not delete contents") lalu import ulang dengan opsi Maven/Gradle yang sesuai.

## Menjalankan dari terminal (jika perlu)
Jika hanya file .java:
```bash
find . -name "*.java" > sources.txt
javac @sources.txt
java com.example.Main
```
Jika Maven:
```bash
mvn package
java -jar target/*.jar
```
Jika Gradle:
```bash
./gradlew build
java -jar build/libs/*.jar
```

Catatan: Ganti `com.example.Main` dengan nama package + kelas main yang ada di repo.

---

Saya menambahkan langkah khusus membuka proyek di Eclipse dan troubleshooting yang umum. Kalau Anda mau, saya dapat:
- Sesuaikan README ini langsung dengan struktur paket/kelas main dari repo (butuh nama kelas main atau saya bisa cek repo),
- atau buat instruksi bahasa Inggris jika diperlukan.
