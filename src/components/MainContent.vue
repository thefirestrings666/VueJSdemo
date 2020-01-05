<template>
  <div id="center">
    <h1>Hello !</h1>
    <chuck-fact :fact="chuckFact" />
    <button @click="generateChuckFact()">Generate</button>
  </div>
</template>

<script>
import ChuckFact from "./ChuckFact";
import axios from "axios";

export default {
  components: {
    ChuckFact
  },
  data: () => {
    return {
      chuckFact: ""
    };
  },
  methods: {
    generateChuckFact() {
      axios.get("https://api.chucknorris.io/jokes/random").then(response => {
        console.log(response);
        this.chuckFact = response.data.value;
      });
    }
  }
};
</script>

<style>
img {
  width: 8rem;
  height: 8rem;
}
</style>
