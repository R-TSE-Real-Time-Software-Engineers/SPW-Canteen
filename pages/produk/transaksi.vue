<template>
  <div class="container my-5">
    <h2 class="text-center mb-4">DATA TRANSAKSI PRODUK</h2>
    <table class="table table-bordered border-dark text-center">
      <thead>
        <tr>
          <th scope="col">NO</th>
          <th scope="col">NAMA</th>
          <th scope="col">KELAS</th>
          <th scope="col">NAMA BARANG</th>
          <th scope="col">HARGA JUAL</th>
          <th scope="col">BANYAK BARANG</th>
          <th scope="col">TRANSAKSI</th>
          <th scope="col">TERJUAL</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th scope="row">1</th>
          <td>elsa</td>
          <td>XII PPLG 1</td>
          <td>Cimol</td>
          <td>10</td>
          <td>3000</td>
          <td>
            <div class="d-flex justify-content-center align-items-center">
              <input type="number" class="form-control form-control-sm mx-2 text-center" value="0" style="width: 70px;" />
              <button class="btn btn-outline-secondary btn-sm" type="button">+</button>
            </div>
          </td>
          <td>3</td>
        </tr>
        <tr>
          <th scope="row">2</th>
          <td>syaima</td>
          <td>10 pplg1</td>
          <td>cilok</td>
          <td>11</td>
          <td>2000</td>
          <td>
            <div class="d-flex justify-content-center align-items-center">
              <input type="number" class="form-control form-control-sm mx-2 text-center" value="0" style="width: 70px;" />
              <button class="btn btn-outline-secondary btn-sm" type="button">+</button>
            </div>
          </td>
          <td>3</td>
        </tr>
      </tbody>
    </table>
  </div>

  <div class="container my-5">
    <div class="row">
      <div class="col text-start">
        <nuxt-link to="form">
          <button type="button" class="btn btn-lg btn-primary">KEMBALI</button>
        </nuxt-link>
      </div>
      <div class="col text-end">
        <nuxt-link to="pembayaran">
          <button type="button" class="btn btn-lg btn-primary">NEXT..</button>
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