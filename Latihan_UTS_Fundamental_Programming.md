# Latihan UTS Fundamental Programming (C++)

50 soal cerita bergaya Quest IV: ada cerita, aturan, contoh tampilan, lalu jawaban kode. Materi yang dicakup: intro C++, selection (if/switch), looping, fungsi & prosedur, array, string, struct, sorting, dan searching.

Cara latihan yang disarankan: baca soal dan contoh tampilannya, coba ketik sendiri dulu, baru cocokkan dengan jawaban.

---

## BAGIAN A — INTRO C++ (input, output, operator)

### Soal 1. Kasir Cendol Mbok Darmi

Mbok Darmi berjualan cendol di pinggir alun-alun. Ia butuh program kasir sederhana: masukkan harga per porsi dan jumlah porsi, tampilkan total tagihan, lalu masukkan uang pembeli dan tampilkan kembaliannya.

Contoh tampilan:
```
Harga cendol per porsi: 5000
Mau pesan berapa porsi: 3
Total tagihan: Rp15000
Uang yang dibayar: 20000
Kembalian dari Mbok Darmi: Rp5000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int hargaCendol, porsiPesan, uangDisodor;
    cout << "Harga cendol per porsi: ";
    cin >> hargaCendol;
    cout << "Mau pesan berapa porsi: ";
    cin >> porsiPesan;
    int tagihanMbok = hargaCendol * porsiPesan;
    cout << "Total tagihan: Rp" << tagihanMbok << endl;
    cout << "Uang yang dibayar: ";
    cin >> uangDisodor;
    cout << "Kembalian dari Mbok Darmi: Rp" << uangDisodor - tagihanMbok << endl;
    return 0;
}
```

### Soal 2. Tungku Penyihir Celsius

Penyihir Celsius hanya bisa membaca suhu tungkunya dalam Celsius, padahal resep ramuannya memakai Fahrenheit, Reamur, dan Kelvin. Buat program konversi suhu dengan rumus F = C × 9/5 + 32, R = C × 4/5, K = C + 273.15.

Contoh tampilan:
```
Suhu tungku penyihir (Celsius): 100
Fahrenheit : 212
Reamur     : 80
Kelvin     : 373.15
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    double derajatTungku;
    cout << "Suhu tungku penyihir (Celsius): ";
    cin >> derajatTungku;
    double versiFahren = derajatTungku * 9 / 5 + 32;
    double versiReamur = derajatTungku * 4 / 5;
    double versiKelvin = derajatTungku + 273.15;
    cout << "Fahrenheit : " << versiFahren << endl;
    cout << "Reamur     : " << versiReamur << endl;
    cout << "Kelvin     : " << versiKelvin << endl;
    return 0;
}
```

### Soal 3. Keranjang Roti Pak Gandum

Pak Gandum memasukkan roti ke keranjang dengan isi yang sama. Hitung berapa keranjang yang terisi penuh dan berapa roti yang tersisa (gunakan operator `/` dan `%`).

Contoh tampilan:
```
Jumlah roti hari ini: 47
Isi satu keranjang: 6
Keranjang penuh: 7
Roti sisa buat sarapan Pak Gandum: 5
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int stokRoti, kapasitasKeranjang;
    cout << "Jumlah roti hari ini: ";
    cin >> stokRoti;
    cout << "Isi satu keranjang: ";
    cin >> kapasitasKeranjang;
    cout << "Keranjang penuh: " << stokRoti / kapasitasKeranjang << endl;
    cout << "Roti sisa buat sarapan Pak Gandum: " << stokRoti % kapasitasKeranjang << endl;
    return 0;
}
```

### Soal 4. Jam Pasir Ajaib

Jam pasir ajaib mencatat waktu dalam detik. Ubah jumlah detik menjadi format jam, menit, dan detik.

Contoh tampilan:
```
Waktu yang tercatat (detik): 3725
1 jam 2 menit 5 detik
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int butirPasir;
    cout << "Waktu yang tercatat (detik): ";
    cin >> butirPasir;
    int jamKu = butirPasir / 3600;
    int menitKu = (butirPasir % 3600) / 60;
    int detikKu = butirPasir % 60;
    cout << jamKu << " jam " << menitKu << " menit " << detikKu << " detik" << endl;
    return 0;
}
```

### Soal 5. Kebun Bundar Petani Lingkar

Petani Lingkar punya kebun berbentuk lingkaran. Hitung luas kebun dan panjang pagar (keliling) dengan π = 3.14 sebagai konstanta.

Contoh tampilan:
```
Jari-jari kebun (meter): 10
Luas kebun     : 314 m2
Panjang pagar  : 62.8 m
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    const double PI_KEBUN = 3.14;
    double jariLadang;
    cout << "Jari-jari kebun (meter): ";
    cin >> jariLadang;
    cout << "Luas kebun     : " << PI_KEBUN * jariLadang * jariLadang << " m2" << endl;
    cout << "Panjang pagar  : " << 2 * PI_KEBUN * jariLadang << " m" << endl;
    return 0;
}
```

---

## BAGIAN B — SELECTION (if, else if, switch)

### Soal 6. Gerbang Ganjil-Genap Kerajaan

Kereta kuda berplat genap lewat gerbang timur, plat ganjil lewat gerbang barat.

Contoh tampilan:
```
Nomor plat kereta kuda: 2468
Plat genap, gerbang timur terbuka!
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int nomorPlatKereta;
    cout << "Nomor plat kereta kuda: ";
    cin >> nomorPlatKereta;
    if (nomorPlatKereta % 2 == 0) {
        cout << "Plat genap, gerbang timur terbuka!" << endl;
    } else {
        cout << "Plat ganjil, silakan lewat gerbang barat." << endl;
    }
    return 0;
}
```

### Soal 7. Pangkat Ksatria Akademi

Akademi Ksatria memberi pangkat berdasarkan skor: ≥85 A, ≥70 B, ≥55 C, ≥40 D, sisanya E. Skor di luar 0–100 dianggap tidak valid.

Contoh tampilan:
```
Skor latihan ksatria (0-100): 78
Pangkat ksatria: B
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int skorLatihan;
    char pangkatKsatria;
    cout << "Skor latihan ksatria (0-100): ";
    cin >> skorLatihan;
    if (skorLatihan < 0 || skorLatihan > 100) {
        cout << "Skor tidak valid!" << endl;
        return 0;
    }
    if (skorLatihan >= 85) pangkatKsatria = 'A';
    else if (skorLatihan >= 70) pangkatKsatria = 'B';
    else if (skorLatihan >= 55) pangkatKsatria = 'C';
    else if (skorLatihan >= 40) pangkatKsatria = 'D';
    else pangkatKsatria = 'E';
    cout << "Pangkat ksatria: " << pangkatKsatria << endl;
    return 0;
}
```

### Soal 8. Parkir Tunggangan Istana

Tarif parkir per jam: Kuda Rp2000, Unta Rp3500, Gajah Rp7000. Kalau parkir lebih dari 5 jam, dapat potongan 10%. Gunakan `switch`.

Contoh tampilan:
```
Jenis tunggangan (1=Kuda, 2=Unta, 3=Gajah): 2
Lama parkir (jam): 6
Biaya parkir: Rp18900
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int kodeTunggangan, lamaInap, tarifPerJam;
    cout << "Jenis tunggangan (1=Kuda, 2=Unta, 3=Gajah): ";
    cin >> kodeTunggangan;
    cout << "Lama parkir (jam): ";
    cin >> lamaInap;
    switch (kodeTunggangan) {
        case 1: tarifPerJam = 2000; break;
        case 2: tarifPerJam = 3500; break;
        case 3: tarifPerJam = 7000; break;
        default:
            cout << "Tunggangan tidak dikenal!" << endl;
            return 0;
    }
    int ongkosParkir = tarifPerJam * lamaInap;
    if (lamaInap > 5) ongkosParkir -= ongkosParkir / 10;
    cout << "Biaya parkir: Rp" << ongkosParkir << endl;
    return 0;
}
```

### Soal 9. Kalender Naga Tidur

Naga tidur 366 hari pada tahun kabisat dan 365 hari pada tahun biasa. Tahun kabisat: habis dibagi 4 tapi tidak habis dibagi 100, atau habis dibagi 400.

Contoh tampilan:
```
Tahun kalender naga: 2024
2024 tahun kabisat, naga tidur 366 hari!
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int tahunNaga;
    cout << "Tahun kalender naga: ";
    cin >> tahunNaga;
    if ((tahunNaga % 4 == 0 && tahunNaga % 100 != 0) || tahunNaga % 400 == 0)
        cout << tahunNaga << " tahun kabisat, naga tidur 366 hari!" << endl;
    else
        cout << tahunNaga << " bukan kabisat, naga tidur 365 hari." << endl;
    return 0;
}
```

### Soal 10. Tiang Jembatan Segitiga

Tiga tiang jembatan harus bisa membentuk segitiga (jumlah dua sisi harus lebih besar dari sisi ketiga). Tentukan jenisnya: sama sisi, sama kaki, atau sembarang.

