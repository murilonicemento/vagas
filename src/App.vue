<template>
  <div>
    <TopoComponent @navegar="componente = $event" />
    <ConteudoComponent v-if="visibilidade" :conteudo="componente" />
  </div>
</template>

<script>
import ConteudoComponent from "./components/layouts/ConteudoComponent.vue";
import TopoComponent from "./components/layouts/TopoComponent.vue";

export default {
  name: "App",
  components: {
    ConteudoComponent,
    TopoComponent,
  },
  data: () => ({
    visibilidade: true,
    componente: "HomeView",
  }),
};
</script>

<style></style>
