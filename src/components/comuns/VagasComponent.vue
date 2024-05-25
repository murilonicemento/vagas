<template>
  <div class="card">
    <div class="card-header bg-dark text-white">
      <div class="row">
        <div class="col d-flex justify-content-between">
          <div>{{ titulo }}</div>
          <div>
            <div class="form-check form-switch">
              <input
                type="checkbox"
                class="form-check-input"
                v-model="favoritada"
              />
              <label type="checkbox" class="form-check-label">Favoritar</label>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="card-body">
      <p>{{ descricao }}</p>
    </div>
    <div class="card-footer">
      <small class="text-muted"
        >Salário: R$ {{ salario }} | Modalidade: {{ getModalidade }} | Tipo:
        {{ getTipo }} | Publicação: {{ getPublicacao }}</small
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "VagasComponent",
  data: () => ({
    favoritada: false,
  }),
  watch: {
    favoritada(valorNovo) {
      if (valorNovo) {
        this.emitter.emit("favoritarVaga", this.titulo);
      } else {
        this.emitter.emit("desfavoritarVaga", this.titulo);
      }
    },
  },
  // props: ["titulo", "descricao", "salario", "modalidade", "tipo", "publicacao"],
  props: {
    titulo: {
      type: String,
      required: true,
      validator(prop) {
        console.log("Prop: ", prop);
        if (prop.length < 4) return false;
        return true;
        // return true; -> se estiver válido
        // return false; -> se estiver inválido
      },
    },
    descricao: {
      type: String,
      required: false,
      default: "Valor default da prop",
    },
    salario: {
      type: [Number, String],
      required: true,
    },
    modalidade: {
      type: String,
      required: false,
      default() {
        return "*".repeat(20);
      },
    },
    tipo: {
      type: String,
      required: true,
    },
    publicacao: {
      type: String,
      required: true,
    },
  },
  methods: {},
  computed: {
    getModalidade() {
      switch (this.modalidade) {
        case "1":
          return "Home Office";
        case "2":
          return "Presencial";
      }

      return "";
    },
    getTipo() {
      switch (this.tipo) {
        case "1":
          return "CLT";
        case "2":
          return "PJ";
      }

      return "";
    },
    getPublicacao() {
      let dataPublicacao = new Date(this.publicacao);
      return dataPublicacao.toLocaleDateString("pt-BR");
    },
  },
};
</script>

<style></style>