Contoh tampilan:
```
Panjang tiga tiang jembatan: 5 5 8
Segitiga sama kaki, jembatan cukup kokoh.
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int tiangA, tiangB, tiangC;
    cout << "Panjang tiga tiang jembatan: ";
    cin >> tiangA >> tiangB >> tiangC;
    if (tiangA + tiangB <= tiangC || tiangA + tiangC <= tiangB || tiangB + tiangC <= tiangA)
        cout << "Tiang tidak bisa membentuk segitiga, jembatan runtuh!" << endl;
    else if (tiangA == tiangB && tiangB == tiangC)
        cout << "Segitiga sama sisi, jembatan sangat kokoh!" << endl;
    else if (tiangA == tiangB || tiangB == tiangC || tiangA == tiangC)
        cout << "Segitiga sama kaki, jembatan cukup kokoh." << endl;
    else
        cout << "Segitiga sembarang, jembatan berdiri miring." << endl;
    return 0;
}
```

### Soal 11. Diskon Bertingkat Pasar Pusaka

Belanja ≥ Rp500.000 diskon 20%, ≥ Rp250.000 diskon 10%, ≥ Rp100.000 diskon 5%, selain itu tanpa diskon.

Contoh tampilan:
```
Total belanja di Pasar Pusaka: Rp300000
Diskon 10% = Rp30000
Yang harus dibayar: Rp270000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    long long belanjaPusaka;
    int persenPotongan;
    cout << "Total belanja di Pasar Pusaka: Rp";
    cin >> belanjaPusaka;
    if (belanjaPusaka >= 500000) persenPotongan = 20;
    else if (belanjaPusaka >= 250000) persenPotongan = 10;
    else if (belanjaPusaka >= 100000) persenPotongan = 5;
    else persenPotongan = 0;
    long long hematBelanja = belanjaPusaka * persenPotongan / 100;
    cout << "Diskon " << persenPotongan << "% = Rp" << hematBelanja << endl;
    cout << "Yang harus dibayar: Rp" << belanjaPusaka - hematBelanja << endl;
    return 0;
}
```

---

## BAGIAN C — LOOPING (for, while, do-while)

### Soal 12. Menara Bintang

Buat menara bintang berbentuk piramida setinggi n lantai.

Contoh tampilan:
```
Tinggi menara bintang: 4
   *
  ***
 *****
*******
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int lantaiMenara;
    cout << "Tinggi menara bintang: ";
    cin >> lantaiMenara;
    for (int tingkat = 1; tingkat <= lantaiMenara; tingkat++) {
        for (int spasiKosong = 1; spasiKosong <= lantaiMenara - tingkat; spasiKosong++) cout << " ";
        for (int bintangKu = 1; bintangKu <= 2 * tingkat - 1; bintangKu++) cout << "*";
        cout << endl;
    }
    return 0;
}
```

### Soal 13. Jurus Klon Bayangan Ninja

Setiap jurus melipatgandakan klon sesuai faktorial. Tampilkan proses perkaliannya.

Contoh tampilan:
```
Jumlah jurus bayangan: 5
5! = 5 x 4 x 3 x 2 x 1 = 120
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int jurusNinja;
    long long klonBayangan = 1;
    cout << "Jumlah jurus bayangan: ";
    cin >> jurusNinja;
    cout << jurusNinja << "! = ";
    for (int urutan = jurusNinja; urutan >= 1; urutan--) {
        klonBayangan *= urutan;
        cout << urutan;
        if (urutan > 1) cout << " x ";
    }
    cout << " = " << klonBayangan << endl;
    return 0;
}
```

### Soal 14. Peternakan Kelinci Fibonacci

Populasi kelinci tiap bulan mengikuti deret Fibonacci (1, 1, 2, 3, 5, ...). Tampilkan populasi selama n bulan dan jumlah totalnya.

Contoh tampilan:
```
Berapa bulan kelinci diternak: 7
Populasi tiap bulan: 1 1 2 3 5 8 13
Jumlah seluruh catatan: 33
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int bulanTernak;
    long long pasanganLama = 1, pasanganBaru = 1, totalKelinci = 0;
    cout << "Berapa bulan kelinci diternak: ";
    cin >> bulanTernak;
    cout << "Populasi tiap bulan:";
    for (int bulanKe = 1; bulanKe <= bulanTernak; bulanKe++) {
        cout << " " << pasanganLama;
        totalKelinci += pasanganLama;
        long long generasiNext = pasanganLama + pasanganBaru;
        pasanganLama = pasanganBaru;
        pasanganBaru = generasiNext;
    }
    cout << endl << "Jumlah seluruh catatan: " << totalKelinci << endl;
    return 0;
}
```

### Soal 15. Bola Kristal Penyihir

Penyihir menyimpan angka rahasia 42. Pemain punya 5 kesempatan menebak, dengan petunjuk "terlalu kecil" atau "terlalu besar".

Contoh tampilan:
```
Tebak angka di bola kristal (1-100), sisa 5 kesempatan: 50
Terlalu besar!
Tebak angka di bola kristal (1-100), sisa 4 kesempatan: 30
Terlalu kecil!
Tebak angka di bola kristal (1-100), sisa 3 kesempatan: 42
Tepat! Penyihir mengakui kehebatanmu!
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    const int bolaKristal = 42;
    int tebakanPetualang, kesempatanSisa = 5;
    bool berhasilTebak = false;
    while (kesempatanSisa > 0 && !berhasilTebak) {
        cout << "Tebak angka di bola kristal (1-100), sisa " << kesempatanSisa << " kesempatan: ";
        cin >> tebakanPetualang;
        if (tebakanPetualang == bolaKristal) berhasilTebak = true;
        else if (tebakanPetualang < bolaKristal) cout << "Terlalu kecil!" << endl;
        else cout << "Terlalu besar!" << endl;
        kesempatanSisa--;
    }
    if (berhasilTebak) cout << "Tepat! Penyihir mengakui kehebatanmu!" << endl;
    else cout << "Kesempatan habis, angkanya " << bolaKristal << ". Kamu dikutuk jadi kodok!" << endl;
    return 0;
}
```

### Soal 16. Penambang Digit Permata

Nomor batu permata dipecah per digit. Hitung banyak digit dan jumlah semua digitnya (gunakan do-while).

Contoh tampilan:
```
Nomor batu permata: 98765
Banyak digit : 5
Total kilau  : 35
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    long long batuPermata;
    int kilauTotal = 0, jumlahKeping = 0;
    cout << "Nomor batu permata: ";
    cin >> batuPermata;
    long long sisaBatu = batuPermata < 0 ? -batuPermata : batuPermata;
    do {
        kilauTotal += sisaBatu % 10;
        jumlahKeping++;
        sisaBatu /= 10;
    } while (sisaBatu > 0);
    cout << "Banyak digit : " << jumlahKeping << endl;
    cout << "Total kilau  : " << kilauTotal << endl;
    return 0;
}
```

### Soal 17. Regu Pasukan Kerajaan (FPB & KPK)

Pasukan panah dan pasukan tombak dibagi ke regu-regu dengan komposisi sama. Cari jumlah regu maksimal (FPB) dengan algoritma Euclid memakai while, lalu tampilkan isi tiap regu dan KPK-nya.

Contoh tampilan:
```
Jumlah pasukan panah dan tombak: 24 36
Maksimal regu yang bisa dibentuk (FPB): 12
Tiap regu: 2 pemanah dan 3 penombak
KPK kedua pasukan: 72
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int pasukanPanah, pasukanTombak;
    cout << "Jumlah pasukan panah dan tombak: ";
    cin >> pasukanPanah >> pasukanTombak;
    int kantongKiri = pasukanPanah, kantongKanan = pasukanTombak;
    while (kantongKanan != 0) {
        int sisaBagi = kantongKiri % kantongKanan;
        kantongKiri = kantongKanan;
        kantongKanan = sisaBagi;
    }
    cout << "Maksimal regu yang bisa dibentuk (FPB): " << kantongKiri << endl;
    cout << "Tiap regu: " << pasukanPanah / kantongKiri << " pemanah dan "
         << pasukanTombak / kantongKiri << " penombak" << endl;
    cout << "KPK kedua pasukan: " << pasukanPanah / kantongKiri * pasukanTombak << endl;
    return 0;
}
```

### Soal 18. Kapten Genap vs Raja Ganjil (pola game Quest IV)

Pertarungan antara Kapten Genap (HP 60) dan Raja Ganjil (HP 80). Tiap ronde user memasukkan angka dari rentang tertentu; rentang mulai 1–20 dan naik 20 setiap ronde. Kalau angkanya genap, Kapten Genap menebas dengan damage = angka / 2. Kalau ganjil, Raja Ganjil mengutuk dengan damage = angka % 7 + 3. Angka di luar rentang harus diulang. Game selesai saat salah satu HP habis, dan tampilkan siapa pemenangnya (dua kemungkinan).

