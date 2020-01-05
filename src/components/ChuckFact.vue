<template>
  <span>{{ fact }}</span>
</template>

<script>
export default {
  name: "ChuckFact",
  props: {
    fact: String
  }
};
</script>
