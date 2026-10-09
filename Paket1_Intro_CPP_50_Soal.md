# Paket 1 — Intro C++ (50 Soal Cerita)

Materi: input/output (`cin`, `cout`), tipe data, operator aritmatika (`+ - * / %`), konstanta, casting, operator gabungan (`+=`, `++`), `char` dan ASCII, serta `cmath`. Semua soal di paket ini dikerjakan tanpa if dan tanpa perulangan.

Cara latihan: baca soal dan contoh tampilan, ketik sendiri dulu, baru cocokkan dengan jawaban.

---

### Soal 1. Ojek Pangkalan Bang Jalu

Bang Jalu menarik biaya buka pintu Rp5000 ditambah Rp2500 per kilometer. Buat program yang menghitung ongkos ojek dari jarak yang dimasukkan.

Contoh tampilan:
```
Jarak tujuan (km): 8
Ongkos ojek Bang Jalu: Rp25000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    const int bukaPintuJalu = 5000;
    const int tarifPerKm = 2500;
    int jarakAntar;
    cout << "Jarak tujuan (km): ";
    cin >> jarakAntar;
    int ongkosJalu = bukaPintuJalu + tarifPerKm * jarakAntar;
    cout << "Ongkos ojek Bang Jalu: Rp" << ongkosJalu << endl;
    return 0;
}
```

### Soal 2. Pizza Pesta Kurcaci

Satu loyang pizza dipotong 8 bagian. Masukkan jumlah loyang dan jumlah kurcaci, lalu tampilkan berapa potong yang didapat tiap kurcaci dan sisa potongannya.

Contoh tampilan:
```
Jumlah loyang pizza: 3
Jumlah kurcaci: 7
Total potongan: 24
Tiap kurcaci dapat 3 potong
Sisa potongan untuk tukang masak: 3
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int loyangPizza, kurcaciLapar;
    cout << "Jumlah loyang pizza: ";
    cin >> loyangPizza;
    cout << "Jumlah kurcaci: ";
    cin >> kurcaciLapar;
    int potonganTotal = loyangPizza * 8;
    cout << "Total potongan: " << potonganTotal << endl;
    cout << "Tiap kurcaci dapat " << potonganTotal / kurcaciLapar << " potong" << endl;
    cout << "Sisa potongan untuk tukang masak: " << potonganTotal % kurcaciLapar << endl;
    return 0;
}
```

### Soal 3. Pita Ukur Penjahit Kerajaan

Penjahit kerajaan mencatat panjang kain dalam kilometer (bilangan desimal). Ubah ke meter dan centimeter.

Contoh tampilan:
```
Panjang kain (km): 1.25
Dalam meter      : 1250 m
Dalam centimeter : 125000 cm
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double gulunganKm;
    cout << "Panjang kain (km): ";
    cin >> gulunganKm;
    double gulunganMeter = gulunganKm * 1000;
    double gulunganCenti = gulunganMeter * 100;
    cout << "Dalam meter      : " << gulunganMeter << " m" << endl;
    cout << "Dalam centimeter : " << gulunganCenti << " cm" << endl;
    return 0;
}
```

### Soal 4. Kereta Uap Lembah Hijau

Hitung kecepatan rata-rata kereta uap dari jarak tempuh (km) dan waktu tempuh (jam).

Contoh tampilan:
```
Jarak tempuh kereta (km): 270
Waktu tempuh (jam): 4.5
Kecepatan rata-rata kereta uap: 60 km/jam
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double relDitempuh, jamPerjalanan;
    cout << "Jarak tempuh kereta (km): ";
    cin >> relDitempuh;
    cout << "Waktu tempuh (jam): ";
    cin >> jamPerjalanan;
    cout << "Kecepatan rata-rata kereta uap: " << relDitempuh / jamPerjalanan << " km/jam" << endl;
    return 0;
}
```

### Soal 5. Celengan Bunga Pak Lurah

Pak Lurah menabung dengan bunga sederhana. Bunga = modal × persen bunga per tahun × lama tahun / 100. Tampilkan bunga dan saldo akhir.

Contoh tampilan:
```
Modal awal: Rp2000000
Bunga per tahun (%): 5
Lama menabung (tahun): 3
Bunga yang didapat: Rp300000
Saldo akhir Pak Lurah: Rp2300000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    long long modalLurah;
    int persenBunga, tahunSimpan;
    cout << "Modal awal: Rp";
    cin >> modalLurah;
    cout << "Bunga per tahun (%): ";
    cin >> persenBunga;
    cout << "Lama menabung (tahun): ";
    cin >> tahunSimpan;
    long long hasilBunga = modalLurah * persenBunga * tahunSimpan / 100;
    cout << "Bunga yang didapat: Rp" << hasilBunga << endl;
    cout << "Saldo akhir Pak Lurah: Rp" << modalLurah + hasilBunga << endl;
    return 0;
}
```

### Soal 6. Sawah Persegi Mbah Karto

Sawah Mbah Karto berbentuk persegi panjang. Hitung luas sawah dan panjang pematang (keliling).

