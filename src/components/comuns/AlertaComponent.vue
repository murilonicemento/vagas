<template>
  <div :class="estiloAlerta" role="alert">
    <slot name="titulo">
      <h3>Título da mensagem de feedback</h3>
    </slot>
    <hr />
    <slot name="descricao">
      <p>Mensagem de feedback</p>
    </slot>
  </div>
</template>

<script>
export default {
  name: "AlertaComponent",
  props: { tipo: String },
  computed: {
    estiloAlerta() {
      switch (this.tipo) {
        case "erro":
          return "alert alert-danger";
        case "sucesso":
          return "alert alert-success";
        default:
          return "alert alert-success";
      }
    },
  },
};
</script>
