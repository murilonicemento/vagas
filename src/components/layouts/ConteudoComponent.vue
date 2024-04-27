<template>
  <div>
    <p>Conteúdo</p>
    <HomeView />
    <PublicarVaga />
  </div>
</template>

<script>
import HomeView from "../views/HomeView.vue";
import PublicarVaga from "../views/PublicarVaga.vue";
export default {
  name: "ConteudoComponent",
  components: {
    HomeView,
    PublicarVaga,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
