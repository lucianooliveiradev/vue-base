<template>
  <header class="header">
    <img class="logo" src="./assets/logo.svg" alt="logo" />
    <Home :msg="'Aprendendo Vue'" :mostrarPaises="exibirPaises"></Home>
  </header>

  <Main style="text-align: center; margin-top: 80px">
    <TemplateTeste>
      <template #corpo>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Eum id
          debitis assumenda, nam rem, distinctio, iusto corporis provident
          reprehenderit eos ex fuga voluptates accusamus! Maiores ratione
          provident illum quibusdam officiis.
        </p>
      </template>

      <template #titulo>
        <h1>Aprendendo Slot</h1>
      </template>
    </TemplateTeste>

    <CustonInput @update:modelValue="showValueInput($event)"></CustonInput>
  </Main>

  <footer>
    <MouseTracker #teste="{ x, y }">
      Mouse is at: {{ x }},{{ y }}
    </MouseTracker>

    <Persons #pessoas="{ id, name }"> {{ id }} - {{ name }} </Persons>
  </footer>
</template>

<script>
import Home from "./components/Home.vue";
import TemplateTeste from "./components/TemplateTeste.vue";
import CustonInput from "./components/CustonInput.vue";
import MouseTracker from "./components/MouseTracker.vue";
import Persons from "./components/Persons.vue";

import { ref } from "vue";

export default {
  components: {
    Home,
    TemplateTeste,
    CustonInput,
    MouseTracker,
    Persons,
  },
  setup() {
    const mensagem = ref("Aprendendo VueJs");
    const exibirPaises = true;
    return {
      mensagem,
      exibirPaises,
    };
  },
  methods: {
    showValueInput(param) {
      alert(param);
    },
  },
};
</script>

<style lang="css" scoped>
.header {
  text-align: center;
}

.logo {
  margin-top: 30px;
  width: 130px;
  height: 130px;
}
</style>