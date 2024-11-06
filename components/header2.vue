<template>
  <div class="header fixed-top">
    <div class="h-img">
      <img src="~/assets/img/logo2.png" alt="COVER">
    </div>
    <div class="h-text text-center">
      <div class="t-judul " >
        <h2>SPW CANTEEN</h2>
      </div>
    </div>
    <div class="button-container">
      <span class="separator">|</span>
      <nuxt-link to="/produk/form" class="text-decoration-none">
        <button class="btn" type="button" style="background-color: #FF6969; color: #ffffff; border: none;">ISI PRODUK</button>
    </nuxt-link>
    <nuxt-link to="/jadwal/gurua" class="text-decoration-none">
      <button class="btn btn-outline-danger" type="button">PIKET</button>
</nuxt-link>

    </div>
  </div>
</template>

<script>
export default {
  name: 'Header2'
};
</script>

<style scoped>
.header {
  display: flex;
  align-items: center;
  width: 100%;
  height: 7rem;
  background-color: #ffffff;
  color: #FF6969;
  background-color: #FFF1F1;
  padding: 0 20px;
  box-sizing: border-box;
  justify-content: space-between;
  border-bottom: 2px solid #e4e4e4;
}

.h-img {
  flex-shrink: 0;
  margin-right: 20px;
}

.h-img img {
  width: 100px;
  height: 100px;
  object-fit: cover;
}

.h-text {
  flex: 1;
  line-height: 1.2;
  flex-direction: row; 
  align-items: center; 
}

.t-judul h2 {
  margin: 0;
  font-size: 30px;
  font-weight: 700;
  font-family: math;
  text-transform: uppercase;
 text-align: center;
}

.search-container {
  flex: 1; 
  margin-left: 20px;
}

.search-container input {
  width: 95%;
}

.button-container {
  display: flex;
  align-items: center;
  gap: 20px; 
  margin-left: 20px;
 
}

.separator {
  margin: 0 50px;
  font-size: 24px;
}

</style>