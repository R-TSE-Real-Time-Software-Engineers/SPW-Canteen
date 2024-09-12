<template>
<div class="tinggi container-fluid">
  <div class="row justify-content-center : justify-">
    <div class="col-3">
        <form>
          <div class="mb-3">
            <h2 class="row justify-content-center">SIGN IN</h2>
          </div>
          <div class="mb-3 d-flex align-items-center">
  <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="currentColor" class="bi bi-person me-2" viewBox="0 0 16 16">
    <path d="M8 8a3 3 0 1 0 0-6 3 3 0 0 0 0 6m2-3a2 2 0 1 1-4 0 2 2 0 0 1 4 0m4 8c0 1-1 1-1 1H3s-1 0-1-1 1-4 6-4 6 3 6 4m-1-.004c-.001-.246-.154-.986-.832-1.664C11.516 10.68 10.289 10 8 10s-3.516.68-4.168 1.332c-.678.678-.83 1.418-.832 1.664z"/>
  </svg>
  <input v-model="email" type="text" class="form-control" placeholder="Username">
</div>
<div class="mb-3 d-flex align-items-center">
  <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="currentColor" class="bi bi-lock me-2" viewBox="0 0 16 16">
    <path d="M8 1a2 2 0 0 1 2 2v4H6V3a2 2 0 0 1 2-2m3 6V3a3 3 0 0 0-6 0v4a2 2 0 0 0-2 2v5a2 2 0 0 0 2 2h6a2 2 0 0 0 2-2V9a2 2 0 0 0-2-2M5 8h6a1 1 0 0 1 1 1v5a1 1 0 0 1-1 1H5a1 1 0 0 1-1-1V9a1 1 0 0 1 1-1"/>
  </svg>
  <input v-model="password" type="password" class="form-control" placeholder="Password">
</div>
<div class="container">
  <div class="mb-5 d-flex justify-content-center">
    <button @click="handlelogin" type="button" class="btn-custom d-flex align-items-center">
      Continue
      <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-chevron-compact-right ms-2" viewBox="0 0 16 16">
        <path fill-rule="evenodd" d="M6.776 1.553a.5.5 0 0 1 .671.223l3 6a.5.5 0 0 1 0 .448l-3 6a.5.5 0 1 1-.894-.448L9.44 8 6.553 2.224a.5.5 0 0 1 .223-.671"/>
      </svg>
    </button>
  </div>
</div>
<nuxt-link to="/produk/form">
    <button type="submit" class="btn ms-3 btn-lg ">continuee</button>
  </nuxt-link>
        </form>
    </div>
<nuxt-link to="/">
    <button type="submit" class="btn ms-3 btn-lg ">KEMBALI</button>
  </nuxt-link>
  </div>
  </div>
</template>

<style scoped>
.mb-3{
  padding: 5px;
}
.tinggi{
  height: 100px;
  padding-block:100px ;
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
.container{
  padding: 15px;
}
.btn-custom {
  display: inline-flex;
  align-items: center;
  background-color: #FFB085; 
  border: none; 
  border-radius: 0.375rem; 
  padding: 0.7rem 2rem; 
  color: #ffffff; 
  font-size: 1rem;
  cursor: pointer; 
  text-align: center; 
  transition: background-color 0.3s, box-shadow 0.3s;
}
.bi-chevron-compact-right {
  color: #ffffff;
  transition: color 0.3s; 
}
.btn-custom:hover {
  background-color: #ddbebe; 
}
.btn-custom:active, .btn-custom:focus {
  background-color: #ddbebe; 
  box-shadow: 0 0 0 0.2rem rgba(0, 0, 0, 0.2); 
  outline: none; 
}
</style>