Contoh tampilan:
```
Ronde 1:
Masukkan angka 1-20: 8
Genap! Kapten Genap menebas Raja Ganjil sebesar 4 damage!
Nyawa Raja Ganjil: 76

Ronde 2:
Masukkan angka 21-40: 27
Ganjil! Raja Ganjil mengutuk Kapten Genap sebesar 9 damage!
Nyawa Kapten Genap: 51

Ronde 3:
Masukkan angka 41-60: 60
Genap! Kapten Genap menebas Raja Ganjil sebesar 30 damage!
Nyawa Raja Ganjil: 46
....
Raja Ganjil tumbang! Kapten Genap menang!
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int nyawaKapten = 60, nyawaRaja = 80;
    int ronde = 1, ujungBawah = 1, ujungAtas = 20;
    while (nyawaKapten > 0 && nyawaRaja > 0) {
        int angkaSakti;
        cout << "\nRonde " << ronde << ":\n";
        cout << "Masukkan angka " << ujungBawah << "-" << ujungAtas << ": ";
        cin >> angkaSakti;
        if (angkaSakti < ujungBawah || angkaSakti > ujungAtas) {
            cout << "Angka di luar batas, ulangi!\n";
            continue;
        }
        if (angkaSakti % 2 == 0) {
            int tebasan = angkaSakti / 2;
            nyawaRaja -= tebasan;
            if (nyawaRaja < 0) nyawaRaja = 0;
            cout << "Genap! Kapten Genap menebas Raja Ganjil sebesar " << tebasan << " damage!\n";
            cout << "Nyawa Raja Ganjil: " << nyawaRaja << endl;
        } else {
            int kutukan = angkaSakti % 7 + 3;
            nyawaKapten -= kutukan;
            if (nyawaKapten < 0) nyawaKapten = 0;
            cout << "Ganjil! Raja Ganjil mengutuk Kapten Genap sebesar " << kutukan << " damage!\n";
            cout << "Nyawa Kapten Genap: " << nyawaKapten << endl;
        }
        ronde++;
        ujungBawah += 20;
        ujungAtas += 20;
    }
    if (nyawaRaja == 0) cout << "\nRaja Ganjil tumbang! Kapten Genap menang!\n";
    else cout << "\nKapten Genap gugur... Raja Ganjil berkuasa!\n";
    return 0;
}
```

### Soal 19. Celengan Sepatu Si Kancil

Si Kancil menabung tiap hari untuk membeli sepatu. Setiap 7 hari, setoran hariannya naik Rp1000. Hitung berapa hari sampai uangnya cukup.

Contoh tampilan:
```
Harga sepatu impian Si Kancil: 50000
Setoran awal per hari: 5000
Si Kancil butuh 10 hari, isi celengan Rp53000
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int targetSepatu, setoranHarian, hariMenabung = 0, isiCelengan = 0;
    cout << "Harga sepatu impian Si Kancil: ";
    cin >> targetSepatu;
    cout << "Setoran awal per hari: ";
    cin >> setoranHarian;
    if (setoranHarian <= 0) {
        cout << "Setoran harus lebih dari 0!" << endl;
        return 0;
    }
    while (isiCelengan < targetSepatu) {
        hariMenabung++;
        isiCelengan += setoranHarian;
        if (hariMenabung % 7 == 0) setoranHarian += 1000;
    }
    cout << "Si Kancil butuh " << hariMenabung << " hari, isi celengan Rp" << isiCelengan << endl;
    return 0;
}
```

---

## BAGIAN D — FUNGSI & PROSEDUR

### Soal 20. Kekuatan Mantra Berlipat

Buat fungsi yang menghitung pangkat dengan perulangan (tanpa `pow`). Energi dasar dipangkatkan dengan tingkat mantra.

Contoh tampilan:
```
Energi dasar mantra: 3
Tingkat pelipatgandaan: 4
Kekuatan mantra: 3^4 = 81
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

long long kekuatanMantra(int dasarSihir, int lipatGanda) {
    long long hasilMantra = 1;
    for (int putaran = 0; putaran < lipatGanda; putaran++) hasilMantra *= dasarSihir;
    return hasilMantra;
}

int main() {
    int energiDasar, tingkatMantra;
    cout << "Energi dasar mantra: ";
    cin >> energiDasar;
    cout << "Tingkat pelipatgandaan: ";
    cin >> tingkatMantra;
    cout << "Kekuatan mantra: " << energiDasar << "^" << tingkatMantra << " = "
         << kekuatanMantra(energiDasar, tingkatMantra) << endl;
    return 0;
}
```

### Soal 21. Bingkai Pelukis Istana

Buat prosedur (`void`) yang menggambar bingkai persegi panjang berongga dengan ukuran dan karakter tinta pilihan user.

Contoh tampilan:
```
Lebar bingkai: 5
Tinggi bingkai: 3
Karakter tinta: #
#####
#   #
#####
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

void lukisBingkai(int lebarKanvas, int tinggiKanvas, char tintaPelukis) {
    for (int barisKanvas = 1; barisKanvas <= tinggiKanvas; barisKanvas++) {
        for (int kolomKanvas = 1; kolomKanvas <= lebarKanvas; kolomKanvas++) {
            if (barisKanvas == 1 || barisKanvas == tinggiKanvas || kolomKanvas == 1 || kolomKanvas == lebarKanvas)
                cout << tintaPelukis;
            else
                cout << " ";
        }
        cout << endl;
    }
}

int main() {
    int ukuranLebar, ukuranTinggi;
    char pilihanTinta;
    cout << "Lebar bingkai: ";
    cin >> ukuranLebar;
    cout << "Tinggi bingkai: ";
    cin >> ukuranTinggi;
    cout << "Karakter tinta: ";
    cin >> pilihanTinta;
    lukisBingkai(ukuranLebar, ukuranTinggi, pilihanTinta);
    return 0;
}
```

### Soal 22. Pintu Cermin Ajaib

Pintu cermin hanya terbuka jika kode kuncinya sama dengan bayangannya (angka palindrom). Buat fungsi pembalik angka dan fungsi pengecek palindrom.

Contoh tampilan:
```
Masukkan kode kunci: 12321
Bayangan di cermin: 12321
Kode cocok dengan bayangannya, pintu cermin terbuka!
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int cerminAngka(int angkaAsli) {
    int bayangan = 0;
    while (angkaAsli > 0) {
        bayangan = bayangan * 10 + angkaAsli % 10;
        angkaAsli /= 10;
    }
    return bayangan;
}

bool pintuCermin(int kodeKunci) {
    return kodeKunci == cerminAngka(kodeKunci);
}

int main() {
    int kodeDiketik;
    cout << "Masukkan kode kunci: ";
    cin >> kodeDiketik;
    cout << "Bayangan di cermin: " << cerminAngka(kodeDiketik) << endl;
    if (pintuCermin(kodeDiketik)) cout << "Kode cocok dengan bayangannya, pintu cermin terbuka!" << endl;
    else cout << "Kode berbeda dengan bayangannya, pintu tetap terkunci." << endl;
    return 0;
}
```

### Soal 23. Sandi Biner Burung Merpati

Burung merpati hanya bisa membawa pesan dalam bentuk biner. Buat fungsi yang mengubah angka desimal menjadi string biner.

Contoh tampilan:
```
Angka pesan (desimal): 13
Sandi biner merpati: 1101
```

Jawaban:
```cpp
#include <iostream>
#include <string>
using namespace std;

string sandiBiner(int desimalPesan) {
    if (desimalPesan == 0) return "0";
    string rangkaianBit = "";
    while (desimalPesan > 0) {
        rangkaianBit = char('0' + desimalPesan % 2) + rangkaianBit;
        desimalPesan /= 2;
    }
    return rangkaianBit;
}

int main() {
    int angkaPesan;
    cout << "Angka pesan (desimal): ";
    cin >> angkaPesan;
    cout << "Sandi biner merpati: " << sandiBiner(angkaPesan) << endl;
    return 0;
}
```

### Soal 24. Barisan Dua Prajurit

Prajurit yang lebih pendek harus berdiri di depan. Buat prosedur penukar posisi menggunakan pass by reference (`&`).

Contoh tampilan:
```
Tinggi prajurit depan: 178
Tinggi prajurit belakang: 165
Sebelum: depan 178, belakang 165
Posisi ditukar!
Sesudah: depan 165, belakang 178
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

void tukarPos(int &penjagaDepan, int &penjagaBelakang) {
    int titipan = penjagaDepan;
    penjagaDepan = penjagaBelakang;
    penjagaBelakang = titipan;
}

int main() {
    int posisiSatu, posisiDua;
    cout << "Tinggi prajurit depan: ";
    cin >> posisiSatu;
    cout << "Tinggi prajurit belakang: ";
    cin >> posisiDua;
    cout << "Sebelum: depan " << posisiSatu << ", belakang " << posisiDua << endl;
    if (posisiSatu > posisiDua) {
        tukarPos(posisiSatu, posisiDua);
        cout << "Posisi ditukar!" << endl;
    } else {
        cout << "Barisan sudah benar." << endl;
    }
    cout << "Sesudah: depan " << posisiSatu << ", belakang " << posisiDua << endl;
    return 0;
}
```

### Soal 25. Batu Candi Bertingkat (Rekursif)

