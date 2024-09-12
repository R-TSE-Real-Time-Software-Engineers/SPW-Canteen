<template>
    <div class="header fixed-top ">
      <div class="h-text">
        <div class="t-judul order-1 p-2 bd-highlight">
          <h1>WELCOME TO SPW CANTEEN</h1>
          <h4>SMKN 4 TASIKMALAYA</h4>
        </div>
      </div>
      <div class="h-img img-fluid" >
        <img src="~/assets/img/logo.jpeg" alt="COVER">
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Header'
  };
  </script>
  
  <style scoped>
  .header {
    display: flex;
    align-items: center;
    width: 100%;
    height: 150px;
    background-color: #FF6969;
    color: #fff;
    padding: 0 20px;
    box-sizing: border-box;
    justify-content: space-between;
  }
  
  .h-img {
    flex-shrink: 0;
    margin-right: 20px;
  }
  
  .h-img img {
    width: 135px;
    height: 135px;
    border-radius: 50%;
    object-fit: cover;
  }
  
  .h-text {
    flex: 1;
    line-height: 1.2;
  }
  
  .t-judul h1 {
    margin: 0;
    font-size: 70px;
    font-weight: 700;
    font-family: math;
    text-transform: uppercase;
    padding-left: 30px;
  }
  
  .h-text p {
    margin: 5px 0 0;
    font-size: 16px;
    font-family: math;
  }
  h4{
    padding-left: 70px;
  }
  </style>
  
  
  