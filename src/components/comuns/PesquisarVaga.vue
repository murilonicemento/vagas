<template>
  <div class="h-100 p-5 bg-light border rounded-3">
    <h2>Pesquisar vagas</h2>
    <div class="row">
      <div class="col">
        <div class="form-group">
          <label for="">Título da vaga</label>
          <input
            type="text"
            class="form-control"
            placeholder="Pesquise por palavras chave, por exemplo 'PHP', 'Pleno', 'Analista'"
            v-model="titulo"
          />
          <small class="form-text text-muted"
            >Informe palavras que estejam relacionadas com o título da vaga que
            você procura</small
          >
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <button
          class="btn btn-outline-dark mt-2"
          type="button"
          @click="pesquisarVaga()"
        >
          Buscar
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PesquisarVaga",
  data: () => ({
    titulo: "",
  }),
  methods: {
    pesquisarVaga() {
      this.emitter.emit("filtrarVagas", { titulo: this.titulo });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
