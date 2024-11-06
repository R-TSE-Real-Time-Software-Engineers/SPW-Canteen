<template>
  <div class="container my-5">
    <div class="row align-items-center mb-4">
      <div class="col text-center">
        <h2 class="mb-0">DATA PEMBAYARAN PRODUK</h2>
      </div>
    </div>
    <div class="row justify-content-end ">
      <div class="col-2">
            <button @click="downloadExcel" class="btn ">
              Download Data
            </button>
  </div>

    
    <table class="table table-bordered border-dark text-center">
      <thead>
        <tr>
          <th scope="col">NO</th>
          <th scope="col">Penanggung Jawab</th>
          <th scope="col">NAMA BARANG</th>
          <th scope="col">Terjual</th>
          <th scope="col">Sisa</th>
          <th scope="col">Jumlah Pendapatan</th>
          <th scope="col">Uang Yang Di Bayarkan</th>       
        </tr>  
      </thead>
      <tbody>
        <tr v-for="(transaction, i) in transactions" :key="i">
          <td>{{ i + 1 }}</td>
          <td>{{ transaction.nama }}</td>
          <td>{{ transaction.nama_barang }}</td>
          <td>{{ transaction.terjual }}</td>
          <td>{{ transaction.sisa }}</td>
          <td>{{ transaction.pendapatan }}</td>
          <td>{{ transaction.uang_dibayarkan }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>
</template>

<script setup>
import * as XLSX from 'xlsx';
import {saveAs} from 'file-saver';

// mendownload data Excel
const downloadExcel = () => {

// Buat worksheet dari data yang ada di visitors
const worksheet = XLSX.utils.json_to_sheet(transactions.value);

// Buat workbook dan tambahkan worksheet ke dalamnya
const workbook = XLSX.utils.book_new();
XLSX.utils.book_append_sheet(workbook, worksheet, 'data');

// Hasilkan file Excel dalam format array buffer
const excelBuffer = XLSX.write(workbook, { bookType: 'xlsx', type: 'array' });

// Buat Blob dan download file 
const blob = new Blob([excelBuffer], { type: 'application/octet-stream' });
saveAs(blob, 'data-pembayaran_produk.xlsx');
};




definePageMeta({
  middleware: 'auth',
  layout: 'produk',
})

const supabase = useSupabaseClient()
const transactions = ref([]);

const getTransactions = async () => {
  // const { data, error } = await supabase.from('transaksi').select('*, produk(*)');
  const { data, error } = await supabase.from('d_pembayaran').select('*');
  if (data) transactions.value=data
  if (error) {
    console.error('Error fetching transactions:', error);
    return;
  }

  if (data) {
    transactions.value = data
  }
};

// Panggil fungsi untuk mengambil data saat komponen dimuat
onMounted(() => {
  getTransactions();
});
</script>

<style scoped>
.btn {
  border: none;
  color: white;
  background: #39ff27;
  margin: 0 0.5rem; 
  padding: 10px 15px;
  font-size: 16px;
  text-align: center;
  display: inline-block;
  cursor: pointer;
  margin-bottom: 1rem;
}
.table thead th {
  background-color: #f8f9fa;
}
.table tbody tr:nth-child(even) {
  background-color: #f2f2f2; 
}
.icon-button {
  background: none;
  border: none;
  cursor: pointer;
}
.bi {
  width: 40px;
  height: 40px;
  fill: #FFB085; 
}
</style>
