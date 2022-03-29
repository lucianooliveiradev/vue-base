<template>
  <h1>{{ msg }}</h1>
  <h1>Países</h1>
  <Pais :paises="paises" :exibirPaises="mostrarPaises" @paisSelecionado="showNameCountry($event)"></Pais>
  <p>País selecionado no lado filho, </p>
  <span style="color: red">{{paisEscolhido}}</span>
</template>

<script>
import Pais from "./Pais.vue";
import { ref } from "vue";

export default {
  components: { Pais },
  props: { msg: String, mostrarPaises: Boolean },
  setup() {
    const paises = ["Brasil", "Japão", "França", "Alemanha"];
    const paisEscolhido = ref('');

    function showNameCountry(countryName) {
      paisEscolhido.value = countryName;
    }

    return {
      paises,
      showNameCountry,
      paisEscolhido
    };
  },
};
</script>

<style lang="css" scoped>
h1 {
  text-align: center;
  margin: 20px 0 0 0;
  font-size: 1.25em;
  font-weight: normal;
}
</style>