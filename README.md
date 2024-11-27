Nama  : Syifa Rahmadina

NIM   : H1D021094

**TUGAS PRAKTIKUM PEMROGRAMAN MOBILE PERTEMUAN 11**

**Masukkan SS CRUD ke dalam Readme.md lalu jelaskan SS CRUD dibawah setiap gambar**

**A. Create (Add a New Todo)**

Icon Add New Todo:

![Screenshot (4258)](https://github.com/user-attachments/assets/3b3dfdfd-e94b-46d1-b6a1-14feace31c52)

Form Add Todo:

![Screenshot (4259)](https://github.com/user-attachments/assets/0d3bbdef-aa75-4489-9a31-9737dd75c0a3)


Proses Frontend:

1. Untuk membuat todo baaru maka klik icon tambah di pojok kanan halaman home page

2. Lalu akan ditampilkan form Add Todo yang berisikan Title and Description

3. User mengisikan title dan description

   ![Screenshot (4260)](https://github.com/user-attachments/assets/0100cf35-77ae-464b-b051-471fec80b213)

4. User klik "Add Todo", disini the hadleSubmit function akan dijalankan untuk memvalidasi input dan menambahkan Todo baru.

   Code yang digunakan:

   ![image](https://github.com/user-attachments/assets/31353191-6569-47e9-8430-d6c1ed8fe437)


Proses Backend:

Ketika todo baru telah dibuat, fungsi firestoreService.addTodo() akan dipanggil untuk menambahkan Todo ke Firestore

Codenya:

![image](https://github.com/user-attachments/assets/1318ddd8-2517-48e2-ab5d-c5d24229ee58)

Firestore collection akan mnenyimpan todos di dalam setiap dokumen yang didalamnya ada title, descrption, status, dan timestamp.

Lalu fungsi addTodo() akan menambahkan dokumen ke dalam "todos" di firestore. Jika berhasil, timestamp createAt juga ditambahkan.



**B. Read (Display Todos**

![Screenshot (4263)](https://github.com/user-attachments/assets/a5426197-a26f-4cb4-b2c5-6682a0e71007)


Proses Frontend:

1. Operasi read akan mengambil semua Todo dari Firestore dan menampilkannya di aplikasi. Todo dibagi menjadi 2 yaitu:

   - Active Todos: Todo yang belum selesai atau masih dijalankan (status false)
  
   - Completed Todos: Todo yang telah ditandai sebagai completed (status true)

Kode untuk front end:

![image](https://github.com/user-attachments/assets/ab8a26ec-d789-4b93-8152-8c76539dee2b)


Proses Backend:

Function firestoreService.getTodos() akan bertanggung jawab untuk mengambil Todos dari Firestore

Kode untuk back end:

![image](https://github.com/user-attachments/assets/816b0d36-11a1-4b8c-8f6c-187006bc794c)

- Query Firestore: Fungsi getTodos() mengambil semua Todos dari Todos collection

- Display: Todos akan dipisahkan active dan completed berdasarkan status field



**C. Update (Edit a Todo)**

Icon Edit:

![Screenshot (4268)](https://github.com/user-attachments/assets/3e108137-a1ae-4a63-bc0c-f8553c956ecb)

Page Edit, Sebelum di Edit:

![Screenshot (4269)](https://github.com/user-attachments/assets/2301f052-bed4-4f50-9157-0cd5f2c5cc0b)

Page Edit, Sesudah di Edit:

![Screenshot (4270)](https://github.com/user-attachments/assets/8a40853b-4c82-43d4-82f0-cbd405ef60b6)

Page Display, Hasil Edit:

![Screenshot (4271)](https://github.com/user-attachments/assets/1885f79a-95ee-4cdb-9656-a88c2ea9ca47)


1. Proses Frontend

   Ketika user melakukan swipe ke kiri maka akan ditampilkan icon untuk edit, lalu kita klik icon tersebut dan kita bisa memodifikasi title dan description dari todo yang telah ada. Setelah selesai user akan klik button "Edit Todo", dan fungsi handleSubmit akan mengupdates Todo ke Firestore.

   Kode untuk Frontend:

   ![image](https://github.com/user-attachments/assets/9f10a765-6dd8-42eb-afff-2539640358ea)


2. Proses Backend

   Fungsi firestoreService.updateTodo() akan mengupdate Todo document di Firestore.

   Kode untuk Backend:

   ![image](https://github.com/user-attachments/assets/bda9a859-5d91-4352-8f14-4ce69dfd48f7)

   Fungsi updateTodo() aka mengupdate Todo document dengan identifikasi dengan id dengan data baru dari title, description, maka akan terupdate timestamp.



**D. Delete (Remove a Todo)**

Tampilan Sebelum Delete:

![Screenshot (4264)](https://github.com/user-attachments/assets/d3971d8e-0d5c-46ee-a44c-68f6a4a6a0e1)

Icon Delete:

![Screenshot (4265)](https://github.com/user-attachments/assets/df0e07c8-da59-4702-a28d-d94e57e79bc0)

Pop-up Berhasil Delete:

![Screenshot (4266)](https://github.com/user-attachments/assets/29a8bca6-9655-4667-90f5-3492f59e65ae)

Tampilan Hasil Setelah Delete:

![Screenshot (4267)](https://github.com/user-attachments/assets/daaf170d-c6d9-4f04-ae1a-cf2691cccd52)


1. Proses Frontend

   Operasi delete terpanggil ketika user melakukan swipes ke kanan dari Todo item dan akan ditampilkan icon delete. Lalu user akan klik icon delete ini lalu todo akan dihampus.

   Disini fungsi handleDelete akan memanggil firestore untuk menghapus todo.

   Kode Frontend yang digunakan:

   ![image](https://github.com/user-attachments/assets/59a61258-475f-4673-9099-3b6888bb3f4c)


2. Proses Backend

   Fungsi firestoreService.deleteTodo() akan menghapus Todo dokumet dari firestore.

   Kode Backend yang digunakan:

   ![image](https://github.com/user-attachments/assets/9cb59d00-34af-49a4-bc5d-19a09707c173)



**E. Update Status (Mark Todo as Completed or Active**

Tampilan Sebelum Todo di Update Status:

![Screenshot (4272)](https://github.com/user-attachments/assets/708cb86e-c1f0-44a1-8716-3ca94a021e17)

Tampilan Icon Update Status:

![Screenshot (4273)](https://github.com/user-attachments/assets/a8f4d0b4-9fb8-4141-a335-182c3a31a8f7)

Pop-up Berhasil Di Update Status:

![Screenshot (4274)](https://github.com/user-attachments/assets/9aaad8c0-2887-44aa-85d7-cce6d8704fe0)

Tampilan Sesudah Todo di Update Status:

![Screenshot (4275)](https://github.com/user-attachments/assets/860e0444-fcbf-4a8a-b9d0-a96274bc4c6e)


1. Proses Frontend

   Operasi update status mengijinkan user untuk mark a Todo as completed or active dengan melakukan swipe ke kiri lalu akan di tampilkan icon update status lalu user akan klik icon ini untuk mengupdate status.

   Lalu fungsi handleStatus akan mengubah fields status Todo di Firestore.

   Kode Frontend yang digunakan:

  ![image](https://github.com/user-attachments/assets/4839646e-933f-4b80-ab14-53e107204140)


2. Proses Backend

   Fungsi firestoreService.updateStatus() akan memperbarui field status dari Todo dokumen todo yang diidentifikasi dengan ID.

   Kode Backend yang digunakan:

   ![image](https://github.com/user-attachments/assets/97e86e92-0a87-433c-9ce3-62c5ba6d248a)
