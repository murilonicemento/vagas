<template>
  <div>
    <TopoComponent />
    <button @click="desmontarComponente()">
      Desmontar o componente conteúdo
    </button>
    <ConteudoComponent v-if="visibilidade" />
    <HomeView />
  </div>
</template>

<script>
import ConteudoComponent from "./components/layouts/ConteudoComponent.vue";
import TopoComponent from "./components/layouts/TopoComponent.vue";
import HomeView from "./components/views/HomeView.vue";

export default {
  name: "App",
  components: {
    ConteudoComponent,
    TopoComponent,
    HomeView,
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
