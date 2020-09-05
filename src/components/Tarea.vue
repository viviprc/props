<template>
  <div>
    {{tarea}}
    <button id="subtract" @click="vaciarTarea"><b>x</b></button>
  </div>
</template>

<script>
export default {
  props: {
    tarea: String,
    indice: Number,
  },
  methods: {
    vaciarTarea() {
      this.$emit("borrar", this.indice);
    },
  },
};
</script>

<style>
</style>