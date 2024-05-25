<template>
  <div>
    <VagasFavoritas />
    <TopoComponent @navegar="componente = $event" />
    <AlertaComponent v-if="exibirAlerta" :tipo="alerta.tipo">
      <template v-slot:titulo>
        <h5>{{ alerta.titulo }}</h5>
      </template>
      <template v-slot:descricao>
        <p>{{ alerta.descricao }}</p>
      </template>
    </AlertaComponent>
    <ConteudoComponent v-if="visibilidade" :conteudo="componente" />
  </div>
</template>

<script>
import ConteudoComponent from "./components/layouts/ConteudoComponent.vue";
import TopoComponent from "./components/layouts/TopoComponent.vue";
import VagasFavoritas from "./components/comuns/VagasFavoritas.vue";
import AlertaComponent from "./components/comuns/AlertaComponent.vue";

export default {
  name: "App",
  components: {
    ConteudoComponent,
    TopoComponent,
    VagasFavoritas,
    AlertaComponent,
  },
  data: () => ({
    visibilidade: true,
    componente: "HomeView",
    exibirAlerta: false,
    alerta: { titulo: "", descricao: "", tipo: "" },
  }),
  mounted() {
    this.emitter.on("alerta", (param) => {
      this.alerta = param;
      this.exibirAlerta = true;
      setTimeout(() => (this.exibirAlerta = false), 4000);
    });
  },
};
</script>

<style></style>
