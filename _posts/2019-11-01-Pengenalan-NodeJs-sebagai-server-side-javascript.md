---
title: NodeJs, Framework Javascript yang  Bisa Berjalan di server
layout: post
author: Mahmud
categories: nosejs
tag: nodejs
tutorial: true
imageUrl: https://upload.wikimedia.org/wikipedia/commons/thumb/d/d9/Node.js_logo.svg/590px-Node.js_logo.svg.png
permalink: /tutorial/nodejs/:title
---

## Apa itu NodeJs?
Node js merupakan suatu pemrograman javascript yang dapat berjalan di server yang mana framework ini di buat dengan mesin javascript Chrome's V8 yang terkenal akan kecepatan dalam pemrosesan.  

Javascript yang dulunya hanya bisa berjalan  di  client (browser), namun sekarang berevolusi  menjadi bahasa yang  dapat berjalan di lingkungan server. Sama halnya dengan bahasa server lainya seperti php, ruby, java node js dapat bekerja dalam menggenerate web page secara dinamis tentunya dengan performa yang lebih baik. 
![cara kerja nodejs](https://sdz-upload.s3.amazonaws.com/prod/upload/p1ch1_With%20Node.js%2C%20we%20can%20also%20use%20JavaScript%20on%20the%20server%21%20-%20New%20Page1.png)

Node js merupakan salah satu framework pilihan apabila ingin membuat aplikasi *secara real time comunication*.  Aplikasi itu bisa berupa aplikasi striming atau chat, hal tersebut karena node js bekerja secara asycronomous programing sehingga aplikasi yang dibuat dengan nodeJs dapat bekerja secara lebih cepat. 

Berbeda dengan bahasa php yang bekerja secara syncronomous dimana kode di eksekusi dari atas ke bawah secara berurutan, nodeJs dalam mengeksekusi suatu kode dilakukan dengan memilih proses lebih ringan terlebih dahulu kemudian proses yang lebih lama.

Misal nya dalam proses mengupload file biasanya bahasa php akan melakukan proses secara berurutan seperti
1.  Proses upload file (program akan melakukan proses upload file)
2.  Tampilkan file (tampilkan file yang sudah di upload apabila sudah selesai)
3.  lakukan proses lainnya (tampilkan proses lainnya apabila sudah selesai)


Sedangkan nodeJs dapat melakukan proses upload file dengan cara berikut
1. proses upload file (program akan melakukan proses upload file)
2. ketika sudah selesai maka tampilkan file (program akan melakukan proses lain sambil menunggu proses upload file selesai. ini bisa dilakukan karena NodeJs merupakan bahasa yang menggunakan event.  Program akan memanggil even ketika file selesai di upload dan kemudian ditampilkan)
3. lakukan proses lainnya. (lakukan proses lainnya)

Untuk lebih jelasnya proses eksekusi program pada nodeJs bisa dilihat pada gambar berikut
![](https://sdz-upload.s3.amazonaws.com/prod/upload/p2ch1_The%20non-blocking%20model%20in%20programming%20-%20New%20Page.png)



Untuk melihat proses kerja nodejs secara nyata bisa melalui kode berikut dalam mengupload file ke sistem.

```js
let link = "http://www.site.com/file.zip";
request.post(link, function(error,  response , body)  {
	if(!error) {
		console.log("upload file selesai...");
	}
});
console.log("lakukan proses lain ketika proses upload file dilakukan…");
```

Apa yang terlihat diatas ialah code yang berfungsi untuk proses upload file. fungsi diatas berfungsi sebagai callback program akan memanggil yang kemudian diproses nya. 
anda sebenarnya bisa menulis kode di atas dengan code seperti berikut. 

```js
let link = "http://www.site.com/file.zip";

function callback(err, res, body) {
	if(!error) {
		console.log("upload file selesai...");
	}
}

request.post(link, callback);
console.log("lakukan proses lain ketika proses upload file dilakukan…");
```


Nodejs dalam memproses code diatas akan melakukan proses upload file terlebih dahulu
kemudian sembari proses mengupload file selesai program akan melakukan proses lainnya tanpa menunggu proses upload selesai terlebih dahulu.

Dalam segi performa, Nodejs yang dalam framework express  ini memiliki kecepatan rata  request sebanyak 7000  requests per detik. seperti yang dikatakan oleh mamaz(2017) dalam blognya <a href="https://mamaz.github.io/benchmarking-nodejs-http-performance.html" target="blank">disini</a> bahwasanya node js dengan menggunakan framework express.js yang di test dengan melakukan request sebanyak 5 juta, node js ini mampu mengandel nya dengan waktu selama 11 menit.

Setelah mengetahui performa dari nodejs keeuntungan lainnya ketika mempelajari atau mengggunakan framework ini ialah
1. 	Menggunakan bahasa javascript. 
		Dengan menggunakan bahasa javascript anda hanya belajar satu bahasa pemrograman dan anda bisa dengan mudah untuk mempelajari hal-hal lainnya seprti teknologi front end (react, react-native, vue, nuxt, gatsby ataupun angular) *learn one write everiwhere*
		
2.	Kaya akan library yang berlimpah. 
		adanya situs npmjs.com membuat anda lebih mudah dalam mengembangkan aplikasi yang anda buat, anda tidak harus membuat semuanya dari awal, banyak orang yang telah membuat fungsi/modul modul kusus untuk berbagai permasalahan dalam pengembangan aplikasi, contohnya socket.io dan dll. 


Sekian dan terimakasih