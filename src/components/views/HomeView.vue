<template>
  <div class="container py-4">
    <div class="row">
      <div class="col"><PesquisarVaga /></div>
    </div>
    <div class="row mt-5">
      <div class="col-4">
        <IndicadorComponent titulo="Vagas abertas" indicador="100" />
      </div>
      <div class="col-4">
        <IndicadorComponent
          titulo="Profissionais cadastrados"
          indicador="225"
        />
      </div>
      <div class="col-4">
        <IndicadorComponent titulo="Visitantes online" indicador="25" />
      </div>
    </div>
  </div>
</template>

<script>
import PesquisarVaga from "../comuns/PesquisarVaga.vue";
import IndicadorComponent from "@/components/comuns/IndicadorComponent.vue";
export default {
  name: "HomeView",
  components: {
    PesquisarVaga,
    IndicadorComponent,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
