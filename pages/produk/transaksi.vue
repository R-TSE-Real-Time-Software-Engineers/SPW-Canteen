<template>
  <div class="container my-5">
    <div class="row align-items-center mb-4">
      <div class="col text-center">
        <h2 class="mb-0">TRANSAKSI PRODUK</h2>
      </div>
    </div>
    <div class="row justify-content-end ">
      <div class="col-1">
        <button class="btn" @click="saveTransactions" style="background-color: #FFB085">Kirim</button>
      </div>
    </div>
    
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
            :disabled="visitor.transaksi >= visitor.jumlah" 
          >
            +
          </button>


              <button
                class="btn btn-outline-danger btn-sm"
                type="button"
                @click="resetTransaction(visitor)"
              >
                Batalkan
              </button>
            </div>
          </td>
          <td>{{ visitor.total }}</td>
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
const visitors = ref([]);
const userID = ref();
const user = useSupabaseUser()

// Fungsi untuk mendapatkan produk dan jumlah terjual
const getproduk = async () => {
  const { data: produkData, error: produkError } = await supabase
    .from('produk')
    .select(`*, kelas(*)`)
    .order('id', { ascending: false });
  
  if (produkData) {
    visitors.value = produkData.map(item => ({ ...item, transaksi: 0, total: 0, terjual: 0 }));
    // console.log(produkData)
    // visitors.value = produkData
  }

  // Mengambil data transaksi untuk menghitung jumlah terjual
 
}

// Fungsi untuk mengupdate total berdasarkan quantity
const updateTotal = (visitor) => {
  visitor.total = visitor.transaksi * visitor.harga; // Hitung total
}

// Fungsi untuk menambah transaksi
const increment = (visitor) => {
  if (visitor.transaksi <= visitor.jumlah) {
    visitor.transaksi += 1; // Hanya tambah jika kurang dari jumlah
    updateTotal(visitor); // Update total setelah penambahan
  } else {
    alert("Jumlah transaksi tidak boleh lebih dari jumlah barang tersedia."); // Pesan kesalahan
  }
}

async function getUserLogin() {
  const {data,error } = await supabase
    .from("login") 
    .select() 
    .eq("user_id", user.value.id)
    .single()
  if(data){
    userID.value = data.id
  }
  
}

const resetTransaction = (visitor) => {
  visitor.transaksi = 0; // Kembalikan nilai transaksi ke 0
  visitor.terjual = 0; // Kembalikan nilai terjual ke 0
  updateTotal(visitor); // Perbarui total setelah reset
}
// Fungsi untuk menyimpan semua transaksi ke database
const saveTransactions = async () => {
  const transactionsToSave = visitors.value
    .filter(visitor => visitor.transaksi > 0) // Ambil yang memiliki transaksi
    .map(visitor => ({
      terjual: visitor.terjual + visitor.transaksi, // Jumlah terjual baru
      quantity: visitor.transaksi,
      total: visitor.total,
      produk: visitor.id,
      id_user :  userID.value// Sesuaikan dengan nama kolom di tabel transaksi
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
        visitor.transaksi = 0; // Reset transaksi
        // Tidak perlu update terjual di sini, karena sudah diupdate
      });
    }
  } else {
    //const { data, error } = await supabase.from('transaksi').update(transactionsToSave);
    alert("Terjadi"); // Pesan kesalahan
  }
}

onMounted(() => {
  getproduk();
  getUserLogin()
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

</style>
