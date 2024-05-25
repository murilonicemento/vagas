<template>
  <div class="container py-4">
    <div class="row">
      <div class="col"><PesquisarVaga /></div>
    </div>
    <ListaVagas v-slot:default="slotProps">
      <div v-for="(vaga, index) in slotProps.vagas" :key="index">
        <h4>{{ vaga.titulo }}</h4>
        <p>{{ vaga.descricao }}</p>
        <hr />
      </div>
    </ListaVagas>
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
import ListaVagas from "../comuns/ListaVagas.vue";

export default {
  name: "HomeView",
  components: {
    PesquisarVaga,
    IndicadorComponent,
    ListaVagas,
  },
  data: () => ({
    vagas: [],
  }),
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