Candi bertingkat: lapisan paling atas 1 batu, lapisan berikutnya 2 batu, dst. Hitung total batu untuk n lapis memakai fungsi rekursif.

Contoh tampilan:
```
Jumlah lapisan candi: 10
Total batu yang dibutuhkan: 55
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int hitungBatuCandi(int lapisCandi) {
    if (lapisCandi <= 1) return lapisCandi;
    return lapisCandi + hitungBatuCandi(lapisCandi - 1);
}

int main() {
    int tingkatCandi;
    cout << "Jumlah lapisan candi: ";
    cin >> tingkatCandi;
    cout << "Total batu yang dibutuhkan: " << hitungBatuCandi(tingkatCandi) << endl;
    return 0;
}
```

### Soal 26. Penyihir Kuadrat vs Golem Batu (pola game Quest IV + fungsi)

Penyihir Kuadrat (HP 40) melawan Golem Batu (HP 75). Rentang input mulai 1–15 dan naik 15 tiap giliran. Jika angka adalah kuadrat sempurna (1, 4, 9, 16, ...), Penyihir menyerang dengan damage = akar × 5. Jika bukan, Golem menyerang dengan damage = angka % 9. Gunakan fungsi untuk mencari akar dan prosedur untuk menampilkan status.

Contoh tampilan:
```
Giliran 1:
Masukkan angka 1-15: 9
9 adalah kuadrat sempurna!
Penyihir Kuadrat melempar bola api dengan 15 damage!
Nyawa Golem Batu: 60

Giliran 2:
Masukkan angka 16-30: 20
20 bukan kuadrat sempurna..
Golem Batu menghantam dengan 2 damage!
Nyawa Penyihir Kuadrat: 38
....
Golem Batu hancur! Penyihir Kuadrat menang!
```

Jawaban:
```cpp
#include <iostream>
#include <string>
using namespace std;

int akarRune(int batuRune) {
    for (int coba = 0; coba * coba <= batuRune; coba++)
        if (coba * coba == batuRune) return coba;
    return -1;
}

void laporanArena(string namaPetarung, int sisaNyawa) {
    cout << "Nyawa " << namaPetarung << ": " << sisaNyawa << endl;
}

int main() {
    int hpPenyihir = 40, hpGolem = 75;
    int giliranDuel = 1, lantaiBawah = 1, lantaiAtas = 15;
    while (hpPenyihir > 0 && hpGolem > 0) {
        int runeDipilih;
        cout << "\nGiliran " << giliranDuel << ":\n";
        cout << "Masukkan angka " << lantaiBawah << "-" << lantaiAtas << ": ";
        cin >> runeDipilih;
        if (runeDipilih < lantaiBawah || runeDipilih > lantaiAtas) {
            cout << "Rune di luar jangkauan, ulangi!\n";
            continue;
        }
        int hasilAkar = akarRune(runeDipilih);
        if (hasilAkar != -1) {
            int bolaApi = hasilAkar * 5;
            hpGolem -= bolaApi;
            if (hpGolem < 0) hpGolem = 0;
            cout << runeDipilih << " adalah kuadrat sempurna!\n";
            cout << "Penyihir Kuadrat melempar bola api dengan " << bolaApi << " damage!\n";
            laporanArena("Golem Batu", hpGolem);
        } else {
            int hantamanGolem = runeDipilih % 9;
            hpPenyihir -= hantamanGolem;
            if (hpPenyihir < 0) hpPenyihir = 0;
            cout << runeDipilih << " bukan kuadrat sempurna..\n";
            cout << "Golem Batu menghantam dengan " << hantamanGolem << " damage!\n";
            laporanArena("Penyihir Kuadrat", hpPenyihir);
        }
        giliranDuel++;
        lantaiBawah += 15;
        lantaiAtas += 15;
    }
    if (hpGolem == 0) cout << "\nGolem Batu hancur! Penyihir Kuadrat menang!\n";
    else cout << "\nPenyihir Kuadrat tumbang... Golem Batu menguasai gua!\n";
    return 0;
}
```

---

## BAGIAN E — ARRAY (1 dimensi & 2 dimensi)

### Soal 27. Lomba Panahan Desa

Simpan skor peserta lomba panahan dalam array. Tampilkan skor tertinggi, terendah, dan rata-rata.

Contoh tampilan:
```
Jumlah peserta lomba panahan: 4
Skor peserta 1: 80
Skor peserta 2: 95
Skor peserta 3: 60
Skor peserta 4: 75
Skor tertinggi : 95
Skor terendah  : 60
Rata-rata skor : 77.5
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int nilaiPanah[100], jumlahPemanah;
    cout << "Jumlah peserta lomba panahan: ";
    cin >> jumlahPemanah;
    if (jumlahPemanah < 1 || jumlahPemanah > 100) {
        cout << "Jumlah peserta harus 1-100!" << endl;
        return 0;
    }
    for (int urutPeserta = 0; urutPeserta < jumlahPemanah; urutPeserta++) {
        cout << "Skor peserta " << urutPeserta + 1 << ": ";
        cin >> nilaiPanah[urutPeserta];
    }
    int skorJawara = nilaiPanah[0], skorBuncit = nilaiPanah[0], akumulasiSkor = 0;
    for (int urutPeserta = 0; urutPeserta < jumlahPemanah; urutPeserta++) {
        if (nilaiPanah[urutPeserta] > skorJawara) skorJawara = nilaiPanah[urutPeserta];
        if (nilaiPanah[urutPeserta] < skorBuncit) skorBuncit = nilaiPanah[urutPeserta];
        akumulasiSkor += nilaiPanah[urutPeserta];
    }
    cout << "Skor tertinggi : " << skorJawara << endl;
    cout << "Skor terendah  : " << skorBuncit << endl;
    cout << "Rata-rata skor : " << (double)akumulasiSkor / jumlahPemanah << endl;
    return 0;
}
```

### Soal 28. Barisan Semut Pulang

Barisan semut berbalik arah saat pulang ke sarang. Simpan nomor semut di array, lalu tampilkan urutan terbaliknya.

Contoh tampilan:
```
Banyak semut: 5
Nomor semut berangkat: 3 8 1 9 4
Urutan semut pulang: 4 9 1 8 3
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int barisanSemut[50], banyakSemut;
    cout << "Banyak semut: ";
    cin >> banyakSemut;
    cout << "Nomor semut berangkat: ";
    for (int langkahSemut = 0; langkahSemut < banyakSemut; langkahSemut++) cin >> barisanSemut[langkahSemut];
    cout << "Urutan semut pulang:";
    for (int langkahSemut = banyakSemut - 1; langkahSemut >= 0; langkahSemut--) cout << " " << barisanSemut[langkahSemut];
    cout << endl;
    return 0;
}
```

### Soal 29. Dadu Keberuntungan Kasino Kurcaci

Catat hasil lemparan dadu (1–6). Gunakan array sebagai penghitung, lalu tampilkan histogram bintang untuk tiap muka dadu. Input di luar 1–6 harus diulang.

Contoh tampilan:
```
Berapa kali dadu dilempar: 6
Hasil lemparan 1: 3
Hasil lemparan 2: 6
Hasil lemparan 3: 3
Hasil lemparan 4: 1
Hasil lemparan 5: 9
Muka dadu cuma 1-6!
Hasil lemparan 5: 6
Hasil lemparan 6: 3
Muka 1: * (1)
Muka 2:  (0)
Muka 3: *** (3)
Muka 4:  (0)
Muka 5:  (0)
Muka 6: ** (2)
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int catatanMuka[7] = {0};
    int kaliLempar, hasilDadu;
    cout << "Berapa kali dadu dilempar: ";
    cin >> kaliLempar;
    for (int lemparanKe = 1; lemparanKe <= kaliLempar; lemparanKe++) {
        cout << "Hasil lemparan " << lemparanKe << ": ";
        cin >> hasilDadu;
        if (hasilDadu < 1 || hasilDadu > 6) {
            cout << "Muka dadu cuma 1-6!" << endl;
            lemparanKe--;
            continue;
        }
        catatanMuka[hasilDadu]++;
    }
    for (int sisiDadu = 1; sisiDadu <= 6; sisiDadu++) {
        cout << "Muka " << sisiDadu << ": ";
        for (int tandaBintang = 0; tandaBintang < catatanMuka[sisiDadu]; tandaBintang++) cout << "*";
        cout << " (" << catatanMuka[sisiDadu] << ")" << endl;
    }
    return 0;
}
```

### Soal 30. Petak Sawah 3×3 (Array 2 Dimensi)

Sawah Pak Tani dibagi 3 baris × 3 kolom petak. Masukkan hasil panen tiap petak, tampilkan total per baris, total keseluruhan, dan baris dengan panen terbanyak.

