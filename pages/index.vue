<template>
<div class="container my-5">
  <div id="carouselExampleCaptions" class="carousel slide mt-5 p-2 bg-" data-bs-ride="carousel">
      <div class="carousel-indicators">
        <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="0" class="active"
          aria-current="true" aria-label="Slide 1"></button>
        <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="1"
          aria-label="Slide 2"></button>
        <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="2"
          aria-label="Slide 3"></button>
      </div>
      <div class="carousel-inner">
        <div class="carousel-item active">
          <img src="../assets/img/1.png" class="d-block w-50 rounded-img img" alt="...">
        </div>
        <div class="carousel-item active">
          <img src="../assets/img/2.png" class="d-block w-50 rounded-img img" alt="...">
        </div>
        <div class="carousel-item">
          <img src="../assets/img/3.png" class="d-block w-50 rounded-img img" alt="...">
        </div>
      </div>
      <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleCaptions"
        data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleCaptions"
        data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
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
@media only screen and (max-width: 100px) {
.carousel {
  padding: 5px;
  position: relative;
  overflow: clip;
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
.rounded-img {
  border-radius: 50px; 
}

</style>