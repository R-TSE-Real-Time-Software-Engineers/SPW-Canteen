<template>
   <div class="container my-5">
    <div class="row align-items-center mb-4">
      <div class="col text-center">
        <h2 class="mb-0">DATA PEMBAYARAN PRODUK
        </h2>
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
        <tr v-for="(visitor, i) in visitors" :key="i">
          <td>{{ i + 1 }}.</td>
          <td>login</td>
          <td>{{ visitor.nama_barang }}</td>
          <td>12</td>
          <td>1</td>
          <td>10000</td>
          <td>9000</td>
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
