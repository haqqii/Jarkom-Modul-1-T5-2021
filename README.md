# Jarkom-Modul-1-T5-2021
Oleh :
1. Shavica Ihya Q A L    (05311940000013)
2. Gerry Putra Fresnando (05311940000031)
3. Mohammad Ibadul Haqqi (05311940000037)

---

## Nomer 1
Sebutkan webserver yang digunakan pada `ichimarumaru.tech` 

Solusi
Gunakan filter :

```
http.host contains "ichimarumaru.tech"
```

Maka akan muncul paket yang mengandung host `ichimarumaru.tech`

<img src="https://i.postimg.cc/wvyS55Wb/Screenshot-592.png">

Jadi webserver yang digunakan adalah **nginx/1.18.0** (Ubuntu)



## Nomer 2
Temukan paket dari web-web yang menggunakan basic authentication method!

Solusi
Gunakan filter :

```
http.authbasic
```

<img src="https://i.postimg.cc/D0J97QkK/Screenshot-593.png">

## Nomer 3
Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!

Solusi
Gunakan filter :

```
http.host contains "basic.ichimarumaru.tech"
```

![Screenshot (609)](https://user-images.githubusercontent.com/73151831/134770009-6c49bbdb-c3cb-43e3-ac52-e02860e09251.png)

Maka didapatkan username `kuncimenujulautan` dan password `tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN`
Setelah itu login ke `basic.ichimarumaru.tech` dan menjawab soal didalamnya

![messageImage_1632146051644](https://user-images.githubusercontent.com/73151831/134770155-fbaf2f16-6ebf-4fab-9df5-096f94b84909.jpg)

## Nomer 4
Temukan paket mysql yang mengandung perintah query select!

Solusi
Gunakan filter :

```
mysql.command ==3 and frame matches "select"
```

![image](https://user-images.githubusercontent.com/73151831/134770061-c14ad9c7-23fa-4c6e-b5fe-daf10c0aed93.png)

## Nomer 5
Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!

Solusi
Gunakan filter :

```
mysql.command ==3 and frame matches "insert"
```

![image](https://user-images.githubusercontent.com/73151831/134770167-4c0e8d3e-98df-4ac4-8e63-42cba226e9d0.png)

Maka didapatkan username `akakanomi` dan password `pemisah4lautan`
Setelah itu login ke `portal.ichimarumaru.tech` dan menjawab soal didalamnya

![messageImage_1632145910524](https://user-images.githubusercontent.com/73151831/134770241-f6ffe9f7-0ed6-48ae-8fab-debe74c7ed39.jpg)

## Nomer 6
Cari username dan password ketika melakukan login ke FTP Server!

Solusi
Gunakan filter :

```
ftp.request.command == PASS || ftp.request.command == USER
```

![Screenshot (610)](https://user-images.githubusercontent.com/73151831/134770574-6e7e0f90-b805-421b-83a2-c3a5373adfab.png)

Maka akan didapatkan username `secretuser` dan password `aku.pengen.pw.aja`

## Nomer 7
Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")

Solusi
Gunakan filter :

```
ftp-data contains "Real.pdf"
```

![image](https://user-images.githubusercontent.com/73151831/134770691-5bf302f5-f8c0-4658-bad2-6637006e2a81.png)

Setelah itu follow TCP stream dan Show data as Raw

![Screenshot (594)](https://user-images.githubusercontent.com/73151831/134771011-339c5115-663b-4ef2-b3a8-5dd3301448c6.png)

Lalu disimpan dengan nama Real.zip dan extract

![Screenshot (595)](https://user-images.githubusercontent.com/73151831/134770805-aea26b37-23ad-4962-9625-8ad1d5edb50a.png)

Buka file Real.pdf

![Screenshot (596)](https://user-images.githubusercontent.com/73151831/134770856-cf25239c-0ba1-4246-93e4-8b2e8e98f473.png)

## Nomer 8
Cari paket yang menunjukan pengambilan file dari FTP tersebut!

Solusi
Gunakan filter :

```
ftp.request.command == STOR
```

![Screenshot (608)](https://user-images.githubusercontent.com/73151831/134770896-fa4f3612-2e64-4c74-9a5d-a7d6d61646b0.png)

## Nomer 9
Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!

Solusi
Gunakan filter :

```
ftp-data contains "secret.zip"
```

![9](https://user-images.githubusercontent.com/73151522/134773573-42c607ba-93a7-42fe-84b8-c1587fe4ef58.jpg)


## Nomer 10
Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!

Solusi
Gunakan filter :

```
ftp-data contains "history.txt"
```

Hasil perolehan unzip file

![10](https://user-images.githubusercontent.com/73151522/134773566-ad16a654-20ce-4171-8763-ad652d5acb70.jpg)


## Nomer 11
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!

Solusi
Gunakan filter :

```
src port 80
```

![11](https://user-images.githubusercontent.com/73151522/134773554-3540673b-371a-46fc-931f-a93f0c80e8d3.png)

Tampilan paket port 80

![11-1](https://user-images.githubusercontent.com/73151522/134773557-7d1e5377-9a5f-41f0-b2ed-c49dfe5dbe24.png)


## Nomer 12
Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

Solusi
Gunakan filter :

```
src port 21
```

![12](https://user-images.githubusercontent.com/73151522/134773544-fb1ff9bb-e588-49f0-9d98-68c1db7c74f1.jpg)


## Nomer 13
Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

Solusi
Gunakan filter :

```
dst port 443
```

![15](https://user-images.githubusercontent.com/73151522/134772889-e23909fc-167b-4600-b077-822fdfef5f07.jpg)

Tampilan paket port 443

![13](https://user-images.githubusercontent.com/73151522/134772937-59c0e74a-0384-413c-ab62-48cc8b2b2c85.jpg)


## Nomer 14
Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!

Solusi
Gunakan filter :

```
dst host kemenag.go.id
```

![14](https://user-images.githubusercontent.com/73151522/134772919-2cc9d205-360d-4182-a253-a32a1633dc45.png)

Hasil perolehan tampilan paket kemenag.go.id

![14-1](https://user-images.githubusercontent.com/73151522/134772922-2e41c632-983c-4f98-9463-22f646aecf90.png)


## Nomer 15
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

Solusi
Gunakan filter :

```
ip src 192.168.43.161
```

![image](https://user-images.githubusercontent.com/73151831/134774319-087488ed-1ae3-44d9-818c-bff9177af0f2.png)

Tampilan paket dengan IP Address 192.168.43.161

![15-2](https://user-images.githubusercontent.com/73151522/134772900-71f385ee-d43e-4da5-9896-b9c40678f10e.png)
