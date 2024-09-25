<template>
    <h2 class="text row justify-content-center">DATA PIKET GURU KANTIN SPW BLOK A</h2>
    <div class="container my-5">
    <table class="table table-bordered border-dark text-center">
      <thead >
        <tr class="tr">
          <th scope="col">NO</th>
          <th scope="col">SENIN</th>
          <th scope="col">SELASA</th>
          <th scope="col">RABU</th>
          <th scope="col">KAMIS</th>
        </tr>
        <tr>
          <th scope="row">1</th>
          <td> Suminar, S.Kom., M.Kom </td>
          <td> Tri Wahyuni, S.Pd</td>
          <td> Fikri A.Yudhistira, S.T., M.Pd</td>
          <td> Anna Rachmiati Hidayat, S.Pd</td>
        </tr>
        <tr>
          <th scope="row">2</th>
          <td> Budi Setiadi, S.T</td>
          <td> Asep Nurul Huda, S.Km</td>
          <td> Lisye Diana Ingriani, S.Kom</td>
          <td> Bintang Anugrahing Widhi, S.T</td>
        </tr>
        <tr>
          <th scope="row">3</th>
          <td> Yusep Saepul Wahyu, S.T</td>
          <td> Syam Rahadian Ardhy, S.Kom</td>
          <td> Andi Moh Permadi, S.Kom</td>
          <td> Arip, S.T., M.Kom</td>
        </tr>
        <tr>
          <th scope="row">4</th>
          <td> Novi Abdul Rohman, S.T</td>
          <td> Deni Maulana, S.T</td>
          <td> Runi Puspa Amallah, S.Pd</td>
          <td> Ade Rohmat, S.T</td>
        </tr>
      </thead>
    </table>
  </div>
  
  </template>
  <script setup>
  definePageMeta({
    middleware: 'auth',
    layout: 'jadwal',
  })
  </script>
  
  <style scoped>
  .text{
    padding: 30px;
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
  </style>
  <script setup>
  </script>
