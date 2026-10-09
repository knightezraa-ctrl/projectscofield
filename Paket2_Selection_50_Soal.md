# Paket 2 — Selection: if, else if, switch (50 Soal Cerita)

Materi: if, if-else, else-if bertingkat, if bersarang (nested), operator logika (`&&`, `||`, `!`), dan switch-case. Semua soal di paket ini dikerjakan tanpa perulangan.

Cara latihan: baca soal dan contoh tampilan, ketik sendiri dulu, baru cocokkan dengan jawaban.

---

### Soal 1. Termometer Tabib Desa

Tabib memeriksa suhu badan pasien: di bawah 35 °C hipotermia, 35 sampai 37.5 normal, di atas 37.5 sampai 39 demam, di atas 39 demam tinggi.

Contoh tampilan:
```
Suhu badan pasien (C): 38.2
Demam, beri ramuan penurun panas.
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double suhuPasienTabib;
    cout << "Suhu badan pasien (C): ";
    cin >> suhuPasienTabib;
    if (suhuPasienTabib < 35) cout << "Hipotermia! Segera hangatkan pasien." << endl;
    else if (suhuPasienTabib <= 37.5) cout << "Suhu normal, pasien sehat." << endl;
    else if (suhuPasienTabib <= 39) cout << "Demam, beri ramuan penurun panas." << endl;
    else cout << "Demam tinggi! Pasien harus dirawat." << endl;
    return 0;
}
```

### Soal 2. Lampu Lalu Lintas Kota Tua

Masukkan kode warna lampu (M, K, atau H) dan tampilkan perintah untuk pengendara dengan switch. Huruf kecil juga diterima.

Contoh tampilan:
```
Warna lampu (M/K/H): k
Kuning: bersiap, kurangi kecepatan.
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    char warnaLampu;
    cout << "Warna lampu (M/K/H): ";
    cin >> warnaLampu;
    switch (warnaLampu) {
        case 'M': case 'm': cout << "Merah: berhenti!" << endl; break;
        case 'K': case 'k': cout << "Kuning: bersiap, kurangi kecepatan." << endl; break;
        case 'H': case 'h': cout << "Hijau: silakan jalan." << endl; break;
        default: cout << "Lampu rusak, panggil petugas!" << endl;
    }
    return 0;
}
```

### Soal 3. Jadwal Pasar Mingguan

Pasar desa buka sesuai hari. Masukkan nomor hari 1–7, tampilkan nama hari dan barang yang dijual. Gunakan switch.

Contoh tampilan:
```
Nomor hari (1-7): 3
Rabu - pasar ternak
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int nomorHariPasar;
    cout << "Nomor hari (1-7): ";
    cin >> nomorHariPasar;
    switch (nomorHariPasar) {
        case 1: cout << "Senin - pasar sayur" << endl; break;
        case 2: cout << "Selasa - pasar ikan" << endl; break;
        case 3: cout << "Rabu - pasar ternak" << endl; break;
        case 4: cout << "Kamis - pasar kain" << endl; break;
        case 5: cout << "Jumat - pasar rempah" << endl; break;
        case 6: cout << "Sabtu - pasar loak" << endl; break;
        case 7: cout << "Minggu - pasar libur" << endl; break;
        default: cout << "Nomor hari tidak dikenal!" << endl;
    }
    return 0;
}
```

### Soal 4. Kalender Bulan Penyihir

Masukkan nomor bulan dan tahun, tampilkan jumlah hari di bulan tersebut. Februari 29 hari jika tahun kabisat. Gunakan switch dengan case bertumpuk.

Contoh tampilan:
```
Bulan dan tahun: 2 2028
Bulan 2 tahun 2028 punya 29 hari
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int bulanSihir, tahunSihir, hariDalamBulan;
    cout << "Bulan dan tahun: ";
    cin >> bulanSihir >> tahunSihir;
    switch (bulanSihir) {
        case 1: case 3: case 5: case 7: case 8: case 10: case 12:
            hariDalamBulan = 31; break;
        case 4: case 6: case 9: case 11:
            hariDalamBulan = 30; break;
        case 2:
            if ((tahunSihir % 4 == 0 && tahunSihir % 100 != 0) || tahunSihir % 400 == 0) hariDalamBulan = 29;
            else hariDalamBulan = 28;
            break;
        default:
            cout << "Bulan tidak valid!" << endl;
            return 0;
    }
    cout << "Bulan " << bulanSihir << " tahun " << tahunSihir << " punya " << hariDalamBulan << " hari" << endl;
    return 0;
}
```

### Soal 5. Kompas Saldo Pedagang

Pedagang mencatat untung (positif), rugi (negatif), atau impas (nol) dari laba hariannya.

Contoh tampilan:
```
Laba hari ini: -15000
Rugi Rp15000, evaluasi dagangan.
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    long long labaHarian;
    cout << "Laba hari ini: ";
    cin >> labaHarian;
    if (labaHarian > 0) cout << "Untung Rp" << labaHarian << ", lanjutkan!" << endl;
    else if (labaHarian < 0) cout << "Rugi Rp" << -labaHarian << ", evaluasi dagangan." << endl;
    else cout << "Impas, tidak untung tidak rugi." << endl;
    return 0;
}
```

### Soal 6. Raksasa Terbesar di Lembah

Tiga raksasa diukur tingginya. Tentukan raksasa tertinggi memakai if dan operator &&.

Contoh tampilan:
```
Tinggi tiga raksasa (m): 12 19 15
Raksasa Hutan tertinggi: 19 m
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int raksasaBukit, raksasaHutan, raksasaSungai;
    cout << "Tinggi tiga raksasa (m): ";
    cin >> raksasaBukit >> raksasaHutan >> raksasaSungai;
    if (raksasaBukit >= raksasaHutan && raksasaBukit >= raksasaSungai)
        cout << "Raksasa Bukit tertinggi: " << raksasaBukit << " m" << endl;
    else if (raksasaHutan >= raksasaBukit && raksasaHutan >= raksasaSungai)
        cout << "Raksasa Hutan tertinggi: " << raksasaHutan << " m" << endl;
    else
        cout << "Raksasa Sungai tertinggi: " << raksasaSungai << " m" << endl;
    return 0;
}
```

### Soal 7. Peri Terkecil di Taman

Tiga peri diukur tingginya dalam cm. Cari peri terkecil memakai variabel penampung dan if berurutan.

