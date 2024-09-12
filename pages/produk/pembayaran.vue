<template>
  <div class="container my-5">
    <h2 class="text-center mb-4">DATA PEMBAYARAN PRODUK</h2>
    <table class="table table-bordered border-dark text-center">
      <thead>
        <tr class="tr">
          <th scope="col">NO</th>
          <th scope="col">Penanggung Jawab</th>
          <th scope="col">NAMA BARANG</th>
          <th scope="col">Terjual</th>
          <th scope="col">Jumlah Pendapatan</th>
          <th scope="col">Uang Yang Di Bayarkan</th>       
        </tr>  
      </thead>
      <tbody>
      <tr>
        <th scope="row">1</th>
        <td> cilok</td>
        <td> 8 </td>
        <td> 30000</td>
        <td> 5000 </td>
        <td> syaima</td>
      </tr>
      <tr>
        <th scope="row">2</th>
        <td> cimol</td>
        <td> 7 </td>
        <td> 25000</td>
        <td> 5000 </td>
        <td> elsa</td>
      </tr>
      <tr>
        
        <td colspan="4"> Total</td>
        <td>55000</td>
        <td>10000</td>
        
      </tr>
    </tbody>
    </table>
  </div>
<div class="container my-5">
    <div class="row">
      <div class="col text-start">
        <nuxt-link to="transaksi">
          <button type="button" class="btn btn-lg btn-primary">KEMBALI</button>
        </nuxt-link>
      </div>
      <div class="col text-end">
        <nuxt-link to="/">
          <button type="button" class="btn btn-lg btn-primary">SELESAI....</button>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .text{
    padding: 30px;
  }
  .btn{
  border: none;
  color: white;
  background:  #FFB085;
  margin: 4px 5px;
  padding: 10px 15px;
  font-size: 16px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  cursor: pointer;
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
.btn {
    margin: 0 0.5rem; 
}
 
  </style>