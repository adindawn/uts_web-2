# Efisiensi Komunikasi Dua Arah: Eksperimen WebSocket pada Aplikasi Web Modern

Nama: Adinda Aulia Nabila Putri 

Nim: 312410309

Kelas: I241D

1. Deskripsi Tugas
  
   Tugas ini bertujuan untuk memahami secara mendalam teknologi web modern melalui eksperimen langsung dan membagikan hasilnya dalam bentuk artikel publikasi online. Ketentuan utama meliputi:
   * Orisinalitas: Karya asli yang menyertakan detail langkah eksperimen dan analisis.
   * Topik: Implementasi WebSocket dan perbandingannya dengan HTTP tradisional.
   * Pengecekan Plagiasi: Skor 14%.
  
```
const WebSocket = require('ws');
const wss = new WebSocket.Server({ port: 8080 });

wss.on('connection', (ws) => {
    console.log('Koneksi baru berhasil dibuka.');
    
    ws.on('message', (message) => {
        // Mengirim balik pesan secara instan (Echo)
        console.log(`Menerima: ${message}`);
        ws.send(`Server merespons: ${message}`);
    });
});
```

```
const socket = new WebSocket('ws://localhost:8080');

socket.onopen = () => {
    socket.send('Halo, ini pesan real-time!');
};

socket.onmessage = (event) => {
    console.log('Data dari server:', event.data);
};
```