Contoh tampilan:
```
Tinggi tiga peri (cm): 14 9 11
Peri terkecil tingginya 9 cm
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int periMawar, periMelati, periAnggrek;
    cout << "Tinggi tiga peri (cm): ";
    cin >> periMawar >> periMelati >> periAnggrek;
    int periMungil = periMawar;
    if (periMelati < periMungil) periMungil = periMelati;
    if (periAnggrek < periMungil) periMungil = periAnggrek;
    cout << "Peri terkecil tingginya " << periMungil << " cm" << endl;
    return 0;
}
```

### Soal 8. Kategori Penduduk Kampung

Kelompokkan penduduk berdasarkan umur: 0–4 balita, 5–12 anak, 13–17 remaja, 18–59 dewasa, 60 ke atas lansia. Umur negatif tidak valid.

Contoh tampilan:
```
Umur warga: 15
Kategori: remaja
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int umurWarga;
    cout << "Umur warga: ";
    cin >> umurWarga;
    if (umurWarga < 0) cout << "Umur tidak valid!" << endl;
    else if (umurWarga <= 4) cout << "Kategori: balita" << endl;
    else if (umurWarga <= 12) cout << "Kategori: anak-anak" << endl;
    else if (umurWarga <= 17) cout << "Kategori: remaja" << endl;
    else if (umurWarga <= 59) cout << "Kategori: dewasa" << endl;
    else cout << "Kategori: lansia" << endl;
    return 0;
}
```

### Soal 9. Loket Bioskop Layar Tancap

Harga tiket: anak (< 12 tahun) Rp15.000, lansia (≥ 60) Rp20.000, dewasa Rp35.000. Jika menonton di akhir pekan (input Y), harga naik Rp5.000.

Contoh tampilan:
```
Umur penonton: 25
Akhir pekan? (Y/T): Y
Harga karcis: Rp40000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int umurPenonton, hargaKarcis;
    char akhirPekan;
    cout << "Umur penonton: ";
    cin >> umurPenonton;
    cout << "Akhir pekan? (Y/T): ";
    cin >> akhirPekan;
    if (umurPenonton < 12) hargaKarcis = 15000;
    else if (umurPenonton >= 60) hargaKarcis = 20000;
    else hargaKarcis = 35000;
    if (akhirPekan == 'Y' || akhirPekan == 'y') hargaKarcis += 5000;
    cout << "Harga karcis: Rp" << hargaKarcis << endl;
    return 0;
}
```

### Soal 10. Burung Beo Pengenal Huruf

Burung beo hanya bisa membedakan huruf vokal dan konsonan. Masukkan satu karakter, tentukan vokal, konsonan, atau bukan huruf.

Contoh tampilan:
```
Masukkan satu karakter: E
E adalah huruf vokal
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    char hurufBeo;
    cout << "Masukkan satu karakter: ";
    cin >> hurufBeo;
    if ((hurufBeo >= 'a' && hurufBeo <= 'z') || (hurufBeo >= 'A' && hurufBeo <= 'Z')) {
        if (hurufBeo == 'a' || hurufBeo == 'i' || hurufBeo == 'u' || hurufBeo == 'e' || hurufBeo == 'o' ||
            hurufBeo == 'A' || hurufBeo == 'I' || hurufBeo == 'U' || hurufBeo == 'E' || hurufBeo == 'O')
            cout << hurufBeo << " adalah huruf vokal" << endl;
        else
            cout << hurufBeo << " adalah huruf konsonan" << endl;
    } else {
        cout << hurufBeo << " bukan huruf, beo bingung!" << endl;
    }
    return 0;
}
```

### Soal 11. Penjaga Gerbang Karakter

Tentukan jenis karakter yang dimasukkan: huruf kapital, huruf kecil, angka, atau simbol.

Contoh tampilan:
```
Karakter: 7
Angka
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    char tandaMasuk;
    cout << "Karakter: ";
    cin >> tandaMasuk;
    if (tandaMasuk >= 'A' && tandaMasuk <= 'Z') cout << "Huruf kapital" << endl;
    else if (tandaMasuk >= 'a' && tandaMasuk <= 'z') cout << "Huruf kecil" << endl;
    else if (tandaMasuk >= '0' && tandaMasuk <= '9') cout << "Angka" << endl;
    else cout << "Simbol" << endl;
    return 0;
}
```

### Soal 12. Teriakan Prajurit Kelipatan

Jika angka kelipatan 3 dan 5, prajurit berteriak "SERBU BENTENG". Jika kelipatan 3 saja "SERBU", kelipatan 5 saja "BENTENG", selain itu sebut angkanya.

Contoh tampilan:
```
Angka komando: 45
SERBU BENTENG
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int angkaKomando;
    cout << "Angka komando: ";
    cin >> angkaKomando;
    if (angkaKomando % 3 == 0 && angkaKomando % 5 == 0) cout << "SERBU BENTENG" << endl;
    else if (angkaKomando % 3 == 0) cout << "SERBU" << endl;
    else if (angkaKomando % 5 == 0) cout << "BENTENG" << endl;
    else cout << angkaKomando << endl;
    return 0;
}
```

### Soal 13. Brankas Bank Kerajaan

Brankas terbuka hanya jika username "bendahara" dan PIN 4321 benar. Tampilkan pesan yang berbeda jika username salah atau PIN salah.

Contoh tampilan:
```
Username: bendahara
PIN: 1234
PIN salah, alarm berbunyi!
```

Jawaban:
```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string namaPengguna;
    int pinBrankas;
    cout << "Username: ";
    cin >> namaPengguna;
    cout << "PIN: ";
    cin >> pinBrankas;
    if (namaPengguna == "bendahara") {
        if (pinBrankas == 4321) cout << "Akses diterima, brankas terbuka!" << endl;
        else cout << "PIN salah, alarm berbunyi!" << endl;
    } else {
        cout << "Username tidak terdaftar." << endl;
    }
    return 0;
}
```

### Soal 14. Kalkulator Saku Saudagar

Masukkan dua angka dan satu operator (+, -, *, /). Hitung dengan switch. Pembagian dengan nol harus ditolak.

Contoh tampilan:
```
Masukkan perhitungan (contoh 8 * 3): 45 / 0
Tidak bisa membagi dengan nol!
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double angkaKiri, angkaKanan;
    char tandaHitung;
    cout << "Masukkan perhitungan (contoh 8 * 3): ";
    cin >> angkaKiri >> tandaHitung >> angkaKanan;
    switch (tandaHitung) {
        case '+': cout << "Hasil: " << angkaKiri + angkaKanan << endl; break;
        case '-': cout << "Hasil: " << angkaKiri - angkaKanan << endl; break;
        case '*': cout << "Hasil: " << angkaKiri * angkaKanan << endl; break;
        case '/':
            if (angkaKanan == 0) cout << "Tidak bisa membagi dengan nol!" << endl;
            else cout << "Hasil: " << angkaKiri / angkaKanan << endl;
            break;
        default: cout << "Operator tidak dikenal!" << endl;
    }
    return 0;
}
```

