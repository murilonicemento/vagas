<template>
  <div>
    <VagasFavoritas />
    <TopoComponent @navegar="componente = $event" />
    <ConteudoComponent v-if="visibilidade" :conteudo="componente" />
  </div>
</template>

<script>
import ConteudoComponent from "./components/layouts/ConteudoComponent.vue";
import TopoComponent from "./components/layouts/TopoComponent.vue";
import VagasFavoritas from "./components/comuns/VagasFavoritas.vue";

export default {
  name: "App",
  components: {
    ConteudoComponent,
    TopoComponent,
    VagasFavoritas,
  },
  data: () => ({
    visibilidade: true,
    componente: "HomeView",
  }),
};
</script>

<style></style>
