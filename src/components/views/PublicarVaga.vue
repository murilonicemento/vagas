<template>
  <div class="container py-4">
    <div class="row">
      <div class="col">
        <h4>Apresente a sua vaga para milhares de profissionais e de graça</h4>
      </div>
    </div>
    <div class="row mt-3">
      <div class="col">
        <label for="" class="form-label">Título da vaga</label>
        <input type="text" class="form-control" v-model="titulo" />
        <div class="form-text">
          Por exemplo: Programador Javascript e VueJS.
        </div>
      </div>
    </div>
    <div class="row mt-3">
      <div class="col">
        <label for="" class="form-label">Descrição</label>
        <textarea class="form-control" v-model="descricao"></textarea>
        <div class="form-text">Informe os destalhes da vaga</div>
      </div>
    </div>
    <div class="row mt-3">
      <div class="col">
        <label for="" class="form-label">Salário</label>
        <input type="number" class="form-control" v-model="salario" />
        <div class="form-text">Informe salário</div>
      </div>
      <div class="col">
        <label for="" class="form-label">Modalidade</label>
        <select class="form-select" v-model="modalidade">
          <option value="" disabled>Selecione</option>
          <option value="1">Home Office</option>
          <option value="2">Presencial</option>
        </select>
        <div class="form-text">Informe onde as atividades serão realizadas</div>
      </div>
      <div class="col">
        <label for="" class="form-label">Tipo</label>
        <select class="form-select" v-model="tipo">
          <option value="" disabled>Selecione</option>
          <option value="1">CLT</option>
          <option value="2">PJ</option>
        </select>
        <div class="form-text">Informe o tipo de contratação</div>
      </div>
    </div>
    <div class="row mt-3">
      <div class="col">
        <button type="submit" class="btn btn-primary" @click="salvarVaga()">
          Cadastrar
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PublicarVaga",
  data: () => ({
    titulo: "",
    descricao: "",
    salario: "",
    modalidade: "",
    tipo: "",
  }),
  methods: {
    salvarVaga() {
      let tempoDecorrido = Date.now();
      let dataAtual = new Date(tempoDecorrido);
      let dataPublicacao = dataAtual.toISOString();
      let vagas = JSON.parse(localStorage.getItem("vagas"));

      if (!vagas) vagas = [];

      vagas.push({
        titulo: this.titulo,
        descricao: this.descricao,
        salario: this.salario,
        modalidade: this.modalidade,
        tipo: this.tipo,
        publicacao: dataPublicacao,
      });

      if (!this.validaFormulario()) {
        this.emitter.emit("alerta", {
          tipo: "erro",
          titulo: "-_- Opsss... Não foi possível realizar o cadastro.",
          descricao:
            "Parece que você esqueceu de preencher alguma informação. Faça o ajuste e tente novamente.",
        });

        return;
      }

      localStorage.setItem("vagas", JSON.stringify(vagas));
      this.emitter.emit("alerta", {
        tipo: "sucesso",
        titulo: `A vaga ${this.titulo} foi cadastrada com sucesso`,
        descricao:
          "Parabéns, a vaga foi cadastrada e poderá ser consultada por milhares de profissionais em nossa plataforma",
      });

      this.resetaFormulario();
    },
    resetaFormulario() {
      this.titulo = "";
      this.descricao = "";
      this.salario = "";
      this.modalidade = "";
      this.tipo = "";
    },
    validaFormulario() {
      let valido = true;
      if (this.titulo === "") valido = false;
      if (this.descricao === "") valido = false;
      if (this.salario === "") valido = false;
      if (this.modalidade === "") valido = false;
      if (this.tipo === "") valido = false;

      return valido;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
