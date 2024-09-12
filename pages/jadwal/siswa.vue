<template>
    <h2 class="text row justify-content-center">DATA PIKET SISWA KANTIN SPW </h2>
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
          <td> XI TBSM (2 Orang)</td>
          <td> XI TBSM (2 Orang)</td>
          <td> XI TBSM (4 Orang)</td>
          <td> XI TBSM (2 Orang)</td>
        </tr>
        <tr>
          <th scope="row">2</th>
          <td> XI RPL (4 Orang)</td>
          <td> XI RPL (2 Orang)</td>
          <td> XI RPL (2 Orang)</td>
          <td> XI RPL (2 Orang)</td>
        </tr>
        <tr>
          <th scope="row">3</th>
          <td> XI TJKT (2 Orang)T</td>
          <td> XI TJKT (4 Orang)</td>
          <td> XI TJKT (2 Orang)</td>
          <td> XI TJKT (2 Orang)</td>
        </tr>
        <tr>
          <th scope="row">4</th>
          <td> XI DKV (2 Orang)</td>
          <td> XI DKV (2 Orang)</td>
          <td> XI DKV (2 Orang)</td>
          <td> XI DKV (4 Orang)</td>
        </tr>
        <tr>
          <th scope="row">5</th>
          <td> XI TOI (2 Orang)</td>
          <td> XI TOI (2 Orang)</td>
          <td> XI TOI (2 Orang)</td>
          <td> XI TOI (2 Orang)</td>
        </tr>
      </thead>
    </table>
  </div>
  <nuxt-link to="piket">
    <button type="submit" class="btn ms-3 btn-lg ">KEMBALI</button>
  </nuxt-link>     
  </template>
  
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