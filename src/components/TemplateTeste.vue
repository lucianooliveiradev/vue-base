<template>

  <slot name="titulo"></slot>

  <div>
    <h1>Projetos</h1>
    <slot></slot>
  </div>

  <slot name="corpo"></slot>
</template>

<script>
export default {
  setup() {
    return {};
  },
};
</script>

<style lang="css" scoped>
</style>