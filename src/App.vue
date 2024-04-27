<template>
  <div>
    <TopoComponent />
    <ConteudoComponent />
  </div>
</template>

<script>
import ConteudoComponent from "./components/layouts/ConteudoComponent.vue";
import TopoComponent from "./components/layouts/TopoComponent.vue";

export default {
  name: "App",
  components: {
    ConteudoComponent,
    TopoComponent,
  },
};
</script>

<style></style>
