<template>
  <div>
    <TopoComponent />
    <button @click="desmontarComponente()">
      Desmontar o componente conteúdo
    </button>
    <ConteudoComponent v-if="visibilidade" />
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
  }),
  methods: {
    desmontarComponente() {
      this.visibilidade = false;
    },
  },
};
</script>

<style></style>
