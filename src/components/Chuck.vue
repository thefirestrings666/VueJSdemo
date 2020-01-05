<template>

  <img v-bind:src="fact"> </img>

</template>

<script>

export default {
  name: "ChuckFact",
  props: {
    fact: String
  }
}

</script>

<style>

</style>