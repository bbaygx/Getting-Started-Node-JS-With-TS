# Instal Node JS + TS 

1. Install semua package di `package.json`

   ```
   npm install
    ```

2. Jalanin Servernya

   ```
   npm run start
   ```



# Untuk membuat dan mengatur ulang proyek Node.js dengan kerangka kerja Express menggunakan TypeScript, ikuti langkah-langkah di bawah ini:

Langkah 1: Persiapan Proyek
1. Buat direktori untuk proyek Anda dan buka terminal di dalamnya.
2. Jalankan perintah `npm init -y` untuk menginisialisasi `package.json` dengan pengaturan default.

Langkah 2: Instalasi Dependensi
1. Instalasi Express dan TypeScript serta dependensi terkait dengan menjalankan perintah:

   ```
   npm install express typescript @types/node @types/express nodemon ts-node --save-dev
   ```

Langkah 3: Konfigurasi TypeScript
1. Buat file `tsconfig.json` dengan perintah:

   ```
   npx tsc --init
   ```

2. Buka file `tsconfig.json` dan sesuaikan pengaturan berikut:

   ```json
   {
     "compilerOptions": {
       "target": "ES6", // Atau versi yang lebih tinggi yang Anda inginkan
       "module": "CommonJS",
       "outDir": "./dist", // Direktori keluaran untuk file JavaScript yang telah dikompilasi
       "rootDir": "./src", // Direktori sumber kode TypeScript
       "strict": true,
       "esModuleInterop": true,
       "skipLibCheck": true,
       "forceConsistentCasingInFileNames": true
     }
   }
   ```

Langkah 4: Struktur Proyek
1. Buat direktori `src` di dalam direktori proyek Anda. Ini akan berisi file-file TypeScript.
2. Di dalam direktori `src`, buat file `app.ts`.

Langkah 5: Tulis Kode Express dengan TypeScript
1. Buka file `app.ts` dan tulis kode untuk mengatur server Express. Contoh sederhana:

```typescript
import express from 'express';

const app = express();
const port = 3000;

app.get('/', (req, res) => {
  res.send('Hello, Express with TypeScript!');
});

app.listen(port, () => {
  console.log(`Server is running on port ${port}`);
});
```

Langkah 6: Kompilasi dan Jalankan
1. Kompilasilah kode TypeScript ke JavaScript dengan perintah:

   ```
   npx tsc
   ```

   Ini akan menghasilkan file JavaScript di direktori `dist`.

2. Setelah kompilasi berhasil, jalankan aplikasi dengan perintah:

   ```
   node dist/app.js
   ```

Dengan langkah-langkah ini, Anda telah mengatur proyek Node.js dengan kerangka kerja Express menggunakan TypeScript. Anda dapat melanjutkan dengan menambahkan rute, middleware, dan fitur lainnya sesuai kebutuhan Anda.


# With nodemon tanpa harus menjalankan folder dist

Tentu, Anda dapat menggunakan `nodemon` untuk memantau perubahan pada file dan secara otomatis memulai ulang server Anda setiap kali ada perubahan. Berikut adalah langkah-langkah untuk mengatur proyek Node.js Express dengan TypeScript menggunakan `nodemon`:

Langkah 1: Persiapan Proyek
1. Buat direktori untuk proyek Anda dan buka terminal di dalamnya.
2. Jalankan perintah `npm init -y` untuk menginisialisasi `package.json` dengan pengaturan default.

Langkah 2: Instalasi Dependensi
1. Instalasi Express, TypeScript, `@types/node`, `@types/express`, dan `nodemon` dengan perintah:

   ```
   npm install express typescript @types/node @types/express nodemon --save-dev
   ```

Langkah 3: Konfigurasi TypeScript
1. Buat file `tsconfig.json` dengan perintah:

   ```
   npx tsc --init
   ```

2. Buka file `tsconfig.json` dan sesuaikan pengaturan yang diperlukan.

Langkah 4: Struktur Proyek
1. Buat direktori `src` di dalam direktori proyek Anda. Ini akan berisi file-file TypeScript.
2. Di dalam direktori `src`, buat file `app.ts`.

Langkah 5: Tulis Kode Express dengan TypeScript
1. Buka file `app.ts` dan tulis kode untuk mengatur server Express.

Langkah 6: Menggunakan Nodemon
1. Di dalam file `package.json`, tambahkan skrip untuk menjalankan server menggunakan `nodemon`. Edit bagian `"scripts"` menjadi seperti ini:

   ```json
   "scripts": {
     "start": "nodemon --exec ts-node src/app.ts"
   },
   ```

   Ini akan menjalankan `nodemon` dengan perintah `ts-node` untuk mengawasi file `app.ts` dan secara otomatis memulai ulang server setiap kali ada perubahan.

Langkah 7: Kompilasi dan Jalankan
1. Jalankan server dengan perintah:

   ```
   npm start
   ```

   `nodemon` akan menjalankan server dan memantau perubahan pada file.

Dengan langkah-langkah ini, Anda telah mengatur proyek Node.js Express dengan kerangka kerja TypeScript dan menggunakan `nodemon` untuk memantau perubahan pada file dan memulai ulang server secara otomatis.
