# Tugas Logika Fuzzy
Terdapat suatu tempat usaha reparasi barang elektronik,
Di luar biaya reparasi, pemilik biasa menerima bonus dari pelanggan sebagai tanda terimakasih.
Besar bonus bergantung pada tiga kriteria yaitu hasil reparasi, biaya reparasi, dan durasi reparasi.
Jika hasil reparasi bagus, biaya reparasi murah, dan durasi reparasi cepat, pelanggan mungkin memberikan bonus yang besar.
Sebaliknya jika hasil reparasi buruk, biaya reparasi mahal, atau durasi reparasi lama, pelanggan mungkin memberikan bonus kecil atau tidak sama sekali.
## Source Code .fis
```
[System]
Name='FISBonusReparasi'
Type='mamdani'
Version=2.0
NumInputs=3
NumOutputs=1
NumRules=18
AndMethod='min'
OrMethod='max'
ImpMethod='min'
AggMethod='max'
DefuzzMethod='centroid'

[Input1]
Name='Hasil_Reparasi'
Range=[0 10]
NumMFs=3
MF1='Buruk':'gaussmf',[1.769 -1.388e-16]
MF2='Normal':'gaussmf',[1.769 5]
MF3='Bagus':'gaussmf',[1.769 10]

[Input2]
Name='Biaya_Reparasi'
Range=[0 10]
NumMFs=2
MF1='Mahal':'trimf',[-4 0 7]
MF2='Murah':'trimf',[3 10 14]

[Input3]
Name='Durasi_Reparasi'
Range=[0 10]
NumMFs=3
MF1='Lama':'gaussmf',[1.74 0.03873]
MF2='Normal':'gaussmf',[1.769 5]
MF3='Cepat':'gaussmf',[1.769 10]

[Output1]
Name='Bonus'
Range=[0 30]
NumMFs=3
MF1='Sedikit':'trimf',[0 5 10]
MF2='Sedang':'trimf',[10 15 20]
MF3='Banyak':'trimf',[20 25 30]

[Rules]
1 1 1, 1 (1) : 1
1 1 2, 1 (1) : 1
1 1 3, 1 (1) : 1
1 2 1, 1 (1) : 1
1 2 2, 2 (1) : 1
1 2 3, 2 (1) : 1
2 1 1, 1 (1) : 1
2 1 2, 2 (1) : 1
2 1 3, 2 (1) : 1
2 2 1, 2 (1) : 1
2 2 2, 2 (1) : 1
2 2 3, 3 (1) : 1
3 1 1, 2 (1) : 1
3 1 2, 2 (1) : 1
3 1 3, 3 (1) : 1
3 2 1, 3 (1) : 1
3 2 2, 3 (1) : 1
3 2 3, 3 (1) : 1

```
## Screenshot
Buka Aplikasi MATLAB, kemudian ketikkan command "fuzzy" hingga muncul FIS Editor. <br>
![Gambar 1](https://raw.githubusercontent.com/risangpanggalih/Tugas-Logika-Fuzzy/main/Screenshot/Fuzzy%20(1).png)<br>
<br>
Pada FIS Editor, variable linguistik yang akan menjadi input dan output dalam menyelesaikan kasus dimasukkan, dalam kasus ini variabel yang akan digunakan adalah Hasil_Reparasi, Biaya_Reparasi, dan Durasi_Reparasi sebagai input dan Bonus sebagai output.<br>
![Gambar 2](https://raw.githubusercontent.com/risangpanggalih/Tugas-Logika-Fuzzy/main/Screenshot/Fuzzy%20(2).png)<br>
<br>
Simpan FIS pada workspace dan to file<br>
![Gambar 3](https://raw.githubusercontent.com/risangpanggalih/Tugas-Logika-Fuzzy/main/Screenshot/Fuzzy%20(3).png)<br>
![Gambar 4](https://raw.githubusercontent.com/risangpanggalih/Tugas-Logika-Fuzzy/main/Screenshot/Fuzzy%20(4).png)<br>
<br>
Buat membership function tiap variabel FIS beserta term nya.<br>
Input Hasil_Reparasi memiliki term Buruk, Normal, dan Bagus (tipe gaussmf)<br>
![Gambar 5](https://raw.githubusercontent.com/risangpanggalih/Tugas-Logika-Fuzzy/main/Screenshot/Fuzzy%20(5).png)<br>
Input Biaya_Reparasi memiliki term Mahal dan Murah (tipe trimf)<br>
![Gambar 6](https://raw.githubusercontent.com/risangpanggalih/Tugas-Logika-Fuzzy/main/Screenshot/Fuzzy%20(6).png)<br>
Input Durasi_Reparasi memiliki term Lama, Normal, dan Cepat (tipe gaussmf)<br>
![Gambar 7](https://raw.githubusercontent.com/risangpanggalih/Tugas-Logika-Fuzzy/main/Screenshot/Fuzzy%20(7).png)<br>
Output Bonus memiliki term Sedikit, Sedang, dan Banyak (tipe trimf)<br>
![Gambar 8](https://raw.githubusercontent.com/risangpanggalih/Tugas-Logika-Fuzzy/main/Screenshot/Fuzzy%20(8).png)<br>
<br>
Tentukan rules dari sistem inferensi fuzzy<br>
![Gambar 9](https://raw.githubusercontent.com/risangpanggalih/Tugas-Logika-Fuzzy/main/Screenshot/Fuzzy%20(9).png)<br>
<br>
Tampilan dalam bentuk Rule Viewer<br>
![Gambar 10](https://raw.githubusercontent.com/risangpanggalih/Tugas-Logika-Fuzzy/main/Screenshot/Fuzzy%20(10).png)<br>
<br>
Tampilan dalam bentuk 3D Surface Viewer<br>
![Gambar 11](https://raw.githubusercontent.com/risangpanggalih/Tugas-Logika-Fuzzy/main/Screenshot/Fuzzy%20(11).png)<br>
![Gambar 12](https://raw.githubusercontent.com/risangpanggalih/Tugas-Logika-Fuzzy/main/Screenshot/Fuzzy%20(12).png)<br>
![Gambar 13](https://raw.githubusercontent.com/risangpanggalih/Tugas-Logika-Fuzzy/main/Screenshot/Fuzzy%20(13).png)<br>
