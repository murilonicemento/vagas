<template>
  <div>
    <h1>{{ titulo }}</h1>
    <button @click="atualizarComponente()">Atualizar</button>
    <button @click="conteudo = 'HomeView'">Home</button>
    <button @click="conteudo = 'PublicarVaga'">Publicar Vaga</button>
    <keep-alive>
      <component :is="conteudo" />
    </keep-alive>
  </div>
</template>

<script>
import PublicarVaga from "../views/PublicarVaga.vue";
import HomeView from "../views/HomeView.vue";

export default {
  name: "ConteudoComponent",
  components: {
    HomeView,
    PublicarVaga,
  },
  data: () => ({
    teste: "O componente foi criado",
    titulo: "Componente conteúdo",
    conteudo: "HomeView",
  }),
  methods: {
    atualizarComponente() {
      this.titulo += "*";
    },
  },
  beforeCreate() {
    console.log("Antes de criar", this.teste);
  },
  created() {
    console.log("Criado", this.teste);
  },
  beforeMount() {
    console.log("Antes de montar o template");
  },
  mounted() {
    console.log("Montado");
  },
  beforeUpdate() {
    console.log("Antes de atualizar");
  },
  updated() {
    console.log("Atualizado");
  },
  beforeUnmount() {
    console.log("Antes de desmontar/destruir");
  },
  unmounted() {
    console.log("Desmontado/destruído");
  },
  errorCaptured() {
    console.log("Erro capturado");
  },
  renderTracked() {
    console.log("Re-renderização rastreada");
  },
  renderTriggered() {
    console.log("Re-renderização acionada");
  },
  activated() {
    console.log("Componente é ativado");
  },
  deactivated() {
    console.log("Componente desativado");
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
