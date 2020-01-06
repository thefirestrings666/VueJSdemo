<template>

  <img v-bind:src="fact"> </img>

</template>

<script>

export default {
  name: "imgLoader",
  props: {
    fact: String
  }
}

</script>

<style>

</style>