<!DOCTYPE html>
<html>
<head>
    <title>Layanan Verifikasi Lokasi</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; padding-top: 50px; }
        #status { color: blue; font-weight: bold; }
        button { padding: 10px 20px; font-size: 16px; cursor: pointer; background: #28a745; color: white; border: none; border-radius: 5px; }
    </style>
</head>
<body>
    <h2>Verifikasi Lokasi Perangkat</h2>
    <p>Silakan klik tombol di bawah untuk membagikan lokasi Anda guna keperluan pelacakan/keamanan.</p>
    
    <button onclick="getLocation()">Bagikan Lokasi</button>
    
    <p id="status"></p>
    <div id="maplink"></div>

    <script>
        const status = document.getElementById('status');
        const maplink = document.getElementById('maplink');

        function getLocation() {
            if (navigator.geolocation) {
                status.innerHTML = "Sedang mencari lokasi...";
                navigator.geolocation.getCurrentPosition(showPosition, showError);
            } else {
                status.innerHTML = "Browser Anda tidak mendukung fitur ini.";
            }
        }

        function showPosition(position) {
            const lat = position.coords.latitude;
            const lon = position.coords.longitude;
            status.innerHTML = "Lokasi Berhasil Didapatkan!";
            maplink.innerHTML = `<h3>Koordinat Anda:</h3>
                                 <p>Latitude: ${lat}<br>Longitude: ${lon}</p>
                                 <a href="https://www.google.com/maps?q=${lat},${lon}" target="_blank">Lihat di Google Maps</a>`;
        }

        function showError(error) {
            switch(error.code) {
                case error.PERMISSION_DENIED:
                    status.innerHTML = "Gagal: Anda harus mengizinkan akses lokasi.";
                    break;
                case error.POSITION_UNAVAILABLE:
                    status.innerHTML = "Informasi lokasi tidak tersedia.";
                    break;
                case error.TIMEOUT:
                    status.innerHTML = "Waktu permintaan habis.";
                    break;
            }
        }
    </script>
</body>
</html>