### Soal 15. Angka Mutu Akademi Sihir

Ubah nilai huruf (A, B, C, D, E) menjadi angka mutu 4, 3, 2, 1, 0 dengan switch.

Contoh tampilan:
```
Nilai huruf: B
Angka mutu: 3
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    char hurufMutu;
    cout << "Nilai huruf: ";
    cin >> hurufMutu;
    switch (hurufMutu) {
        case 'A': cout << "Angka mutu: 4" << endl; break;
        case 'B': cout << "Angka mutu: 3" << endl; break;
        case 'C': cout << "Angka mutu: 2" << endl; break;
        case 'D': cout << "Angka mutu: 1" << endl; break;
        case 'E': cout << "Angka mutu: 0" << endl; break;
        default: cout << "Nilai huruf tidak dikenal!" << endl;
    }
    return 0;
}
```

### Soal 16. Pemeriksaan Prajurit Baru

Hitung indeks massa tubuh calon prajurit dan tentukan kategorinya: < 18.5 kurus, < 25 normal, < 30 gemuk, selebihnya obesitas.

Contoh tampilan:
```
Berat (kg) dan tinggi (m): 72 1.68
IMT: 25.5102
Kategori: gemuk
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double bobotCalon, tinggiCalon;
    cout << "Berat (kg) dan tinggi (m): ";
    cin >> bobotCalon >> tinggiCalon;
    double imtCalon = bobotCalon / (tinggiCalon * tinggiCalon);
    cout << "IMT: " << imtCalon << endl;
    if (imtCalon < 18.5) cout << "Kategori: kurus" << endl;
    else if (imtCalon < 25) cout << "Kategori: normal" << endl;
    else if (imtCalon < 30) cout << "Kategori: gemuk" << endl;
    else cout << "Kategori: obesitas" << endl;
    return 0;
}
```

### Soal 17. Tagihan Listrik Rumah Pandai Besi

Tarif per kWh: 0–100 kWh Rp1000, 101–200 kWh Rp1500, di atas 200 kWh Rp2000. Tarif berlaku untuk seluruh pemakaian. Tambahkan abonemen Rp20.000.

Contoh tampilan:
```
Pemakaian listrik (kWh): 175
Tarif per kWh: Rp1500
Total tagihan: Rp282500
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int pemakaianKwh, tarifSetrum;
    cout << "Pemakaian listrik (kWh): ";
    cin >> pemakaianKwh;
    if (pemakaianKwh <= 100) tarifSetrum = 1000;
    else if (pemakaianKwh <= 200) tarifSetrum = 1500;
    else tarifSetrum = 2000;
    int tagihanSetrum = pemakaianKwh * tarifSetrum + 20000;
    cout << "Tarif per kWh: Rp" << tarifSetrum << endl;
    cout << "Total tagihan: Rp" << tagihanSetrum << endl;
    return 0;
}
```

### Soal 18. Ekspedisi Kilat Merpati

Ongkos kirim per kg tergantung zona: zona 1 Rp8000, zona 2 Rp12000, zona 3 Rp18000. Berat di bawah 1 kg dihitung 1 kg. Gunakan switch untuk zona.

Contoh tampilan:
```
Berat paket (kg) dan zona (1-3): 0.6 2
Ongkos kirim: Rp12000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double beratPaket;
    int zonaTujuan, tarifZona;
    cout << "Berat paket (kg) dan zona (1-3): ";
    cin >> beratPaket >> zonaTujuan;
    if (beratPaket < 1) beratPaket = 1;
    switch (zonaTujuan) {
        case 1: tarifZona = 8000; break;
        case 2: tarifZona = 12000; break;
        case 3: tarifZona = 18000; break;
        default: cout << "Zona tidak tersedia!" << endl; return 0;
    }
    cout << "Ongkos kirim: Rp" << beratPaket * tarifZona << endl;
    return 0;
}
```

### Soal 19. Peta Harta Empat Kuadran

Titik harta karun (x, y) dicek berada di kuadran mana, di sumbu, atau di titik pusat.

Contoh tampilan:
```
Koordinat harta (x y): -3 7
Harta di kuadran II
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int posisiX, posisiY;
    cout << "Koordinat harta (x y): ";
    cin >> posisiX >> posisiY;
    if (posisiX == 0 && posisiY == 0) cout << "Harta di titik pusat peta!" << endl;
    else if (posisiX == 0) cout << "Harta di sumbu Y" << endl;
    else if (posisiY == 0) cout << "Harta di sumbu X" << endl;
    else if (posisiX > 0 && posisiY > 0) cout << "Harta di kuadran I" << endl;
    else if (posisiX < 0 && posisiY > 0) cout << "Harta di kuadran II" << endl;
    else if (posisiX < 0 && posisiY < 0) cout << "Harta di kuadran III" << endl;
    else cout << "Harta di kuadran IV" << endl;
    return 0;
}
```

### Soal 20. Ramalan Akar Persamaan Kuadrat

Peramal menghitung akar ax² + bx + c = 0. Gunakan diskriminan D = b² − 4ac: D > 0 dua akar berbeda, D = 0 akar kembar, D < 0 akar imajiner.

Contoh tampilan:
```
Nilai a b c: 1 -5 6
Dua akar berbeda: 3 dan 2
```

Jawaban:
```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main() {
    double koefA, koefB, koefC;
    cout << "Nilai a b c: ";
    cin >> koefA >> koefB >> koefC;
    double diskriminanRamal = koefB * koefB - 4 * koefA * koefC;
    if (diskriminanRamal > 0) {
        double akarPertama = (-koefB + sqrt(diskriminanRamal)) / (2 * koefA);
        double akarKedua = (-koefB - sqrt(diskriminanRamal)) / (2 * koefA);
        cout << "Dua akar berbeda: " << akarPertama << " dan " << akarKedua << endl;
    } else if (diskriminanRamal == 0) {
        cout << "Akar kembar: " << -koefB / (2 * koefA) << endl;
    } else {
        cout << "Akar imajiner, ramalan gagal!" << endl;
    }
    return 0;
}
```

### Soal 21. Salam Penjaga Menara

Penjaga menara menyapa sesuai jam (0–23): 4–10 pagi, 11–14 siang, 15–17 sore, selain itu malam.