Contoh tampilan:
```
Panen baris 1 (3 petak): 10 20 30
Panen baris 2 (3 petak): 15 25 5
Panen baris 3 (3 petak): 40 10 20
Total baris 1: 60
Total baris 2: 45
Total baris 3: 70
Total seluruh sawah: 175
Baris paling subur: baris 3
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int hasilPetak[3][3];
    int totalSawah = 0, barisSubur = 0, panenSubur = -1;
    for (int barisPetak = 0; barisPetak < 3; barisPetak++) {
        cout << "Panen baris " << barisPetak + 1 << " (3 petak): ";
        for (int kolomPetak = 0; kolomPetak < 3; kolomPetak++) cin >> hasilPetak[barisPetak][kolomPetak];
    }
    for (int barisPetak = 0; barisPetak < 3; barisPetak++) {
        int panenBaris = 0;
        for (int kolomPetak = 0; kolomPetak < 3; kolomPetak++) panenBaris += hasilPetak[barisPetak][kolomPetak];
        cout << "Total baris " << barisPetak + 1 << ": " << panenBaris << endl;
        totalSawah += panenBaris;
        if (panenBaris > panenSubur) {
            panenSubur = panenBaris;
            barisSubur = barisPetak + 1;
        }
    }
    cout << "Total seluruh sawah: " << totalSawah << endl;
    cout << "Baris paling subur: baris " << barisSubur << endl;
    return 0;
}
```

### Soal 31. Pemilah Batu Murni

Penambang memilah batu: batu bernomor prima masuk gudang murni, sisanya masuk gudang biasa. Gunakan fungsi cek prima dan dua array hasil.

Contoh tampilan:
```
Jumlah batu dalam karung: 6
Nomor batu: 2 9 11 15 17 20
Gudang murni (prima): 2 11 17
Gudang biasa        : 9 15 20
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

bool batuMurni(int kodeBatu) {
    if (kodeBatu < 2) return false;
    for (int pembagiBatu = 2; pembagiBatu * pembagiBatu <= kodeBatu; pembagiBatu++)
        if (kodeBatu % pembagiBatu == 0) return false;
    return true;
}

int main() {
    int karungBatu[50], gudangMurni[50], gudangBiasa[50];
    int isiKarung, isiMurni = 0, isiBiasa = 0;
    cout << "Jumlah batu dalam karung: ";
    cin >> isiKarung;
    cout << "Nomor batu: ";
    for (int ambilBatu = 0; ambilBatu < isiKarung; ambilBatu++) {
        cin >> karungBatu[ambilBatu];
        if (batuMurni(karungBatu[ambilBatu])) gudangMurni[isiMurni++] = karungBatu[ambilBatu];
        else gudangBiasa[isiBiasa++] = karungBatu[ambilBatu];
    }
    cout << "Gudang murni (prima):";
    for (int rakGudang = 0; rakGudang < isiMurni; rakGudang++) cout << " " << gudangMurni[rakGudang];
    cout << endl << "Gudang biasa        :";
    for (int rakGudang = 0; rakGudang < isiBiasa; rakGudang++) cout << " " << gudangBiasa[rakGudang];
    cout << endl;
    return 0;
}
```

### Soal 32. Gerbong Kereta Berputar

Rangkaian gerbong kereta diputar (rotasi) ke kanan sebanyak k langkah. Gerbong paling belakang pindah ke depan.

Contoh tampilan:
```
Jumlah gerbong: 5
Nomor gerbong: 1 2 3 4 5
Geser ke kanan berapa langkah: 2
Rangkaian baru: 4 5 1 2 3
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int rangkaianGerbong[50], gerbongBaru[50], jmlGerbong, langkahGeser;
    cout << "Jumlah gerbong: ";
    cin >> jmlGerbong;
    cout << "Nomor gerbong: ";
    for (int posGerbong = 0; posGerbong < jmlGerbong; posGerbong++) cin >> rangkaianGerbong[posGerbong];
    cout << "Geser ke kanan berapa langkah: ";
    cin >> langkahGeser;
    for (int posGerbong = 0; posGerbong < jmlGerbong; posGerbong++)
        gerbongBaru[(posGerbong + langkahGeser) % jmlGerbong] = rangkaianGerbong[posGerbong];
    cout << "Rangkaian baru:";
    for (int posGerbong = 0; posGerbong < jmlGerbong; posGerbong++) cout << " " << gerbongBaru[posGerbong];
    cout << endl;
    return 0;
}
```

### Soal 33. Pendekar Ganjil vs Tiga Slime (pola game Quest IV + array)

Pendekar Ganjil (HP 50) harus mengalahkan tiga slime berurutan yang disimpan dalam array: Slime Hijau (HP 30), Slime Biru (HP 40), Slime Raja (HP 50). Rentang input mulai 1–10 dan naik 10 tiap putaran. Angka ganjil: pendekar menyerang slime aktif dengan damage = angka itu. Angka genap: slime aktif menyerang dengan damage = angka % 10. Slime yang HP-nya habis diganti slime berikutnya. Pendekar menang kalau ketiga slime kalah.

Contoh tampilan:
```
Putaran 1 (lawan: Slime Hijau)
Masukkan angka 1-10: 7
Ganjil! Pendekar menebas Slime Hijau dengan 7 damage!
HP Slime Hijau: 23

Putaran 2 (lawan: Slime Hijau)
Masukkan angka 11-20: 14
Genap.. Slime Hijau menyembur pendekar dengan 4 damage!
HP Pendekar Ganjil: 46

Putaran 3 (lawan: Slime Hijau)
Masukkan angka 21-30: 25
Ganjil! Pendekar menebas Slime Hijau dengan 25 damage!
HP Slime Hijau: 0
Slime Hijau meleleh! Lawan berikutnya maju!
....
Semua slime musnah! Pendekar Ganjil menang!
```

Jawaban:
```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    int darahSlime[3] = {30, 40, 50};
    string julukanSlime[3] = {"Slime Hijau", "Slime Biru", "Slime Raja"};
    int darahPendekar = 50, slimeAktif = 0;
    int putaranDuel = 1, lantaiMin = 1, lantaiMax = 10;
    while (darahPendekar > 0 && slimeAktif < 3) {
        int angkaPilihan;
        cout << "\nPutaran " << putaranDuel << " (lawan: " << julukanSlime[slimeAktif] << ")\n";
        cout << "Masukkan angka " << lantaiMin << "-" << lantaiMax << ": ";
        cin >> angkaPilihan;
        if (angkaPilihan < lantaiMin || angkaPilihan > lantaiMax) {
            cout << "Angka di luar rentang, ulangi!\n";
            continue;
        }
        if (angkaPilihan % 2 != 0) {
            darahSlime[slimeAktif] -= angkaPilihan;
            if (darahSlime[slimeAktif] < 0) darahSlime[slimeAktif] = 0;
            cout << "Ganjil! Pendekar menebas " << julukanSlime[slimeAktif] << " dengan " << angkaPilihan << " damage!\n";
            cout << "HP " << julukanSlime[slimeAktif] << ": " << darahSlime[slimeAktif] << endl;
            if (darahSlime[slimeAktif] == 0) {
                cout << julukanSlime[slimeAktif] << " meleleh! ";
                slimeAktif++;
                if (slimeAktif < 3) cout << "Lawan berikutnya maju!";
                cout << endl;
            }
        } else {
            int semburan = angkaPilihan % 10;
            darahPendekar -= semburan;
            if (darahPendekar < 0) darahPendekar = 0;
            cout << "Genap.. " << julukanSlime[slimeAktif] << " menyembur pendekar dengan " << semburan << " damage!\n";
            cout << "HP Pendekar Ganjil: " << darahPendekar << endl;
        }
        putaranDuel++;
        lantaiMin += 10;
        lantaiMax += 10;
    }
    if (slimeAktif == 3) cout << "\nSemua slime musnah! Pendekar Ganjil menang!\n";
    else cout << "\nPendekar Ganjil kehabisan tenaga... para slime menang!\n";
    return 0;
}
```

---

## BAGIAN F — STRING

### Soal 34. Mantra Kuno Penuh Vokal

Kekuatan mantra ditentukan oleh jumlah huruf vokal. Masukkan satu kalimat mantra (boleh ada spasi, pakai `getline`), hitung jumlah vokal dan konsonan.

Contoh tampilan:
```
Ucapkan mantra: Abrakadabra Simsalabim
Jumlah vokal   : 9
Jumlah konsonan: 12
```

Jawaban:
```cpp
#include <iostream>
#include <string>
#include <cctype>
using namespace std;

int main() {
    string mantraKuno;
    int vokalKu = 0, konsonanKu = 0;
    cout << "Ucapkan mantra: ";
    getline(cin, mantraKuno);
    for (int posHuruf = 0; posHuruf < (int)mantraKuno.length(); posHuruf++) {
        char hurufKecil = tolower(mantraKuno[posHuruf]);
        if (isalpha(hurufKecil)) {
            if (hurufKecil == 'a' || hurufKecil == 'i' || hurufKecil == 'u' || hurufKecil == 'e' || hurufKecil == 'o')
                vokalKu++;
            else
                konsonanKu++;
        }
    }
    cout << "Jumlah vokal   : " << vokalKu << endl;
    cout << "Jumlah konsonan: " << konsonanKu << endl;
    return 0;
}
```

### Soal 35. Kata Sandi Terbalik Gua Harta

Pintu gua harta terbuka jika kata sandinya dibaca sama dari depan maupun belakang (palindrom). Balik string secara manual dengan perulangan.