Contoh tampilan:
```
Panjang sawah (m): 40
Lebar sawah (m): 25
Luas sawah Mbah Karto: 1000 m2
Panjang pematang: 130 m
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int panjangPetak, lebarPetak;
    cout << "Panjang sawah (m): ";
    cin >> panjangPetak;
    cout << "Lebar sawah (m): ";
    cin >> lebarPetak;
    cout << "Luas sawah Mbah Karto: " << panjangPetak * lebarPetak << " m2" << endl;
    cout << "Panjang pematang: " << 2 * (panjangPetak + lebarPetak) << " m" << endl;
    return 0;
}
```

### Soal 7. Kolam Ikan Koi Juragan

Kolam koi berbentuk balok. Hitung volume kolam dalam m³ dan liter (1 m³ = 1000 liter).

Contoh tampilan:
```
Panjang, lebar, kedalaman kolam (m): 4 3 1.5
Volume kolam: 18 m3
Air yang dibutuhkan: 18000 liter
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double sisiPanjangKolam, sisiLebarKolam, dalamKolam;
    cout << "Panjang, lebar, kedalaman kolam (m): ";
    cin >> sisiPanjangKolam >> sisiLebarKolam >> dalamKolam;
    double isiKolam = sisiPanjangKolam * sisiLebarKolam * dalamKolam;
    cout << "Volume kolam: " << isiKolam << " m3" << endl;
    cout << "Air yang dibutuhkan: " << isiKolam * 1000 << " liter" << endl;
    return 0;
}
```

### Soal 8. Tangki Air Desa Tirta

Tangki air berbentuk tabung. Hitung volume tangki dengan rumus π × r² × t (π = 3.14, sebagai konstanta).

Contoh tampilan:
```
Jari-jari tangki (dm): 7
Tinggi tangki (dm): 10
Volume tangki: 1538.6 liter
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    const double PI_TIRTA = 3.14;
    double jariTangki, tinggiTangki;
    cout << "Jari-jari tangki (dm): ";
    cin >> jariTangki;
    cout << "Tinggi tangki (dm): ";
    cin >> tinggiTangki;
    cout << "Volume tangki: " << PI_TIRTA * jariTangki * jariTangki * tinggiTangki << " liter" << endl;
    return 0;
}
```

### Soal 9. Rapor Si Bungsu

Masukkan tiga nilai ulangan Si Bungsu (bilangan bulat), lalu tampilkan rata-ratanya dalam bentuk desimal. Perhatikan casting agar hasil tidak dibulatkan.

Contoh tampilan:
```
Tiga nilai ulangan Si Bungsu: 80 75 92
Rata-rata nilai Si Bungsu: 82.3333
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int ulanganSatu, ulanganDua, ulanganTiga;
    cout << "Tiga nilai ulangan Si Bungsu: ";
    cin >> ulanganSatu >> ulanganDua >> ulanganTiga;
    double rerataBungsu = (double)(ulanganSatu + ulanganDua + ulanganTiga) / 3;
    cout << "Rata-rata nilai Si Bungsu: " << rerataBungsu << endl;
    return 0;
}
```

### Soal 10. Penukaran Uang Bandara

Pelancong menukar rupiah ke dolar. Masukkan jumlah rupiah dan kurs, tampilkan hasil dalam dolar.

Contoh tampilan:
```
Rupiah yang ditukar: 3200000
Kurs 1 dolar (Rp): 16000
Dolar yang diterima: $200
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double rupiahDompet, kursHariIni;
    cout << "Rupiah yang ditukar: ";
    cin >> rupiahDompet;
    cout << "Kurs 1 dolar (Rp): ";
    cin >> kursHariIni;
    cout << "Dolar yang diterima: $" << rupiahDompet / kursHariIni << endl;
    return 0;
}
```

### Soal 11. Umur Kura-Kura Tua

Umur kura-kura dicatat dalam tahun, bulan, dan hari. Ubah menjadi total hari (anggap 1 tahun = 365 hari, 1 bulan = 30 hari).

Contoh tampilan:
```
Umur kura-kura (tahun bulan hari): 120 5 17
Kura-kura sudah hidup 43967 hari
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int tahunKura, bulanKura, hariKura;
    cout << "Umur kura-kura (tahun bulan hari): ";
    cin >> tahunKura >> bulanKura >> hariKura;
    long long totalHariKura = tahunKura * 365LL + bulanKura * 30 + hariKura;
    cout << "Kura-kura sudah hidup " << totalHariKura << " hari" << endl;
    return 0;
}
```

### Soal 12. Timbangan Pesilat

Pelatih silat menghitung indeks massa tubuh: berat (kg) dibagi kuadrat tinggi (meter).

Contoh tampilan:
```
Berat badan (kg): 65
Tinggi badan (m): 1.70
Indeks massa tubuh pesilat: 22.4913
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double beratPesilat, tinggiPesilat;
    cout << "Berat badan (kg): ";
    cin >> beratPesilat;
    cout << "Tinggi badan (m): ";
    cin >> tinggiPesilat;
    double indeksTubuh = beratPesilat / (tinggiPesilat * tinggiPesilat);
    cout << "Indeks massa tubuh pesilat: " << indeksTubuh << endl;
    return 0;
}
```

