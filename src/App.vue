<template>
  <div id="app" class="containerCat ">
    <div class="row">
      <div class="col bg-miauu p-5 text-center">
        <h1>Random <b>Gif Cat 🐈</b></h1>
      </div>
    </div>
    <div class="row bg-form p-5">
      <div class="col">
        <form>
          <div class="form-group m-2">
            <label class="text-white mr-3">Titulo: </label><br />
            <input type="text" class="form-control" v-model="title" />
          </div>
          <div class="form-group m-2">
            <label class="text-white mr-3">Filtro</label>
            <select class="form-control" v-model="filter">
              <option value="blur">blur</option>
              <option value="mono">mono</option>
              <option value="sepia">sepia</option>
              <option value="negative">negative</option>
              <option value="paint">paint</option>
              <option value="pixel">pixel</option>
            </select>
          </div>
          <div>
            <div class=" form-group m-2">
              <label class="text-white mr-3">Color</label>
              <select class="form-control" v-model="color">
                <option value="red">rojo</option>
                <option value="blue">azul</option>
                <option value="green">verde</option>
                <option value="yellow">amarillo</option>
                <option value="black">negro</option>
                <option value="white">blanco</option>
              </select>
              <div
                class="circle-color col-4 mt-2"
                :style="{ backgroundColor: color }"
              ></div>
            </div>
          </div>
          <div class="form-group m-2">
            <label class="text-white mr-3">Tamaño: </label>
            <input
              type="number"
              class="form-control"
              v-model.number="size"
              step="100"
              min="100"
              max="500"
            />
          </div>
        </form>
      </div>
    </div>
    <div class="row bg-miauu">
      <div class="col-12 p-3 text-center">
        <button class="btn btn-danger" @click="gatosData">
          Obtener mi gatito😻
        </button>
      </div>
      <div class="col-12 p-5 text-center">
        <img :src="gatosGif" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    title: "",
    filter: "",
    color: "",
    size: "",
    gatosGif: "",
  }),
  methods: {
    gatosData() {
      this.gatosGif = `https://cataas.com/cat/gif/says/${this.title}?filter=${this.filter}&color=${this.color}&size=${this.size}&type=or`;
    },
  },
};
</script>

<style>
.containerCat {
  width: 50%;
  margin-left: auto;
  margin-right: auto;
}
.bg-miauu {
  background-color: lightblue;
}
.bg-form {
  background-color: lightcoral;
}
.circle-color {
  background-color: blue;
  width: 50px;
  height: 50px;
  border-radius: 50% !important;
  margin-left: 1rem !important;
}
</style>
