<template>
  <div class="container py-4">
    <div class="row">
      <div class="col"><PesquisarVaga /></div>
    </div>
    <div class="row mt-5" v-for="(vaga, index) in vagas" :key="index">
      <div class="col">
        <VagasComponent v-bind="vaga" />
      </div>
    </div>
    <div class="row mt-5">
      <div class="col-4">
        <IndicadorComponent
          titulo="Vagas abertas"
          indicador="100"
          bg="bg-dark"
          color="text-white"
        />
      </div>
      <div class="col-4">
        <IndicadorComponent
          titulo="Profissionais cadastrados"
          indicador="225"
          bg="bg-dark"
          color="text-white"
        />
      </div>
      <div class="col-4">
        <IndicadorComponent
          titulo="Visitantes online"
          indicador="25"
          bg="bg-light"
          color="text-dark"
        />
      </div>
    </div>
  </div>
</template>

<script>
import PesquisarVaga from "../comuns/PesquisarVaga.vue";
import IndicadorComponent from "@/components/comuns/IndicadorComponent.vue";
import VagasComponent from "../comuns/VagasComponent.vue";

export default {
  name: "HomeView",
  components: {
    PesquisarVaga,
    IndicadorComponent,
    VagasComponent,
  },
  data: () => ({
    vagas: [],
  }),
  activated() {
    this.vagas = JSON.parse(localStorage.getItem("vagas"));
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