Contoh tampilan:
```
Jam sekarang (0-23): 16
Selamat sore, pengembara!
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int jamMenara;
    cout << "Jam sekarang (0-23): ";
    cin >> jamMenara;
    if (jamMenara < 0 || jamMenara > 23) cout << "Jam tidak valid!" << endl;
    else if (jamMenara >= 4 && jamMenara <= 10) cout << "Selamat pagi, pengembara!" << endl;
    else if (jamMenara <= 14 && jamMenara >= 11) cout << "Selamat siang, pengembara!" << endl;
    else if (jamMenara >= 15 && jamMenara <= 17) cout << "Selamat sore, pengembara!" << endl;
    else cout << "Selamat malam, pengembara!" << endl;
    return 0;
}
```

### Soal 22. Ujian Pandai Besi

Murid pandai besi lulus jika nilai teori DAN nilai praktik minimal 60. Jika hanya salah satu yang kurang, tampilkan bagian mana yang harus diulang.

Contoh tampilan:
```
Nilai teori dan praktik: 75 52
Tidak lulus, ulangi ujian praktik.
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int skorTeori, skorPraktik;
    cout << "Nilai teori dan praktik: ";
    cin >> skorTeori >> skorPraktik;
    if (skorTeori >= 60 && skorPraktik >= 60) cout << "LULUS! Kamu resmi jadi pandai besi." << endl;
    else if (skorTeori < 60 && skorPraktik < 60) cout << "Tidak lulus, ulangi teori dan praktik." << endl;
    else if (skorTeori < 60) cout << "Tidak lulus, ulangi ujian teori." << endl;
    else cout << "Tidak lulus, ulangi ujian praktik." << endl;
    return 0;
}
```

### Soal 23. Beasiswa Perguruan Tinggi Kerajaan

Beasiswa penuh jika IPK ≥ 3.5 dan penghasilan orang tua < Rp3.000.000. Beasiswa sebagian jika IPK ≥ 3.0 dan penghasilan < Rp5.000.000. Selain itu tidak dapat.

Contoh tampilan:
```
IPK dan penghasilan orang tua: 3.2 2500000
Selamat! Beasiswa sebagian.
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double ipkPelamar;
    long long gajiOrtu;
    cout << "IPK dan penghasilan orang tua: ";
    cin >> ipkPelamar >> gajiOrtu;
    if (ipkPelamar >= 3.5 && gajiOrtu < 3000000) cout << "Selamat! Beasiswa penuh." << endl;
    else if (ipkPelamar >= 3.0 && gajiOrtu < 5000000) cout << "Selamat! Beasiswa sebagian." << endl;
    else cout << "Maaf, belum memenuhi syarat beasiswa." << endl;
    return 0;
}
```

### Soal 24. Suit Batu Gunting Kertas

Dua pemain memilih B (batu), G (gunting), atau K (kertas). Tentukan pemenangnya atau seri.

Contoh tampilan:
```
Pilihan pemain 1 dan 2 (B/G/K): G K
Pemain 1 menang!
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    char tanganSatu, tanganDua;
    cout << "Pilihan pemain 1 dan 2 (B/G/K): ";
    cin >> tanganSatu >> tanganDua;
    if (tanganSatu == tanganDua) cout << "Seri!" << endl;
    else if ((tanganSatu == 'B' && tanganDua == 'G') || (tanganSatu == 'G' && tanganDua == 'K') || (tanganSatu == 'K' && tanganDua == 'B'))
        cout << "Pemain 1 menang!" << endl;
    else
        cout << "Pemain 2 menang!" << endl;
    return 0;
}
```

### Soal 25. Batu Penimbang Dua Sifat

Sebuah batu bernomor dinilai dua sifatnya sekaligus dengan if bersarang: positif/negatif, lalu ganjil/genap.

Contoh tampilan:
```
Nomor batu: -8
Batu negatif genap
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int nomorBatuAjaib;
    cout << "Nomor batu: ";
    cin >> nomorBatuAjaib;
    if (nomorBatuAjaib == 0) {
        cout << "Batu netral (nol)" << endl;
    } else if (nomorBatuAjaib > 0) {
        if (nomorBatuAjaib % 2 == 0) cout << "Batu positif genap" << endl;
        else cout << "Batu positif ganjil" << endl;
    } else {
        if (nomorBatuAjaib % 2 == 0) cout << "Batu negatif genap" << endl;
        else cout << "Batu negatif ganjil" << endl;
    }
    return 0;
}
```

### Soal 26. Tilang Polisi Jalan Raya

Batas kecepatan 80 km/jam. Lebih 1–20 km/jam denda Rp250.000, lebih 21–40 denda Rp500.000, lebih dari 40 denda Rp1.000.000 dan SIM ditahan.

Contoh tampilan:
```
Kecepatan terekam (km/jam): 117
Denda Rp500000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int lajuPengendara;
    cout << "Kecepatan terekam (km/jam): ";
    cin >> lajuPengendara;
    int kelebihanLaju = lajuPengendara - 80;
    if (kelebihanLaju <= 0) cout << "Aman, tidak ada pelanggaran." << endl;
    else if (kelebihanLaju <= 20) cout << "Denda Rp250000" << endl;
    else if (kelebihanLaju <= 40) cout << "Denda Rp500000" << endl;
    else cout << "Denda Rp1000000 dan SIM ditahan!" << endl;
    return 0;
}
```

### Soal 27. Gaji Pegawai Istana per Golongan

Gaji pokok per golongan (switch): golongan 1 Rp3.000.000, 2 Rp4.500.000, 3 Rp6.000.000. Jika sudah menikah (Y), dapat tunjangan 10% dari gaji pokok.

Contoh tampilan:
```
Golongan (1-3): 2
Sudah menikah? (Y/T): Y
Gaji pokok : Rp4500000
Tunjangan  : Rp450000
Total gaji : Rp4950000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int golonganAbdi;
    char statusNikah;
    long long gajiAbdi;
    cout << "Golongan (1-3): ";
    cin >> golonganAbdi;
    cout << "Sudah menikah? (Y/T): ";
    cin >> statusNikah;
    switch (golonganAbdi) {
        case 1: gajiAbdi = 3000000; break;
        case 2: gajiAbdi = 4500000; break;
        case 3: gajiAbdi = 6000000; break;
        default: cout << "Golongan tidak ada!" << endl; return 0;
    }
    long long tunjanganKeluarga = 0;
    if (statusNikah == 'Y' || statusNikah == 'y') tunjanganKeluarga = gajiAbdi / 10;
    cout << "Gaji pokok : Rp" << gajiAbdi << endl;
    cout << "Tunjangan  : Rp" << tunjanganKeluarga << endl;
    cout << "Total gaji : Rp" << gajiAbdi + tunjanganKeluarga << endl;
    return 0;
}
```