### Soal 13. Mesin Kembalian Toko Kelontong

Mesin kasir memecah uang kembalian menjadi lembaran 5000, 2000, 1000, dan koin 500 sebanyak mungkin, dimulai dari pecahan terbesar. Gunakan pembagian dan modulus berantai.

Contoh tampilan:
```
Jumlah kembalian: Rp13500
Rp5000 : 2 lembar
Rp2000 : 1 lembar
Rp1000 : 1 lembar
Rp500  : 1 koin
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int kembalianToko;
    cout << "Jumlah kembalian: Rp";
    cin >> kembalianToko;
    int lembarLimaRibu = kembalianToko / 5000;
    kembalianToko %= 5000;
    int lembarDuaRibu = kembalianToko / 2000;
    kembalianToko %= 2000;
    int lembarSeribu = kembalianToko / 1000;
    kembalianToko %= 1000;
    int koinGopek = kembalianToko / 500;
    cout << "Rp5000 : " << lembarLimaRibu << " lembar" << endl;
    cout << "Rp2000 : " << lembarDuaRibu << " lembar" << endl;
    cout << "Rp1000 : " << lembarSeribu << " lembar" << endl;
    cout << "Rp500  : " << koinGopek << " koin" << endl;
    return 0;
}
```

### Soal 14. Kalender Pertapa Gunung

Pertapa mencatat lama bertapa dalam hari. Ubah menjadi minggu dan sisa hari.

Contoh tampilan:
```
Lama bertapa (hari): 100
Pertapa sudah bertapa 14 minggu 2 hari
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int hariBertapa;
    cout << "Lama bertapa (hari): ";
    cin >> hariBertapa;
    cout << "Pertapa sudah bertapa " << hariBertapa / 7 << " minggu " << hariBertapa % 7 << " hari" << endl;
    return 0;
}
```

### Soal 15. Wartel Jadul Pak Darso

Wartel Pak Darso menarik Rp350 per menit ditambah biaya admin Rp1000. Hitung total biaya telepon.

Contoh tampilan:
```
Lama menelepon (menit): 12
Biaya telepon: Rp5200
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    const int tarifMenitDarso = 350;
    const int adminWartel = 1000;
    int menitNgobrol;
    cout << "Lama menelepon (menit): ";
    cin >> menitNgobrol;
    cout << "Biaya telepon: Rp" << menitNgobrol * tarifMenitDarso + adminWartel << endl;
    return 0;
}
```

### Soal 16. Kode Rahasia Huruf Penyihir

Penyihir ingin tahu kode ASCII dari sebuah huruf. Masukkan satu karakter, tampilkan nilai ASCII-nya dengan casting ke int.

Contoh tampilan:
```
Masukkan satu huruf: K
Kode ASCII huruf K adalah 75
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    char hurufMantra;
    cout << "Masukkan satu huruf: ";
    cin >> hurufMantra;
    cout << "Kode ASCII huruf " << hurufMantra << " adalah " << (int)hurufMantra << endl;
    return 0;
}
```

### Soal 17. Langkah Huruf Kurir

Kurir menyamarkan huruf dengan menggesernya satu langkah ke depan dan satu langkah ke belakang di tabel ASCII.

Contoh tampilan:
```
Huruf asli: m
Satu langkah ke depan   : n
Satu langkah ke belakang: l
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    char hurufKurir;
    cout << "Huruf asli: ";
    cin >> hurufKurir;
    char hurufMaju = hurufKurir + 1;
    char hurufMundur = hurufKurir - 1;
    cout << "Satu langkah ke depan   : " << hurufMaju << endl;
    cout << "Satu langkah ke belakang: " << hurufMundur << endl;
    return 0;
}
```

### Soal 18. Tukar Isi Dua Gelas

Gelas A berisi teh, gelas B berisi kopi (dinyatakan dengan angka ml). Tukar isinya memakai gelas kosong (variabel bantu).

Contoh tampilan:
```
Isi gelas A dan B (ml): 200 150
Sebelum ditukar: A = 200, B = 150
Sesudah ditukar: A = 150, B = 200
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int gelasTeh, gelasKopi;
    cout << "Isi gelas A dan B (ml): ";
    cin >> gelasTeh >> gelasKopi;
    cout << "Sebelum ditukar: A = " << gelasTeh << ", B = " << gelasKopi << endl;
    int gelasKosong = gelasTeh;
    gelasTeh = gelasKopi;
    gelasKopi = gelasKosong;
    cout << "Sesudah ditukar: A = " << gelasTeh << ", B = " << gelasKopi << endl;
    return 0;
}
```

### Soal 19. Tukar Kantong Tanpa Kantong Ketiga

Dua pedagang menukar isi kantong koin tanpa kantong tambahan. Gunakan trik penjumlahan dan pengurangan.

