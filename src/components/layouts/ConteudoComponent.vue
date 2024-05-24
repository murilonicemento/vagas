<template>
  <div>
    <keep-alive>
      <component :is="conteudo" />
    </keep-alive>
  </div>
</template>

<script>
import PublicarVaga from "../views/PublicarVaga.vue";
import HomeView from "../views/HomeView.vue";

export default {
  name: "ConteudoComponent",
  components: {
    HomeView,
    PublicarVaga,
  },
  props: {
    conteudo: {
      type: String,
      required: true,
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
