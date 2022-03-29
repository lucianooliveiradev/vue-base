<template>
  <div class="container flex">
    <section v-for="(pais, i) in paises" :key="i" v-if="exibirPaises">
      <!-- Existe 2 ou mais formas de realizar o emit -->
      <!-- <div class="item" @click="emitNameCountryToHome(pais)">{{ pais }}</div> -->
      <div class="item" @click="$emit('paisSelecionado', pais)">{{ pais }}</div>
    </section>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  props: ["paises", "exibirPaises"],
  emits: ["paisSelecionado"],
  methods: {
    isDisabled() {
      return true;
    },
  },
  setup() {
    //   <!-- Existe 2 ou mais formas de realizar o emit -->
    // function emitNameCountryToHome(pais) {
    //   const paisSelecionado = pais;
    //   emit("paisSelecionado", paisSelecionado);
    // }

    return {
      //   emitNameCountryToHome,
    };
  },
};
</script>

<style lang="css" scoped>
.flex {
  display: flex;
}

.flex-wrap {
  flex-wrap: wrap;
}

.flex-item-1 {
  flex: 1;
}

/* Flex Item */
.item {
  margin: 5px;
  background: tomato;
  text-align: center;
  font-size: 1.5em;
  padding: 10px;
}

.container {
  max-width: 400px;
  margin: 0 auto;
  border: 1px solid #ccc;
}

h1 {
  text-align: center;
  margin: 20px 0 0 0;
  font-size: 1.25em;
  font-weight: normal;
}
</style>