### Soal 28. Kartu Member Toko Serba Ada

Member G (gold) diskon 15%, S (silver) 10%, B (bronze) 5%. Diskon hanya berlaku jika belanja minimal Rp100.000.

Contoh tampilan:
```
Jenis member (G/S/B): S
Total belanja: Rp250000
Diskon 10%: Rp25000
Bayar: Rp225000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    char jenisMember;
    double totalKeranjang;
    int persenMember = 0;
    cout << "Jenis member (G/S/B): ";
    cin >> jenisMember;
    cout << "Total belanja: Rp";
    cin >> totalKeranjang;
    if (totalKeranjang >= 100000) {
        if (jenisMember == 'G') persenMember = 15;
        else if (jenisMember == 'S') persenMember = 10;
        else if (jenisMember == 'B') persenMember = 5;
    }
    double potonganMember = totalKeranjang * persenMember / 100;
    cout << "Diskon " << persenMember << "%: Rp" << potonganMember << endl;
    cout << "Bayar: Rp" << totalKeranjang - potonganMember << endl;
    return 0;
}
```

### Soal 29. Juru Catat Tanggal Sah

Periksa apakah tanggal (hari bulan tahun) valid, termasuk 29 Februari hanya pada tahun kabisat.

Contoh tampilan:
```
Tanggal (hari bulan tahun): 29 2 2023
Tanggal tidak sah! Bulan itu hanya sampai 28.
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int tglCatat, blnCatat, thnCatat, batasTanggal;
    cout << "Tanggal (hari bulan tahun): ";
    cin >> tglCatat >> blnCatat >> thnCatat;
    if (blnCatat < 1 || blnCatat > 12) {
        cout << "Bulan tidak valid!" << endl;
        return 0;
    }
    if (blnCatat == 2) {
        bool kabisatCatat = (thnCatat % 4 == 0 && thnCatat % 100 != 0) || thnCatat % 400 == 0;
        batasTanggal = kabisatCatat ? 29 : 28;
    } else if (blnCatat == 4 || blnCatat == 6 || blnCatat == 9 || blnCatat == 11) {
        batasTanggal = 30;
    } else {
        batasTanggal = 31;
    }
    if (tglCatat >= 1 && tglCatat <= batasTanggal) cout << "Tanggal sah." << endl;
    else cout << "Tanggal tidak sah! Bulan itu hanya sampai " << batasTanggal << "." << endl;
    return 0;
}
```

### Soal 30. Jam Dinding Gaya Amerika

Ubah jam format 24 jam (jam menit) menjadi format 12 jam dengan AM/PM. Jam 0 menjadi 12 AM, jam 12 menjadi 12 PM.

Contoh tampilan:
```
Jam dan menit (format 24 jam): 0 45
Format 12 jam: 12:45 AM
```

Jawaban:
```cpp
#include <iostream>
#include <iomanip>
#include <string>
using namespace std;

int main() {
    int jamMiliter, menitMiliter;
    cout << "Jam dan menit (format 24 jam): ";
    cin >> jamMiliter >> menitMiliter;
    if (jamMiliter < 0 || jamMiliter > 23 || menitMiliter < 0 || menitMiliter > 59) {
        cout << "Waktu tidak valid!" << endl;
        return 0;
    }
    string penandaWaktu = (jamMiliter < 12) ? "AM" : "PM";
    int jamSipil = jamMiliter % 12;
    if (jamSipil == 0) jamSipil = 12;
    cout << "Format 12 jam: " << jamSipil << ":" << setw(2) << setfill('0') << menitMiliter << " " << penandaWaktu << endl;
    return 0;
}
```

### Soal 31. Jarak Dua Pemanah

Dua pemanah berdiri di posisi (bisa negatif) pada garis lurus. Hitung jarak keduanya (nilai mutlak selisih) dengan if, tanpa fungsi abs.

Contoh tampilan:
```
Posisi pemanah A dan B: -4 9
Jarak kedua pemanah: 13 langkah
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int posPemanahA, posPemanahB;
    cout << "Posisi pemanah A dan B: ";
    cin >> posPemanahA >> posPemanahB;
    int selisihPosisi = posPemanahA - posPemanahB;
    if (selisihPosisi < 0) selisihPosisi = -selisihPosisi;
    if (selisihPosisi == 0) cout << "Kedua pemanah berdiri di titik yang sama!" << endl;
    else cout << "Jarak kedua pemanah: " << selisihPosisi << " langkah" << endl;
    return 0;
}
```

### Soal 32. Barisan Tiga Kurcaci

Urutkan tinggi tiga kurcaci dari terpendek ke tertinggi hanya dengan if dan pertukaran (tanpa loop).

Contoh tampilan:
```
Tinggi tiga kurcaci: 92 78 85
Barisan rapi: 78 85 92
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int kurcaciKiri, kurcaciTengah, kurcaciKanan, wadahTukar;
    cout << "Tinggi tiga kurcaci: ";
    cin >> kurcaciKiri >> kurcaciTengah >> kurcaciKanan;
    if (kurcaciKiri > kurcaciTengah) { wadahTukar = kurcaciKiri; kurcaciKiri = kurcaciTengah; kurcaciTengah = wadahTukar; }
    if (kurcaciTengah > kurcaciKanan) { wadahTukar = kurcaciTengah; kurcaciTengah = kurcaciKanan; kurcaciKanan = wadahTukar; }
    if (kurcaciKiri > kurcaciTengah) { wadahTukar = kurcaciKiri; kurcaciKiri = kurcaciTengah; kurcaciTengah = wadahTukar; }
    cout << "Barisan rapi: " << kurcaciKiri << " " << kurcaciTengah << " " << kurcaciKanan << endl;
    return 0;
}
```

### Soal 33. Tenda Donor Darah

Tentukan apakah pendonor boleh mendonorkan darah ke penerima. Aturan sederhana: O ke semua; A ke A dan AB; B ke B dan AB; AB hanya ke AB. Golongan diketik sebagai teks (A, B, AB, O).

Contoh tampilan:
```
Golongan darah pendonor: B
Golongan darah penerima: AB
Cocok! Donor bisa dilakukan.
```

Jawaban:
```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string darahPendonor, darahPenerima;
    cout << "Golongan darah pendonor: ";
    cin >> darahPendonor;
    cout << "Golongan darah penerima: ";
    cin >> darahPenerima;
    bool bolehDonor = false;
    if (darahPendonor == "O") bolehDonor = true;
    else if (darahPendonor == "A" && (darahPenerima == "A" || darahPenerima == "AB")) bolehDonor = true;
    else if (darahPendonor == "B" && (darahPenerima == "B" || darahPenerima == "AB")) bolehDonor = true;
    else if (darahPendonor == "AB" && darahPenerima == "AB") bolehDonor = true;
    if (bolehDonor) cout << "Cocok! Donor bisa dilakukan." << endl;
    else cout << "Tidak cocok, cari pendonor lain." << endl;
    return 0;
}
```

