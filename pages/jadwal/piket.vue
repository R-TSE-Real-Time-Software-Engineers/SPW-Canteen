<template>
   <h2 class="text row justify-content-center pt-5">JADWAL PIKET</h2>
  <div class="container-fluid font">
  <div class="row my-5 justify-content-center">
    <div class="col-lg-4 col-md-6 mb-4 d-flex justify-content-center">
      <div class="card rounded-5 w-100">
        <div class="card-body d-flex justify-content-center align-items-center">
        <nuxt-link to="gurua" class="text-decoration-none text-white">
          <h2>GURU BLOK A</h2>
        </nuxt-link>
        </div>
      </div>
    </div>
    <div class="col-lg-4 col-md-6 mb-4 d-flex justify-content-center">
  <div class="card rounded-5 w-100">
    <div class="card-body d-flex justify-content-center align-items-center">
      <nuxt-link to="gurub" class="text-decoration-none text-white">
        <h2 class="mb-0">GURU BLOK B</h2>
      </nuxt-link>
    </div>
  </div>
</div>
  </div>
</div>
<div class="container-fluid font">
  <div class="row my-5 justify-content-center">
    <div class="col-lg-4 col-md-6 mb-4 d-flex justify-content-center">
      <div class="card rounded-5 w-100">
        <div class="card-body d-flex justify-content-center align-items-center">
        <nuxt-link to="siswa" class="text-decoration-none text-white">
          <h2 class="mb-0">SISWA</h2> 
        </nuxt-link>
        </div>
      </div>
    </div>
  </div>
</div>

 <nuxt-link to="/">
    <button type="submit" class="btn ms-3 btn-lg ">KEMBALI</button>
  </nuxt-link>
</template>

<style scoped>
h2 {
  font-size: 1.5rem; 
}
.card {
    height: 250px;
    width: 500px;
    box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    border: 1px solid #dee2e6;
    background-color:#FF9999;
}
.card-body>h2 {
    color: #ffffff;
    position: static;
    bottom: 5px;
    right: 15px;
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
.text{
  padding: 30px;
}
</style>