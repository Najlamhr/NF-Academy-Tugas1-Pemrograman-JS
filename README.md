# NF-Academy-Tugas1-Pemrograman-JS

<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Menghitung Luas dan Volume Bangun</title>
    <style>
        /* Gaya untuk body */
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(to right, lightcoral, pink
             );
            color: white;
            text-align: center;
            margin: 0;
            padding: 20px;
        }

        /* Gaya untuk container utama */
        .container {
            background: rgba(255, 255, 255, 0);
            padding: 20px;
            border-radius: 10px;
            max-width: 600px;
            margin: auto;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.377);
        }

        /* Gaya untuk judul */
        h2 {
            margin-bottom: 10px;
        }

        /* Gaya untuk setiap bagian input */
        .section {
            background: rgba(255, 255, 255, 0.3);
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 15px;
        }

        /* Gaya untuk label */
        label {
            font-weight: bold;
            display: block;
            margin: 10px 0 5px;
        }

        /* Gaya untuk input */
        input {
            width: 90%;
            padding: 8px;
            border-radius: 5px;
            border: none;
            outline: none;
            font-size: 16px;
            text-align: center;
        }

        /* Gaya untuk tombol */
        button {
            background: magenta;
            color: white;
            border: none;
            padding: 10px 20px;
            font-size: 18px;
            cursor: pointer;
            border-radius: 5px;
            transition: 0.3s;
            margin-top: 10px;
        }

        button:hover {
            background: #ff416c;
        }

        /* Gaya untuk hasil perhitungan */
        #hasil {
            background: rgba(0, 0, 0, 0.3);
            padding: 15px;
            margin-top: 20px;
            border-radius: 8px;
            font-size: 18px;
            text-align: left;
        }

        /* Gaya responsif */
        @media (max-width: 600px) {
            .container {
                width: 90%;
            }
            input {
                width: 100%;
            }
        }
    </style>
    <script>
        // Fungsi untuk menghitung luas persegi panjang: panjang × lebar
        function luasPersegiPanjang(panjang, lebar) {
            return panjang * lebar;
        }

        // Fungsi untuk menghitung volume balok: panjang × lebar × tinggi
        function volumeBalok(panjang, lebar, tinggi) {
            return panjang * lebar * tinggi;
        }

        // Fungsi untuk menghitung luas bujur sangkar: sisi × sisi
        function luasBujurSangkar(sisi) {
            return sisi * sisi;
        }

        // Fungsi untuk menghitung volume kubus: sisi³ (sisi × sisi × sisi)
        function volumeKubus(sisi) {
            return sisi * sisi * sisi;
        }

        // Fungsi untuk menghitung luas segitiga: (alas × tinggi) ÷ 2
        function luasSegitiga(alas, tinggi) {
            return (alas * tinggi) / 2;
        }

        // Fungsi untuk menghitung volume prisma segitiga: (alas × tinggi segitiga ÷ 2) × tinggi prisma
        function volumePrismaSegitiga(alas, tinggiSegitiga, tinggiPrisma) {
            return (alas * tinggiSegitiga / 2) * tinggiPrisma;
        }

        // Fungsi untuk mengambil input dari pengguna, melakukan perhitungan, dan menampilkan hasil di halaman
        function hitungLuasDanVolume() {
            let panjang = parseFloat(document.getElementById("panjang_persegi_panjang").value);
            let lebar = parseFloat(document.getElementById("lebar_persegi_panjang").value);
            let tinggiBalok = parseFloat(document.getElementById("tinggi_balok").value);
            let sisi = parseFloat(document.getElementById("sisi_bujur_sangkar").value);
            let alas = parseFloat(document.getElementById("alas_segitiga").value);
            let tinggiSegitiga = parseFloat(document.getElementById("tinggi_segitiga").value);
            let tinggiPrisma = parseFloat(document.getElementById("tinggi_prisma").value);

            document.getElementById("hasil").innerHTML = `
                <p><strong>Luas Persegi Panjang:</strong> ${luasPersegiPanjang(panjang, lebar)}</p>
                <p><strong>Volume Balok:</strong> ${volumeBalok(panjang, lebar, tinggiBalok)}</p>
                <p><strong>Luas Bujur Sangkar:</strong> ${luasBujurSangkar(sisi)}</p>
                <p><strong>Volume Kubus:</strong> ${volumeKubus(sisi)}</p>
                <p><strong>Luas Segitiga:</strong> ${luasSegitiga(alas, tinggiSegitiga)}</p>
                <p><strong>Volume Prisma Segitiga:</strong> ${volumePrismaSegitiga(alas, tinggiSegitiga, tinggiPrisma)}</p>
            `;
        }
    </script>
</head>
<body>

    <div class="container">
        <h2>Menghitung Luas dan Volume Bangun</h2>

        <!-- Persegi Panjang & Balok -->
        <div class="section">
            <h3>Persegi Panjang & Balok</h3>
            <label>Panjang:</label>
            <input type="number" id="panjang_persegi_panjang">
            <label>Lebar:</label>
            <input type="number" id="lebar_persegi_panjang">
            <label>Tinggi Balok:</label>
            <input type="number" id="tinggi_balok">
        </div>

        <!-- Bujur Sangkar & Kubus -->
        <div class="section">
            <h3>Bujur Sangkar & Kubus</h3>
            <label>Sisi:</label>
            <input type="number" id="sisi_bujur_sangkar">
        </div>

        <!-- Segitiga & Prisma Segitiga -->
        <div class="section">
            <h3>Segitiga & Prisma Segitiga</h3>
            <label>Alas:</label>
            <input type="number" id="alas_segitiga">
            <label>Tinggi Segitiga:</label>
            <input type="number" id="tinggi_segitiga">
            <label>Tinggi Prisma:</label>
            <input type="number" id="tinggi_prisma">
        </div>

        <!-- Tombol untuk menghitung -->
        <button onclick="hitungLuasDanVolume()">Hitung Luas dan Volume</button>

        <!-- Hasil perhitungan -->
        <div id="hasil"></div>
    </div>

</body>
</html>