Contoh tampilan:
```
Kata sandi gua: katak
Dibaca terbalik: katak
Palindrom! Pintu gua harta terbuka!
```

Jawaban:
```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string kataSandi, sandiTerbalik = "";
    cout << "Kata sandi gua: ";
    cin >> kataSandi;
    for (int posisiHuruf = (int)kataSandi.length() - 1; posisiHuruf >= 0; posisiHuruf--)
        sandiTerbalik += kataSandi[posisiHuruf];
    cout << "Dibaca terbalik: " << sandiTerbalik << endl;
    if (kataSandi == sandiTerbalik) cout << "Palindrom! Pintu gua harta terbuka!" << endl;
    else cout << "Bukan palindrom, pintu gua tetap tertutup." << endl;
    return 0;
}
```

### Soal 36. Surat Rahasia Kurir Kerajaan (Caesar Cipher)

Kurir menyandikan surat dengan menggeser setiap huruf sejauh k posisi. Huruf besar tetap besar, huruf kecil tetap kecil, selain huruf tidak berubah.

Contoh tampilan:
```
Isi surat: Serang Jam Lima
Kunci geser: 3
Surat tersandi: Vhudqj Mdp Olpd
```

Jawaban:
```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string suratRahasia;
    int geserKunci;
    cout << "Isi surat: ";
    getline(cin, suratRahasia);
    cout << "Kunci geser: ";
    cin >> geserKunci;
    geserKunci = ((geserKunci % 26) + 26) % 26;
    for (int idxSurat = 0; idxSurat < (int)suratRahasia.length(); idxSurat++) {
        char hurufSurat = suratRahasia[idxSurat];
        if (hurufSurat >= 'A' && hurufSurat <= 'Z')
            suratRahasia[idxSurat] = (hurufSurat - 'A' + geserKunci) % 26 + 'A';
        else if (hurufSurat >= 'a' && hurufSurat <= 'z')
            suratRahasia[idxSurat] = (hurufSurat - 'a' + geserKunci) % 26 + 'a';
    }
    cout << "Surat tersandi: " << suratRahasia << endl;
    return 0;
}
```

### Soal 37. Burung Beo Jungkir Balik

Burung beo menirukan kalimat tapi huruf besar jadi kecil dan huruf kecil jadi besar.

Contoh tampilan:
```
Kalimat untuk beo: Halo Kakak Tua
Tiruan beo: hALO kAKAK tUA
```

Jawaban:
```cpp
#include <iostream>
#include <string>
#include <cctype>
using namespace std;

int main() {
    string ocehanBeo;
    cout << "Kalimat untuk beo: ";
    getline(cin, ocehanBeo);
    for (int idxOceh = 0; idxOceh < (int)ocehanBeo.length(); idxOceh++) {
        if (isupper(ocehanBeo[idxOceh])) ocehanBeo[idxOceh] = tolower(ocehanBeo[idxOceh]);
        else if (islower(ocehanBeo[idxOceh])) ocehanBeo[idxOceh] = toupper(ocehanBeo[idxOceh]);
    }
    cout << "Tiruan beo: " << ocehanBeo << endl;
    return 0;
}
```

### Soal 38. Juru Tulis Penghitung Kata

Juru tulis kerajaan menghitung jumlah kata pada pengumuman. Spasi bisa lebih dari satu di antara kata.

Contoh tampilan:
```
Isi pengumuman: Kerajaan   ini sangat  luas
Jumlah kata: 4
```

Jawaban:
```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string lembarPengumuman;
    int hitungKata = 0;
    bool sedangDalamKata = false;
    cout << "Isi pengumuman: ";
    getline(cin, lembarPengumuman);
    for (int idxLembar = 0; idxLembar < (int)lembarPengumuman.length(); idxLembar++) {
        if (lembarPengumuman[idxLembar] != ' ' && !sedangDalamKata) {
            hitungKata++;
            sedangDalamKata = true;
        } else if (lembarPengumuman[idxLembar] == ' ') {
            sedangDalamKata = false;
        }
    }
    cout << "Jumlah kata: " << hitungKata << endl;
    return 0;
}
```

### Soal 39. Singkatan Gelar Bangsawan

Nama bangsawan terlalu panjang, jadi pengawal hanya menyebut inisialnya (huruf pertama tiap kata, huruf besar, diberi titik).

Contoh tampilan:
```
Nama lengkap bangsawan: raden Mas bagus Prakoso
Inisial: R.M.B.P.
```

Jawaban:
```cpp
#include <iostream>
#include <string>
#include <cctype>
using namespace std;

int main() {
    string gelarBangsawan, singkatanGelar = "";
    bool awalKata = true;
    cout << "Nama lengkap bangsawan: ";
    getline(cin, gelarBangsawan);
    for (int idxGelar = 0; idxGelar < (int)gelarBangsawan.length(); idxGelar++) {
        char hurufGelar = gelarBangsawan[idxGelar];
        if (hurufGelar != ' ' && awalKata) {
            singkatanGelar += (char)toupper(hurufGelar);
            singkatanGelar += '.';
            awalKata = false;
        } else if (hurufGelar == ' ') {
            awalKata = true;
        }
    }
    cout << "Inisial: " << singkatanGelar << endl;
    return 0;
}
```

---

## BAGIAN G — STRUCT

### Soal 40. Kartu Pahlawan Desa

Buat struct `Pahlawan` berisi julukan, level, dan serangan dasar. Total kekuatan = level × serangan dasar. Tampilkan dalam bentuk kartu.

Contoh tampilan:
```
Julukan pahlawan: Si Pedang Petir
Level: 12
Serangan dasar: 15
===== KARTU PAHLAWAN =====
Julukan : Si Pedang Petir
Level   : 12
Kekuatan: 180
==========================
```

Jawaban:
```cpp
#include <iostream>
#include <string>
using namespace std;

struct Pahlawan {
    string julukan;
    int levelSakti;
    int seranganDasar;
};

int main() {
    Pahlawan jagoanDesa;
    cout << "Julukan pahlawan: ";
    getline(cin, jagoanDesa.julukan);
    cout << "Level: ";
    cin >> jagoanDesa.levelSakti;
    cout << "Serangan dasar: ";
    cin >> jagoanDesa.seranganDasar;
    cout << "===== KARTU PAHLAWAN =====" << endl;
    cout << "Julukan : " << jagoanDesa.julukan << endl;
    cout << "Level   : " << jagoanDesa.levelSakti << endl;
    cout << "Kekuatan: " << jagoanDesa.levelSakti * jagoanDesa.seranganDasar << endl;
    cout << "==========================" << endl;
    return 0;
}
```

### Soal 41. Cendekia Teladan Perguruan

Simpan data beberapa murid perguruan (nama, nomor induk, IPK) dalam array of struct. Cari murid dengan IPK tertinggi dan hitung berapa murid yang IPK-nya di atas 3.5.

Contoh tampilan:
```
Jumlah murid: 3
Murid 1 (nama nim ipk): Bima 2401 3.45
Murid 2 (nama nim ipk): Laras 2402 3.88
Murid 3 (nama nim ipk): Satria 2403 3.62
Cendekia teladan: Laras (2402) dengan IPK 3.88
Murid dengan IPK di atas 3.5: 2 orang
```

Jawaban:
```cpp
#include <iostream>
#include <string>
using namespace std;

struct Cendekia {
    string namaPanggilan;
    string kodeInduk;
    double ipkSemester;
};

int main() {
    Cendekia rombelMurid[30];
    int jumlahMurid, idxTeladan = 0, muridCumlaude = 0;
    cout << "Jumlah murid: ";
    cin >> jumlahMurid;
    for (int urutMurid = 0; urutMurid < jumlahMurid; urutMurid++) {
        cout << "Murid " << urutMurid + 1 << " (nama nim ipk): ";
        cin >> rombelMurid[urutMurid].namaPanggilan >> rombelMurid[urutMurid].kodeInduk >> rombelMurid[urutMurid].ipkSemester;
    }
    for (int urutMurid = 0; urutMurid < jumlahMurid; urutMurid++) {
        if (rombelMurid[urutMurid].ipkSemester > rombelMurid[idxTeladan].ipkSemester) idxTeladan = urutMurid;
        if (rombelMurid[urutMurid].ipkSemester > 3.5) muridCumlaude++;
    }
    cout << "Cendekia teladan: " << rombelMurid[idxTeladan].namaPanggilan << " ("
         << rombelMurid[idxTeladan].kodeInduk << ") dengan IPK " << rombelMurid[idxTeladan].ipkSemester << endl;
    cout << "Murid dengan IPK di atas 3.5: " << muridCumlaude << " orang" << endl;
    return 0;
}
```

### Soal 42. Gudang Lapak Saudagar

Saudagar mencatat barang dagangan (nama, stok, harga satuan) dalam array of struct. Tampilkan nilai tiap barang, total nilai gudang, dan peringatan untuk barang dengan stok kurang dari 5.

