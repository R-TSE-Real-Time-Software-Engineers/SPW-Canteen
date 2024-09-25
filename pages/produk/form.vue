


<template>
  <div class="container my-5">
   
      <div class="col text-center">
        <h2 class="mb-0">FORM ISI PRODUK</h2>
      </div>
    </div>


  <div class="container my-5">
    <div class="row justify-content-center">
      <div class="col-lg-6 col-md-8">
        <form>
          <div class="text-center mb-3">
            <input type="text" class="form-control form-control-lg radius" placeholder="Nama:" />
          </div>
          <div class="text-center mb-3">
            <select class="form-select form-select-lg radius" aria-label="Kelas">
              <option value="" disabled selected>Kelas</option>
              <option value="1">PPLG 1</option>
              <option value="2">PPLG 2</option>
              <option value="3">PPLG 3</option>
              <option value="4">PPLG 4</option>
            </select>
          </div>
          <div class="text-center mb-3">
            <input type="text" class="form-control form-control-lg radius" placeholder="Nama Barang:" />
          </div>
          <div class="text-center mb-3">
            <input type="number" class="form-control form-control-lg radius" placeholder="Banyak:" />
          </div>
          <div class="text-center mb-3">
            <input type="text" class="form-control form-control-lg radius" placeholder="Harga Jual:" />
          </div>
        </form>
        
        <div class="d-flex justify-content-end mt-4">
          <nuxt-link to="form">
            <button type="button" class="btn btn-lg">KIRIM</button>
          </nuxt-link>
        </div>
      </div>
    </div>
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
  text-decoration: none;
  display: inline-block;
  cursor: pointer;
}

.icon-button {
  background: none;
  border: none;
  cursor: pointer;
}

.radius {
  border-radius: 0.375rem;
}

.mb-3 {
  margin-bottom: 1.5rem; 
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
