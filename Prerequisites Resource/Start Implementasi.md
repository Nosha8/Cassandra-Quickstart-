<h1> Implementasi Cassandra Quickstart </h1>
Start PowerShell or Command Prompt 
<br><br>
<p1><strong> STEP 1: CASSANDRA pada DOCKER DESKTOP</strong></p1>
<br>Docker Desktop harus sudah terinsall pada PC

`docker pull cassandra:latest`

<p2> <strong>STEP 2: CREATE NETWORK</strong></p2>

`docker network create cassandra`

<p3><strong> STEP 3: RUN CASSANDRA</strong></p3>

`docker run --rm -d --name cassandra --hostname cassandra --network cassandra cassandra`

<p3><strong> STEP 4: CREATE cql FILE</strong></p3>
<br>Cassandra Query Language (CQL) mirip dengan SQL tetapi cocok untuk JOINless structure.

Buat file dengan nama data.cql and copy paste CQL script dibawah ini ke file tersebut. script ini akan membuat keyspace, layer dimana Cassandra mereplikasi data, tabel untuk menyimpan data, dan insert data ke table:

-- Create a keyspace
<br>`CREATE KEYSPACE IF NOT EXISTS store WITH REPLICATION = { 'class' : 'SimpleStrategy', 'replication_factor' : '1' };`

-- Create a table
<br>`CREATE TABLE IF NOT EXISTS store.shopping_cart (
userid text PRIMARY KEY,
item_count int,
last_update_timestamp timestamp
);`

-- Insert some data
<br>`INSERT INTO store.shopping_cart
(userid, item_count, last_update_timestamp)
VALUES ('9876', 2, toTimeStamp(now()));
INSERT INTO store.shopping_cart
(userid, item_count, last_update_timestamp)
VALUES ('1234', 5, toTimeStamp(now()));`

<p4><strong> STEP 5: RUN KONTEN data.cql</strong></p4>
<br>The CQL shell, atau cqlsh, adalah salah satu tool untuk interaksi dengan database. Kita dapat menggunakan ini untuk load beberapa data ke database menggunakan script pada data.cql.

`docker run --rm -it --network cassandra  -v "$(pwd)/data.cql:/scripts/data.cql" nuvo/docker-cqlsh cqlsh cassandra 9042 --cqlversion='3.4.6' -f /scripts/data.cql`

<br>Note: Cassandra server itu sendiri (the first docker run command you ran) membutuhkan beberapa detik untuk start up. The command diatas akan memberikan status error jika server belum selesai proses init, sehingga harus menunggu sebentar.

<p5><strong> STEP 6: JALANKAN INTERAKTIF CQL/Shell</strong></p4>
<br>Seperti pada SQL shell, dapat menggunakan CQLSH untuk run CQL commands secara interaktif.

`docker run --rm -it --network cassandra  -v "$(pwd)/data.cql:/scripts/data.cql" nuvo/docker-cqlsh cqlsh cassandra 9042 --cqlversion='3.4.6'`

<br>maka pada powershell akan muncul sebagai berikut:
<br>Connected to Test Cluster at cassandra:9042.
<br>[cqlsh 5.0.1 | Cassandra 4.0.4 | CQL spec 3.4.5 | Native protocol v5]
<br>Use HELP for help.
<br>cqlsh>'
_____________________________________________________________________________________________
<p5><strong> STEP 7: TESTING CASSANDRA</strong></p4>
1. READ DATA

`SELECT * FROM store.shopping_cart;`

2. INSERT DATA

`INSERT INTO store.shopping_cart (userid, item_count) VALUES ('4567', 20);`

3. READ KEMBALI DATA

`SELECT * FROM store.shopping_cart;`

4. CLEAN UP

`docker kill cassandra`

`docker network rm cassandra`

<strong>CONGRATULATION!</strong>

Untuk mempelajari lebih lanjut silahkan ke next step berikut:

<li>Pelajari Cassandra Basics untuk memahami konsep dan high level : https://cassandra.apache.org/_/cassandra-basics.html</li>
<li>Untuk mengetahui detail tentang cassandra dapat mengakses berikut Docs:https://cassandra.apache.org/doc/latest/</li>
<li>Check case studi untuk mempelajari bagaimana value cassandra secara global : https://cassandra.apache.org/_/case-studies.html</li>
