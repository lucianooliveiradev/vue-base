
<script>
export default {
  data() {
    return {
      pessoas: [],
    };
  },
  mounted() {
    setTimeout(() => {
      this.pessoas = [
        { id: 1, name: "Luciano" },
        { id: 2, name: "Maria" },
        { id: 3, name: "Pedro" },
      ];
    }, 1000);
  },
};
</script>

<template>
  <ul class="item-parent-person">
    <li class="item-child-person" v-if="!pessoas.length">loading....</li>
    <li class="item-child-person" v-for="(pessoa, i) in pessoas" key="i">
      <slot class="teste" name="pessoas" v-bind="pessoa"></slot>
    </li>
  </ul>
</template>


<style lang="css" scoped>
.item-parent-person {
  background: linear-gradient(315deg, #42d392 25%, #647eff);
  padding: 10px;
}

.item-child-person {
  margin: 10px;
  list-style: none;
  background: #fff;
  padding: 10px;
}


</style>