<script>
export default {
  data() {
    return {
      x: 0,
      y: 0,
    };
  },
  methods: {
    update(e) {
      //   console.log(e);
      this.x = e.pageX;
      this.y = e.pageY;
    },
  },
  mounted() {
    window.addEventListener("mousemove", this.update);
  },
  unmounted() {
    window.removeEventListener("mousemove", this.update);
  },
};
</script>

<template>
  <slot name="teste" :x="x" :y="y"></slot>
</template>
