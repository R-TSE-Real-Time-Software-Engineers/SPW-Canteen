<template>
  <div class="container my-5">
    <div class="row align-items-center mb-4">
      <div class="col text-center">
        <h2 class="mb-0">TRANSAKSI PRODUK</h2>
      </div>
    </div>
    <button class="btn btn-primary " @click="saveTransactions">Kirim</button>
    <table class="table table-bordered border-dark text-center">
      <thead>
        <tr>
          <th>NO</th>
          <th>NAMA</th>
          <th>KELAS</th>
          <th>NAMA BARANG</th>
          <th>HARGA JUAL</th>
          <th>BANYAK BARANG</th>
          <th>TRANSAKSI</th>
          <th>TOTAL</th>
          <th>TERJUAL</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(visitor, i) in visitors" :key="i">
          <td>{{ i + 1 }}.</td>
          <td>{{ visitor.nama }}</td>
          <td>{{ visitor.kelas.nama }}</td>
          <td>{{ visitor.nama_barang }}</td>
          <td>{{ visitor.harga }}</td>
          <td>{{ visitor.jumlah }}</td>
          <td>
            <div class="d-flex justify-content-center align-items-center">
              <input
                type="number"
                v-model.number="visitor.transaksi"
                class="form-control form-control-sm mx-2 text-center"
                style="width: 70px;"
                min="0"
                @change="updateTotal(visitor); updateTerjual(visitor)"
              />
              <button
                class="btn btn-outline-secondary btn-sm"
                type="button"
                @click="increment(visitor)"
              >
                +
              </button>
            </div>
          </td>
          <td>{{ visitor.total }}</td>
          <td>{{ visitor.terjual }}</td>
        </tr>
      </tbody>
    </table>

    <button class="btn btn-primary " @click="saveTransactions">Kirim</button>
  </div>
</template>

<script setup>
definePageMeta({
  middleware: 'auth',
  layout: 'produk',
})

const supabase = useSupabaseClient()
const visitors = ref([]);

// Fungsi untuk mendapatkan produk dan jumlah terjual
const getproduk = async () => {
  const { data: produkData, error: produkError } = await supabase.from('produk').select(`*, kelas(*)`).order('id', { ascending: false });
  
  if (produkData) {
    visitors.value = produkData.map(item => ({ ...item, transaksi: 0, total: 0, terjual: 0 }));
  }

  // Mengambil data transaksi untuk menghitung jumlah terjual
  const { data: transaksiData, error: transaksiError } = await supabase
    .from('transaksi')
    .select('produk, sum(quantity) as total_terjual')
    .group('produk');

  if (transaksiData) {
    // Update jumlah terjual di visitors
    transaksiData.forEach(transaksi => {
      const product = visitors.value.find(v => v.id === transaksi.produk);
      if (product) {
        product.terjual = transaksi.total_terjual; // Memperbarui jumlah terjual
      }
    });
  }
}

// Fungsi untuk mengupdate total berdasarkan quantity
const updateTotal = (visitor) => {
  visitor.total = visitor.transaksi * visitor.harga; // Hitung total
}

const updateTerjual = (visitor) => {
  // Hitung jumlah terjual berdasarkan transaksi yang telah dilakukan
  visitor.terjual = visitor.terjual + visitor.transaksi; // Update terjual berdasarkan transaksi saat ini
}

// Fungsi untuk menambah transaksi
const increment = (visitor) => {
  visitor.transaksi += 1; // Menambah transaksi dengan 1
  updateTotal(visitor); // Update total setelah penambahan
  updateTerjual(visitor); // Update terjual setelah penambahan
}

// Fungsi untuk menyimpan semua transaksi ke database
const saveTransactions = async () => {
  const transactionsToSave = visitors.value
    .filter(visitor => visitor.transaksi > 0) // Ambil yang memiliki transaksi
    .map(visitor => ({
      terjual : visitor.transaksi + visitor.terjual, // Jumlah terjual baru
      quantity: visitor.transaksi,
      total: visitor.total,
      produk: visitor.id, // Sesuaikan dengan nama kolom di tabel transaksi
    }));

  if (transactionsToSave.length > 0) {
    const { data, error } = await supabase.from('transaksi').insert(transactionsToSave);
    
    if (error) {
      console.error('Error saving transactions:', error);
      alert("Terjadi kesalahan saat menyimpan transaksi."); // Pesan kesalahan
    } else {
      console.log('Transactions saved:', data);
      alert("Transaksi berhasil disimpan!"); // Pesan sukses
      // Reset transaksi setelah disimpan
      visitors.value.forEach(visitor => {
        visitor.transaksi = 0;
        updateTerjual(visitor); // Reset terjual berdasarkan transaksi baru
      });
    }
  } else {
    alert("Tidak ada transaksi untuk disimpan.");
  }
}

onMounted(() => {
  getproduk();
});
</script>

<style scoped>
.btn {
  border: none;
  color: white;
  background: #FFB085; 
  margin: 4px 5px;
  padding: 10px 15px;
  font-size: 16px;
  text-align: center;
  display: inline-block;
  cursor: pointer;
}

.icon-button {
  background:none;
  border: none;
  cursor: pointer;
  padding: 10px; 
  border-radius: 0.375rem;
}

.table thead th {
  background-color: #f8f9fa;
}

.table tbody tr:nth-child(even) {
  background-color: #f2f2f2; 
}

.form-control {
  border-radius: 0.375rem;
}

.text-center {
  text-align: center;
}
.bi {
  width: 40px;
  height: 40px;
  fill: #FFB085; 
}
</style>
