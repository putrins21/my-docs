# Business Requirements Document (BRD)

## 1. Pendahuluan
**Judul Proyek**: Sistem Reimbursement Karyawan  
**Tujuan**: Membuat sistem untuk mempermudah proses pengajuan, approval, dan pencairan reimbursement karyawan.  
**Latar Belakang**: Proses manual reimbursement saat ini memakan waktu lama dan rawan kesalahan.

---

## 2. Ruang Lingkup
- Fitur pengajuan reimbursement oleh karyawan.
- Fitur approval oleh HR dan Finance.
- Notifikasi status pengajuan.
- Integrasi dengan sistem payroll.

**Out of Scope**:
- Integrasi dengan vendor eksternal.
- Fitur pinjaman karyawan.

---

## 3. Stakeholders
- **Karyawan**: mengajukan reimbursement.
- **HR**: melakukan verifikasi data.
- **Finance**: melakukan approval final dan pencairan dana.
- **IT Support**: maintain sistem.

---

## 4. Kebutuhan Fungsional
1. **Pengajuan Reimbursement**
   - Karyawan dapat mengisi form pengajuan.
   - Upload bukti transaksi.
2. **Approval**
   - HR dapat menyetujui atau menolak pengajuan.
   - Finance melakukan approval akhir.
3. **Notifikasi**
   - Karyawan mendapat notifikasi status pengajuan.
4. **Laporan**
   - Admin dapat men-generate laporan bulanan reimbursement.

---

## 5. Kebutuhan Non-Fungsional
- **Keamanan**: hanya user terotorisasi yang bisa login.
- **Performance**: sistem dapat melayani minimal 100 user bersamaan.
- **Usability**: antarmuka mudah digunakan oleh karyawan non-teknis.

---

## 6. Flow Proses
```mermaid
flowchart TD
    A[Karyawan Ajukan] --> B[HR Approval]
    B -->|Disetujui| C[Finance Approval]
    B -->|Ditolak| D[Notifikasi Penolakan]
    C -->|Disetujui| E[Pencairan Dana]
    C -->|Ditolak| D

