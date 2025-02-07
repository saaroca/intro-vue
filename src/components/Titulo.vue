<template>
  <div>
    <h1 v-bind:class="color">
      {{ title }} <a :href="pagina">{{ texto }}</a>
    </h1>
    <Subtitulo />
  </div>
</template>

<script>
import Subtitulo from "./Subtitulo.vue";

export default {
  name: "TituloVue",
  components: {
    Subtitulo,
  },
  props: ["title", "color"],
  data() {
    return {
      pagina: "https://vuejs.org/",
      texto: "Vue",
      target: "_blank",
    };
  },
};
</script>

<style scoped>
h1 {
  color: blue;
  font-weight: bolder;
}

.red {
  color: red;
}
.blue {
  color: blue;
}
.brown {
  color: brown;
}
</style>