Contoh tampilan:
```
Jumlah jenis barang: 3
Barang 1 (nama stok harga): Kain 10 25000
Barang 2 (nama stok harga): Rempah 3 40000
Barang 3 (nama stok harga): Kopi 8 15000
Kain: 10 x 25000 = 250000
Rempah: 3 x 40000 = 120000 (stok menipis!)
Kopi: 8 x 15000 = 120000
Total nilai gudang: Rp490000
```

Jawaban:
```cpp
#include <iostream>
#include <string>
using namespace std;

struct BarangLapak {
    string namaDagangan;
    int stokGudang;
    long long hargaSatuan;
};

int main() {
    BarangLapak lapakSaudagar[20];
    int ragamBarang;
    long long hartaGudang = 0;
    cout << "Jumlah jenis barang: ";
    cin >> ragamBarang;
    for (int noBarang = 0; noBarang < ragamBarang; noBarang++) {
        cout << "Barang " << noBarang + 1 << " (nama stok harga): ";
        cin >> lapakSaudagar[noBarang].namaDagangan >> lapakSaudagar[noBarang].stokGudang >> lapakSaudagar[noBarang].hargaSatuan;
    }
    for (int noBarang = 0; noBarang < ragamBarang; noBarang++) {
        long long nilaiBarang = lapakSaudagar[noBarang].stokGudang * lapakSaudagar[noBarang].hargaSatuan;
        hartaGudang += nilaiBarang;
        cout << lapakSaudagar[noBarang].namaDagangan << ": " << lapakSaudagar[noBarang].stokGudang
             << " x " << lapakSaudagar[noBarang].hargaSatuan << " = " << nilaiBarang;
        if (lapakSaudagar[noBarang].stokGudang < 5) cout << " (stok menipis!)";
        cout << endl;
    }
    cout << "Total nilai gudang: Rp" << hartaGudang << endl;
    return 0;
}
```

### Soal 43. Ksatria Kelipatan Tiga vs Naga Sisa Bagi (pola game Quest IV + struct)

Simpan data petarung dalam struct (nama, nyawa, tenaga). Ksatria Kelipatan Tiga: nyawa 45, tenaga 12. Naga Sisa Bagi: nyawa 90, tenaga = angka % 8. Rentang input mulai 1–10 dan naik 10 tiap giliran. Jika angka kelipatan 3, ksatria menyerang; jika bukan, naga menyerang. Buat prosedur `hantam` dengan parameter struct by reference.

Contoh tampilan:
```
Giliran 1:
Masukkan angka 1-10: 9
9 kelipatan 3!
Ksatria Kelipatan Tiga menghantam Naga Sisa Bagi dengan 12 damage!
Nyawa Naga Sisa Bagi: 78

Giliran 2:
Masukkan angka 11-20: 17
17 bukan kelipatan 3..
Naga Sisa Bagi menghantam Ksatria Kelipatan Tiga dengan 1 damage!
Nyawa Ksatria Kelipatan Tiga: 44
....
Naga Sisa Bagi dikalahkan! Ksatria Kelipatan Tiga menang!
```

Jawaban:
```cpp
#include <iostream>
#include <string>
using namespace std;

struct Petarung {
    string gelar;
    int nyawa;
    int tenaga;
};

void hantam(Petarung &pemukul, Petarung &sasaran) {
    sasaran.nyawa -= pemukul.tenaga;
    if (sasaran.nyawa < 0) sasaran.nyawa = 0;
    cout << pemukul.gelar << " menghantam " << sasaran.gelar << " dengan " << pemukul.tenaga << " damage!\n";
    cout << "Nyawa " << sasaran.gelar << ": " << sasaran.nyawa << endl;
}

int main() {
    Petarung ksatriaTiga = {"Ksatria Kelipatan Tiga", 45, 12};
    Petarung nagaSisa = {"Naga Sisa Bagi", 90, 0};
    int giliranTarung = 1, tepiBawah = 1, tepiAtas = 10;
    while (ksatriaTiga.nyawa > 0 && nagaSisa.nyawa > 0) {
        int angkaTakdir;
        cout << "\nGiliran " << giliranTarung << ":\n";
        cout << "Masukkan angka " << tepiBawah << "-" << tepiAtas << ": ";
        cin >> angkaTakdir;
        if (angkaTakdir < tepiBawah || angkaTakdir > tepiAtas) {
            cout << "Angka tidak sesuai rentang, ulangi!\n";
            continue;
        }
        if (angkaTakdir % 3 == 0) {
            cout << angkaTakdir << " kelipatan 3!\n";
            hantam(ksatriaTiga, nagaSisa);
        } else {
            nagaSisa.tenaga = angkaTakdir % 8;
            cout << angkaTakdir << " bukan kelipatan 3..\n";
            hantam(nagaSisa, ksatriaTiga);
        }
        giliranTarung++;
        tepiBawah += 10;
        tepiAtas += 10;
    }
    if (nagaSisa.nyawa == 0) cout << "\n" << nagaSisa.gelar << " dikalahkan! " << ksatriaTiga.gelar << " menang!\n";
    else cout << "\n" << ksatriaTiga.gelar << " gugur... " << nagaSisa.gelar << " menang!\n";
    return 0;
}
```

### Soal 44. Jadwal Kapal Layar

Simpan jam berangkat kapal dalam struct (jam, menit). Masukkan lama pelayaran dalam menit, hitung jam tiba. Jika lewat tengah malam, tandai "hari berikutnya". Tampilkan dengan format dua digit (HH:MM).

Contoh tampilan:
```
Jam berangkat (jam menit): 21 45
Lama berlayar (menit): 150
Kapal berangkat 21:45 dan tiba 00:15 (hari berikutnya)
```

Jawaban:
```cpp
#include <iostream>
#include <iomanip>
using namespace std;

struct WaktuLayar {
    int jamKapal;
    int menitKapal;
};

int main() {
    WaktuLayar jadwalBerangkat, jadwalTiba;
    int durasiLaut;
    cout << "Jam berangkat (jam menit): ";
    cin >> jadwalBerangkat.jamKapal >> jadwalBerangkat.menitKapal;
    cout << "Lama berlayar (menit): ";
    cin >> durasiLaut;
    int menitTotal = jadwalBerangkat.jamKapal * 60 + jadwalBerangkat.menitKapal + durasiLaut;
    int hariTerlewat = menitTotal / (24 * 60);
    menitTotal %= 24 * 60;
    jadwalTiba.jamKapal = menitTotal / 60;
    jadwalTiba.menitKapal = menitTotal % 60;
    cout << setfill('0');
    cout << "Kapal berangkat " << setw(2) << jadwalBerangkat.jamKapal << ":" << setw(2) << jadwalBerangkat.menitKapal
         << " dan tiba " << setw(2) << jadwalTiba.jamKapal << ":" << setw(2) << jadwalTiba.menitKapal;
    if (hariTerlewat == 1) cout << " (hari berikutnya)";
    else if (hariTerlewat > 1) cout << " (" << hariTerlewat << " hari kemudian)";
    cout << endl;
    return 0;
}
```

---

## BAGIAN H — SORTING

### Soal 45. Barisan Pemain Basket (Bubble Sort)

Pelatih ingin pemain berbaris dari yang paling pendek. Urutkan tinggi pemain dengan bubble sort, dan hitung berapa kali terjadi pertukaran.

Contoh tampilan:
```
Jumlah pemain: 5
Tinggi pemain: 172 165 180 158 175
Barisan rapi: 158 165 172 175 180
Jumlah pertukaran: 5
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int tinggiPemain[50], banyakPemain, totalTukar = 0;
    cout << "Jumlah pemain: ";
    cin >> banyakPemain;
    cout << "Tinggi pemain: ";
    for (int idxPemain = 0; idxPemain < banyakPemain; idxPemain++) cin >> tinggiPemain[idxPemain];
    for (int putaranSortir = 0; putaranSortir < banyakPemain - 1; putaranSortir++) {
        bool adaTukar = false;
        for (int idxPemain = 0; idxPemain < banyakPemain - 1 - putaranSortir; idxPemain++) {
            if (tinggiPemain[idxPemain] > tinggiPemain[idxPemain + 1]) {
                int simpanTinggi = tinggiPemain[idxPemain];
                tinggiPemain[idxPemain] = tinggiPemain[idxPemain + 1];
                tinggiPemain[idxPemain + 1] = simpanTinggi;
                totalTukar++;
                adaTukar = true;
            }
        }
        if (!adaTukar) break;
    }
    cout << "Barisan rapi:";
    for (int idxPemain = 0; idxPemain < banyakPemain; idxPemain++) cout << " " << tinggiPemain[idxPemain];
    cout << endl << "Jumlah pertukaran: " << totalTukar << endl;
    return 0;
}
```

### Soal 46. Podium Turnamen Catur (Selection Sort Descending)

Urutkan skor peserta turnamen dari terbesar ke terkecil dengan selection sort, lalu tampilkan tiga juara teratas.