Contoh tampilan:
```
Koin kantong utara dan selatan: 35 80
Setelah ditukar: utara = 80, selatan = 35
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int kantongUtara, kantongSelatan;
    cout << "Koin kantong utara dan selatan: ";
    cin >> kantongUtara >> kantongSelatan;
    kantongUtara = kantongUtara + kantongSelatan;
    kantongSelatan = kantongUtara - kantongSelatan;
    kantongUtara = kantongUtara - kantongSelatan;
    cout << "Setelah ditukar: utara = " << kantongUtara << ", selatan = " << kantongSelatan << endl;
    return 0;
}
```

### Soal 20. Nomor Loker Tiga Digit

Nomor loker selalu tiga digit. Pisahkan menjadi digit ratusan, puluhan, dan satuan menggunakan / dan %.

Contoh tampilan:
```
Nomor loker (3 digit): 472
Ratusan : 4
Puluhan : 7
Satuan  : 2
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int nomorLoker;
    cout << "Nomor loker (3 digit): ";
    cin >> nomorLoker;
    cout << "Ratusan : " << nomorLoker / 100 << endl;
    cout << "Puluhan : " << nomorLoker / 10 % 10 << endl;
    cout << "Satuan  : " << nomorLoker % 10 << endl;
    return 0;
}
```

### Soal 21. Cermin Angka Tiga Digit

Pintu cermin membalik nomor tiga digit (misal 472 menjadi 274). Kerjakan tanpa perulangan.

Contoh tampilan:
```
Angka tiga digit: 472
Bayangan di cermin: 274
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int angkaDepanCermin;
    cout << "Angka tiga digit: ";
    cin >> angkaDepanCermin;
    int digitKanan = angkaDepanCermin % 10;
    int digitTengah = angkaDepanCermin / 10 % 10;
    int digitKiri = angkaDepanCermin / 100;
    int angkaBalikCermin = digitKanan * 100 + digitTengah * 10 + digitKiri;
    cout << "Bayangan di cermin: " << angkaBalikCermin << endl;
    return 0;
}
```

### Soal 22. Kilau Empat Batu Akik

Kode batu akik terdiri dari empat digit. Jumlahkan keempat digitnya tanpa perulangan.

Contoh tampilan:
```
Kode batu akik (4 digit): 2718
Total kilau batu akik: 18
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int kodeAkik;
    cout << "Kode batu akik (4 digit): ";
    cin >> kodeAkik;
    int kilauAkik = kodeAkik / 1000 + kodeAkik / 100 % 10 + kodeAkik / 10 % 10 + kodeAkik % 10;
    cout << "Total kilau batu akik: " << kilauAkik << endl;
    return 0;
}
```

### Soal 23. Slip Gaji Buruh Pelabuhan

Gaji buruh = gaji pokok + jam lembur × Rp25.000. Tampilkan rincian dan total gaji.

Contoh tampilan:
```
Gaji pokok: Rp3500000
Jam lembur: 14
Uang lembur : Rp350000
Total gaji  : Rp3850000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    const long long upahLemburPerJam = 25000;
    long long gajiPokokBuruh;
    int jamLemburBuruh;
    cout << "Gaji pokok: Rp";
    cin >> gajiPokokBuruh;
    cout << "Jam lembur: ";
    cin >> jamLemburBuruh;
    long long uangLembur = jamLemburBuruh * upahLemburPerJam;
    cout << "Uang lembur : Rp" << uangLembur << endl;
    cout << "Total gaji  : Rp" << gajiPokokBuruh + uangLembur << endl;
    return 0;
}
```

### Soal 24. Struk Pajak Kedai Kopi

Kedai kopi mengenakan PPN 11% dari harga pesanan. Tampilkan pajak dan total bayar.

Contoh tampilan:
```
Harga pesanan: Rp45000
PPN 11%     : Rp4950
Total bayar : Rp49950
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    const double PPN_KEDAI = 0.11;
    double pesananKopi;
    cout << "Harga pesanan: Rp";
    cin >> pesananKopi;
    double pajakKopi = pesananKopi * PPN_KEDAI;
    cout << "PPN 11%     : Rp" << pajakKopi << endl;
    cout << "Total bayar : Rp" << pesananKopi + pajakKopi << endl;
    return 0;
}
```

### Soal 25. Obral Baju Lebaran

Toko baju memberi diskon tetap 25%. Tampilkan besar potongan dan harga akhir.

Contoh tampilan:
```
Harga baju: Rp180000
Potongan 25%: Rp45000
Harga akhir : Rp135000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double bandrolBaju;
    cout << "Harga baju: Rp";
    cin >> bandrolBaju;
    double potonganLebaran = bandrolBaju * 25 / 100;
    cout << "Potongan 25%: Rp" << potonganLebaran << endl;
    cout << "Harga akhir : Rp" << bandrolBaju - potonganLebaran << endl;
    return 0;
}
```

### Soal 26. Kuda Pos Antar Kota

Kuda pos berlari dengan kecepatan tetap. Hitung jarak tempuh dari kecepatan (km/jam) dan lama berlari (jam).

Contoh tampilan:
```
Kecepatan kuda pos (km/jam): 35
Lama berlari (jam): 2.5
Jarak yang ditempuh: 87.5 km
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double lajuKudaPos, lamaBerlari;
    cout << "Kecepatan kuda pos (km/jam): ";
    cin >> lajuKudaPos;
    cout << "Lama berlari (jam): ";
    cin >> lamaBerlari;
    cout << "Jarak yang ditempuh: " << lajuKudaPos * lamaBerlari << " km" << endl;
    return 0;
}
```

