<template>
  <div class="container my-5">
    <div class="row align-items-center mb-4">
      <div class="col text-center">
        <h2 class="mb-0">FORM ISI PRODUK</h2>
      </div>
    </div>

    <table class="table table-bordered border-dark text-center">
      <thead>
        <tr>
          <th >NO</th>
          <th >NAMA</th>
          <th >KELAS</th>
          <th >NAMA BARANG</th>
          <th >HARGA JUAL</th>
          <th>BANYAK BARANG</th>
          <th>TRANSAKSI</th>
          <th >TERJUAL</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(visitor,i) in visitors" :key="i">
          <td>{{ i+1 }}.</td>
          <td>{{ visitor.nama }}</td>
          <td>{{ visitor.kelas.nama }}</td>
          <td>{{ visitor.nama_barang }}</td>
          <td>{{ visitor.harga }}</td>
          <td>{{ visitor.jumlah }}</td>
          <div class="d-flex justify-content-center align-items-center">
              <input type="number" class="form-control form-control-sm mx-2 text-center" value="0" style="width: 70px;" />
              <button class="btn btn-outline-secondary btn-sm" type="button">+</button>
            </div>
          <td>3</td>
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

const getproduk = async () => {
    const { data, error } = await supabase.from('produk').select(`*, kelas(*)`)
    .order('id', { ascending: false })
    if(data) visitors.value = data
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
