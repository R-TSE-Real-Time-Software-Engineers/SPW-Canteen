<template>
<div class="container my-5">
  <div id="carouselExampleIndicators" class="carousel slide" data-bs-ride="carousel">
    <div class="carousel-indicators">
      <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
      <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="1" aria-label="Slide 2"></button>
      <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="2" aria-label="Slide 3"></button>
    </div>
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img src="assets/img/SPW.jpeg" class="d-block w-100" alt="Slide 1">
      </div>
      <div class="carousel-item">
        <img src="assets/img/spw1.jpeg" class="d-block w-100" alt="Slide 2">
      </div>
      <div class="carousel-item">
        <img src="assets/img/spw2.jpeg" class="d-block w-100" alt="Slide 3">
      </div>
    </div>
    <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Previous</span>
    </button>
    <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Next</span>
    </button>
  </div>
</div>

<div class="container-fluid">
        <div class="row my-5 d-flex justify-content-around">
            <div class="col-lg-5 box ">
  <div class="card rounded-5 ">
    <div class="card-body d-flex justify-content-center align-items-center">
      <nuxt-link to="/login/login" class="text-decoration-none text-white d-flex align-items-center">
        <h2>LOGIN</h2>
        <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" class="icon bi bi-person-circle" viewBox="0 0 16 16">
          <path d="M11 6a3 3 0 1 1-6 0 3 3 0 0 1 6 0"/>
          <path fill-rule="evenodd" d="M0 8a8 8 0 1 1 16 0A8 8 0 0 1 0 8m8-7a7 7 0 0 0-5.468 11.37C3.242 11.226 4.805 10 8 10s4.757 1.225 5.468 2.37A7 7 0 0 0 8 1"/>
        </svg>
      </nuxt-link>
    </div>
  </div>
</div>
<div class="col-lg-5 d-flex justify-content-center mb-4 ">
      <div class="card rounded-5 w-100">
        <div class="card-body d-flex justify-content-center align-items-center">
          <nuxt-link to="/jadwal/piket" class="text-decoration-none text-white ">
            <h2>JADWAL PIKET</h2>
          </nuxt-link>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="text-center mb-4">
    <h2>Menu</h2>
  </div>
<div class="container my-5">
  <table class="table table-bordered border-dark text-center">
    <thead >
      <tr class="tr">
        <th scope="col">NO</th>
        <th scope="col">NAMA BARANG</th>
        <th scope="col">BANYAK BARANG</th>
        <th scope="col">HARGA JUAL</th>
      </tr>
      <tr>
        <th scope="row">1</th>
        <td>cilok</td>
        <td>10</td>
        <td>2k</td>
      </tr>
      <tr>
        <th scope="row">2</th>
        <td>cireng</td>
        <td>10</td>
        <td>3k</td>
      </tr>
    </thead>
  </table>
</div>
  </template>

<style scoped>
.tr{
  background-color: #bdb9b9
}
.icon{
  height: 200px;
  width: 200px;
  padding-left: 60px;
}
.carousel {
  padding: 5px;
  position: relative;
  height: 380px; 
  overflow: hidden;
  margin: 10px 0;
}
.carousel-inner {
  height: 100%;
}
.box {
    width: 45%;
}
.carousel-item {
  height: 100%;
}
.carousel-item img {
  object-fit: cover;
  height: 100%;
  width: 100%;
  display: block; 
  border-radius: 45px;
}
.card {
    height: 140px;
    box-shadow: 1px 1px 10px #424242;
    background-color: #FF9671;
    color: white;
}
.text {
    display: flex;
    justify-content: center;
    align-items: center;
}
.icon{
  height: 100px;
  color:white;
}
.container {
  padding: 2px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.carousel {
  max-width: 200%;
  width: 200%;
}
.carousel-control-prev-icon,
.carousel-control-next-icon {
  background-color: rgba(0, 0, 0, 0.5);
  border-radius: 50%; 
}
</style>