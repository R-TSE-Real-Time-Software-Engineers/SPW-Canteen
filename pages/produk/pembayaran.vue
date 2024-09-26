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
        <tr>
          <th scope="row">1</th>
          <td>syaima</td>
          <td>cilok</td>
          <td>2</td>
          <td>1</td>
          <td>5000</td>
          <td>4500</td>
        </tr>
        <tr>
          <th scope="row">2</th>
          <td>elsa</td>
          <td>cimol</td>
          <td>3</td>
          <td>2</td>
          <td>5000</td>
          <td>40000</td>
        </tr>
        <tr>
          <td colspan="5">Total</td>
          <td>55000</td>
          <td>10000</td>
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