### Soal 34. Upeti Bertingkat Kerajaan

Upeti dihitung bertingkat: 5% untuk Rp0–50 juta pertama, 15% untuk bagian di atas 50 juta sampai 250 juta, 25% untuk bagian di atas 250 juta.

Contoh tampilan:
```
Penghasilan setahun: Rp300000000
Upeti yang harus dibayar: Rp45000000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    long long penghasilanSetahun, upetiKerajaan;
    cout << "Penghasilan setahun: Rp";
    cin >> penghasilanSetahun;
    if (penghasilanSetahun <= 50000000)
        upetiKerajaan = penghasilanSetahun * 5 / 100;
    else if (penghasilanSetahun <= 250000000)
        upetiKerajaan = 50000000LL * 5 / 100 + (penghasilanSetahun - 50000000) * 15 / 100;
    else
        upetiKerajaan = 50000000LL * 5 / 100 + 200000000LL * 15 / 100 + (penghasilanSetahun - 250000000) * 25 / 100;
    cout << "Upeti yang harus dibayar: Rp" << upetiKerajaan << endl;
    return 0;
}
```

### Soal 35. Seismograf Desa Lereng

Kategorikan gempa berdasarkan skala Richter: < 3 tidak terasa, < 5 ringan, < 6 sedang, < 7 kuat, ≥ 7 sangat kuat dan sirine dibunyikan.

Contoh tampilan:
```
Kekuatan gempa (SR): 6.4
Gempa kuat! Keluar dari bangunan.
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double getaranRichter;
    cout << "Kekuatan gempa (SR): ";
    cin >> getaranRichter;
    if (getaranRichter < 3) cout << "Gempa tidak terasa." << endl;
    else if (getaranRichter < 5) cout << "Gempa ringan." << endl;
    else if (getaranRichter < 6) cout << "Gempa sedang, waspada." << endl;
    else if (getaranRichter < 7) cout << "Gempa kuat! Keluar dari bangunan." << endl;
    else cout << "Gempa sangat kuat! Sirine dibunyikan!" << endl;
    return 0;
}
```

### Soal 36. Warung Makan Mak Ijah

Menu: 1 Nasi Goreng Rp15.000, 2 Mie Ayam Rp12.000, 3 Soto Rp13.000, 4 Gado-gado Rp10.000. Masukkan pilihan menu dan jumlah porsi, tampilkan nama menu dan total harga.

Contoh tampilan:
```
Menu Mak Ijah: 1.Nasi Goreng 2.Mie Ayam 3.Soto 4.Gado-gado
Pilih menu: 3
Jumlah porsi: 4
4 porsi Soto = Rp52000
```

Jawaban:
```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    int pilihanMenu, porsiMakan, hargaMenu;
    string namaMenu;
    cout << "Menu Mak Ijah: 1.Nasi Goreng 2.Mie Ayam 3.Soto 4.Gado-gado" << endl;
    cout << "Pilih menu: ";
    cin >> pilihanMenu;
    cout << "Jumlah porsi: ";
    cin >> porsiMakan;
    switch (pilihanMenu) {
        case 1: namaMenu = "Nasi Goreng"; hargaMenu = 15000; break;
        case 2: namaMenu = "Mie Ayam"; hargaMenu = 12000; break;
        case 3: namaMenu = "Soto"; hargaMenu = 13000; break;
        case 4: namaMenu = "Gado-gado"; hargaMenu = 10000; break;
        default: cout << "Menu tidak tersedia!" << endl; return 0;
    }
    cout << porsiMakan << " porsi " << namaMenu << " = Rp" << porsiMakan * hargaMenu << endl;
    return 0;
}
```

### Soal 37. Juru Eja Angka

Ubah angka 1–10 menjadi kata (satu, dua, ..., sepuluh) dengan switch.

Contoh tampilan:
```
Angka (1-10): 7
tujuh
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int angkaEja;
    cout << "Angka (1-10): ";
    cin >> angkaEja;
    switch (angkaEja) {
        case 1: cout << "satu" << endl; break;
        case 2: cout << "dua" << endl; break;
        case 3: cout << "tiga" << endl; break;
        case 4: cout << "empat" << endl; break;
        case 5: cout << "lima" << endl; break;
        case 6: cout << "enam" << endl; break;
        case 7: cout << "tujuh" << endl; break;
        case 8: cout << "delapan" << endl; break;
        case 9: cout << "sembilan" << endl; break;
        case 10: cout << "sepuluh" << endl; break;
        default: cout << "Di luar jangkauan juru eja!" << endl;
    }
    return 0;
}
```

### Soal 38. Tukang Ubin Istana

Tukang ubin mengukur ruangan. Jika panjang sama dengan lebar, ruangan persegi; jika tidak, persegi panjang. Ukuran ≤ 0 tidak valid. Tampilkan juga luasnya.

Contoh tampilan:
```
Panjang dan lebar ruangan (m): 6 6
Ruangan berbentuk persegi
Luas ubin yang dibutuhkan: 36 m2
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double panjangRuang, lebarRuang;
    cout << "Panjang dan lebar ruangan (m): ";
    cin >> panjangRuang >> lebarRuang;
    if (panjangRuang <= 0 || lebarRuang <= 0) {
        cout << "Ukuran ruangan tidak valid!" << endl;
    } else {
        if (panjangRuang == lebarRuang) cout << "Ruangan berbentuk persegi" << endl;
        else cout << "Ruangan berbentuk persegi panjang" << endl;
        cout << "Luas ubin yang dibutuhkan: " << panjangRuang * lebarRuang << " m2" << endl;
    }
    return 0;
}
```

### Soal 39. Satu Tebakan Sang Sphinx

Sphinx menyimpan angka 73. Pengembara hanya punya satu kesempatan menebak. Jika selisihnya ≤ 5, Sphinx berkata "hampir!" selain memberi petunjuk lebih besar/kecil.

