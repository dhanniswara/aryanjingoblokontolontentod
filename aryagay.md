## **1. Pastikan Docker Desktop Sudah RUNNING**
- Buka Docker Desktop, pastikan status: **"Docker Desktop is running"**.
- Cek versi dengan:
  ```powershell
  docker version
  ```
  Pastikan tidak ada error.

---

## **2. Masuk ke Folder Project**
Biasanya di:
```powershell
cd "C:\Users\USER\Downloads\Fraud-Detector-for-Financial-System-main\finshield-link"
```
Pastikan di folder ini ada file `docker-compose.yml`.

---

## **3. Jalankan Semua Service Docker**
```powershell
docker-compose up --build
```
- Tunggu semua service (Kafka, MongoDB, backend, dsb) running.
- Biarkan terminal ini tetap terbuka selama service berjalan.
- Kalau ada error besar, copy log-nya ke sini.

---

## **4. Cek dan (Jika Perlu) Jalankan Backend Python**
Kalau backend TIDAK otomatis jalan di Docker, jalankan manual:
```powershell
cd ingestion
pip install -r requirements.txt
python main.py
```
(Sesuaikan nama folder/file menurut project kamu.)

---

## **5. Jalankan Frontend (Dashboard)**
Buka terminal baru, lalu:
```powershell
cd "C:\Users\USER\Downloads\Fraud-Detector-for-Financial-System-main\finshield-link\dashboard"
yarn install
yarn start
```
atau
```powershell
npm install
npm start
```
- Tunggu hingga muncul info dashboard running di http://localhost:3000 (atau port lain).

---

## **6. Masukkan Data Dummy (Jika Perlu)**
Karena database-nya fresh, kemungkinan **tidak ada transaksi** yang bisa muncul di dashboard.
- Jika project ada script untuk seed data (misal: `python scripts/seed.py`), jalankan itu.
- Atau, lakukan transaksi dummy lewat API/backend/fitur dashboard agar ada data yang bisa dianalisis.

---

## **7. Cek Dashboard**
- Buka http://localhost:3000 di browser.
- Pastikan data mulai muncul di bagian Risk Scores.
- Kalau masih kosong, pastikan backend, Kafka, dan database benar-benar running dan sudah ada data masuk.

---

### **Jika Ada Error:**
- Copy-paste error atau screenshot-nya ke sini.
- Tulis step ke berapa error muncul, biar saya bantu troubleshooting.

---

**Singkatnya:**  
1. Docker Desktop running  
2. `docker-compose up --build` di folder project  
3. Jalankan backend Python (jika perlu)  
4. Jalankan frontend dashboard  
5. Tambahkan data dummy jika dashboard masih kosong  
6. Cek dashboardnya

---

**Lanjutkan satu per satu!**