### Soal 27. Timbangan Pasar Rempah

Pedagang rempah menimbang dalam kilogram. Ubah ke ons dan gram (1 kg = 10 ons = 1000 gram).

Contoh tampilan:
```
Berat rempah (kg): 2.3
Dalam ons  : 23 ons
Dalam gram : 2300 gram
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double timbanganKilo;
    cout << "Berat rempah (kg): ";
    cin >> timbanganKilo;
    cout << "Dalam ons  : " << timbanganKilo * 10 << " ons" << endl;
    cout << "Dalam gram : " << timbanganKilo * 1000 << " gram" << endl;
    return 0;
}
```

### Soal 28. Galon Es Teh Kantin

Satu galon es teh berisi sekian liter. Ubah ke ml, lalu hitung berapa gelas 300 ml yang bisa diisi penuh dan sisa ml-nya.

Contoh tampilan:
```
Isi galon (liter): 19
Isi galon: 19000 ml
Gelas penuh (300 ml): 63 gelas
Sisa es teh: 100 ml
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int literGalon;
    cout << "Isi galon (liter): ";
    cin >> literGalon;
    int mlGalon = literGalon * 1000;
    cout << "Isi galon: " << mlGalon << " ml" << endl;
    cout << "Gelas penuh (300 ml): " << mlGalon / 300 << " gelas" << endl;
    cout << "Sisa es teh: " << mlGalon % 300 << " ml" << endl;
    return 0;
}
```

### Soal 29. Termometer Turis Amerika

Turis membawa termometer Fahrenheit. Ubah ke Celsius dengan rumus C = (F − 32) × 5 / 9.

Contoh tampilan:
```
Suhu (Fahrenheit): 98.6
Dalam Celsius: 37
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double suhuTuris;
    cout << "Suhu (Fahrenheit): ";
    cin >> suhuTuris;
    double suhuLokal = (suhuTuris - 32) * 5 / 9;
    cout << "Dalam Celsius: " << suhuLokal << endl;
    return 0;
}
```

### Soal 30. Layar Perahu Segitiga

Hitung luas kain layar perahu yang berbentuk segitiga dari alas dan tingginya.

Contoh tampilan:
```
Alas layar (m): 6
Tinggi layar (m): 9
Luas kain layar: 27 m2
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double alasLayar, tinggiLayar;
    cout << "Alas layar (m): ";
    cin >> alasLayar;
    cout << "Tinggi layar (m): ";
    cin >> tinggiLayar;
    cout << "Luas kain layar: " << 0.5 * alasLayar * tinggiLayar << " m2" << endl;
    return 0;
}
```

### Soal 31. Tangga Pemadam Kebakaran

Tangga disandarkan ke dinding. Dari tinggi dinding dan jarak kaki tangga ke dinding, hitung panjang tangga dengan teorema Pythagoras (`sqrt` dari `cmath`).

Contoh tampilan:
```
Tinggi dinding (m): 8
Jarak kaki tangga ke dinding (m): 6
Panjang tangga yang dibutuhkan: 10 m
```

Jawaban:
```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main() {
    double tinggiDinding, jarakKakiTangga;
    cout << "Tinggi dinding (m): ";
    cin >> tinggiDinding;
    cout << "Jarak kaki tangga ke dinding (m): ";
    cin >> jarakKakiTangga;
    double panjangTangga = sqrt(tinggiDinding * tinggiDinding + jarakKakiTangga * jarakKakiTangga);
    cout << "Panjang tangga yang dibutuhkan: " << panjangTangga << " m" << endl;
    return 0;
}
```

### Soal 32. Meja Bundar Para Ksatria

Tukang kayu tahu diameter meja bundar. Hitung jari-jari, keliling, dan luas permukaannya (π = 3.14).

Contoh tampilan:
```
Diameter meja (m): 4
Jari-jari : 2 m
Keliling  : 12.56 m
Luas      : 12.56 m2
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    const double PI_MEJA = 3.14;
    double garisTengahMeja;
    cout << "Diameter meja (m): ";
    cin >> garisTengahMeja;
    double jariMeja = garisTengahMeja / 2;
    cout << "Jari-jari : " << jariMeja << " m" << endl;
    cout << "Keliling  : " << PI_MEJA * garisTengahMeja << " m" << endl;
    cout << "Luas      : " << PI_MEJA * jariMeja * jariMeja << " m2" << endl;
    return 0;
}
```

### Soal 33. Ladang Trapesium Pak Bejo

Ladang Pak Bejo berbentuk trapesium. Hitung luasnya: (sisi atas + sisi bawah) × tinggi / 2.

Contoh tampilan:
```
Sisi atas, sisi bawah, tinggi ladang (m): 10 16 8
Luas ladang Pak Bejo: 104 m2
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double sisiAtasLadang, sisiBawahLadang, tinggiLadang;
    cout << "Sisi atas, sisi bawah, tinggi ladang (m): ";
    cin >> sisiAtasLadang >> sisiBawahLadang >> tinggiLadang;
    cout << "Luas ladang Pak Bejo: " << (sisiAtasLadang + sisiBawahLadang) * tinggiLadang / 2 << " m2" << endl;
    return 0;
}
```

