Kita dapat mengeksekusi perintah secara langsung ke kontainer setelah Pod siap dan berjalan.
Untuk ini, kita gunakan perintah `exec` dan menggunakan nama Pod sebagai parameter. Mari kita daftar variabel lingkungan:

`kubectl exec $POD_NAME env`{{execute T1}}

Lagi-lagi, layak diingatkan lagi bahwa nama kontainer dapat dihilangkan karena kita hanya punya satu kontainer dalam Pod.

Selanjutkan mari kita mulai sesi bash di kontainer dalam Pod:

`kubectl exec -ti $POD_NAME bash`{{execute T1}}

Kita sekarang telah membukan konsol dalam kontainer di mana kita menjalankan aplikasi NondeJS kita. Kode sumber dari aplikasi berada di berkas server.js:

`cat server.js`{{execute T1}}

Kamu dapat memastikan bahwa aplikasi sudah siap dengan menjalankan perintah curl:

`curl localhost:8080`{{execute T1}}

*Catatan: di sini kita menggunakan localhost karena kita mengeksekusi perintah dalam Pod NodeJS. Jika kamu tidak bisa menyambung ke localhost:8000, cek untuk memastikan kamu sudah menjalankan perintah kubectl exec dan meluncurkan perintah dari dalam Pod*

Untuk mengakhiri koneksi kontainermu ketik `exit`{{execute T1}}.
