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
          <td>Elsa</td>
          <td>XII PPLG 1</td>
          <td>Cimol</td>
          <td>1000</td>
          <td>3</td>
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
          <td>Syaima</td>
          <td>XII PPLG 1</td>
          <td>Cilok</td>
          <td>1000</td>
          <td>2</td>
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
