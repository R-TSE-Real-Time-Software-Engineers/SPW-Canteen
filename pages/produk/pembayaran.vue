<template>
  <div class="container my-5">
    <div class="row align-items-center mb-4">
      <div class="col text-center">
        <h2 class="mb-0">DATA PEMBAYARAN PRODUK</h2>
      </div>
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
          <td>{{ penanggungJawab }}</td>
          <td>{{ transaction.nama_barang }}</td>
          <td>{{ transaction.terjual }}</td>
          <td>{{ transaction.sisa }}</td>
          <td>{{ transaction.jumlah_pendapatan }}</td>
          <td>{{ transaction.uang_dibayarkan }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>
definePageMeta({
  middleware: 'auth',
  layout: 'produk',
})

const supabase = useSupabaseClient()
const transactions = ref([]);

const penanggungJawab = "Nama Penanggung Jawab"; // Ganti dengan nama yang sesuai dari data login

const getTransactions = async () => {
  const { data, error } = await supabase.from('transaksi').select('*, produk(*)');
  
  if (error) {
    console.error('Error fetching transactions:', error);
    return;
  }

  if (data) {
    transactions.value = data.map(item => {
      const jumlahPendapatan = item.quantity * item.produk.harga; // Hitung jumlah pendapatan
      return {
        nama_barang: item.produk.nama_barang,
        terjual: item.quantity,
        sisa: item.produk.jumlah - item.quantity, // Hitung sisa
        jumlah_pendapatan: jumlahPendapatan, // Simpan jumlah pendapatan
        uang_dibayarkan: jumlahPendapatan * 0.9, // Hitung uang yang dibayarkan (90% dari jumlah pendapatan)
      };
    });
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
  background: #FFB085;
  margin: 0 0.5rem; 
  padding: 10px 15px;
  font-size: 16px;
  text-align: center;
  display: inline-block;
  cursor: pointer;
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
