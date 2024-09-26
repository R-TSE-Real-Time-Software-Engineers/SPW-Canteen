<template>
  <div class="container my-5"> 
      <div class="col text-center">
        <h2 class="mb-0">FORM ISI PRODUK</h2>
      </div>
    </div>
  <div class="container my-5">
    <div class="row justify-content-center">
      <div class="col-lg-6 col-md-8">
        <form  @submit.prevent="kirimData">
          <div class="text-center mb-3">
            <input  v-model="form.nama" type="text" class="form-control form-control-lg radius" placeholder="Nama:" />
          </div>
          <div class="text-center mb-3">
            <select v-model="form.kelas"  class="form-control form-select-lg radius" aria-label="Kelas">
              <option value="" selected>Kelas</option>
              <option v-for="(member, i) in members" :key="i" :value="member.id">{{ member.nama }}</option>
            </select>
          </div>
          <div class="text-center mb-3">
            <input v-model="form.nama_barang" type="text" class="form-control form-control-lg radius" placeholder="Nama Barang:" />
          </div>
          <div class="text-center mb-3">
            <input v-model="form.jumlah" type="number" class="form-control form-control-lg radius" placeholder="Banyak:" />
          </div>
          <div class="text-center mb-3">
            <input v-model="form.harga" type="text" class="form-control form-control-lg radius" placeholder="Harga Jual:" />
          </div>
          <div class="text-center mb-3">
            <input type="file" class="form-control form-control-lg radius" id="file-input" accept="image/*" placeholder="Upload Foto:" required />
          </div>
          <div class="d-flex justify-content-end mt-4">
            <button type="submit" class="btn btn-lg">KIRIM</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup>
definePageMeta({
  middleware: 'auth',
  layout: 'produk',
})

const supabase = useSupabaseClient()
const members=ref ([]);

const form = ref({
    nama: "",
    kelas:"",
    nama_barang:"",
    jumlah:"",
    harga:"",
});

const kirimData = async () => {
    console.log(form.value)
    const { error } = await supabase.from("produk").insert([form.value])
    if(!error) navigateTo("/produk/form")
    else throw error
}
const getkelas = async () => {
    const { data, error } = await supabase.from("kelas").select("*")
    if(data) members.value = data
};
onMounted(() => {
    getkelas();
});
</script>
<style scoped>
.btn {
  border: none;
  color: white;
  background: #FFB085;
  margin: 4px 5px;
  padding: 10px 15px;
  font-size: 16px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  cursor: pointer;
}

.icon-button {
  background: none;
  border: none;
  cursor: pointer;
}

.radius {
  border-radius: 0.375rem;
}

.mb-3 {
  margin-bottom: 1.5rem; 
}

.text-center {
  text-align: center;
}

.bi {
  width: 40px;
  height: 40px;
  fill: #FFB085; 
}
</style>
