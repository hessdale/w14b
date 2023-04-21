<template>
  <div>
    <p @click="sendJoke">sendjoke</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  methods: {
    sendJoke(joke) {
      joke;
      this.$root.$emit(`joke_request`, this.joke);
    },
  },
  data() {
    return {
      joke: undefined,
    };
  },
  mounted() {
    axios
      .request({
        url: `https://ron-swanson-quotes.herokuapp.com/v2/quotes`,
      })
      .then((response) => {
        response;
        this.joke = response.data[0];
        console.log(`request success`);
      })
      .catch((error) => {
        error;
        console.log(`request error`);
      });
  },
};
</script>

<style scoped>
</style>