Contoh tampilan:
```
Tebak angka Sphinx (1-100): 70
Terlalu kecil, tapi hampir!
Angkanya 73. Kamu gagal.
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    const int angkaSphinx = 73;
    int tebakanKelana;
    cout << "Tebak angka Sphinx (1-100): ";
    cin >> tebakanKelana;
    if (tebakanKelana == angkaSphinx) {
        cout << "Benar! Sphinx membiarkanmu lewat." << endl;
    } else {
        if (tebakanKelana < angkaSphinx) cout << "Terlalu kecil";
        else cout << "Terlalu besar";
        int bedaSphinx = tebakanKelana - angkaSphinx;
        if (bedaSphinx < 0) bedaSphinx = -bedaSphinx;
        if (bedaSphinx <= 5) cout << ", tapi hampir!";
        cout << endl << "Angkanya " << angkaSphinx << ". Kamu gagal." << endl;
    }
    return 0;
}
```

### Soal 40. Kecepatan Jaringan Warnet

Kategorikan kecepatan internet (Mbps): < 5 lambat, 5–20 sedang, 21–100 cepat, > 100 sangat cepat. Tampilkan juga kegiatan yang disarankan.

Contoh tampilan:
```
Kecepatan internet (Mbps): 45
Cepat - lancar untuk game online.
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int mbpsWarnet;
    cout << "Kecepatan internet (Mbps): ";
    cin >> mbpsWarnet;
    if (mbpsWarnet < 5) cout << "Lambat - cukup untuk chatting." << endl;
    else if (mbpsWarnet <= 20) cout << "Sedang - bisa streaming video biasa." << endl;
    else if (mbpsWarnet <= 100) cout << "Cepat - lancar untuk game online." << endl;
    else cout << "Sangat cepat - siap live streaming." << endl;
    return 0;
}
```

### Soal 41. Nasihat Petani Cuaca

Berdasarkan suhu dan kelembapan: suhu > 30 dan kelembapan > 70 → siram tanaman sore hari; suhu > 30 → siram pagi dan sore; kelembapan > 85 → waspada jamur; selain itu cuaca bersahabat.

Contoh tampilan:
```
Suhu (C) dan kelembapan (%): 33 80
Panas dan lembap: siram tanaman sore hari saja.
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int suhuLadang, lembapLadang;
    cout << "Suhu (C) dan kelembapan (%): ";
    cin >> suhuLadang >> lembapLadang;
    if (suhuLadang > 30 && lembapLadang > 70) cout << "Panas dan lembap: siram tanaman sore hari saja." << endl;
    else if (suhuLadang > 30) cout << "Panas kering: siram tanaman pagi dan sore." << endl;
    else if (lembapLadang > 85) cout << "Terlalu lembap: waspada jamur daun!" << endl;
    else cout << "Cuaca bersahabat, tanaman aman." << endl;
    return 0;
}
```

### Soal 42. Parkir Progresif Mal Kota

Jam pertama Rp5.000, setiap jam berikutnya Rp3.000, maksimal Rp25.000 per hari. Masukkan jam masuk dan jam keluar (hari yang sama).

Contoh tampilan:
```
Jam masuk dan jam keluar (0-23): 9 17
Lama parkir: 8 jam
Biaya parkir: Rp25000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int jamDatang, jamPulang;
    cout << "Jam masuk dan jam keluar (0-23): ";
    cin >> jamDatang >> jamPulang;
    if (jamPulang < jamDatang) {
        cout << "Jam keluar tidak boleh sebelum jam masuk!" << endl;
        return 0;
    }
    int durasiParkir = jamPulang - jamDatang;
    if (durasiParkir == 0) durasiParkir = 1;
    int biayaMal = 5000 + (durasiParkir - 1) * 3000;
    if (biayaMal > 25000) biayaMal = 25000;
    cout << "Lama parkir: " << durasiParkir << " jam" << endl;
    cout << "Biaya parkir: Rp" << biayaMal << endl;
    return 0;
}
```

### Soal 43. Penjurusan Akademi Kerajaan

Calon murid masuk jurusan Sihir jika nilai sihir ≥ 80 dan lebih tinggi dari nilai pedang, jurusan Pedang jika nilai pedang ≥ 80, selain itu masuk kelas Umum.

Contoh tampilan:
```
Nilai sihir dan nilai pedang: 85 90
Diterima di jurusan Pedang
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int nilaiSihirCalon, nilaiPedangCalon;
    cout << "Nilai sihir dan nilai pedang: ";
    cin >> nilaiSihirCalon >> nilaiPedangCalon;
    if (nilaiSihirCalon >= 80 && nilaiSihirCalon > nilaiPedangCalon) cout << "Diterima di jurusan Sihir" << endl;
    else if (nilaiPedangCalon >= 80) cout << "Diterima di jurusan Pedang" << endl;
    else cout << "Masuk kelas Umum" << endl;
    return 0;
}
```

### Soal 44. Ujian Bahasa Pelaut

Skor ujian bahasa (310–677): ≥ 550 mahir, ≥ 500 menengah atas, ≥ 450 menengah, di bawahnya dasar. Skor di luar rentang tidak valid.

Contoh tampilan:
```
Skor ujian bahasa: 523
Level: menengah atas
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int skorBahasaPelaut;
    cout << "Skor ujian bahasa: ";
    cin >> skorBahasaPelaut;
    if (skorBahasaPelaut < 310 || skorBahasaPelaut > 677) cout << "Skor tidak valid!" << endl;
    else if (skorBahasaPelaut >= 550) cout << "Level: mahir" << endl;
    else if (skorBahasaPelaut >= 500) cout << "Level: menengah atas" << endl;
    else if (skorBahasaPelaut >= 450) cout << "Level: menengah" << endl;
    else cout << "Level: dasar" << endl;
    return 0;
}
```

### Soal 45. Plat Nomor Cantik

Plat empat digit disebut "kembar" jika semua digit sama, "cermin" jika palindrom (digit 1 = digit 4 dan digit 2 = digit 3), selain itu biasa. Kerjakan tanpa perulangan.

Contoh tampilan:
```
Nomor plat (4 digit): 2442
Plat cermin! Lumayan cantik.
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int platEmpatDigit;
    cout << "Nomor plat (4 digit): ";
    cin >> platEmpatDigit;
    if (platEmpatDigit < 1000 || platEmpatDigit > 9999) {
        cout << "Plat harus 4 digit!" << endl;
        return 0;
    }
    int dPertama = platEmpatDigit / 1000;
    int dKedua = platEmpatDigit / 100 % 10;
    int dKetiga = platEmpatDigit / 10 % 10;
    int dKeempat = platEmpatDigit % 10;
    if (dPertama == dKedua && dKedua == dKetiga && dKetiga == dKeempat) cout << "Plat kembar! Harga mahal." << endl;
    else if (dPertama == dKeempat && dKedua == dKetiga) cout << "Plat cermin! Lumayan cantik." << endl;
    else cout << "Plat biasa." << endl;
    return 0;
}
```

