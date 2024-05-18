<template>
  <div class="container py-4">
    <div class="row">
      <div class="col"><PesquisarVaga /></div>
    </div>
    <div class="row mt-5">
      <div class="col-4">
        <div class="h-100 p-5 rounded-6 border bg-dark text-white">
          <p>Vagas abertas</p>
          <h2>25</h2>
        </div>
      </div>
      <div class="col-4">
        <div class="h-100 p-5 rounded-6 border bg-dark text-white">
          <p>Profissionais cadastrados</p>
          <h2>125</h2>
        </div>
      </div>
      <div class="col-4">
        <div class="h-100 p-5 rounded-6 border bg-light text-white">
          <p>Visitantes online</p>
          <h2>15</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import PesquisarVaga from "../comuns/PesquisarVaga.vue";
export default {
  name: "HomeView",
  components: {
    PesquisarVaga,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
