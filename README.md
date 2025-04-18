# Stream Wahyu Arliansyah

# Soal 1

Ganti title dengan nama panggilan

```Dart
 return MaterialApp(
      title: 'Wahyu Arliansyah',
      theme: ThemeData(primarySwatch: Colors.blue),
      home: const StreamHomePage(),
    );
```

# Soal 2

Ganti 5 warna sesuai keinginan

```Dart
final List<Color> colors = [
    Colors.red,
    Colors.green,
    Colors.blue,
    Colors.yellow,
    Colors.orange,
  ];
```

# Soal 3

1. `yield*` dalam code ini berfungsi untuk mendelegasikan semua nilai yang dihasilkan oleh `Stream.periodic` ke stream yang sedang dibangun, `Stream.periodic` akan menghasilkan warna dari list `colors` setiap 1 detik.
2. Code ini bermaksud untuk membuat suatu `stream` yang mengeluarkan warna setiap 1 detik secara berulang-ulang dari list warna yang udah dibuat diatas.

# Soal 4

![Soal3](images/gif1.gif)

# Soal 5

Perbedaan antara menggunakan `listen` dan `await for`

1. `listen` Eksekusi kode berlanjut setelah pemanggilan dan lebih cocok untuk UI karena non-blocking dan lebih mudah dikontrol (bisa di-cancel)
2. `await for` kode akan berhenti ketika sudah berhenti looping (karena menggunakan `stream periodic` jadi tidak akan pernah berhenti/selesai).

# Soal 6

1. Pengertian praktikum 8 dan 10
   Praktikum 8

   ```Dart
   void initState() {
    numberStream = NumberStream();
    numberStreamController = numberStream.controller;
    Stream stream = numberStreamController.stream;
    stream.listen((event) {
      setState(() {
        lastNumber = event;
      });
    });
    super.initState();
   }
   ```

   Persiapan stream ketika wigdet pertama kali dibuat, membuat sistem untuk menerima data angka yang dikirim melalui stream, dan setiap ada angka yang baru, akan update `lastNumber` dan rebuild wigdet.

   Praktikum 10

   ```Dart
     void addRandomNumber() {
    Random random = Random();
    int myNum = random.nextInt(10);
    numberStream.addNumberToSink(myNum);
   }
   ```

   Maksud dari kode ini adalah membuat angka yang random/acak dari 0-9, ngirim angka ke stream lewat sink dan angka ini akan nerima oleh listener di `initState()` dan memperbarui UI.