### Soal 34. Jam Tidur Si Pemalas

Masukkan jam tidur dan jam bangun (format 24 jam, bilangan bulat). Hitung lama tidur tanpa if, meskipun tidurnya lewat tengah malam. Petunjuk: gunakan (bangun − tidur + 24) % 24.

Contoh tampilan:
```
Jam tidur (0-23): 22
Jam bangun (0-23): 7
Si Pemalas tidur selama 9 jam
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int jamMerem, jamMelek;
    cout << "Jam tidur (0-23): ";
    cin >> jamMerem;
    cout << "Jam bangun (0-23): ";
    cin >> jamMelek;
    int lamaMolor = (jamMelek - jamMerem + 24) % 24;
    cout << "Si Pemalas tidur selama " << lamaMolor << " jam" << endl;
    return 0;
}
```

### Soal 35. Kilat Cahaya Menara Suar

Cahaya merambat 300.000 km per detik. Hitung jarak yang ditempuh cahaya menara suar dalam sekian detik.

Contoh tampilan:
```
Lama cahaya merambat (detik): 12
Jarak tempuh cahaya: 3600000 km
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    const long long LAJU_CAHAYA = 300000;
    long long detikSorotan;
    cout << "Lama cahaya merambat (detik): ";
    cin >> detikSorotan;
    cout << "Jarak tempuh cahaya: " << detikSorotan * LAJU_CAHAYA << " km" << endl;
    return 0;
}
```

### Soal 36. Investasi Emas Juragan Batik

Modal juragan tumbuh dengan bunga majemuk. Saldo akhir = modal × (1 + persen/100)^tahun. Gunakan `pow` dari `cmath`.

Contoh tampilan:
```
Modal awal: Rp10000000
Pertumbuhan per tahun (%): 6
Lama investasi (tahun): 5
Saldo akhir juragan: Rp13382255
```

Jawaban:
```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main() {
    double modalJuragan, persenTumbuh;
    int tahunInvestasi;
    cout << "Modal awal: Rp";
    cin >> modalJuragan;
    cout << "Pertumbuhan per tahun (%): ";
    cin >> persenTumbuh;
    cout << "Lama investasi (tahun): ";
    cin >> tahunInvestasi;
    double saldoJuragan = modalJuragan * pow(1 + persenTumbuh / 100, tahunInvestasi);
    cout << "Saldo akhir juragan: Rp" << (long long)saldoJuragan << endl;
    return 0;
}
```

### Soal 37. Cicilan Motor Mas Tejo

Mas Tejo membeli motor dengan uang muka. Sisa harga dicicil rata setiap bulan. Hitung cicilan per bulan.

Contoh tampilan:
```
Harga motor: Rp24000000
Uang muka: Rp4000000
Lama cicilan (bulan): 20
Sisa yang dicicil: Rp20000000
Cicilan per bulan: Rp1000000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    long long hargaMotorTejo, uangMukaTejo;
    int tenorBulan;
    cout << "Harga motor: Rp";
    cin >> hargaMotorTejo;
    cout << "Uang muka: Rp";
    cin >> uangMukaTejo;
    cout << "Lama cicilan (bulan): ";
    cin >> tenorBulan;
    long long sisaUtangMotor = hargaMotorTejo - uangMukaTejo;
    cout << "Sisa yang dicicil: Rp" << sisaUtangMotor << endl;
    cout << "Cicilan per bulan: Rp" << sisaUtangMotor / tenorBulan << endl;
    return 0;
}
```

### Soal 38. Absensi Perguruan Silat

Hitung persentase kehadiran murid dari jumlah hadir dan total pertemuan. Gunakan casting supaya hasil tidak jadi 0.

Contoh tampilan:
```
Jumlah hadir: 13
Total pertemuan: 16
Persentase kehadiran: 81.25%
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int kaliHadir, totalLatihan;
    cout << "Jumlah hadir: ";
    cin >> kaliHadir;
    cout << "Total pertemuan: ";
    cin >> totalLatihan;
    double persenRajin = (double)kaliHadir / totalLatihan * 100;
    cout << "Persentase kehadiran: " << persenRajin << "%" << endl;
    return 0;
}
```

### Soal 39. Apel Dibagi Dua Saudara

Ibu membagi apel ke dua anak. Tampilkan perbedaan hasil pembagian integer (int / int) dan pembagian desimal (double).

Contoh tampilan:
```
Jumlah apel: 7
Pembagian int    : 3 apel per anak
Pembagian double : 3.5 apel per anak
Sisa apel utuh   : 1
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int apelIbu;
    cout << "Jumlah apel: ";
    cin >> apelIbu;
    int bagianBulat = apelIbu / 2;
    double bagianPecahan = apelIbu / 2.0;
    cout << "Pembagian int    : " << bagianBulat << " apel per anak" << endl;
    cout << "Pembagian double : " << bagianPecahan << " apel per anak" << endl;
    cout << "Sisa apel utuh   : " << apelIbu % 2 << endl;
    return 0;
}
```