### Soal 46. Promo Harian Toko Roti

Diskon berdasarkan hari (switch): 1 Senin 10%, 3 Rabu 20%, 5 Jumat 15%, hari lain tanpa diskon. Hitung total bayar.

Contoh tampilan:
```
Hari ke- (1=Senin ... 7=Minggu): 3
Total belanja roti: Rp80000
Diskon hari ini: 20%
Total bayar: Rp64000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int hariBelanjaRoti, diskonHarian;
    double belanjaRoti;
    cout << "Hari ke- (1=Senin ... 7=Minggu): ";
    cin >> hariBelanjaRoti;
    cout << "Total belanja roti: Rp";
    cin >> belanjaRoti;
    switch (hariBelanjaRoti) {
        case 1: diskonHarian = 10; break;
        case 3: diskonHarian = 20; break;
        case 5: diskonHarian = 15; break;
        default: diskonHarian = 0;
    }
    cout << "Diskon hari ini: " << diskonHarian << "%" << endl;
    cout << "Total bayar: Rp" << belanjaRoti - belanjaRoti * diskonHarian / 100 << endl;
    return 0;
}
```

### Soal 47. ATM Desa Makmur

Penarikan tunai harus kelipatan Rp50.000, tidak boleh melebihi saldo, dan saldo minimal yang tersisa Rp50.000. Tampilkan alasan jika ditolak.

Contoh tampilan:
```
Saldo: Rp500000
Jumlah penarikan: Rp475000
Ditolak: harus kelipatan Rp50000.
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    long long saldoNasabah, tarikTunai;
    cout << "Saldo: Rp";
    cin >> saldoNasabah;
    cout << "Jumlah penarikan: Rp";
    cin >> tarikTunai;
    if (tarikTunai % 50000 != 0) cout << "Ditolak: harus kelipatan Rp50000." << endl;
    else if (tarikTunai > saldoNasabah) cout << "Ditolak: saldo tidak cukup." << endl;
    else if (saldoNasabah - tarikTunai < 50000) cout << "Ditolak: saldo minimal Rp50000 harus tersisa." << endl;
    else cout << "Berhasil! Sisa saldo Rp" << saldoNasabah - tarikTunai << endl;
    return 0;
}
```

### Soal 48. Gerbang Tol Lintas Pulau

Tarif tol per golongan (switch): 1 sedan Rp12.000, 2 truk kecil Rp18.000, 3 truk sedang Rp24.000, 4 truk besar Rp30.000. Jika membayar dengan kartu tol (K), dapat potongan Rp1.000.

Contoh tampilan:
```
Golongan kendaraan (1-4): 2
Bayar pakai (K=kartu, T=tunai): K
Tarif tol: Rp17000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int golonganKendaraan, tarifTol;
    char caraBayar;
    cout << "Golongan kendaraan (1-4): ";
    cin >> golonganKendaraan;
    cout << "Bayar pakai (K=kartu, T=tunai): ";
    cin >> caraBayar;
    switch (golonganKendaraan) {
        case 1: tarifTol = 12000; break;
        case 2: tarifTol = 18000; break;
        case 3: tarifTol = 24000; break;
        case 4: tarifTol = 30000; break;
        default: cout << "Golongan tidak dikenal!" << endl; return 0;
    }
    if (caraBayar == 'K' || caraBayar == 'k') tarifTol -= 1000;
    cout << "Tarif tol: Rp" << tarifTol << endl;
    return 0;
}
```

### Soal 49. Tiga Teka-Teki Penjaga Jembatan

Penjaga jembatan memberi tiga pertanyaan: 7 × 8, ibu kota Indonesia (huruf J/B/S untuk Jakarta/Bandung/Surabaya), dan 100 % 7. Setiap jawaban benar bernilai 1. Skor 3 boleh lewat, skor 2 boleh lewat dengan bayar, skor di bawah itu ditolak.

Contoh tampilan:
```
Teka-teki 1: 7 x 8 = 56
Teka-teki 2: Ibu kota Indonesia? (J/B/S): J
Teka-teki 3: 100 % 7 = 3
Skor kamu: 2/3
Lumayan, boleh lewat dengan bayar 1 koin.
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int jawabanPertama, jawabanKetiga, poinTekaTeki = 0;
    char jawabanKedua;
    cout << "Teka-teki 1: 7 x 8 = ";
    cin >> jawabanPertama;
    if (jawabanPertama == 56) poinTekaTeki++;
    cout << "Teka-teki 2: Ibu kota Indonesia? (J/B/S): ";
    cin >> jawabanKedua;
    if (jawabanKedua == 'J' || jawabanKedua == 'j') poinTekaTeki++;
    cout << "Teka-teki 3: 100 % 7 = ";
    cin >> jawabanKetiga;
    if (jawabanKetiga == 2) poinTekaTeki++;
    cout << "Skor kamu: " << poinTekaTeki << "/3" << endl;
    if (poinTekaTeki == 3) cout << "Sempurna! Silakan menyeberang gratis." << endl;
    else if (poinTekaTeki == 2) cout << "Lumayan, boleh lewat dengan bayar 1 koin." << endl;
    else cout << "Kembali dan belajar lagi!" << endl;
    return 0;
}
```

### Soal 50. Tukang Kayu Segitiga Siku

Tukang kayu punya tiga bilah kayu (urutan input bebas). Cek apakah ketiganya bisa membentuk segitiga siku-siku (a² + b² = c² dengan c sisi terpanjang).

Contoh tampilan:
```
Panjang tiga bilah kayu: 10 6 8
Bisa jadi segitiga siku-siku dengan sisi miring 10
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int bilahSatu, bilahDua, bilahTiga;
    cout << "Panjang tiga bilah kayu: ";
    cin >> bilahSatu >> bilahDua >> bilahTiga;
    int bilahMiring, kakiA, kakiB;
    if (bilahSatu >= bilahDua && bilahSatu >= bilahTiga) { bilahMiring = bilahSatu; kakiA = bilahDua; kakiB = bilahTiga; }
    else if (bilahDua >= bilahSatu && bilahDua >= bilahTiga) { bilahMiring = bilahDua; kakiA = bilahSatu; kakiB = bilahTiga; }
    else { bilahMiring = bilahTiga; kakiA = bilahSatu; kakiB = bilahDua; }
    if (kakiA * kakiA + kakiB * kakiB == bilahMiring * bilahMiring)
        cout << "Bisa jadi segitiga siku-siku dengan sisi miring " << bilahMiring << endl;
    else
        cout << "Bukan segitiga siku-siku." << endl;
    return 0;
}
```
