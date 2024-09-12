<template>
<div class="container my-5">
  <div class="row align-items-center">
    <div class="col ">
      <h2 class="mb-0">FORM ISI PRODUK</h2>
    </div>
    <div class="col text-end">
        <nuxt-link to="transaksi" class="text-decoration-none text-white">
        <button type="submit" class="btn btn-lg">DATA</button>
        </nuxt-link>
    </div>
  </div>
</div>

  <div class="container my-5">
    <div class="row justify-content-center">
      <div class="col-lg-6 col-md-8">
        <form>
          <div class="mb-3">
            <input type="text" class="form-control form-control-lg radius" placeholder="Nama:" />
          </div>
          <div class="mb-3">
            <select class="form-select form-select-lg radius"  aria-label="Kelas">
              <option value="" disabled selected>Kelas</option>
              <option value="1">PPLG 1</option>
              <option value="2">PPLG 2</option>
              <option value="3">PPLG 3</option>
              <option value="4">PPLG 4</option>
            </select>
          </div>
          <div class="mb-3">
            <input type="text" class="form-control form-control-lg radius" placeholder="Nama Barang:" />
          </div>
          <div class="mb-3">
            <input type="number" class="form-control form-control-lg radius" placeholder="Banyak:" />
          </div>
          <div class="mb-3">
            <input type="text" class="form-control form-control-lg radius" placeholder="Harga Jual:" />
          </div>
        </form>
      </div>
    </div>
  </div>

<div class="container my-5">
  <div class="row">
    <div class="col d-flex justify-content-start">
      <nuxt-link to="/login/login">
        <button type="button" class="btn btn-lg">KEMBALI</button>
      </nuxt-link>
    </div>
    <div class="col d-flex justify-content-end">
      <nuxt-link to="form">
        <button type="button" class="btn btn-lg">KIRIM</button>
      </nuxt-link>
    </div>
  </div>
</div>
</template>

<style scoped>
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

.radius {
  border-radius: 0.375rem;
}

.mb-3 {
  margin-bottom: 1.5rem; 
}

</style>