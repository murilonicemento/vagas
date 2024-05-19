<template>
  <div class="card">
    <div class="card-header bg-dark text-white">{{ titulo }}</div>
    <div class="card-body">
      <p>{{ descricao }}</p>
    </div>
    <div class="card-footer">
      <small class="text-muted"
        >Salário: R$ {{ salario }} | Modalidade: {{ modalidade }} | Tipo:
        {{ tipo }} | Publicação: {{ publicacao }}</small
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "VagasComponent",
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
      required: true,
    },
    salario: {
      type: [Number, String],
      required: true,
    },
    modalidade: {
      type: String,
      required: true,
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
};
</script>

<style></style>