### Soal 40. Skor Pemain Arkade

Pemain arkade memulai dengan skor tertentu. Ia mendapat bonus 50 (pakai +=), naik satu level (pakai ++), lalu skornya dilipatgandakan (pakai *=). Tampilkan skor dan level akhir.

Contoh tampilan:
```
Skor awal: 120
Level awal: 3
Setelah bonus, naik level, dan pengganda:
Skor  : 340
Level : 4
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int skorArkade, levelArkade;
    cout << "Skor awal: ";
    cin >> skorArkade;
    cout << "Level awal: ";
    cin >> levelArkade;
    skorArkade += 50;
    levelArkade++;
    skorArkade *= 2;
    cout << "Setelah bonus, naik level, dan pengganda:" << endl;
    cout << "Skor  : " << skorArkade << endl;
    cout << "Level : " << levelArkade << endl;
    return 0;
}
```

### Soal 41. Rapat Panjang Dewan Desa

Notulen mencatat durasi rapat dalam menit. Ubah ke satuan jam dalam bentuk desimal.

Contoh tampilan:
```
Durasi rapat (menit): 135
Rapat berlangsung 2.25 jam
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int menitRapat;
    cout << "Durasi rapat (menit): ";
    cin >> menitRapat;
    double jamRapat = menitRapat / 60.0;
    cout << "Rapat berlangsung " << jamRapat << " jam" << endl;
    return 0;
}
```

### Soal 42. Mudik Dua Etape

Perjalanan mudik terdiri dari dua etape. Masukkan jarak dan waktu tiap etape, hitung kecepatan rata-rata seluruh perjalanan (total jarak / total waktu).

Contoh tampilan:
```
Etape 1 - jarak (km): 120
Etape 1 - waktu (jam): 2
Etape 2 - jarak (km): 90
Etape 2 - waktu (jam): 1.5
Total jarak: 210 km
Kecepatan rata-rata: 60 km/jam
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double jarakEtapeSatu, waktuEtapeSatu, jarakEtapeDua, waktuEtapeDua;
    cout << "Etape 1 - jarak (km): ";
    cin >> jarakEtapeSatu;
    cout << "Etape 1 - waktu (jam): ";
    cin >> waktuEtapeSatu;
    cout << "Etape 2 - jarak (km): ";
    cin >> jarakEtapeDua;
    cout << "Etape 2 - waktu (jam): ";
    cin >> waktuEtapeDua;
    double jarakMudik = jarakEtapeSatu + jarakEtapeDua;
    double waktuMudik = waktuEtapeSatu + waktuEtapeDua;
    cout << "Total jarak: " << jarakMudik << " km" << endl;
    cout << "Kecepatan rata-rata: " << jarakMudik / waktuMudik << " km/jam" << endl;
    return 0;
}
```

### Soal 43. Pembakar Kalori Lari Pagi

Setiap menit lari membakar 11 kalori. Hitung kalori yang terbakar dan berapa gorengan (masing-masing 150 kalori) yang setara.

Contoh tampilan:
```
Lama lari pagi (menit): 45
Kalori terbakar: 495
Setara dengan 3 gorengan utuh
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    const int KALORI_PER_MENIT = 11;
    const int KALORI_GORENGAN = 150;
    int menitJogging;
    cout << "Lama lari pagi (menit): ";
    cin >> menitJogging;
    int kaloriLenyap = menitJogging * KALORI_PER_MENIT;
    cout << "Kalori terbakar: " << kaloriLenyap << endl;
    cout << "Setara dengan " << kaloriLenyap / KALORI_GORENGAN << " gorengan utuh" << endl;
    return 0;
}
```

### Soal 44. Sudut Meriam Benteng

Juru meriam memakai derajat, tapi rumus balistik memakai radian. Ubah derajat ke radian (radian = derajat × π / 180) dan tampilkan nilai sinusnya.

Contoh tampilan:
```
Sudut meriam (derajat): 30
Dalam radian : 0.523599
Nilai sinus  : 0.5
```

Jawaban:
```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main() {
    const double PI_BENTENG = 3.14159265;
    double sudutMeriam;
    cout << "Sudut meriam (derajat): ";
    cin >> sudutMeriam;
    double sudutRadian = sudutMeriam * PI_BENTENG / 180;
    cout << "Dalam radian : " << sudutRadian << endl;
    cout << "Nilai sinus  : " << sin(sudutRadian) << endl;
    return 0;
}
```

### Soal 45. Lapangan Latihan Prajurit

Prajurit berlari mengelilingi lapangan persegi panjang. Hitung keliling lapangan, berapa putaran penuh untuk menempuh target jarak, dan sisa meter yang belum genap satu putaran.

