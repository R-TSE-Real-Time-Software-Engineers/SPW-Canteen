<template>
  <div class="container pt-5">
    <div class="row justify-content-center">
      <div class="col">
        <div id="carouselExampleIndicators" class="carousel slide" data-bs-ride="true">
          <div class="carousel-indicators">
            <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
            <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="1" aria-label="Slide 2"></button>
            <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="2" aria-label="Slide 3"></button>
          </div>
          <div class="carousel-inner rounded-5">
            <div class="carousel-item active">
              <img src="/assets/img/1.png" class="d-block w-100" alt="...">
            </div>
            <div class="carousel-item">
              <img src="/assets/img/2.png" class="d-block w-100" alt="...">
            </div>
            <div class="carousel-item">
              <img src="/assets/img/3.png" class="d-block w-100" alt="...">
            </div>
          </div>
          <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide="prev">
            <span class="carousel-control-prev-icon rounded-5 bg-secondary" aria-hidden="true"></span>
            <span class="visually-hidden">Previous</span>
          </button>
          <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide="next">
            <span class="carousel-control-next-icon rounded-5 bg-secondary" aria-hidden="true"></span>
            <span class="visually-hidden">Next</span>
          </button>
        </div>
      </div>
    </div>
    <div class="row pt-3">
      <div class="col">
        <h1>Product Hari Ini</h1>
      </div>
    </div>
    <div class="row pt-3 pb-5 gap-3 justify-content-evenly">
      <!-- looping data -->
      <div class="col-lg-3">
        <div class="card">
          <img src="/assets/img/mochi.webp" class="card-img-top" alt="...">
          <div class="card-body">
            <p class="card-text">Mochi</p>
            <h5 class="card-title">Rp5000</h5>
          </div>
        </div>
      </div>
 
    </div>
  </div>
</template>
