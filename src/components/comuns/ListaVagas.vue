<template>
  <slot :vagas="vagas">
    <div class="row mt-5" v-for="(vaga, index) in vagas" :key="index">
      <div class="col">
        <VagasComponent v-bind="vaga" />
      </div>
    </div>
  </slot>
</template>

<script>
import VagasComponent from "../comuns/VagasComponent.vue";

export default {
  name: "ListaVagas",
  data: () => ({
    vagas: [],
  }),
  components: {
    VagasComponent,
  },
  activated() {
    this.vagas = JSON.parse(localStorage.getItem("vagas"));
  },
  mounted() {
    this.emitter.on("filtrarVagas", (vaga) => {
      const vagas = JSON.parse(localStorage.getItem("vagas"));

      this.vagas = vagas.filter((reg) =>
        reg.titulo.toLowerCase().includes(vaga.titulo.toLowerCase())
      );
    });
  },
};
</script>
