<template>
  <div id="app" class="container">
    <TituloVue :title="texto" color="blue" />
    <input
      type="text"
      placeholder="Escribe un titulo"
      v-model="texto"
      class="form-control"
    />
    <hr />
    <div class="row mt-3">
      <div class="col-lg-4">
        <input
          type="text"
          placeholder="Titulo Pelicula"
          v-model="titulo"
          class="form-control"
        />
      </div>
      <div class="col-lg-4">
        <input
          type="text"
          placeholder="Año Pelicula"
          v-model="año"
          class="form-control"
        />
      </div>
      <div class="col-lg-4">
        <button class="btn btn-success btn-block" @click="agregar">
          Agregar
        </button>
      </div>
    </div>
    <table class="table mt-3">
      <thead>
        <tr>
          <th>Titulo</th>
          <th>Año</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="pelicula in peliculas" :key="pelicula.titulo">
          <td>{{ pelicula.titulo }}</td>
          <td>{{ pelicula.año }}</td>
        </tr>
      </tbody>
    </table>
    <button @click="alerta('Alerta')" class="btn btn-success">Click me</button>
  </div>
</template>

<script>
import TituloVue from "./components/Titulo.vue";

export default {
  name: "App",
  components: {
    TituloVue,
  },
  data() {
    return {
      texto: "Mi texto",
      titulo: "",
      año: "",
      peliculas: [
        { titulo: "Terminator", año: "1995" },
        { titulo: "Jurasic Park", año: "1996" },
        { titulo: "Pokemon", año: "1997" },
        { titulo: "Gladiator 2", año: "2025" },
        { titulo: "Torrente", año: "2021" },
      ],
    };
  },
  methods: {
    alerta(msg) {
      alert(msg);
    },
    agregar() {
      this.peliculas.push({
        titulo: this.titulo,
        año: this.año,
      });
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