Contoh tampilan:
```
Panjang dan lebar lapangan (m): 100 60
Target lari (m): 3000
Keliling lapangan: 320 m
Putaran penuh: 9
Sisa jarak: 120 m
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int panjangLapangan, lebarLapangan, targetLari;
    cout << "Panjang dan lebar lapangan (m): ";
    cin >> panjangLapangan >> lebarLapangan;
    cout << "Target lari (m): ";
    cin >> targetLari;
    int satuPutaran = 2 * (panjangLapangan + lebarLapangan);
    cout << "Keliling lapangan: " << satuPutaran << " m" << endl;
    cout << "Putaran penuh: " << targetLari / satuPutaran << endl;
    cout << "Sisa jarak: " << targetLari % satuPutaran << " m" << endl;
    return 0;
}
```

### Soal 46. Toko Emas Koh Liong

Harga perhiasan = berat (gram) × harga per gram + ongkos bikin. Tampilkan rincian dan totalnya.

Contoh tampilan:
```
Berat perhiasan (gram): 5.5
Harga emas per gram: Rp1200000
Ongkos bikin: Rp150000
Nilai emas  : Rp6600000
Total harga : Rp6750000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double gramPerhiasan, hargaPerGram, ongkosBikin;
    cout << "Berat perhiasan (gram): ";
    cin >> gramPerhiasan;
    cout << "Harga emas per gram: Rp";
    cin >> hargaPerGram;
    cout << "Ongkos bikin: Rp";
    cin >> ongkosBikin;
    double nilaiEmasMurni = gramPerhiasan * hargaPerGram;
    cout << "Nilai emas  : Rp" << (long long)nilaiEmasMurni << endl;
    cout << "Total harga : Rp" << (long long)(nilaiEmasMurni + ongkosBikin) << endl;
    return 0;
}
```

### Soal 47. Tribun Stadion Kampung

Masukkan kapasitas tribun dan jumlah penonton yang datang. Tampilkan kursi kosong dan persentase keterisian.

Contoh tampilan:
```
Kapasitas tribun: 1200
Penonton yang datang: 870
Kursi kosong: 330
Keterisian tribun: 72.5%
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int kapasitasTribun, penontonDatang;
    cout << "Kapasitas tribun: ";
    cin >> kapasitasTribun;
    cout << "Penonton yang datang: ";
    cin >> penontonDatang;
    cout << "Kursi kosong: " << kapasitasTribun - penontonDatang << endl;
    cout << "Keterisian tribun: " << (double)penontonDatang / kapasitasTribun * 100 << "%" << endl;
    return 0;
}
```

### Soal 48. Struk Belanja Tiga Barang

Pembeli membeli tiga barang. Masukkan harga dan jumlah tiap barang, tampilkan subtotal masing-masing dan total belanja.

Contoh tampilan:
```
Beras  (harga jumlah): 12000 2
Gula   (harga jumlah): 8500 3
Minyak (harga jumlah): 25000 1
-----------------------
Beras  : Rp24000
Gula   : Rp25500
Minyak : Rp25000
TOTAL  : Rp74500
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int hargaBeras, qtyBeras, hargaGula, qtyGula, hargaMinyak, qtyMinyak;
    cout << "Beras  (harga jumlah): ";
    cin >> hargaBeras >> qtyBeras;
    cout << "Gula   (harga jumlah): ";
    cin >> hargaGula >> qtyGula;
    cout << "Minyak (harga jumlah): ";
    cin >> hargaMinyak >> qtyMinyak;
    int subBeras = hargaBeras * qtyBeras;
    int subGula = hargaGula * qtyGula;
    int subMinyak = hargaMinyak * qtyMinyak;
    cout << "-----------------------" << endl;
    cout << "Beras  : Rp" << subBeras << endl;
    cout << "Gula   : Rp" << subGula << endl;
    cout << "Minyak : Rp" << subMinyak << endl;
    cout << "TOTAL  : Rp" << subBeras + subGula + subMinyak << endl;
    return 0;
}
```

### Soal 49. Speedometer Pembalap Gerobak

Kecepatan gerobak dicatat dalam km/jam. Ubah ke meter per detik (bagi 3.6).

Contoh tampilan:
```
Kecepatan gerobak (km/jam): 54
Dalam meter per detik: 15 m/s
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double lajuGerobak;
    cout << "Kecepatan gerobak (km/jam): ";
    cin >> lajuGerobak;
    cout << "Dalam meter per detik: " << lajuGerobak / 3.6 << " m/s" << endl;
    return 0;
}
```

### Soal 50. Juru Ketik Istana

Juru ketik mengetik sejumlah kata dalam sekian menit. Hitung kecepatan mengetik (kata per menit) dan berapa detik rata-rata untuk satu kata.

Contoh tampilan:
```
Jumlah kata yang diketik: 540
Lama mengetik (menit): 12
Kecepatan mengetik: 45 kata/menit
Rata-rata per kata: 1.33333 detik
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int kataTerketik, menitMengetik;
    cout << "Jumlah kata yang diketik: ";
    cin >> kataTerketik;
    cout << "Lama mengetik (menit): ";
    cin >> menitMengetik;
    double kecepatanJari = (double)kataTerketik / menitMengetik;
    cout << "Kecepatan mengetik: " << kecepatanJari << " kata/menit" << endl;
    cout << "Rata-rata per kata: " << 60 / kecepatanJari << " detik" << endl;
    return 0;
}
```