Contoh tampilan:
```
Jumlah peserta: 6
Skor peserta: 450 720 310 890 560 700
Urutan skor: 890 720 700 560 450 310
Juara 1: 890
Juara 2: 720
Juara 3: 700
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int poinCatur[50], pesertaCatur;
    cout << "Jumlah peserta: ";
    cin >> pesertaCatur;
    cout << "Skor peserta: ";
    for (int idxPapan = 0; idxPapan < pesertaCatur; idxPapan++) cin >> poinCatur[idxPapan];
    for (int idxPapan = 0; idxPapan < pesertaCatur - 1; idxPapan++) {
        int posTerbesar = idxPapan;
        for (int idxLawan = idxPapan + 1; idxLawan < pesertaCatur; idxLawan++)
            if (poinCatur[idxLawan] > poinCatur[posTerbesar]) posTerbesar = idxLawan;
        int tampungPoin = poinCatur[idxPapan];
        poinCatur[idxPapan] = poinCatur[posTerbesar];
        poinCatur[posTerbesar] = tampungPoin;
    }
    cout << "Urutan skor:";
    for (int idxPapan = 0; idxPapan < pesertaCatur; idxPapan++) cout << " " << poinCatur[idxPapan];
    cout << endl;
    for (int idxPodium = 0; idxPodium < 3 && idxPodium < pesertaCatur; idxPodium++)
        cout << "Juara " << idxPodium + 1 << ": " << poinCatur[idxPodium] << endl;
    return 0;
}
```

### Soal 47. Hasil Tangkapan Nelayan (Insertion Sort pada Struct)

Nelayan mencatat jenis ikan dan beratnya dalam array of struct. Urutkan dari ikan terberat ke teringan dengan insertion sort.

Contoh tampilan:
```
Jumlah tangkapan: 4
Ikan 1 (jenis berat): Tongkol 3.5
Ikan 2 (jenis berat): Kakap 7.2
Ikan 3 (jenis berat): Bandeng 1.8
Ikan 4 (jenis berat): Tuna 12
Urutan dari terberat:
1. Tuna - 12 kg
2. Kakap - 7.2 kg
3. Tongkol - 3.5 kg
4. Bandeng - 1.8 kg
```

Jawaban:
```cpp
#include <iostream>
#include <string>
using namespace std;

struct TangkapanIkan {
    string jenisIkan;
    double beratKilo;
};

int main() {
    TangkapanIkan jaringNelayan[30];
    int jumlahTangkapan;
    cout << "Jumlah tangkapan: ";
    cin >> jumlahTangkapan;
    for (int noIkan = 0; noIkan < jumlahTangkapan; noIkan++) {
        cout << "Ikan " << noIkan + 1 << " (jenis berat): ";
        cin >> jaringNelayan[noIkan].jenisIkan >> jaringNelayan[noIkan].beratKilo;
    }
    for (int noIkan = 1; noIkan < jumlahTangkapan; noIkan++) {
        TangkapanIkan ikanDipegang = jaringNelayan[noIkan];
        int posSelip = noIkan - 1;
        while (posSelip >= 0 && jaringNelayan[posSelip].beratKilo < ikanDipegang.beratKilo) {
            jaringNelayan[posSelip + 1] = jaringNelayan[posSelip];
            posSelip--;
        }
        jaringNelayan[posSelip + 1] = ikanDipegang;
    }
    cout << "Urutan dari terberat:" << endl;
    for (int noIkan = 0; noIkan < jumlahTangkapan; noIkan++)
        cout << noIkan + 1 << ". " << jaringNelayan[noIkan].jenisIkan << " - " << jaringNelayan[noIkan].beratKilo << " kg" << endl;
    return 0;
}
```

---

## BAGIAN I — SEARCHING

### Soal 48. Pencarian Tiket Penonton (Linear Search)

Petugas mencari nomor tiket di antrean. Tampilkan semua posisi antrean tempat nomor itu muncul dan berapa kali muncul.

Contoh tampilan:
```
Jumlah penonton di antrean: 7
Nomor tiket: 12 5 33 5 8 21 5
Nomor tiket yang dicari: 5
Ditemukan di antrean ke: 2 4 7
Nomor 5 muncul 3 kali
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int antreanTiket[50], panjangAntrean, tiketBuruan, kaliKetemu = 0;
    cout << "Jumlah penonton di antrean: ";
    cin >> panjangAntrean;
    cout << "Nomor tiket: ";
    for (int posAntre = 0; posAntre < panjangAntrean; posAntre++) cin >> antreanTiket[posAntre];
    cout << "Nomor tiket yang dicari: ";
    cin >> tiketBuruan;
    for (int posAntre = 0; posAntre < panjangAntrean; posAntre++) {
        if (antreanTiket[posAntre] == tiketBuruan) {
            if (kaliKetemu == 0) cout << "Ditemukan di antrean ke:";
            cout << " " << posAntre + 1;
            kaliKetemu++;
        }
    }
    if (kaliKetemu > 0) cout << endl << "Nomor " << tiketBuruan << " muncul " << kaliKetemu << " kali" << endl;
    else cout << "Nomor " << tiketBuruan << " tidak ada di antrean." << endl;
    return 0;
}
```

### Soal 49. Rak Buku Perpustakaan Istana (Binary Search)

Kode buku di rak sudah urut dari kecil ke besar. Cari kode buku dengan binary search dan tampilkan setiap langkah pencariannya.

Contoh tampilan:
```
Jumlah buku di rak: 8
Kode buku (urut naik): 101 115 120 134 150 167 180 199
Kode yang dicari: 167
Langkah 1: cek rak ke-4 (kode 134)
Langkah 2: cek rak ke-6 (kode 167)
Buku ditemukan di rak ke-6 setelah 2 langkah!
```

Jawaban:
```cpp
#include <iostream>
using namespace std;

int main() {
    int rakBuku[50], banyakBuku, kodeDicari;
    cout << "Jumlah buku di rak: ";
    cin >> banyakBuku;
    cout << "Kode buku (urut naik): ";
    for (int idxRak = 0; idxRak < banyakBuku; idxRak++) cin >> rakBuku[idxRak];
    cout << "Kode yang dicari: ";
    cin >> kodeDicari;
    int batasKiri = 0, batasKanan = banyakBuku - 1, letakBuku = -1, langkahCari = 0;
    while (batasKiri <= batasKanan) {
        int tengahRak = (batasKiri + batasKanan) / 2;
        langkahCari++;
        cout << "Langkah " << langkahCari << ": cek rak ke-" << tengahRak + 1 << " (kode " << rakBuku[tengahRak] << ")" << endl;
        if (rakBuku[tengahRak] == kodeDicari) {
            letakBuku = tengahRak;
            break;
        } else if (rakBuku[tengahRak] < kodeDicari) {
            batasKiri = tengahRak + 1;
        } else {
            batasKanan = tengahRak - 1;
        }
    }
    if (letakBuku != -1) cout << "Buku ditemukan di rak ke-" << letakBuku + 1 << " setelah " << langkahCari << " langkah!" << endl;
    else cout << "Buku dengan kode " << kodeDicari << " tidak ada di rak." << endl;
    return 0;
}
```

### Soal 50. Buku Tamu Penginapan (Searching pada Struct)

Penginapan mencatat nama tamu dan nomor kamarnya dalam array of struct. Resepsionis mencari kamar berdasarkan nama tamu, tanpa memedulikan huruf besar/kecil. Buat fungsi untuk mengubah string ke huruf kecil.

Contoh tampilan:
```
Jumlah tamu: 4
Tamu 1 (nama kamar): Budi 101
Tamu 2 (nama kamar): Sari 205
Tamu 3 (nama kamar): Anton 310
Tamu 4 (nama kamar): Dewi 112
Nama tamu yang dicari: sari
Tamu Sari menginap di kamar 205
```

Jawaban:
```cpp
#include <iostream>
#include <string>
#include <cctype>
using namespace std;

struct TamuInap {
    string namaTamu;
    int nomorKamar;
};

string kecilkanHuruf(string kataAsal) {
    for (int idxKata = 0; idxKata < (int)kataAsal.length(); idxKata++) kataAsal[idxKata] = tolower(kataAsal[idxKata]);
    return kataAsal;
}

int main() {
    TamuInap bukuTamu[30];
    int jumlahTamu, kamarKetemu = -1;
    string namaBuruan;
    cout << "Jumlah tamu: ";
    cin >> jumlahTamu;
    for (int urutTamu = 0; urutTamu < jumlahTamu; urutTamu++) {
        cout << "Tamu " << urutTamu + 1 << " (nama kamar): ";
        cin >> bukuTamu[urutTamu].namaTamu >> bukuTamu[urutTamu].nomorKamar;
    }
    cout << "Nama tamu yang dicari: ";
    cin >> namaBuruan;
    for (int urutTamu = 0; urutTamu < jumlahTamu; urutTamu++) {
        if (kecilkanHuruf(bukuTamu[urutTamu].namaTamu) == kecilkanHuruf(namaBuruan)) {
            kamarKetemu = urutTamu;
            break;
        }
    }
    if (kamarKetemu != -1)
        cout << "Tamu " << bukuTamu[kamarKetemu].namaTamu << " menginap di kamar " << bukuTamu[kamarKetemu].nomorKamar << endl;
    else
        cout << "Tidak ada tamu bernama " << namaBuruan << " di penginapan ini." << endl;
    return 0;
}
```
